---
description: Le panneau de configuration d’Activity Map vous permet de modifier les paramètres et les propriétés de tous les types de visualisations des superpositions.
title: Paramétrage d’Activity Map
uuid: 42a0309e-3efc-4506-989b-09b6fe419423
feature: Activity Map
role: Business Practitioner, Administrator
exl-id: 65c9c690-81e0-4f0f-989d-586d247ed380
translation-type: tm+mt
source-git-commit: d4296a721e01e37c57a8fb44b67599a3cc9e4758
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 60%

---

# Paramétrage d’Activity Map

Le panneau de configuration d’Activity Map vous permet de modifier les paramètres et les propriétés de tous les types de visualisations des superpositions.

Accédez au panneau de configuration d’Activity Map en cliquant sur l’icône de l’engrenage dans la barre d’outils d’Activity Map.

## Paramètres généraux {#section_697A12F099494D699A4BF498598178C5}

![](assets/settings_other.png)

| Paramètre | Description |
| --- | --- |
| **[!UICONTROL Sociétés]** | Sélectionnez la société de connexion appropriée. |
| **[!UICONTROL Suite de rapports]** | La liste des suites de rapports auxquelles vous avez accès ne se limite plus aux seules suites de rapports définies dans une balise de page web. Vous pouvez désormais remplacer la suite de rapports sélectionnée (correspondant à l’une des balises de la page) par une autre suite de rapports. Il n’est pas nécessaire que celle-ci soit liée à une balise sur la page. Si vous modifiez la suite de rapports sélectionnée dans les paramètres du Activity Map, le processus Enregistrer actualise tous les rapports Analytics concernés.<br>**Important** :  [!UICONTROL Les suites de rapports virtuelles ] ne sont pas compatibles avec le mode réel, mais uniquement avec le mode standard. Si vous êtes en [!UICONTROL mode réel] pour une suite de rapports standard, mais que vous sélectionnez une [!UICONTROL suite de rapports virtuelle] dans cette boîte de dialogue, une fois que vous avez cliqué sur **[!UICONTROL OK]** ici, le mode standard s’affiche. En outre, le contrôle Calendar est réinitialisé pour correspondre au type de calendrier de la suite de rapports (grégorien, vente au détail, personnalisé..). |
| **[!UICONTROL Nom de la page]** | Page à laquelle ces paramètres s’appliquent. |
| **[!UICONTROL Langue]** | La sélection correspond aux langues proposées dans Adobe Analytics. |
| **[!UICONTROL Étiqueter les superpositions avec]** | <ul><li>**[!UICONTROL Aucune étiquette]** : uniquement applicable pour la superposition en dégradé. Dans ce cas, la couleur de l’incrustation donne une idée du classement du lien.</li><li>**[!UICONTROL Valeur]** : valeur brute totale pour ce lien.</li><li>**[!UICONTROL Pourcentage]** : pourcentage de la mesure pour ce lien par rapport à la mesure totale pour la page.</li><li>**[!UICONTROL Classement]** : classement de ce lien parmi tous les liens présents sur la page rendue.</li></ul> |
| **[!UICONTROL Taille de police de l’étiquette]** | Vous permet d’augmenter ou de réduire la taille de police de l’étiquette de la superposition à l’aide d’un curseur pour une meilleure lisibilité. |
| **[!UICONTROL Couleur de dégradé/bulle]** | Pour afficher les classements des liens d’incrustation pour les visualisations d’incrustation en dégradé ou en bulle, sélectionnez une plage de couleurs. |
| **[!UICONTROL Couleur du dégradé basée sur]** | <ul><li>**[!UICONTROL 30 premiers classements]** : l’intensité des couleurs est normalisée pour les 30 premières valeurs.</li><li>**[!UICONTROL Valeur de mesure absolue]** : l’intensité des couleurs dépend de la valeur de mesure absolue.</li></ul> |
| **[!UICONTROL Transparence du dégradé]** | Sélectionnez le niveau de transparence pour les superpositions en dégradé. Ce paramètre n’affecte pas les incrustations [!UICONTROL Bulle]. |

## Paramètres standard {#section_24DB95376E1A448494ECF3F57743FC19}

Ces paramètres s’appliquent à l’incrustation en mode standard.

![](assets/settings_standard.png)

| Paramètre | Description |
| --- | --- |
| **[!UICONTROL Filtrage dynamique des données]** |  |
| **[!UICONTROL Masquer les superpositions pour les liens qui n’ont reçu aucun accès]**. | Cette case à cocher vous permet de masquer les superpositions pour les liens qui n’ont reçu aucune visite, afin de limiter l’encombrement de l’interface. |

## Paramètres en direct {#section_D30F6E62FB5D404090B588F396A460AF}

Ces paramètres s’appliquent à l’incrustation en mode réel.

![](assets/settings_live.png)

| Paramètre | Description |
|---|---|
| **[!UICONTROL Afficher en haut]** | Pour afficher les **[!UICONTROL gagnants]** ou **[!UICONTROL perdants]** (ou les deux) sous forme d’incrustations, sélectionnez le nombre de liens. |
| **[!UICONTROL Exclure le bas (%)]** | Sélectionnez cette option pour éliminer les liens des gagnants et des perdants avec des données éparses. Filtrez les pourcentages inférieurs des changements de liens pour afficher uniquement les liens avec suffisamment de données pour présenter des gains ou des pertes significatives. Le pourcentage est calculé en fonction du nombre de liens sur la page. Par exemple, le filtrage des 10 % inférieurs d’une liste de 200 liens éliminerait les 20 liens inférieurs. |
| **[!UICONTROL Mettre à jour les données automatiquement]** | Permet de décider si les données Analytics affichées dans l’interface sont automatiquement mises à jour lors du calcul d’une nouvelle période. |
| **[!UICONTROL Période de mise à jour automatique]** | Actualise la page web à chaque nouvelle récupération des données afin que les liens de la page soient mieux synchronisés avec les données collectées. |
