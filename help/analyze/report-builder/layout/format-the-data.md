---
description: Découvrez comment appliquer une mise en forme standard et limitée à des plages de cellules.
title: Comment formater la date en Report Builder
uuid: 5211db30-07b3-4413-97c3-e40e6ff223cd
feature: Report Builder
role: User, Admin
exl-id: 9b251b09-9156-40b5-8e1f-fb6594a25c26
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 81%

---

# Mise en forme de la date

Outre les options de mise en forme de cellules standard disponibles via la fonction Format > Cellules (Ctrl+1) d’Excel, vous pouvez appliquer une mise en forme limitée à des plages de cellules avec Report Builder. Ces options dépendent, en fait, de la mesure choisie.

Après avoir [ajouté des dimensions](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) à la grille Libellés de lignes, cliquez sur **[!UICONTROL Format]**.

Dans le menu **[!UICONTROL Format]**, cliquez sur **[!UICONTROL Format personnalisé]** pour appliquer des formats personnalisés aux dates ; de la même manière que la fonction d’ajout de texte en préfixe ou suffixe. Vous pouvez, par exemple, entrer du texte qui s’affiche toujours après la date (tel que « av. J.-C. », « apr. J.-C. », etc.). Il vous est également possible d’ajouter du texte avant la date ; par exemple, [!UICONTROL Date de début] et [!UICONTROL Date de début et de fin]. Vous pouvez, en outre, créer une expression de date personnalisée à partir des abréviations jour, mois et année, et utiliser un séparateur personnalisé entre les différentes parties de la date. Tous les formats de date doivent être constitués de trois abréviations, placées entre crochets.

Le tableau suivant décrit l’utilisation des abréviations de date dans le champ [!UICONTROL Format personnalisé] :

| Abréviation | Signification | Exemple   utilisant le mercredi 14 mars 2012 |
|--- |--- |--- |
| jj/MM/aaa | Date numérique complète | 03/14/2012 |
| M | Numéro du mois | 3 |
| MM | Numéro du mois avec un caractère 0 de remplissage pour les mois &lt; 10 | 03 |
| MMM | Forme abrégée du nom du mois | Mar |
| MMMM | Forme longue du nom du mois | Mars |
| J | Nom de la date au format long | jeudi 14 mars 2012 |
| j | Numéro du jour | 14 |
| jj | Numéro du jour avec un caractère 0 de remplissage pour les jours &lt; 10 | 01 - 09 |
| jjj | Forme abrégée du nom du jour | Mer |
| jjjj | Forme longue du nom du jour | Mercredi |
| aa | Année en 2 chiffres | 10 |
| aaaa | Année en 4 chiffres | 2012 |
