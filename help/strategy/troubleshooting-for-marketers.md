---
title: Solução de problemas para profissionais de marketing
description: Conhecer os erros mais comuns pode ajudar na solução mais rápida de problemas e aumentar sua produtividade. Essas dicas de solução de problemas ajudam você a resolver com eficiência erros semelhantes que ocorrem.
feature: Workflows
role: User
level: Beginner, Intermediate, Experienced
doc-type: Article
last-substantial-update: 2023-05-18T00:00:00Z
jira: KT-13256
thumbnail: KT-13256.jpeg
exl-id: 24a6815b-52d1-4bd6-9d27-522720a91f83
source-git-commit: 83b1b0c98d74d4555269a7d90051146d21824dc0
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 0%

---

# Solução de problemas para profissionais de marketing: 5 erros comuns de fluxo de trabalho e delivery

Por: [Suraj Patra](https://www.linkedin.com/in/suraj-p-51612053/){target="_blank"}, consultor sênior, Meijer

Como engenheiro sênior e especialista em clientes de produtos Adobe Experience Cloud nos últimos cinco anos, eu ofereço aos usuários de negócios da [Meijer](https://www.meijer.com/){target="_blank"}, uma cadeia de supercentros americana fundada em 1934, a capacidade de executar campanhas transacionais e de marketing complexas com o ACS. Alguns projetos nos quais trabalhei incluem campanhas personalizadas para armazenar ofertas e detalhes de pedidos para personalização, integradas ao Adobe Audience Manager, e insight do cliente para assimilação de segmentos.


No meu tempo usando o ACS, me deparei com erros que podem ser demorados e frustrantes de resolver. Conhecer os erros mais comuns pode ajudar na solução mais rápida de problemas e aumentar sua produtividade. Abaixo estão minhas dicas de solução de problemas para ajudar você a resolver com eficiência erros semelhantes que ocorrem.

## Erro de incompatibilidade de tipo de dados

**Código de Erro:**
`PGS-220000 PostgreSQL error: ERROR: operator does not exist: character varying = bigint`

**Causa:**
Esses tipos de erros aparecem em um fluxo de trabalho quando você tenta reconciliar usando campos de tipos de dados diferentes. Por exemplo, ao fazer upload de um arquivo usando carregar arquivo, que tem um campo de sequência, e você tenta reconciliar o campo de sequência com um campo de perfil que tem o tipo de dados int.

![erro de incompatibilidade de tipo de dados](/help/assets/kt-13256/data-type-mismatch.png)

**Solução:**
Altere o tipo de dados do campo na atividade &quot;Load file&quot; para o tipo com o qual você está correspondendo. Abra a atividade &quot;Load File&quot;. Vá até a guia &quot;DEFINIÇÃO DE COLUNA&quot; e altere o tipo de dados do campo desejado.


![solução-incompatibilidade-tipo-dados](/help/assets/kt-13256/data-type-mismatch-solution.png)

## Erro de entrega do Personalization

**Código de Erro:**
`The schema for profiles specified in the transition ('') is not compatible with the schema defined in the delivery template ('nms:recipient'). They should be identical.`

**Causa:**
Este erro aparece ao enviar um email para um endereço, mas o email ou qualquer outro identificador não é reconciliado com um perfil. Para enviar uma comunicação por email, o email ou o identificador deve estar sempre vinculado a um perfil.

![fluxo de trabalho com atividade de reconciliação](/help/assets/kt-13256/del-persn-error-wf.png)

**Solução:**
Uma ID comum deve existir no arquivo carregado com a tabela de recipients. Essa chave comum une o arquivo de carregamento à tabela de recipients na atividade de reconciliação. Emails não podem ser enviados a registros que não existem na tabela de recipients, o que requer essa etapa de reconciliação no workflow. Ao fazer isso, você reconciliaria a atividade do arquivo de carregamento recebido com um identificador como a ID do email do perfil. O esquema `nms:recipient` faz referência à tabela de perfil e a reconciliação dos registros de entrada com o perfil o torna disponível durante a preparação do email.

Consulte a captura de tela para atividade de reconciliação, como mostrado abaixo.

![fluxo de trabalho com detalhes de reconciliação](/help/assets/kt-13256/del-persn-error-wf-solution.png)

Saiba mais sobre [reconciliação](https://experienceleague.adobe.com/pt-br/docs/campaign-standard/using/managing-processes-and-data/data-management-activities/reconciliation).

## Erro de conjunto de dados de campo comum

**Código de Erro:**
`The document types of inbound events (''and'') are incompatible (step 'Exclusion'). Unable to perform the operation. `

**Causa:**
Esse problema ocorre ao usar a **atividade de exclusão** em fluxos de trabalho ACS, ao executar uma exclusão com base na ID, quando o conjunto Principal e o conjunto excluído não têm os mesmos nomes de campo.


![Erro no conjunto de dados do campo comum](/help/assets/kt-13256/dataset-error.png)

**Solução:**

Há duas maneiras de resolver esse erro:

1. Use o mesmo nome de campo no principal e no excluído e use esse campo como ID

   OU

2. Use o método de exclusão JOINS para selecionar o campo com base no qual deseja excluir os registros.

![Erro de Conjunto de Dados de Campo Comum - Solução &#x200B;](/help/assets/kt-13256/dataset-error-solution.png)

## Erro de descarte de nome de campo

**Código de Erro:**
`XTK-170036 Unable to parse expression 'i__name'`

**Causa:**

Podem ocorrer pontos de falha em uma **atividade de enriquecimento**. Uma das mais comuns é exibida abaixo.

![Nome do Campo Descartado Erro](/help/assets/kt-13256/field-name-dropped-error.png)

Isso acontece quando você edita manualmente um nome de expressão na atividade. A imagem mostra que a expressão foi modificada de `name ` para `i__name`.

**Solução:**

Você pode resolver esse erro de três maneiras:

1. Retorne o nome para a expressão que estava originalmente presente.

2. Se quiser usar um novo nome, altere os valores na **atividade de enriquecimento**.

3. Se você não lembrar o que mudou, a melhor opção seria recriar a atividade.

## Erro de descarte de tabela temporária 

**Código de Erro:**
`XTK-170024 The temporary schema "temp:deliveryEmail1" is not defined in the current context.`

**Causa:**
Esse é um erro comum em workflows complicados envolvendo enriquecimento ou outra atividade. Isso provavelmente significa que alguns dos workflows de atividade não são salvos corretamente durante várias alterações no workflow.

![Tabela Temporária Removida Erro &#x200B;](/help/assets/kt-13256/temp-table-dropped-error.png)

**Solução:**
Há muitas maneiras de esse erro ocorrer, portanto, não há uma correção simples. Se for um fluxo de trabalho simples, é melhor reconfigurar a atividade. Em um workflow complicado, é melhor copiar as atividades do workflow para um novo workflow, salvá-lo e executá-lo novamente.
