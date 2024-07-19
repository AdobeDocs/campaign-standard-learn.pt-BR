---
title: Etapa 1 - Criação do aplicativo Android e configuração para usar o Firebase Cloud Messaging
description: Nesta parte, criaremos o  [!DNL Android] Aplicativo para receber [!UICONTROL Push notifications] enviado do Adobe Campaign Standard. Para receber as notificações por push, o aplicativo precisa ser registrado com o  [!DNL Firebase Cloud Service] do Google.
feature: Push
user: Admin
level: Experienced
jira: KT-4825
doc-type: tutorial
activity: use
team: TM
recommendations: noDisplay
exl-id: f087d9f2-cce9-4903-977f-3c5b47522c06
source-git-commit: 0ad82fb0533ed8fc2a85c2a32c7e54deef14d05a
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# Etapa 1 - Criando o aplicativo [!DNL Android] e configurando para usar [!DNL Firebase Cloud Messaging]

Nesta parte, você criará o aplicativo [!DNL Android] para receber [!UICONTROL Push notifications] enviado do Adobe Campaign Standard. Para receber as notificações por push, o aplicativo precisa ser registrado com o [!DNL Firebase Cloud Service] da Google.

1. Faça logon na sua conta do [!DNL Firebase].

   O [!DNL Firebase] é a plataforma móvel da Google que ajuda você a desenvolver aplicativos de alta qualidade. Se você não tiver uma conta [!DNL Firebase], crie um [daqui](https://firebase.google.com).

2. Iniciar [!DNL Android Studio]
3. Clique em **[!UICONTROL File]** > **[!UICONTROL New]** > **[!UICONTROL New Project].**
4. Selecione **[!UICONTROL Empty Activity]** e clique em **[!UICONTROL Next].**

   ![projeto-android](assets/android-project.PNG)

5. Forneça um nome significativo para o projeto.

   Para o propósito desta demonstração, nomeamos nosso projeto como *[!DNL ACSPushTutorial]*

   ![android-project-configuration](assets/android-project-configuration.PNG)

6. Aceite os nomes de pacote padrão e clique em **[!DNL Finish]** para criar seu projeto.
7. A estrutura do projeto deve ser semelhante à captura de tela abaixo

   ![estrutura-projeto-android](assets/android-project-structure.PNG)

8. Clique em **[!UICONTROL Tools]** > **[!UICONTROL Firebase].** (isso adiciona o projeto a [!DNL Firebase])
9. Clique em **[!UICONTROL Set up Firebase Cloud Messaging].**

   ![configurar firebase](assets/android-project-firebase-messaging.PNG)

10. Clique em **[!UICONTROL Connect to Firebase].**
11. Depois que seu aplicativo for conectado ao Firebase, clique em **[!UICONTROL Add FCM to your app].**
12. Clique em **[!UICONTROL Accept Changes].**

   Quando você está adicionando o FCM ao aplicativo, o assistente precisa de sua permissão para fazer algumas alterações no projeto.

   ![[!DNL add-fcm-to-your-app]](assets/firebase-add-fcm-to-app.PNG)

Ao integrar com êxito seu aplicativo ao Firebase, você deve receber uma mensagem como a mostrada abaixo:

![[!DNL fcm-successfull]](assets/android-firebase-success.PNG)

[Verifique se o projeto está listado no [!DNL Firebase ]console](https://console.firebase.google.com/)

## Definir Configurações de [!UICONTROL Push Channel]

1. Fazer logon no console [!DNL Firebase]
2. Abra o projeto **[!UICONTROL ACSPushTutorial]**.
3. Clique no **ícone de engrenagem** e abra as configurações do projeto

   ![configurações-projeto](assets/firebase-project-settings.PNG)

4. Vá até a guia **[!UICONTROL Cloud Messaging]**.
5. Copiar a chave do servidor

   ![chave-do-servidor](assets/firebase-server-key.PNG)

6. Faça logon na sua instância do Adobe Campaign Standard
7. Clique em **[!UICONTROL Adobe Campaign]** > **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile App].**
8. Selecione o **[!UICONTROL Mobile Application Property].** apropriado
9. Clique no ícone **[!DNL Android]** na seção **[!UICONTROL Push Channel settings]**.
10. Cole a chave do servidor no campo de chave do servidor.

Se tudo correr bem, você verá uma mensagem de SUCESSO.

![configurações-do-canal-de-push](assets/push-channel-settings.PNG)

Para resumir, criamos um [!DNL Android App] e conectamos o [!DNL Android App] com [!DNL Firebase]. Em seguida, conectamos o Aplicativo Móvel no Adobe Campaign com o [!DNL Android App] colando a chave do servidor do Aplicativo [!DNL Android] no Aplicativo Móvel no Adobe Campaign Standard.
