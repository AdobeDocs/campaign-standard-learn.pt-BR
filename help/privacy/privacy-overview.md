---
title: Solicitações de privacidade com o Adobe Campaign Standard (ACS) - Visão geral
description: O tutorial explica como criar solicitações de privacidade por meio da interface do Adobe Campaign Standard (ACS).
feature: GDPR, CCAP
topic: Privacy
kt: 1480
doc-type: feature video
activity: use
team: TM
translation-type: tm+mt
source-git-commit: 556bff4c94e16d3a94561dee1ccb311bc003b631
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 7%

---


# Solicitações de privacidade com a interface de usuário padrão do Adobe Campaign

O Adobe Campaign oferta Data Controller utiliza três métodos para executar o acesso à privacidade e excluir solicitações de dados PII em conformidade com atos de privacidade, como o GDPR (General Data Protection Regulation) e o CCPA (California Consumer Privacy Act):

* **Através da integração do Privacy Core Service:** As solicitações de privacidade enviadas de todas [!UICONTROL Privacy Service] para todas as soluções da Experience Cloud são automaticamente tratadas pela Campanha por meio de um fluxo de trabalho dedicado. Consulte o [Adobe Experience Platform Privacy Service](https://adobe.io/apis/cloudplatform/gdpr.html) para saber como criar solicitações de privacidade do Privacy Core Service

* **Pela API:** O Adobe Campaign fornece uma API que permite o processo automático de solicitações de privacidade usando REST

* **Pela interface do Adobe Campaign:** para cada solicitação de privacidade, o controlador de dados cria uma nova solicitação de privacidade no Adobe Campaign

>[!NOTE]
>
> **ALTERAÇÕES COM ACS 19.4:**
> 
> A integração [](https://adobe.io/apis/cloudplatform/gdpr.html) do Privacy Service é o método que você deve usar para todas as solicitações de acesso e exclusão. A partir da versão 19.4, o uso da API e da interface do Campaign para solicitações de acesso e exclusão ficará obsoleto. Para obter mais informações sobre os recursos desaprovados e removidos do Campaign Standard, consulte [esta página](https://helpx.adobe.com/br/campaign/kb/acs-deprecated-and-removed-features.html).
>
>**Recusar a venda de informações pessoais (CCPA)**
>
>A partir do 19.4, um campo de opção de não participação CCPA é fornecido prontamente na interface de Campanha e na API. Para 19.3, para aproveitar essas informações, é necessário criar esse campo no Adobe Campaign Standard. Consulte a documentação [](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa) detalhada para obter mais informações.
>
> Você pode verificar sua versão clicando em ? no canto superior direito da interface e selecionando Sobre.

## Tutoriais em vídeo

### Pré-requisitos para solicitações de privacidade

1. [Criar uma Namespace](/help/privacy/namespaces-for-privacy-requests.md)
1. [Modificar recursos personalizados](/help/privacy/custom-resources-for-privacy-requests.md)

### Criar, rastrear e executar solicitações de privacidade na interface do usuário do Adobe Campaign

* [Criar e rastrear solicitações de privacidade por meio da interface do usuário do Adobe Campaign](/help/privacy/create-and-track-privacy-requests.md)
* [Executar solicitações de privacidade](/help/privacy/execute-privacy-requests.md)

## Recursos adicionais

* [Diretrizes gerais de privacidade para Campanhas](https://helpx.adobe.com/br/campaign/kb/campaign-privacy-overview.html)
* [CCPA para ACS](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa)
* [Adobe Experience Platform Privacy Service](https://adobe.io/apis/cloudplatform/gdpr.html)
* [Documentação da API REST padrão do Adobe Campaign](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#privacy-management)