---
title: ETAPA 4 - Definir pushidentifier
description: O **pushIdentifier** é uma string que contém o token do dispositivo para notificações por push. É o mesmo token enviado pelo Firebase e passado para o SDK usando o método MobileCore.setPushIdentifier.
feature: Push
user: Admin
level: Experienced
jira: KT-4828
doc-type: tutorial
activity: use
team: TM
exl-id: 08387b84-edaa-45ee-ae66-53bcbd5c7c39
TQID: 'https://experienceleague.adobe.com/Sr5MNZscXvLdlEZL0nIWf1SRicemz-fu87GpB55PVGE'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: a4657621-810c-498b-8a27-7ced9c176dda
    internal-label: Push notifications
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 508c3590ce956401ccfba3a256000cbc5849a684
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 0%
---
# Etapa 4 - Definir [!DNL pushidentifier]

O **[!DNL pushidentifier]** é uma cadeia de caracteres que contém o token do dispositivo para notificações [!DNL Push]. É o mesmo token enviado por [!DNL Firebase] e passado para a SDK usando o método [!DNL MobileCore.setPushIdentifier].

Abra o projeto no [!DNL Android™]studio. Exclua todo o código em [!DNL MainActivity] **exceto a primeira linha que é a instrução do pacote**.

Cole o código a seguir em [!DNL MainActivity]:

<!--
Removed `{.line-numbers}` below
-->

```java
import androidx.annotation.NonNull;
import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.util.Log;
import android.widget.Toast;

import com.adobe.marketing.mobile.MobileCore;
import com.google.android.gms.tasks.OnCompleteListener;
import com.google.android.gms.tasks.Task;
import com.google.firebase.iid.FirebaseInstanceId;
import com.google.firebase.iid.InstanceIdResult;

public class MainActivity extends AppCompatActivity {

@Override
protected void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState);
setContentView(R.layout.activity_main);

registerToken();
}

void registerToken() {
FirebaseInstanceId.getInstance().getInstanceId()
    .addOnCompleteListener(new OnCompleteListener<InstanceIdResult>() {
        @Override
        public void onComplete(@NonNull Task<InstanceIdResult> task) {
            if (!task.isSuccessful()) {
                Log.w("Message App", "getInstanceId failed", task.getException());
                return;
            }

// Get new Instance ID token
String token = task.getResult().getToken();

Log.d("Got token", token);

MobileCore.setPushIdentifier(token);
}
});
}

@Override
public void onResume() {
super.onResume();
MobileCore.setApplication(getApplication());
MobileCore.lifecycleStart(null);
}

@Override
public void onPause() {
super.onPause();
MobileCore.lifecyclePause();
}
}
```

## Testar seu aplicativo

Agora é um bom momento para testar seu aplicativo, antes de prosseguir.

* Execute seu aplicativo clicando na seta verde ou selecione **[!DNL Run->Run'app']**.
* O emulador [!DNL Android™] deve ser iniciado e você deve ver seu aplicativo em execução com texto [!DNL "Hello World"].
* Abra a janela [!DNL logcat]. Pesquisar por &quot;[!DNL Got]&quot;. Você deve ver o token recebido de [!DNL Firebase] gravado no log como mostrado abaixo. A cadeia longa após &quot;[!DNL Got token]&quot; é o [!DNL pushidentifier] enviado ao Adobe Campaign.

![logcat-token](assets/logcat-got-token.PNG)

### Verificar assinantes de aplicativos móveis

Faça logon na sua instância do Adobe Campaign Standard.
Navegar **[!UICONTROL Administration->Channels->Mobile App(Experience Platform SDK)]**. Abra o aplicativo para dispositivos móveis apropriado. Vá até a guia [!UICONTROL Mobile Application Subscribers]. Você deve ver um [!UICONTROL registration token] listado.

![assinantes de aplicativos móveis](assets/mobile-application-subscribers.PNG)

>[!NOTE]
>
>Se você não vir o token de registro na guia [!UICONTROL Mobile Application Subscribers], PARE aqui antes de continuar.
