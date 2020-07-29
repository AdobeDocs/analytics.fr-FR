---
title: Code de suivi
description: Nom du code de suivi ou de la campagne.
translation-type: tm+mt
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---


# Code de suivi

La dimension &quot;Code de suivi&quot; liste les noms des codes de suivi sur votre site. Cette dimension est généralement collectée à l’aide de paramètres de chaîne de requête. Vous pouvez placer des liens avec différentes valeurs de paramètre de chaîne de requête à différents endroits sur Internet. Cette dimension indique les liens qui ont généré le plus de trafic vers votre site.

## Renseigner cette dimension avec des données

Cette dimension récupère les données de la chaîne [`v0` de](/help/implement/validate/query-parameters.md) requête dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la [`campaign`](/help/implement/vars/page-vars/campaign.md) variable.

## Éléments de Dimension

Les éléments de Dimension incluent les noms des codes de suivi sur votre site. Votre organisation détermine les éléments de dimension spécifiques que vous souhaitez utiliser.

## Comparaison de la dimension Code de suivi avec les canaux marketing qui collectent les codes de suivi

Certains utilisateurs qui configurent des règles de traitement de canal marketing configurent une règle qui prend toutes les valeurs utilisées dans la dimension Code de suivi. Bien qu&#39;excellente pratique, elles sont différentes en raison des différences inhérentes au traitement et à l&#39;architecture. La liste suivante explique pourquoi ces deux dimensions, même si elles sont similaires d’un seul coup d’oeil, ne peuvent pas être comparées.

* **canaux antérieurs dans les règles** de traitement : Les règles de traitement des canaux marketing plus élevées dans la liste peuvent empêcher les accès d’être attribués à votre canal marketing Codes de suivi. Par exemple :

   1. Vous avez configuré les réseaux sociaux comme première règle et les codes de suivi comme seconde règle.
   2. Un utilisateur publie un lien vers votre site contenant un code de suivi sur un site de médias sociaux, et plusieurs de ses amis cliquent sur ce lien vers votre site.

   Comme les réseaux sociaux sont la première règle de traitement du canal marketing, ces utilisateurs attribuent au canal marketing Réseaux sociaux, et non à votre canal marketing Codes de suivi.
* **D’autres canaux marketing peuvent voler l’attribution**: Lors de l’utilisation d’une dimension Codes de suivi standard, vous n’avez pas à vous soucier des autres parties de l’attribution de vol de votre site. Toutefois, avec les canaux marketing, un utilisateur peut correspondre à une règle différente, en attribuant une attribution différente. Par exemple :
   1. Vous avez &quot;Codes de suivi&quot; comme premier canal et &quot;Direct&quot; comme second.
   2. Un utilisateur arrive d’abord sur votre site par le biais d’un code de suivi, puis le quitte.
   3. Le lendemain, ils saisissent votre URL dans leur barre d&#39;adresse, puis effectuent un achat.

   Le canal marketing Codes de suivi n&#39;obtiendrait pas le crédit Dernière touche pour cet achat. Au lieu de cela, il serait dirigé vers le canal marketing &quot;direct&quot;.
* **Différences** d&#39;expiration : Les canaux marketing présentent une expiration d’engagement visiteur de 30 jours, qu’un canal ait été touché ou non. Les codes de suivi ont une expiration en fonction du moment où la variable a été définie. Par exemple :
   1. Vous disposez d’une expiration d’engagement de visiteur de 30 jours et vous avez également configuré la dimension Code de suivi pour qu’elle expire après 30 jours.
   2. Un utilisateur arrive sur votre site par le biais d’un code de suivi. Ils parcourent le site, puis s&#39;en vont.
   3. Trois semaines plus tard, ils reviennent sans code de suivi ou canal marketing, puis repartent.
   4. Deux autres semaines plus tard (cinq semaines après leur première visite), ils reviennent sans code de suivi ou canal marketing, puis font un achat.
   L’utilisateur a finalement effectué un achat au-delà de 30 jours, mais n’a jamais été inactif pendant plus de 30 jours. Les recettes sont attribuées au canal marketing Codes de suivi, mais pas à la dimension autonome.
