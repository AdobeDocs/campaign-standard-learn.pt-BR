---
title: Solicitações de privacidade com o Adobe Campaign Standard (ACS) - Visão geral
description: O tutorial explica como criar solicitações de privacidade por meio da interface do Adobe Campaign Standard.
feature: Privacy Tools
jira: KT-1480
doc-type: feature video
activity: use
role: Admin
level: Advanced
team: TM
recommendations: noDisplay
exl-id: fb766403-694c-4a7b-b3d1-4a418df85891
source-git-commit: 89f520da0455da693b27c397f95cdabab4552770
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 90%

---

# Solicitações de privacidade com a interface do Adobe Campaign Standard

O Adobe Campaign oferece aos controladores de dados três métodos para executar o acesso à Privacidade e excluir solicitações de dados PII em conformidade com as leis de privacidade, como o GDPR (Regulamento Geral sobre a Proteção de Dados) e a CCPA (Lei de Privacidade do Consumidor da Califórnia):

* **Pela integração do Serviço principal de privacidade:** as solicitações de privacidade transmitidas do [!UICONTROL Privacy Service] para todas as soluções da Experience Cloud são tratadas automaticamente pelo Campaign, por meio de um fluxo de trabalho específico. Para saber como criar solicitações de privacidade do Privacy Core Service consulte o [Adobe Experience Platform Privacy Service](https://developer.adobe.com/apis/experienceplatform/gdpr.html)

* **Pela API:** o Adobe Campaign fornece uma API que permite o processo automático de solicitações de privacidade usando REST

* **Pela interface do Adobe Campaign:** para cada solicitação de privacidade, o controlador de dados cria uma solicitação de privacidade no Adobe Campaign

>[!NOTE]
>
> **ALTERAÇÕES NO ACS 19.4:**
> 
> A variável [integração de Privacy Service](https://developer.adobe.com/apis/experienceplatform/gdpr.html) é o método que deve ser usado para todas as solicitações de acesso e exclusão. A partir da versão 19.4, o uso da API e da interface do Campaign para solicitações de acesso e exclusão se tornará obsoleto. Para obter mais informações sobre recursos obsoletos e removidos do Campaign Standard, consulte [esta página](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=br).
>
>**Recusar a venda de informações pessoais (CCPA)**
>
> O campo Recusa da CCPA é oferecido pronto para uso na interface e API do Campaign.
>
> Para verificar sua versão, clique no ícone **?** no canto superior direito da interface e selecionando Sobre.

## Tutoriais em vídeo

### Pré-requisitos para solicitações de privacidade

1. [Criar um namespace](/help/privacy/namespaces-for-privacy-requests.md)
1. [Modificar recursos personalizados](/help/privacy/custom-resources-for-privacy-requests.md)

### Criar, rastrear e executar solicitações de privacidade por meio da interface do usuário do Adobe Campaign

* [Criar e rastrear solicitações de privacidade por meio da interface do usuário do Adobe Campaign](/help/privacy/create-and-track-privacy-requests.md)
* [Executar solicitações de privacidade](/help/privacy/execute-privacy-requests.md)

## Recursos adicionais

* [Diretrizes gerais de privacidade do Campaign](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=br#getting-started)
* [CCPA para ACS](https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=br#privacy-requests)
* [Adobe Experience Platform Privacy Service](https://developer.adobe.com/apis/experienceplatform/gdpr.html)
* [Documentação da API REST do Adobe Campaign Standard](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#privacy-management)
