---
title: Mise en correspondance des éléments de données de lancement avec les variables Analytics
description: Affectez des éléments de données à des variables Analytics afin que vous puissiez les utiliser comme dimensions dans  espace de travail .
translation-type: tm+mt
source-git-commit: 6937d47e3cf980a21bec680cdbd2931a4a368221

---


# Mise en correspondance des éléments de données de lancement avec les variables Analytics

Une fois que vous disposez d’un référentiel des éléments de données dans le lancement d’Adobe Experience Platform, vous pouvez les affecter aux dimensions Analytics.

## Conditions préalables

[Mappez les objets de couche de données aux éléments](layer-to-elements.md)de données : Assurez-vous de bien comprendre les éléments de données dans Lancement et que vous devez en utiliser plusieurs.

[Créez un de conception de solution](../prepare/solution-design.md): Un de conception de solution est essentiel pour rester organisé. Le de conception de votre solution simplifie l’affectation des éléments de données aux variables Analytics.

## Affectation d’éléments de données à des variables Analytics

La publication d’une bibliothèque dans Lancer après avoir suivi ces étapes vous permet d’utiliser des dimensions personnalisées dans  espace de travail . Vous pouvez définir des variables Analytics globalement ou dans des règles individuelles.

### Définition de variables globales

Les variables globales sont idéales lorsque vous souhaitez définir des valeurs de variable sur toutes les pages sur lesquelles votre élément de données existe.

1. Accédez à [Adobe Experience Platform Launch](https://launch.adobe.com) et connectez-vous si vous y êtes invité.
1. Cliquez sur la propriété Launch de votre choix.
1. Cliquez sur [!UICONTROL Extensions tab], puis sur [!UICONTROL Configure] sous l’extension Adobe Analytics.
1. Cliquez sur l’ [!UICONTROL Global variables] accordéon, qui révèle l’interface permettant d’affecter des variables globales.

### Définition de variables dans les règles

Les variables définies dans les règles sont idéales lorsque vous ne souhaitez pas que les variables soient définies sur chaque page. Vous définissez les critères dans la règle. See [Rules](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/rules.html) in the Adobe Experience Platform Launch user guide.

1. Accédez à [Adobe Experience Platform Launch](https://launch.adobe.com) et connectez-vous si vous y êtes invité.
1. Cliquez sur la propriété Launch de votre choix.
1. Cliquez sur l’ [!UICONTROL Rules] onglet, puis sur la règle souhaitée (ou créez-en une).
1. Cliquez sur le [!UICONTROL Add] bouton sous [!UICONTROL Actions].
1. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to Set Variables.
1. Cliquez sur l’icône d’élément ![de](assets/data-element.png) données à droite de la variable Analytics souhaitée. Le de conception de [solution de votre entreprise](../prepare/solution-design.md) détermine la variable Analytics à utiliser.
1. Sélectionnez l’élément de données souhaité dans la fenêtre modale. Cliquez sur [!UICONTROL Select].
1. Le nom de l’élément de données est ajouté au champ de texte entouré de `%` signes. Par exemple, si vous avez nommé votre élément de données &quot;Nom de page&quot;, la chaîne s’affichera `%Page name%` lors de l’affectation d’un élément de données à une variable.

> [!TIP] Vous pouvez concaténer des éléments de données dans la même variable. Par exemple, si vous disposez d’un élément de données &quot;Nom d’hôte&quot; et d’un élément de données &quot;Nom de chemin&quot;, vous pouvez combiner les deux dans une variable unique à l’aide de `%Hostname%%Pathname%`.

## Étapes suivantes

[Variables](../vars/page-vars/page-variables.md)de page : Découvrez les variables de niveau page que vous pouvez utiliser dans votre implémentation pour tirer le meilleur parti des dimensions dans   Workspace de.

[Variables](../vars/config-vars/configuration-variables.md)de configuration : Découvrez les variables de configuration que vous pouvez utiliser dans votre implémentation pour déverrouiller d’autres fonctionnalités d’Adobe Analytics.
