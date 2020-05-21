---
title: Etapa 1 - Criar aplicativo Android e configurar para usar o Firebase Cloud Messaging
description: Nesta parte, criaremos o aplicativo [!DNL Android] para receber [!UICONTROL Push notifications] enviadas do Adobe Campaign Standard. Para receber notificações por push, o aplicativo precisa ser registrado com o [!DNL Firebase Cloud Service] do Google.
feature: Push
topics: Mobile
kt: 4825
doc-type: tutorial
activity: use
team: TM
translation-type: tm+mt
source-git-commit: afe1ae6c8d73b7b776e0eec327fa16db76c23ce1
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 2%

---


# Etapa 1 - Criar [!DNL Android] aplicativo e configurar para usar [!DNL Firebase Cloud Messaging]

Nesta parte, você criará o [!DNL Android] aplicativo para receber [!UICONTROL Push notifications] o envio do Adobe Campaign Standard. Para receber notificações por push, o aplicativo precisa ser registrado no Google [!DNL Firebase Cloud Service].

1. Faça logon em sua [!DNL Firebase] conta.

   [!DNL Firebase] é a plataforma móvel do Google que ajuda você a desenvolver rapidamente aplicativos de alta qualidade. Se você não tiver uma [!DNL Firebase] conta, crie uma [daqui](https://firebase.google.com).

2. Iniciar [!DNL Android Studio]
3. Click **[!UICONTROL File]** > **[!UICONTROL New]** > **[!UICONTROL New Project].**
4. Selecione **[!UICONTROL Empty Activity]** e clique em **[!UICONTROL Next].**

   ![android-project](assets/android-project.PNG)

5. Forneça um nome significativo para o projeto.

   Para o objetivo desta demonstração nós chamamos nosso projeto de *[!DNL ACSPushTutorial]*

   ![android-project-configuration](assets/android-project-configuration.PNG)

6. Aceite os nomes de pacote padrão e clique em **[!DNL Finish]** para criar seu projeto.
7. A estrutura do projeto deve ser semelhante à captura de tela abaixo

   ![android-project-structure](assets/android-project-structure.PNG)

8. Clique em **[!UICONTROL Tools]** > **[!UICONTROL Firebase].**(isso adiciona o projeto ao[!DNL Firebase])
9. Clique em **[!UICONTROL Set up Firebase Cloud Messaging].**

   ![firebase de configuração](assets/android-project-firebase-messaging.PNG)

10. Clique em **[!UICONTROL Connect to Firebase].**
11. Depois que o aplicativo estiver conectado ao Firebase, clique em **[!UICONTROL Add FCM to your app].**
12. Clique em **[!UICONTROL Accept Changes].**

   Ao adicionar o FCM ao seu aplicativo, o assistente precisa de sua permissão para fazer algumas alterações no seu projeto.

   ![[!DNL add-fcm-to-your-app]](assets/firebase-add-fcm-to-app.PNG)

Na integração bem-sucedida de seu aplicativo com o Firebase, você deve receber uma mensagem como a mostrada abaixo:

![[!DNL fcm-successfull]](assets/android-firebase-success.PNG)

[Certifique-se de que seu projeto esteja listado no console [!DNL Firebase ]](https://console.firebase.google.com/)

## Definir [!UICONTROL Push Channel] configurações

1. Fazer logon no [!DNL Firebase] console
2. Abra o **[!UICONTROL ACSPushTutorial]** projeto.
3. Clique no ícone **de** engrenagem e abra as configurações do projeto

   ![project-settings](assets/firebase-project-settings.PNG)

4. Pressione até a **[!UICONTROL Cloud Messaging]** guia.
5. Copiar a chave do servidor

   ![chave de servidor](assets/firebase-server-key.PNG)

6. Faça logon na sua instância do Adobe Campaign Standard
7. Click **[!UICONTROL Adobe Campaign]** > **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile App].**
8. Selecione a opção apropriada **[!UICONTROL Mobile Application Property].**
9. Click the **[!DNL Android]icon **in the **[!UICONTROL Push Channel settings]**section.
10. Cole a chave do servidor no campo da chave do servidor.

Se tudo correr bem, você deverá ver uma mensagem de sucesso.

![configurações de canal de push](assets/push-channel-settings.PNG)

Resumindo, criamos um [!DNL Android App] e conectamos o [!DNL Android App] grupo ao [!DNL Firebase]. Em seguida, conectamos o aplicativo móvel ao Adobe Campaign com o aplicativo, [!DNL Android App] colando a chave do servidor do [!DNL Android] aplicativo no aplicativo móvel no Adobe Campaign Standard.