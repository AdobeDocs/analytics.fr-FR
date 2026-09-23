---
title: Code de suivi
description: Nom du code de suivi ou de la campagne.
feature: Dimensions
exl-id: e4f70552-6946-4974-a9e2-928faf563ecd
TQID: https://experienceleague.adobe.com/8e9126PxGCNXJqo4a3XYTgXwrcHdf34FVwygpHXm5JI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 88%
---
# Code de suivi

La [dimension](overview.md) « Code de suivi » répertorie les noms des codes de suivi sur votre site. Vous pouvez placer des liens avec différentes valeurs de paramètre de chaîne de requête à différents endroits sur Internet. Cette dimension vous aide à mieux comprendre quels liens ont généré le plus de trafic vers votre site.

L’ajout de chaînes de requête de code de suivi est courant dans les e-mails, les publicités, les publications sur les réseaux sociaux et d’autres efforts marketing utilisés par votre organisation.

## Renseignement de cette dimension avec des données

AppMeasurement collecte ces données à l’aide de la variable [`campaign`](/help/implement/vars/page-vars/campaign.md). Cette variable obtient généralement sa valeur à partir d’une chaîne de requête à l’aide de la méthode de l’utilitaire [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md), bien que votre entreprise détermine exactement comment la définir.

| Propriété | Valeur |
| --- | --- |
| **Variable** | [`campaign`](/help/implement/vars/page-vars/campaign.md) |
| **Champ Web SDK/XDM** | [`marketing.trackingCode`](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/field-groups/event/campaign-marketing-details) |
| **Paramètre de requête** | [`v0`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Balise XML** | [`<campaign>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite d’octets** | 255 octets |
| **Persistance** | Configurable |

## Éléments de dimension

Les éléments de dimension incluent les noms des codes de suivi sur votre site. Votre entreprise détermine les éléments de dimension spécifiques à utiliser. Consultez [Suivi de campagne](/help/implement/use-cases/campaign-tracking.md) pour plus d’informations.

## Comparaison de la dimension Code de suivi avec les canaux marketing qui collectent les codes de suivi

Certains utilisateurs ou utilisatrices qui configurent des règles de traitement du canal marketing définissent une règle qui prend toutes les valeurs utilisées dans la dimension Code de suivi. Bien qu’il s’agisse d’une excellente pratique, des différences inhérentes au traitement et à l’architecture les distinguent. La liste suivante explique pourquoi ces deux méthodes, bien que similaires au premier abord, peuvent modifier le comportement d’attribution.

### Canaux précédents dans les règles de traitement

Les règles de traitement des canaux marketing situées plus haut dans la liste peuvent empêcher l’attribution des hits à votre canal marketing Codes de suivi. Par exemple :

1. Vous avez configuré les « Réseaux sociaux » comme première règle et les « Codes de suivi » comme seconde règle.
2. Un utilisateur publie un lien vers votre site contenant un code de suivi sur un réseau social, et plusieurs de ses amis cliquent sur ce lien pour accéder à votre site.

Comme les « Réseaux sociaux » sont la première règle de traitement des canaux marketing, ces utilisateurs sont attribués au canal marketing « Réseaux sociaux », et non à votre canal marketing Codes de suivi.

### D’autres canaux marketing peuvent utiliser l’attribution via la dernière touche.

Lors de l’utilisation d’une dimension Codes de suivi standard, il est inutile de se soucier de la possibilité que d’autres parties de votre site puissent voler l’attribution. Toutefois, avec les canaux marketing, un utilisateur peut correspondre à une règle différente, ce qui donne une attribution différente. Par exemple :

1. Votre premier canal est « Codes de suivi » et votre deuxième canal est « Direct ».
2. Un utilisateur arrive d’abord sur votre site par le biais d’un code de suivi, puis le quitte.
3. Le lendemain, il saisit votre URL dans la barre d’adresse, puis effectue un achat.

Dans cet exemple, le canal marketing Codes de suivi n’obtient pas le crédit Dernière touche pour cet achat. Il est attribué au canal marketing « Direct ».


### Différences d’expiration

Les canaux marketing ont un délai d’expiration glissant de 30 jours pour l’engagement des visiteurs ou des visiteuses, qu’un canal ait été touché ou non. L’expiration des codes de suivi dépend du moment auquel la variable a été définie. Par exemple :

1. Vous disposez d’un délai d’expiration de l’engagement des visiteurs de 30 jours et avez également configuré la dimension Code de suivi pour qu’elle expire après 30 jours.
2. Un utilisateur arrive sur votre site par le biais d’un code de suivi. Il parcourt le site, puis le quitte.
3. Trois semaines plus tard, il revient sans code de suivi ou canal marketing, puis quitte à nouveau le site.
4. Au bout de deux semaines supplémentaires (cinq semaines après sa première visite), il revient sans code de suivi ou canal marketing, puis effectue un achat.

L’utilisateur a finalement effectué un achat au-delà de 30 jours, mais n’a jamais été inactif pendant plus de 30 jours. Dans ce cas, le chiffre d’affaires est attribué au canal marketing Codes de suivi, mais pas à la dimension autonome Code de suivi elle-même.



