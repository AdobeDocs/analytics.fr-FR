---
title: Mappage des objets de couche de données aux éléments de données
description: Configurez Launch pour qu’il lise à partir de la couche de données.
translation-type: tm+mt
source-git-commit: 283fcd5832abe4c09caa332c2ebc3a22029e6707

---


# Mappage des objets de couche de données aux éléments de données

Une fois que votre entreprise a établi et mis en oeuvre une couche de données sur votre site, vous pouvez mapper des objets de couche de données aux éléments de données dans Lancement.

## Conditions préalables

[Créez une couche](../prepare/data-layer.md)de données : Assurez-vous qu’une couche de données existe sur votre site. Bien que vous puissiez techniquement mapper n’importe quel objet JavaScript ou filtrer les éléments CSS directement depuis la page, Adobe recommande cette pratique en dernier recours. Si la mise en page de votre site change, les sélecteurs CSS utilisés dans Launch ne fonctionnent plus, provoquant ainsi une perte de données.

## Utilisation d’Adobe Experience Platform Launch pour créer des éléments de données

[Les éléments](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/data-elements.html#create-a-data-element) de données sont des composants dans Lancement que vous pouvez utiliser dans l’ensemble de l’outil. Vous pouvez affecter des valeurs de variable dans l’extension Adobe Analytics à l’aide d’éléments de données.

1. Accédez à [Adobe Experience Platform Launch](https://launch.adobe.com) et connectez-vous si vous y êtes invité.
1. Cliquez sur la propriété Launch de votre choix.
1. Click the [!UICONTROL Data Elements] tab, then click [!UICONTROL Add Data Element].

   ![créer un élément de données](assets/createelement.png)

1. Entrez un nom pour votre élément de données. Il peut s’agir d’un libellé simple qui correspond à une variable JavaScript dans la couche de données dont vous souhaitez effectuer le suivi.
1. Dans la [!UICONTROL Extension] liste déroulante, sélectionnez [!UICONTROL Core].
1. Dans la [!UICONTROL Data Element Type] liste déroulante, sélectionnez [!UICONTROL JavaScript Variable]. Un champ de texte s’affiche à droite et vous permet de saisir la variable JavaScript à mapper à cet élément de données.
1. Entrez la variable JavaScript souhaitée, généralement dans la couche de données. Par exemple, si la couche de données de votre entreprise correspond étroitement à la pratique recommandée par Adobe, une valeur peut être `digitalData.page.pageInfo.pageName`. Vous pouvez utiliser la console de votre navigateur pour valider la syntaxe et les valeurs des variables JavaScript.
1. Cliquez sur [!UICONTROL Save].

## Étapes suivantes

[Mappez les éléments de données aux variables](elements-to-variable.md)Analytics : Affectez des éléments de données à des variables Analytics afin que vous puissiez les utiliser comme dimensions dans  espace de travail .
