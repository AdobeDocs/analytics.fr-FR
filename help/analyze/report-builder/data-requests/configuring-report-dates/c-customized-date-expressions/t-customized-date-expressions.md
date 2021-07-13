---
description: Vous pouvez préciser une période complexe en créant une expression personnalisée.
title: Expressions de dates personnalisées - Aperçu
uuid: 7d6d7c03-a3f4-4dec-8343-de2e6478bf06
feature: Report Builder
role: User, Admin
exl-id: b3bdc07e-5c2d-4be3-86c9-b4b7380be0f6
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 30%

---

# Expressions de dates personnalisées - Aperçu

Vous pouvez préciser une période complexe en créant une expression personnalisée.

Nous vous recommandons de vous référer à un calendrier lors de la création d’expressions afin de préciser correctement le nombre de semaines et de jours. Excel est doté de plusieurs fonctions intégrées qui permettent de calculer le nombre de jours, de jours ouvrables, de mois et d’années entre les dates. Vous pouvez appliquer ces fonctions dans des formules afin de calculer d’autres intervalles, tels que des semaines et des trimestres.

**Pour activer des expressions personnalisées**

Il s’agit d’un exemple utilisant **[!UICONTROL Dates roulantes]**.

1. Dans l’ [!UICONTROL Assistant Requête : Étape 1], au lieu d’utiliser **[!UICONTROL Préconfigurer les dates]**, sélectionnez **[!UICONTROL Dates roulantes]**.

   ![](assets/rolldates1.png)

1. Passez à une version variable hebdomadaire, mensuelle, trimestrielle ou annuelle. Notez comment les options ci-dessous changent.
1. Pour plus d’options de personnalisation, cliquez sur **[!UICONTROL Afficher les options avancées]**.

   ![](assets/rolldates2.png)

1. Par exemple, si vous modifiez les dates ci-dessus pour qu’elles soient mensuelles roulantes depuis le premier jour du mois, il y a trois mois, jusqu’au premier jour du mois, les dates de la partie Options avancées se mettent à jour pour refléter ce qui suit :

   ![](assets/rolldatesfor3.png)

1. Activez **[!UICONTROL Personnaliser l’expression]**. En sélectionnant des options sous **[!UICONTROL Dates roulantes]**, vous pouvez facilement voir la syntaxe des expressions de date personnalisées.

   ![](assets/rolldatesfor5.png)

   Vous pouvez utiliser les options avancées pour mélanger et faire correspondre des expressions de date personnalisées. Par exemple, si vous souhaitez afficher les données du premier de l’année jusqu’à la fin du dernier mois complet, vous pouvez saisir les informations suivantes : `From: cy` `To: cm-1d`. Dans l’assistant, ces dates s’affichent sous la forme 1/1/2020-1/31/2020.
