---
description: Outre les options de mise en forme de cellules standard disponibles par le biais du menu Format > Cellules (Ctrl+1) d’Excel, vous pouvez appliquer une mise en forme limitée à des plages de cellules à l’aide du Créateur de rapports. Ces options dépendent, en fait, de la mesure choisie.
seo-description: Outre les options de mise en forme de cellules standard disponibles par le biais du menu Format > Cellules (Ctrl+1) d’Excel, vous pouvez appliquer une mise en forme limitée à des plages de cellules à l’aide du Créateur de rapports. Ces options dépendent, en fait, de la mesure choisie.
seo-title: Mettre en forme la date
solution: Analytics
title: Mettre en forme la date
topic: Créateur de rapports
uuid: 5211 db 30-07 b 3-4413-97 c 3-e 40 e 6 ff 223 cd
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Mettre en forme la date

Outre les options de mise en forme de cellules standard disponibles par le biais du menu Format &gt; Cellules (Ctrl+1) d’Excel, vous pouvez appliquer une mise en forme limitée à des plages de cellules à l’aide du Créateur de rapports. Ces options dépendent, en fait, de la mesure choisie.

After you [add dimensions](../../../analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md#task_E3F520C020F64C5A96DC5C96FEF71FC4) to the Row Labels grid, click **[!UICONTROL Format]**.

Dans le menu **[!UICONTROL Format]**, cliquez sur **Format personnalisé]pour appliquer des formats personnalisés aux dates ; de la même manière que la fonction d’ajout de texte en préfixe ou suffixe.[!UICONTROL ** Vous pouvez, par exemple, entrer du texte qui s’affiche toujours après la date (tel que « av. J.-C. », « apr. J.-C. », etc.). Il vous est également possible d’ajouter du texte avant la date ; par exemple, [!UICONTROL Date de début] et [!UICONTROL Date de début et de fin]. Vous pouvez, en outre, créer une expression de date personnalisée à partir des abréviations jour, mois et année, et utiliser un séparateur personnalisé entre les différentes parties de la date. Tous les formats de date doivent être constitués de trois abréviations, placées entre crochets.

Le tableau suivant décrit l’utilisation des abréviations de date dans le champ [!UICONTROL Format personnalisé] :

| Abréviation | Signification | Exemple   en utilisant, comme exemple, le mercredi 14 mars 2012 |
|--- |--- |--- |
| MM/dd/yyy | Date numérique complète | 03/14/2012 |
| M | Numéro du mois | 3 |
| MM | Numéro du mois avec un caractère 0 de remplissage pour les mois &lt; 10 | 03 |
| MMM | Forme abrégée du nom du mois | Mar |
| MMMM | Forme longue du nom du mois | Mars |
| D | Nom de la date au format long | Mercredi, 14 mars 2012 |
| d | Numéro du jour | 14 |
| dd | Numéro du jour avec un caractère 0 de remplissage pour les jours &lt; 10 | 01 - 09 |
| ddd | Forme abrégée du nom du jour | Mer |
| dddd | Forme longue du nom du jour | Mercredi |
| yy | Année en 2 chiffres | 10 |
| yyyy | Année en 4 chiffres | 2012 |