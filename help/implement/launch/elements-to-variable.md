---
title: Mappage des éléments de données de balises aux variables Analytics
description: Attribuez des éléments de données à des variables Analytics afin de les utiliser comme dimensions dans Analysis Workspace.
feature: Tags
exl-id: 996c1204-3f8a-453e-8104-5e8e1279517c
role: Admin, Developer
TQID: https://experienceleague.adobe.com/-eif71BEIQnPRQWSaXK5Wb5WL0rTROwRDDxzbUNL98I
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 448
ht-degree: 96%

---

# Mappage des éléments de données de balises aux variables Analytics

Une fois que vous disposez d’un référentiel d’éléments de données de balises, vous pouvez les attribuer aux dimensions Analytics.

## Conditions préalables

[Mapper des objets de couche de données aux éléments de données](layer-to-elements.md) : assurez-vous de comprendre les éléments de données de balises et de disposer de plusieurs éléments pour travailler.

[Créer un document de conception de solution](../prepare/solution-design.md) : Un document de conception de solution est essentiel pour rester organisé. En suivant votre document de conception de solution, vous simplifiez l’affectation des éléments de données aux variables Analytics.

## Affectation d’éléments de données à des variables Analytics

La publication d’une bibliothèque de balises après le suivi de ces étapes vous permet d’utiliser des dimensions personnalisées dans Analysis Workspace. Vous pouvez définir des variables Analytics globalement ou dans des règles individuelles.

### Définition de variables globales

Les variables globales sont idéales lorsque vous souhaitez définir des valeurs de variable sur toutes les pages où se trouve votre élément de données.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Cliquez sur l’[!UICONTROL onglet Extensions], puis sur [!UICONTROL Configurer] sous l’extension Adobe Analytics.
1. Cliquez sur l’accordéon [!UICONTROL Variables globales], qui révèle l’interface permettant d’affecter des variables globales.

### Définition de variables dans les règles

Les variables définies dans les règles sont idéales lorsque vous ne souhaitez pas que les variables soient définies sur chaque page. Vous définissez les critères dans la règle. Consultez la section [Règles](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=fr) de la documentation sur les balises Adobe Experience Platform.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Cliquez sur l’onglet [!UICONTROL Règles], puis sur la règle de votre choix (ou créez-en une).
1. Cliquez sur le bouton [!UICONTROL Ajouter] sous [!UICONTROL Actions].
1. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics, et le [!UICONTROL Type d’action] sur Définir les variables.
1. Cliquez sur l’icône ![Élément de données](assets/data-element.png) à droite de la variable Analytics souhaitée. Le [document de conception de solution](../prepare/solution-design.md) de votre entreprise détermine la variable Analytics à utiliser.
1. Sélectionnez l’élément de données de votre choix dans la fenêtre modale. Cliquez sur [!UICONTROL Sélectionner].
1. Le nom de l’élément de données est ajouté au champ de texte entouré de signes `%`. Par exemple, si vous avez nommé votre élément de données « Nom de page », la chaîne `%Page name%` apparaît lors de l’affectation d’un élément de données à une variable.

>[!TIP]
>
>Vous pouvez concaténer des éléments de données dans la même variable. Par exemple, si vous disposez d’un élément de données « Nom d’hôte » et d’un élément de données « Nom de chemin », vous pouvez combiner les deux dans une variable unique à l’aide de `%Hostname%%Pathname%`.

## Étapes suivantes

[Variables de page](../vars/page-vars/page-variables.md) : Découvrez les variables de niveau page que vous pouvez utiliser dans votre implémentation pour tirer davantage parti des dimensions dans Analysis Workspace.

[Variables de configuration](../vars/config-vars/configuration-variables.md) : Découvrez les variables de configuration que vous pouvez utiliser dans votre implémentation pour déverrouiller d’autres fonctionnalités dans Adobe Analytics.
