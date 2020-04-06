---
description: Les superpositions proposent plusieurs manières de configurer la visualisation de données afin de consulter et de comprendre facilement la popularité des liens sur une page.
title: Superpositions personnalisables
topic: Activity map
uuid: c1e56480-c1df-4a81-8a2a-42ea1362175c
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Superpositions personnalisables

Les superpositions proposent plusieurs manières de configurer la visualisation de données afin de consulter et de comprendre facilement la popularité des liens sur une page.

Les superpositions vous permettent de visualiser les données de clic directement sur la page. C’est ce qui sépare un outil de  visuel  tel que  Carte de de , des outils principalement tabulaires et graphiques tels que les Rapports et analyses.

  de mappage de  trois types d’incrustations :

* Incrustation en dégradé (carte thermique)
* Incrustation bulle
* Superposition des gagnants et des perdants

Vous pouvez également configurer [le rendu des superpositions pour le contenu dynamique](/help/analyze/activity-map/activitymap-link-tracking/activitymap-stl-track-custom-elements.md).

Pour apporter des modifications aux incrustations, ouvrez le panneau [Paramètres d’](/help/analyze/activity-map/activitymap-overlay-settings.md) incrustation et modifiez les options disponibles.

Placer le pointeur sur une incrustation affiche ses [détails](/help/analyze/activity-map/activitymap-overlay-details.md).

## Superposition en dégradé (carte thermique) {#section_06AF13DE05A1454D960176CD0DA921A6}

Avec l’incrustation en dégradé, l’intensité des couleurs dépend de la popularité du lien. Cette intensité peut être normalisée pour les 30 premiers classements ou une fonction de la valeur de mesure absolue.

Ces mesures sont superposées au-dessus des liens de la page sous la forme d&#39;une sorte de &quot;carte thermique&quot; pour répondre à des questions critiques, notamment :

* Quelle est la valeur d’une page individuelle ?
* Quelle est la valeur d’un élément individuel d’une page ?
* Quel est le &quot;domaine numérique&quot; le plus précieux d&#39;une page ?

![](assets/gradient.png)

## Superposition bulle {#section_A657AB3F64CB47F881BBFFD72B37D9D4}

L’incrustation Bulle affiche le contenu de l’incrustation (mesure, pourcentage ou classement) dans une petite bulle de légende.

Les incrustations bulles s’affichent lorsque vous sélectionnez cette incrustation dans le type d’incrustation de la barre d’outils. . Les superpositions bulles s’affichent pour tous les liens qui correspondent à la sélection dans [Paramètres](/help/analyze/activity-map/activitymap-overlay-settings.md) de  de zone cliquable (30 premiers, 50 premiers, tous...). Les superpositions en dégradé s’affichent si cette option n’est pas sélectionnée.

![](assets/bubble_overlay.png)

>[!NOTE] Les superpositions bulle pour les sous-menus apparaissent uniquement lorsque vous affichez le sous-menu :
>
>![](assets/bubbles_submenu.png)>

## Superpositions des gagnants et des perdants {#section_EE80278E20C14824869BF5A27A4634C8}

**[!UICONTROL Gainers and losers overlays]** sont disponibles uniquement en mode réel. Ils signalent les modifications en temps réel des liens  des en comparant les mesures de la période en cours aux mesures de la dernière période. Ils vous offrent un moyen visuellement attrayant de en temps réel.

Cette incrustation en temps réel classe les clics en fonction des modifications de la valeur de la mesure entre les périodes précédente et actuelle.

![](assets/gainers_losers.png)

