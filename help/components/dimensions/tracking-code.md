---
title: Code de suivi
description: Nom du code de suivi ou de la campagne.
feature: Dimensions
exl-id: e4f70552-6946-4974-a9e2-928faf563ecd
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 66%

---

# Code de suivi

La [dimension](overview.md) du &quot;code de suivi&quot; liste les noms des codes de suivi sur votre site. Vous pouvez placer des liens avec différentes valeurs de paramètre de chaîne de requête à différents endroits sur Internet. Cette dimension vous aide à identifier les liens qui ont généré le plus de trafic vers votre site.

L’ajout de chaînes de requête de code de suivi est courant dans les emails, les publicités, les publications de médias sociaux et d’autres efforts marketing que votre entreprise utilise.

## Renseignement de cette dimension avec des données

Cette dimension récupère les données de la chaîne de requête [`v0`](/help/implement/validate/query-parameters.md) dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la variable [`campaign`](/help/implement/vars/page-vars/campaign.md).

## Éléments de dimension

Les éléments de dimension incluent les noms des codes de suivi sur votre site. Votre entreprise détermine les éléments de dimension spécifiques à utiliser. Voir [Suivi de campagne](/help/implement/use-cases/campaign-tracking.md) pour plus d’informations.

## Comparaison de la dimension Code de suivi avec les canaux marketing qui collectent les codes de suivi

Certains utilisateurs qui configurent des règles de traitement des canaux marketing configurent une règle qui prend toutes les valeurs utilisées dans la dimension Code de suivi. Bien qu’il s’agisse d’une excellente pratique, des différences inhérentes au traitement et à l’architecture les distinguent. La liste suivante explique pourquoi ces deux méthodes, bien que semblables en un coup d’oeil, peuvent modifier le comportement d’attribution.

### Canaux antérieurs aux règles de traitement

Les règles de traitement des canaux marketing situées plus haut dans la liste peuvent empêcher l’attribution des accès à votre canal marketing Codes de suivi. Par exemple :

1. Vous avez configuré les « Réseaux sociaux » comme première règle et les « Codes de suivi » comme seconde règle.
2. Un utilisateur publie un lien vers votre site contenant un code de suivi sur un site de réseau social, et plusieurs de ses amis cliquent sur ce lien pour accéder à votre site.

Comme les « Réseaux sociaux » sont la première règle de traitement des canaux marketing, ces utilisateurs sont attribués au canal marketing « Réseaux sociaux », et non à votre canal marketing Codes de suivi.

### D’autres canaux marketing peuvent effectuer l’attribution par le biais de la Dernière touche.

Lorsque vous gérez une dimension Codes de suivi standard, vous n’avez pas à vous soucier de ce que d’autres parties de votre site puissent voler l’attribution. Toutefois, avec les canaux marketing, un utilisateur peut correspondre à une règle différente, ce qui donne une attribution différente. Par exemple :

1. Votre premier canal est « Codes de suivi » et votre deuxième canal est « Direct ».
2. Un utilisateur arrive d’abord sur votre site par le biais d’un code de suivi, puis le quitte.
3. Le lendemain, il saisit votre URL dans la barre d’adresse, puis effectue un achat.

Dans cet exemple, le canal marketing Codes de suivi n’obtient pas de crédit Dernière touche pour cet achat. Il est attribué au canal marketing « Direct ».


### Différences d’expiration

Les canaux marketing ont une expiration variable de l’engagement des visiteurs de 30 jours, qu’un canal ait été touché ou non. L’expiration des codes de suivi dépend du moment auquel la variable a été définie. Par exemple :

1. Vous disposez d’un délai d’expiration de l’engagement des visiteurs de 30 jours et avez également configuré la dimension Code de suivi pour qu’elle expire après 30 jours.
2. Un utilisateur arrive sur votre site par le biais d’un code de suivi. Il parcourt le site, puis le quitte.
3. Trois semaines plus tard, il revient sans code de suivi ou canal marketing, puis quitte à nouveau le site.
4. Au bout de deux semaines supplémentaires (cinq semaines après sa première visite), il revient sans code de suivi ou canal marketing, puis effectue un achat.

L’utilisateur a finalement effectué un achat au-delà de 30 jours, mais n’a jamais été inactif pendant plus de 30 jours. Dans ce cas, les recettes seraient attribuées au canal marketing Codes de suivi , mais pas à la dimension Code de suivi elle-même.



