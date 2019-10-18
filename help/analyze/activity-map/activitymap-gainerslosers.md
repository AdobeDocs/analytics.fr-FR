---
description: Les superpositions proposent plusieurs manières de configurer la visualisation de données afin de consulter et de comprendre facilement la popularité des liens sur une page.
seo-description: Les superpositions proposent plusieurs manières de configurer la visualisation de données afin de consulter et de comprendre facilement la popularité des liens sur une page.
seo-title: Superpositions personnalisables
solution: Analytics
title: Superpositions personnalisables
topic: Activity Map
uuid: c1e56480-c1df-4a81-8a2a-42ea1362175c
translation-type: tm+mt
source-git-commit: 36637b76b8026fbf87ad48adcfa47386c530e732

---


# Superpositions personnalisables

Les superpositions proposent plusieurs manières de configurer la visualisation de données afin de consulter et de comprendre facilement la popularité des liens sur une page.

Les superpositions vous permettent de visualiser les données de clic directement sur la page. This is what separates a visual analysis tool like [!DNL Activity Map] from mostly tabular and graphical tools like Reports &amp; Analytics.

[!DNL Activity Map] propose trois types d’incrustations :

* Superposition en dégradé (carte thermique)
* Superposition bulle
* Superposition des gagnants et des perdants

Vous pouvez également configurer [le rendu des superpositions pour le contenu dynamique](/help/analyze/activity-map/activitymap-link-tracking/activitymap-stl-track-custom-elements.md).

Pour modifier les superpositions, ouvrez le [panneau Paramètres de superposition](/help/analyze/activity-map/activitymap-overlay-settings.md) et modifiez les options disponibles.

Survolez une superposition pour afficher ses [détails](/help/analyze/activity-map/activitymap-overlay-details.md).

## Gradient overlay (Heatmap) {#section_06AF13DE05A1454D960176CD0DA921A6}

Avec la superposition en dégradé, l’intensité des couleurs dépend de la popularité du lien. Cette intensité peut être normalisée pour les 30 premiers classements ou dépendre de la valeur de mesure absolue.

Ces mesures sont superposées au-dessus des liens de la page sous la forme d’une sorte de « carte thermique » afin de répondre à des questions critiques, notamment :

* Quelle est la valeur d’une page spécifique ?
* Quelle est la valeur d’un élément spécifique sur une page ?
* Quels sont les « biens numériques » les plus précieux sur la page ?

![](assets/gradient.png)

## Bubble overlay {#section_A657AB3F64CB47F881BBFFD72B37D9D4}

La superposition bulle affiche le contenu de la superposition (mesure, pourcentage ou classement) dans une petite bulle de légende.

Les superpositions bulle s’affichent lorsque vous sélectionnez cette superposition dans Type de superposition dans la barre d’outils. Bubble overlays show for all links that match the selection in [[!DNL Activity Map] Settings](/help/analyze/activity-map/activitymap-overlay-settings.md) (top 30, top 50, all...). Les superpositions en dégradé s’affichent si cette option n’est pas sélectionnée.

![](assets/bubble_overlay.png)

>[!NOTE]
>
>Les superpositions bulles des sous-menus s’affichent uniquement lorsque vous affichez le sous-menu :
>
>![](assets/bubbles_submenu.png)&gt;

## Gainers and losers overlays {#section_EE80278E20C14824869BF5A27A4634C8}

**[!UICONTROL Les incrustations]** gagnants et perdants sont disponibles uniquement en mode réel. Elles signalent les changements de l’activité des liens en temps réel en comparant les mesures de la période actuelle à celles de la dernière période. Elles offrent une manière visuellement attractive d’afficher les tendances en temps réel.

Cette superposition en temps réel établit le classement des clics en fonction des changements de la valeur de mesure entre la période précédente et la période actuelle.

![](assets/gainers_losers.png)

