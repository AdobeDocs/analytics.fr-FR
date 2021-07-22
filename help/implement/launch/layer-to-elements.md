---
title: Mise en correspondance des objets de couche de données avec les éléments de données
description: Configurez des balises à lire à partir de votre couche de données.
exl-id: b7594084-cb5f-408e-8a76-0a0815cc7553
source-git-commit: 5368e808a862a3e320f5d079433db96ab79b45c8
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 60%

---

# Mise en correspondance des objets de couche de données avec les éléments de données

Une fois que votre entreprise a établi et mis en oeuvre une couche de données sur votre site, vous pouvez mapper des objets de couche de données aux éléments de données au sein des balises .

>[!NOTE]
>Adobe Experience Platform Launch a été rebaptisé en tant que suite de technologies de collecte de données dans Experience Platform. Plusieurs modifications terminologiques ont par conséquent été apportées à la documentation du produit. Reportez-vous au [document](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) suivant pour consulter une référence consolidée des modifications terminologiques.

## Conditions préalables

[Créer une couche de données](../prepare/data-layer.md) : Assurez-vous qu’une couche de données existe sur votre site. Techniquement, vous pouvez mettre en correspondance n’importe quel objet JavaScript ou récupérer des éléments CSS directement à partir de la page, mais Adobe recommande cette pratique en dernier recours. Si la mise en page de votre site change, les sélecteurs CSS utilisés dans les balises ne fonctionnent plus, ce qui entraîne une perte de données.

## Utilisation de balises pour créer des éléments de données

[Les ](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=en) éléments de données sont des composants de l’interface utilisateur de collecte de données que vous pouvez utiliser dans l’ensemble de l’outil. Vous pouvez attribuer des valeurs de variable dans l’extension Adobe Analytics à l’aide d’éléments de données.

1. Accédez à [experience.adobe.com](https://experience.adobe.com) et connectez-vous lorsque vous y êtes invité.
1. Sélectionnez **[!UICONTROL Lancer / Collecte de données]**.
1. Cliquez sur **[!UICONTROL Aller à Launch / Collecte de données]**, puis sélectionnez **[!UICONTROL Balises]**.
1. Cliquez sur la propriété de balise de votre choix.
1. Cliquez sur l’onglet **[!UICONTROL Éléments de données]**, puis sur **[!UICONTROL Ajouter un élément de données]**.

   ![Création d’un élément de données](assets/createelement.png)

1. Entrez un nom pour votre élément de données. Il peut s’agir d’un libellé simple qui correspond à une variable JavaScript dans la couche de données dont vous souhaitez effectuer le suivi.
1. Dans la liste déroulante **[!UICONTROL Extension]**, sélectionnez **[!UICONTROL Core]**.
1. Dans la liste déroulante **[!UICONTROL Type d’élément de données]**, sélectionnez **[!UICONTROL Variable JavaScript]**. Un champ de texte s’affiche à droite et vous permet de saisir la variable JavaScript à faire correspondre à cet élément de données.
1. Entrez la variable JavaScript souhaitée, généralement dans la couche de données. Par exemple, si la couche de données de votre entreprise correspond étroitement à la pratique recommandée par Adobe, une valeur `digitalData.page.pageInfo.pageName` peut être indiquée. Vous pouvez utiliser la console de votre navigateur pour valider la syntaxe et les valeurs des variables JavaScript.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Étapes suivantes

[Mise en correspondance d’éléments de données aux variables Analytics](elements-to-variable.md) : Affectez des éléments de données à des variables Analytics afin de les utiliser comme dimensions dans Analysis Workspace.
