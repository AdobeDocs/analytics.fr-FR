---
description: Le panneau de configuration d’Activity Map vous permet de modifier les paramètres et les propriétés de tous les types de visualisations des superpositions.
title: Paramétrage d’Activity Map
uuid: 42a0309e-3efc-4506-989b-09b6fe419423
feature: Activity Map
role: User, Admin
exl-id: 65c9c690-81e0-4f0f-989d-586d247ed380
source-git-commit: 78cfb1f3c4d45fc983982a8da11b66f2b2c9ecbc
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 50%

---

# Paramétrage d’Activity Map

Le panneau de configuration d’Activity Map vous permet de modifier les paramètres et les propriétés de tous les types de visualisations des superpositions.

Accédez au panneau de configuration d’Activity Map en cliquant sur l’icône de l’engrenage dans la barre d’outils d’Activity Map.

## Paramètres généraux {#section_697A12F099494D699A4BF498598178C5}

![](assets/settings_other.png)

| Paramètre | Description |
| --- | --- |
| **[!UICONTROL Sociétés]** | Sélectionnez la société de connexion concernée. |
| **[!UICONTROL Suite de rapports]** | La liste des suites de rapports auxquelles vous avez accès ne se limite plus aux seules suites de rapports définies dans une balise de page web. Vous pouvez désormais remplacer la suite de rapports sélectionnée (correspondant à l’une des balises de la page) par une autre suite de rapports. Il n’est pas nécessaire que celle-ci soit liée à une balise sur la page. Si vous modifiez la suite de rapports sélectionnée dans les paramètres du Activity Map, le processus d’enregistrement entraîne l’actualisation de tous les rapports Analytics affectés.<br>**Important**: [!UICONTROL Suites de rapports virtuelles] ne sont pas compatibles avec [!UICONTROL Mode réel], uniquement avec [!UICONTROL Mode standard]. Si vous êtes dans [!UICONTROL Mode réel] pour une suite de rapports standard, mais sélectionnez une [!UICONTROL Suite de rapports virtuelle] dans cette boîte de dialogue, une fois que vous avez cliqué sur **[!UICONTROL OK]** Le mode standard s’affiche alors. En outre, la commande Calendrier est réinitialisée pour correspondre au type de calendrier de la suite de rapports (grégorien, vente au détail, personnalisé..). |
| **[!UICONTROL Nom de la page]** | Page à laquelle ces paramètres s’appliquent. |
| **[!UICONTROL Langue]** | La sélection correspond aux langues proposées dans Adobe Analytics. |
| **[!UICONTROL Étiqueter les superpositions avec]** | <ul><li>**[!UICONTROL Aucune étiquette]** : uniquement applicable pour la superposition en dégradé. Dans ce cas, la couleur de la superposition indique le classement du lien.</li><li>**[!UICONTROL Valeur]** : valeur brute totale pour ce lien.</li><li>**[!UICONTROL Pourcentage]** : pourcentage de la mesure pour ce lien par rapport à la mesure totale pour la page.</li><li>**[!UICONTROL Classement]** : classement de ce lien parmi tous les liens présents sur la page rendue.</li></ul> |
| **[!UICONTROL Taille de police de l’étiquette]** | Vous permet d’augmenter ou de réduire la taille de police de l’étiquette de la superposition à l’aide d’un curseur pour une meilleure lisibilité. |
| **[!UICONTROL Couleur du dégradé/de la bulle]** | Pour afficher les classements des liens de superposition pour les visualisations des superpositions en dégradé ou bulle, sélectionnez l’une des différentes couleurs . |
| **[!UICONTROL Couleur du dégradé basée sur]** | <ul><li>**[!UICONTROL 30 premiers classements]** : l’intensité des couleurs est normalisée pour les 30 premières valeurs.</li><li>**[!UICONTROL Valeur de mesure absolue]** : l’intensité des couleurs dépend de la valeur de mesure absolue.</li></ul> |
| **[!UICONTROL Transparence du dégradé]** | Sélectionnez le niveau de transparence pour les superpositions en dégradé. Ce paramètre n’a aucune incidence sur la variable [!UICONTROL Bulle] superpositions. |

## Paramètres standard {#section_24DB95376E1A448494ECF3F57743FC19}

Ces paramètres s’appliquent à la superposition en mode standard.

![](assets/settings_standard.png)

| Paramètre | Description |
| --- | --- |
| **[!UICONTROL Filtrage des données dynamiques]** | Cette liste déroulante vous permet d’afficher des superpositions pour<ul><li>(par défaut) Tous les liens de la page</li><li>Nombre de liens de classement du haut (le plus élevé) ou du bas (le plus faible) sur la page, où # peut être un choix de 1, 10, 50 ou 100.</li></ul> |
| **[!UICONTROL Masquer les superpositions pour les liens qui n’ont reçu aucune visite]**. | Case à cocher qui active la visibilité des superpositions pour les liens qui ne contiennent aucune donnée.<ul><li>(par défaut) Si la case est cochée, aucun recouvrement n’est affiché lorsqu’un lien ne contient aucune donnée de lien Activity Map.</li><li>Si la case est décochée, si un lien ne contient aucune donnée de lien Activity Map, une superposition s’affiche et le libellé est &quot;-&quot;, ce qui signifie N/A (non applicable). |

## Paramètres en direct {#section_D30F6E62FB5D404090B588F396A460AF}

Ces paramètres s’appliquent à la superposition en mode réel.

![](assets/settings_live.png)

| Paramètre | Description |
|---|---|
| **[!UICONTROL Afficher en haut]** | Pour afficher la variable **[!UICONTROL Gagnants]** ou **[!UICONTROL Perdants]** (ou les deux) sous forme de superpositions, sélectionnez le nombre de liens. |
| **[!UICONTROL Exclure le bas (%)]** | Sélectionnez cette option pour éliminer les liens des gagnants et des perdants avec des données éparses. Filtrez les pourcentages inférieurs des changements de liens pour afficher uniquement les liens avec suffisamment de données pour présenter des gains ou des pertes significatives. Le pourcentage est calculé en fonction du nombre de liens sur la page. Par exemple, le filtrage des 10 % inférieurs d’une liste de 200 liens filtrerait les 20 liens inférieurs. |
| **[!UICONTROL Mettre à jour les données automatiquement]** | Permet de décider si les données Analytics affichées dans l’interface sont automatiquement mises à jour lorsqu’une nouvelle période est calculée. |
| **[!UICONTROL Période de mise à jour automatique]** | Actualise la page web à chaque nouvelle récupération des données afin que les liens de la page soient mieux synchronisés avec les données collectées. |
