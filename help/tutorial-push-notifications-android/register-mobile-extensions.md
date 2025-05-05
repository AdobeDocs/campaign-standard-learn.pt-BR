---
title: Etapa 3 — Registrar extensões no aplicativo móvel
description: Nesta parte, adicionamos o código para registrar as extensões UserProfile, Identity, Lifecycle e Signal.
feature: Push
user: Admin
level: Experienced
jira: KT-4827
doc-type: tutorial
activity: use
team: TM
exl-id: d8c0d8c6-2e04-4c27-b27a-d0de79dd953b
source-git-commit: 9be31e056800b806c49a2c5ffbf9f9f42b001d4c
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 14%

---

# Etapa 3 — Registrar extensões no aplicativo móvel

Nesta parte, adicionamos o código para registrar as extensões Perfil do usuário, Identidade, Ciclo de vida e Sinal. Também devemos registrar a extensão do Adobe Campaign Standard como mostrado no código abaixo.

Abra o projeto no [!DNL Android] studio. Exclua todo o código no MainApp **exceto a primeira linha que é a instrução do pacote**.

Cole o código a seguir no MainApp

<!--
Removed `{.line-numbers}` below
-->

```java
import [!DNL android].app.Application;
import android.util.Log;

import com.adobe.marketing.mobile.AdobeCallback;
import com.adobe.marketing.mobile.Campaign;
import com.adobe.marketing.mobile.Identity;
import com.adobe.marketing.mobile.InvalidInitException;
import com.adobe.marketing.mobile.Lifecycle;
import com.adobe.marketing.mobile.LoggingMode;
import com.adobe.marketing.mobile.MobileCore;
import com.adobe.marketing.mobile.Signal;
import com.adobe.marketing.mobile.UserProfile;

public class MainApp extends Application {

@Override
public void onCreate() {
super.onCreate();

MobileCore.setApplication(this);
MobileCore.setLogLevel(LoggingMode.DEBUG);

try{
    Campaign.registerExtension();
    UserProfile.registerExtension();
    Identity.registerExtension();
    Lifecycle.registerExtension();
    Signal.registerExtension();
    MobileCore.start(new AdobeCallback () {
        @Override
        public void call(Object o) {
            MobileCore.configureWithAppID("copy your launch property id here");
        }
    });
} catch (InvalidInitException e) {
    Log.d("ACS Exception", "exception");
}
}
}
```

Linha 32, você deve fornecer sua ID de arquivo de ambiente da Propriedade [!UICONTROL &#x200B; Launch]. Isto pode ser acessado a partir do [!UICONTROL environment tab] da sua propriedade [!UICONTROL Launch].

![id-inicialização](assets/launch-id-property.PNG)
