---
description: Vous pouvez préciser une période complexe en créant une expression personnalisée.
title: Expressions de dates personnalisées - Aperçu
topic: Report builder
uuid: 7d6d7c03-a3f4-4dec-8343-de2e6478bf06
translation-type: tm+mt
source-git-commit: fa1b0b7fb24d0cd2c205fbbb6a1e526f243531f8

---


# Expressions de dates personnalisées - Aperçu

Vous pouvez préciser une période complexe en créant une expression personnalisée.

Nous vous recommandons de consulter un calendrier lors de la création d’expressions afin de spécifier correctement le nombre de semaines et de jours. Excel est doté de plusieurs fonctions intégrées qui permettent de calculer le nombre de jours, de jours ouvrables, de mois et d’années entre les dates. Vous pouvez appliquer ces fonctions dans des formules afin de calculer d’autres intervalles, tels que des semaines et des trimestres.

**Pour activer des expressions personnalisées**

Voici un exemple d&#39;utilisation **[!UICONTROL Rolling Dates]**.

1. Sur la [!UICONTROL Request Wizard: Step 1], au lieu d’utiliser **[!UICONTROL Preset Dates]**, sélectionnez **[!UICONTROL Rolling Dates]**.

   ![](assets/rolldates1.png)

1. Passez à hebdomadaire, mensuel, trimestriel ou annuel variable. Remarquez comment les options ci-dessous changent.
1. Pour plus d’options de personnalisation, cliquez sur **[!UICONTROL Show Advanced Options]**.

   ![](assets/rolldates2.png)

1. Par exemple, si vous modifiez les dates ci-dessus en mois variable, du premier jour il y a trois mois au premier jour du mois, les dates dans la partie Options avancées se mettent à jour pour refléter ce qui suit :

   ![](assets/rolldatesfor3.png)

1. Activer **[!UICONTROL Customize Expression]**. En sélectionnant des options sous **[!UICONTROL Rolling Dates]**, vous pouvez facilement voir la syntaxe des expressions de date personnalisées.

   ![](assets/rolldatesfor5.png)

   Vous pouvez utiliser les options avancées pour combiner et faire correspondre des expressions de date personnalisées. Par exemple, si vous souhaitez afficher les données du premier de l’année jusqu’à la fin du dernier mois complet, vous pouvez saisir les informations suivantes : `From: cy``To: cm-1d`. Dans l’assistant, ces dates s’affichent sous la forme 1/1/2020-1/31/2020.
