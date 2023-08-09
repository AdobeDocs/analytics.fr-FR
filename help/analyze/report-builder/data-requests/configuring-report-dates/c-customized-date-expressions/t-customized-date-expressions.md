---
description: Vous pouvez préciser une période complexe en créant une expression personnalisée.
title: Expressions de dates personnalisées - Aperçu
uuid: 7d6d7c03-a3f4-4dec-8343-de2e6478bf06
feature: Report Builder
role: User, Admin
exl-id: b3bdc07e-5c2d-4be3-86c9-b4b7380be0f6
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 25%

---

# Expressions de dates personnalisées

Vous pouvez préciser une période complexe en créant une expression personnalisée.

Lorsque vous créez des expressions, reportez-vous à un calendrier pour définir correctement le nombre de semaines et de jours. Excel est doté de plusieurs fonctions intégrées qui permettent de calculer le nombre de jours, de jours ouvrables, de mois et d’années entre les dates. Vous pouvez appliquer ces fonctions dans des formules afin de calculer d’autres intervalles, tels que des semaines et des trimestres.

**Pour activer des expressions personnalisées**

L’exemple suivant montre comment activer une expression personnalisée pour **[!UICONTROL Dates roulantes]**.

1. Sur le [!UICONTROL Assistant Requête : Étape 1], au lieu d’utiliser **[!UICONTROL Préconfigurer les dates]**, sélectionnez **[!UICONTROL Dates roulantes]**.

   ![Capture d’écran montrant les dates roulantes sélectionnées.](assets/rolldates1.png)

1. Passez à une version variable hebdomadaire, mensuelle, trimestrielle ou annuelle. Notez comment les options ci-dessous changent.
1. Pour plus d’options de personnalisation, cliquez sur **[!UICONTROL Afficher les options avancées]**.

   ![Capture d’écran mettant en surbrillance les options d’affichage avancées.](assets/rolldates2.png)

1. Par exemple, si vous modifiez les dates ci-dessus pour qu’elles soient mensuelles roulantes depuis le premier jour du mois, il y a trois mois, jusqu’au premier jour du mois, les dates de la partie Options avancées se mettent à jour pour refléter ce qui suit :

   ![Capture d&#39;écran montrant les dates roulantes du premier jour du mois il y a trois mois au premier jour du mois.](assets/rolldatesfor3.png)

1. Activer **[!UICONTROL Expression personnalisée]**. En sélectionnant les options sous **[!UICONTROL Dates roulantes]**, vous pouvez facilement voir la syntaxe des expressions de date personnalisées.

   ![Capture d’écran montrant l’option Personnaliser l’expression sélectionnée.](assets/rolldatesfor5.png)

   Vous pouvez utiliser les options avancées pour mélanger et faire correspondre des expressions de date personnalisées. Par exemple, si vous souhaitez afficher les données du premier de l’année jusqu’à la fin du dernier mois complet, vous pouvez saisir les informations suivantes : `From: cy` `To: cm-1d`. Dans l’assistant, ces dates s’affichent sous la forme 1/1/2020-1/31/2020.
