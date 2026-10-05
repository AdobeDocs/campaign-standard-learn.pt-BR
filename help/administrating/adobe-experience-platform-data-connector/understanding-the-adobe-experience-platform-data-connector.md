---
title: Entender o conector de dados do Adobe Experience Platform
description: O Conector de dados do Adobe Experience Platform ajuda os clientes existentes a disponibilizar seus dados no Adobe Experience Platform, mapeando os dados XTK (dados assimilados no Campaign) para dados do Experience Data Model (XDM) no Adobe Experience Platform.
feature: People Core Service Integration
jira: KT-2826
thumbnail: 27304.jpg
role: User
level: Experienced
doc-type: feature video
activity: understand
team: TM
exl-id: 686961f9-5374-4cc6-8b36-7ee0584ea720
TQID: 'https://experienceleague.adobe.com/8z32-bArYoMN41QFSi19bXUFc617UqZvdzxaam0Xr-E'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: a8512b64-d668-4084-b4f0-34baa899e306
    internal-label: People Core Service integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 508c3590ce956401ccfba3a256000cbc5849a684
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 4%
---
# Compreender o Adobe Experience Platform [!UICONTROL Data Connector]

>[!NOTE]
>
>Esse recurso está na versão beta e está sujeito a atualizações e modificações frequentes sem aviso prévio.
>
>Entre em contato com [!UICONTROL Adobe Customer Support] se planeja implementar esse recurso.

## Visão geral

O Adobe Experience Platform [!UICONTROL Data Connector] ajuda os clientes existentes a disponibilizar seus dados no Adobe Experience Platform, mapeando os dados XTK (dados assimilados no Adobe Campaign) para dados do [!DNL Experience Data Model] (XDM) no Adobe Experience Platform.

O conector é unidirecional e envia os dados do Adobe Campaign Standard para a Adobe Experience Platform. Os dados nunca são enviados da Adobe Experience Platform para o Adobe Campaign Standard.

O Adobe Experience Platform [!UICONTROL Data Connector] destina-se a engenheiros de dados que compreendem o Adobe Campaign Standard [!UICONTROL custom resources] e que têm uma compreensão de como o esquema de dados geral do cliente deve estar dentro do Adobe Experience Platform.

>[!VIDEO](https://video.tv.adobe.com/v/34326?captions=por_br&learn=on){transcript=true}

*Este vídeo fornece uma visão geral sobre o Adobe Experience Platform [!UICONTROL Data Connector] (09:35 min)*

>[!NOTE]
>
>A transferência predefinida de [!UICONTROL subscription events] não é suportada. Para transferir [!UICONTROL subscription events], você pode criar o XDM e o conjunto de dados correspondentes no Adobe Experience Platform e, em seguida, configurar um mapeamento de dados personalizado para esses dados.
>
>Não é possível assimilar [!UICONTROL experience events] existente no Adobe Experience Platform, mas o [!UICONTROL experience events] gerado continuamente é transmitido para o Adobe Experience Platform.

## Etapas principais para executar um mapeamento de dados

Os tutoriais a seguir descrevem as principais etapas para executar um mapeamento de dados entre o Campaign Standard e a Adobe Experience Platform:

1. [Mapeamento de recursos personalizados](/help/administrating/adobe-experience-platform-data-connector/mapping-custom-resources.md)
2. [Mapeamento de eventos de experiência](/help/administrating/adobe-experience-platform-data-connector/mapping-experience-events.md)
3. [Mapeamento de dados da tabela de seed](/help/administrating/adobe-experience-platform-data-connector/mapping-seed-table-data.md)
4. [Modificação do Mapeamento de Dados](/help/administrating/adobe-experience-platform-data-connector/modifying-data-mapping.md)
5. [Verificar o status de um processo de ingestão de dados](/help/administrating/adobe-experience-platform-data-connector/checking-status-of-data-ingestion-jobs.md)

