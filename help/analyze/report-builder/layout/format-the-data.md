---
description: Outre les options de mise en forme de cellules standard disponibles par le biais du menu Format > Cellules (Ctrl+1) d’Excel, vous pouvez appliquer une mise en forme limitée à des plages de cellules à l’aide du Créateur de rapports. Ces options dépendent, en fait, de la mesure choisie.
title: Mise en forme de la date
topic: Report builder
uuid: 5211db30-07b3-4413-97c3-e40e6ff223cd
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Mise en forme de la date

Outre les options de mise en forme de cellules standard disponibles par le biais du menu Format > Cellules (Ctrl+1) d’Excel, vous pouvez appliquer une mise en forme limitée à des plages de cellules à l’aide du Créateur de rapports. Ces options dépendent, en fait, de la mesure choisie.

Après avoir [ajouté des dimensions](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) à la grille Libellés de lignes, cliquez sur **[!UICONTROL Format]**.

In the **[!UICONTROL Format]** menu, click **[!UICONTROL Custom Format]** to apply customized formats for dates similar to the prepend and postpend feature. Vous pouvez, par exemple, entrer du texte qui s’affiche toujours après la date (tel que « av. J.-C. », « apr. J.-C. », etc.). Vous pouvez ajouter du texte avant la date, par exemple [!UICONTROL Start Date] et [!UICONTROL Start and End Date]. Vous pouvez, en outre, créer une expression de date personnalisée à partir des abréviations jour, mois et année, et utiliser un séparateur personnalisé entre les différentes parties de la date. Tous les formats de date doivent être constitués de trois abréviations, placées entre crochets.

The following table describes how you can use date abbreviations in the [!UICONTROL Custom Format] field:

| Abréviation | Signification | Exemple   en utilisant, comme exemple, le mercredi 14 mars 2012 |
|--- |--- |--- |
| jj/MM/aaa | Date numérique complète | 03/14/2012 |
| M | Numéro du mois | 3 |
| MM | Numéro du mois avec un caractère 0 de remplissage pour les mois &lt; 10 | 03 |
| MMM | Forme abrégée du nom du mois | Mar |
| MMMM | Forme longue du nom du mois | Mars |
| J | Nom de la date au format long | Mercredi, 14 mars 2012 |
| j | Numéro du jour | 14 |
| jj | Numéro du jour avec un caractère 0 de remplissage pour les jours &lt; 10 | 01 - 09 |
| jjj | Forme abrégée du nom du jour | Mer |
| jjjj | Forme longue du nom du jour | Mercredi |
| aa | Année en 2 chiffres | 10 |
| aaaa | Année en 4 chiffres | 2012 |
