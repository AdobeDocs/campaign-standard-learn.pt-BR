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
source-git-commit: 943599bd7ce139ef846f093ebda9084a91550aca
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 5%

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

>[!VIDEO](https://video.tv.adobe.com/v/27304?learn=on){transcript=true}

*Este vídeo fornece uma visão geral sobre o Adobe Experience Platform [!UICONTROL Data Connector] (09:35 min)*

>[!NOTE]
>
>A transferência predefinida de [!UICONTROL subscription events] não é suportada. Para transferir [!UICONTROL subscription events], você pode criar o XDM e o conjunto de dados correspondentes no Adobe Experience Platform e, em seguida, configurar um mapeamento de dados personalizado para esses dados.
>
>Não é possível assimilar [!UICONTROL experience events] existente no Adobe Experience Platform, mas o [!UICONTROL experience events] gerado continuamente é transmitido para o Adobe Experience Platform.

## Etapas principais para executar um mapeamento de dados

Os tutoriais a seguir descrevem as principais etapas para executar um mapeamento de dados entre o Campaign Standard e o Adobe Experience Platform:

1. [Mapeamento de recursos personalizados](/help/administrating/adobe-experience-platform-data-connector/mapping-custom-resources.md)
2. [Mapeamento de eventos de experiência](/help/administrating/adobe-experience-platform-data-connector/mapping-experience-events.md)
3. [Mapeamento de dados da tabela de seed](/help/administrating/adobe-experience-platform-data-connector/mapping-seed-table-data.md)
4. [Modificação do Mapeamento de Dados](/help/administrating/adobe-experience-platform-data-connector/modifying-data-mapping.md)
5. [Verificar o status dos trabalhos de assimilação de dados](/help/administrating/adobe-experience-platform-data-connector/checking-status-of-data-ingestion-jobs.md)

