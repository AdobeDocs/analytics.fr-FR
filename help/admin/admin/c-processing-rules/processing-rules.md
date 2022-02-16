---
description: Les règles de traitement simplifient la collecte de données et gèrent le contenu lorsqu’il est envoyé pour la création de rapports.
subtopic: Processing rules
title: Règles de traitement - Aperçu
feature: Processing Rules
exl-id: 0244aba2-4345-463a-8528-d4dcd2f872ff
source-git-commit: 71b3b1937e7fa272f0497008e8e510204bbb4418
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 68%

---

# Règles de traitement - Aperçu

Les règles de traitement simplifient la collecte de données et gèrent le contenu lorsqu’il est envoyé pour la création de rapports. Ces règles fournissent une interface pour effectuer les opérations suivantes, ce qui se traduit par une interaction plus aisée avec les groupes informatiques et les développeurs Web :

* Définir un événement sur la page d’aperçu du produit.
* Renseigner un paramètre de chaîne de requête dans une campagne.
* Concaténer une catégorie et un nom de page dans une variable prop afin de faciliter la création de rapports.
* Copier une variable eVar dans une variable prop pour visualiser les chemins.
* Corriger les sections de site mal orthographiées.
* Extraire des termes de recherche internes ou un identifiant de campagne d’une requête de chaîne pour les placer dans une variable eVar.

>[!VIDEO](https://video.tv.adobe.com/v/26124/?quality=12&learn=on)

## Autorisations des règles de traitement {#section_8A4846688050453784DAE4D89355169A}

Les administrateurs ont les droits d’utiliser les règles de traitement **par défaut**. Les administrateurs peuvent également octroyer ces droits à des utilisateurs qui ne sont pas administrateurs à l’aide de l’interface des outils d’administration. Pour obtenir des instructions, voir []

![](assets/processing-rules.png)

>[!IMPORTANT]
>
>Les règles de traitement affectant en permanence les données d’Analytics, Adobe recommande vivement que les administrateurs de règles de traitement reçoivent une formation de certification dans Adobe Analytics et connaissent toutes les sources de données de vos suites de rapports (sites web standard, sites mobiles, applications mobiles, API d’insertion de données, etc.). La connaissance des variables de données contextuelles et des variables standard renseignées sur différentes plateformes permettra de prévenir la suppression ou la modification accidentelle des données.

## Utilisation de données contextuelles afin de simplifier la collecte des données {#section_09EEA03612D24C15839631AA9E9668D8}

Les variables de données contextuelles sont un type de variable disponible uniquement pour les règles de traitement. Pour utiliser les variables de données contextuelles, des paires de données clé/valeur sont envoyées par votre implémentation et les règles de traitement sont utilisées pour capturer ces valeurs dans des variables Analytics standard. De ce fait, les programmeurs ne doivent plus obligatoirement connaître la valeur contenue dans une variable prop et/ou eVar.

```js
s.contextData['author'] = "Robert Munch";
s.contextData['section'] = "Books";
s.contextData['genre'] = "Youth";
```

Une fois défini dans le code, vous pouvez définir des règles de traitement pour affecter des valeurs à des variables. Par exemple :

1. Carte `author` to `eVar2`
2. Carte `section` to `prop1` et `eVar3`
3. If `author` et `section` existent, défini `event5`

Voir [contextData](/help/implement/vars/page-vars/contextdata.md) pour plus d’informations.

## Utiliser des règles de traitement pour transformer des données d’accès et des événements de déclenchement {#section_8284E72E999244E091CD7FB1A22342B6}

Les règles de traitement peuvent contrôler les valeurs entrantes afin de transformer les fautes de frappe courantes et définir des événements sur la base de données reprises dans un rapport. Les variables prop peuvent être copiées sur des eVars. Les valeurs peuvent être concaténées et des événements peuvent être définis.

## Utilisation des variables de données contextuelles dans les rapports {#section_BD098BC503024A0B8703596628071134}

Lorsque les variables de données contextuelles ont été définies dans votre implémentation, elles doivent être copiées dans des variables telles que des eVar pour être utilisées dans les rapports.

Voir [Copier une variable de données contextuelles dans un eVar](processing-rules-examples/processing-rules-copy-context-data.md) et [Définition d’un événement à l’aide d’une variable de données contextuelles](processing-rules-examples/processing-rules-copy-context-data-event.md) pour plus d’informations.
