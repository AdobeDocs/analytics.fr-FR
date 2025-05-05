---
description: Les règles de traitement simplifient la collecte de données et gèrent le contenu lorsqu’il est envoyé pour la création de rapports.
subtopic: Processing rules
title: Règles de traitement - Aperçu
feature: Processing Rules
role: Admin
exl-id: 0244aba2-4345-463a-8528-d4dcd2f872ff
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 97%

---

# Règles de traitement - Aperçu

Les règles de traitement simplifient la collecte de données et gèrent le contenu lorsqu’il est envoyé pour la création de rapports. Ces règles fournissent une interface pour effectuer les opérations suivantes, ce qui se traduit par une interaction plus aisée avec les groupes informatiques et les développeurs Web :

* Définir un événement sur la page d’aperçu du produit.
* Renseigner un paramètre de chaîne de requête dans une campagne.
* Concaténer une catégorie et un nom de page dans une variable prop afin de faciliter la création de rapports.
* Copier une variable eVar dans une variable prop pour visualiser les chemins.
* Corriger les sections de site mal orthographiées.
* Extraire des termes de recherche internes ou un identifiant de campagne d’une requête de chaîne pour les placer dans une variable eVar.



>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Présentation des règles de traitement](https://video.tv.adobe.com/v/327635/?quality=12&learn=on&captions=fre_fr){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


## Autorisations des règles de traitement {#section_8A4846688050453784DAE4D89355169A}

Les administrateurs disposent des droits d’utiliser les règles de traitement **par défaut**. Les administrateurs peuvent également octroyer ces droits à des utilisateurs qui ne sont pas administrateurs à l’aide de l’interface des outils d’administration. Pour obtenir des instructions, voir [].

![Règles de traitement](assets/processing-rules.png)

## Utilisation de données contextuelles afin de simplifier la collecte de données {#section_09EEA03612D24C15839631AA9E9668D8}

Les variables de données contextuelles représentent un type de variable disponible uniquement pour les règles de traitement. Pour utiliser les variables de données contextuelles, des paires de données clé/valeur sont envoyées par votre implémentation et les règles de traitement sont utilisées pour capturer ces valeurs dans des variables Analytics standard. De ce fait, les programmeurs ne doivent plus obligatoirement connaître la valeur contenue dans une variable prop et/ou eVar.

```js
s.contextData['author'] = "Robert Munch";
s.contextData['section'] = "Books";
s.contextData['genre'] = "Youth";
```

Une fois définies dans le code, vous pouvez définir des règles de traitement pour affecter des valeurs à des variables. Par exemple :

1. Mappez `author` à `eVar2`.
2. Mappez `section` à `prop1` et `eVar3`.
3. Si `author` et `section` existent, définissez `event5`.

Voir [contextData](/help/implement/vars/page-vars/contextdata.md) dans le guide de l’utilisateur destiné à l’implémentation pour plus d’informations.

## Utiliser des règles de traitement pour transformer des données d’accès et déclencher des événements {#section_8284E72E999244E091CD7FB1A22342B6}

Les règles de traitement peuvent contrôler les valeurs entrantes afin de transformer les fautes de frappe courantes et définir des événements sur la base de données reprises dans un rapport. Les variables prop peuvent être copiées sur des eVars. Les valeurs peuvent être concaténées et des événements peuvent être définis.

## Utilisation des variables de données contextuelles dans les rapports {#section_BD098BC503024A0B8703596628071134}

Lorsque les variables de données contextuelles ont été définies dans votre implémentation, elles doivent être copiées dans des variables telles que des eVar pour être utilisées dans les rapports.

Voir [Copier une variable de données contextuelles dans une eVar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md) et [Définir un événement à l’aide d’une variable de données contextuelles](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md) pour plus d’informations.

## Limites connues

**Utilisation de carats (^) dans les règles de traitement.** Si vous souhaitez utiliser des carats dans les règles de traitement comme délimiteurs ou à d’autres fins, chaque carat doit être représenté par deux carats. Par exemple, représentez un carat simple par ^^, un carat double par ^^^^, etc.