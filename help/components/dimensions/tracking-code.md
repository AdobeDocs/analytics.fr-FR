---
title: Code de suivi
description: Nom du code de suivi ou de la campagne.
translation-type: tm+mt
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 100%

---


# Code de suivi

La dimension « Code de suivi » liste les noms des codes de suivi sur votre site. Cette dimension est généralement collectée à l’aide de paramètres de chaîne de requête. Vous pouvez placer des liens avec différentes valeurs de paramètre de chaîne de requête à différents endroits sur Internet. Cette dimension indique les liens qui ont généré le plus de trafic vers votre site.

## Renseignement de cette dimension avec des données

Cette dimension récupère les données de la [`v0`chaîne de requête](/help/implement/validate/query-parameters.md) dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la variable [`campaign`](/help/implement/vars/page-vars/campaign.md).

## Éléments de dimension

Les éléments de dimension incluent les noms des codes de suivi sur votre site. Votre entreprise détermine les éléments de dimension spécifiques à utiliser.

## Comparaison de la dimension Code de suivi avec les canaux marketing qui collectent les codes de suivi

Certains utilisateurs qui configurent des règles de traitement des canaux marketing configurent une règle qui prend toutes les valeurs utilisées dans la dimension Code de suivi. Bien qu’il s’agisse d’une excellente pratique, des différences inhérentes au traitement et à l’architecture les distinguent. La liste suivante explique pourquoi ces deux dimensions, bien que semblables au premier abord, ne sont pas comparables.

* **Canaux antérieurs aux règles de traitement** : les règles de traitement des canaux marketing situées plus haut dans la liste peuvent empêcher l’attribution des accès à votre canal marketing Codes de suivi. Par exemple :

   1. Vous avez configuré les « Réseaux sociaux » comme première règle et les « Codes de suivi » comme seconde règle.
   2. Un utilisateur publie un lien vers votre site contenant un code de suivi sur un site de réseaux sociaux, et plusieurs de ses amis cliquent sur ce lien pour accéder à votre site.

   Comme les « Réseaux sociaux » sont la première règle de traitement des canaux marketing, ces utilisateurs sont attribués au canal marketing « Réseaux sociaux », et non à votre canal marketing Codes de suivi.
* **D’autres canaux marketing peuvent voler l’attribution** : lors de l’utilisation d’une dimension Codes de suivi standard, il est inutile de se soucier de la possibilité que d’autres parties de votre site puissent voler l’attribution. Toutefois, avec les canaux marketing, un utilisateur peut correspondre à une règle différente, ce qui donne une attribution différente. Par exemple :
   1. Votre premier canal est « Codes de suivi » et votre deuxième canal est « Direct ».
   2. Un utilisateur arrive d’abord sur votre site par le biais d’un code de suivi, puis le quitte.
   3. Le lendemain, il saisit votre URL dans la barre d’adresse, puis effectue un achat.

   Le canal marketing Codes de suivi n’obtient pas le crédit Dernière touche pour cet achat. Il est attribué au canal marketing « Direct ».
* **Différences d’expiration** : le délai d’expiration de l’engagement des visiteurs des canaux marketing correspond à une période variable de 30 jours, qu’un canal ait été touché ou non. L’expiration des codes de suivi dépend du moment auquel la variable a été définie. Par exemple :
   1. Vous disposez d’un délai d’expiration de l’engagement des visiteurs de 30 jours et avez également configuré la dimension Code de suivi pour qu’elle expire après 30 jours.
   2. Un utilisateur arrive sur votre site par le biais d’un code de suivi. Il parcourt le site, puis le quitte.
   3. Trois semaines plus tard, il revient sans code de suivi ou canal marketing, puis quitte à nouveau le site.
   4. Au bout de deux semaines supplémentaires (cinq semaines après sa première visite), il revient sans code de suivi ou canal marketing, puis effectue un achat.
   L’utilisateur a finalement effectué un achat au-delà de 30 jours, mais n’a jamais été inactif pendant plus de 30 jours. Le chiffre d’affaires est attribué au canal marketing Codes de suivi, mais pas à la dimension autonome.
