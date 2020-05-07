---
title: Différences de traitement et d’architecture entre les plateformes Analytics
description: Découvrez les différentes façons dont certaines données sont collectées et affichées dans différentes plateformes, telles qu’Adobe Analytics et Google Analytics.
translation-type: tm+mt
source-git-commit: 3211598c2ff43493b329a9be4fb6877ae29cf08b
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 66%

---


# Différences de traitement et d’architecture entre les plateformes Analytics

Bien qu’Adobe Analytics et Google Analytics soient deux outils d’analyse, la manière dont ces plateformes collectent et traitent les données est très différente. Grâce à cette page, vous comprendrez quelques-unes des principales différences dans la manière dont certaines dimensions et mesures sont collectées et pourquoi elles peuvent afficher des résultats différents dans des rapports similaires.

## [!UICONTROL Taux de rebond]

[!UICONTROL Le taux de rebond est un IPC courant qui permet de mesurer l’efficacité et la pertinence des pages d’entrée dans la plupart des outils d’analyse. ] Il est généralement défini comme étant le nombre de visiteurs qui accèdent au site web et le quittent sans cliquer sur une autre page.

* In Adobe Analytics, [!UICONTROL Bounce Rate] is calculated using the formula **Bounces divided by Entries**.
* In Google Analytics, [!UICONTROL Bounce Rate] is calculated using the formula **Single-page sessions divided by Sessions**.

Sur les deux plateformes, si plusieurs accès sont envoyés au cours d’une même visite ou session, ce n’est pas considéré comme un rebond. Dans Adobe Analytics, des liens personnalisés sont disponibles et assez courants, ce qui peut empêcher une visite d’être comptée comme un rebond. Google Analytics envoie généralement une seule requête de données maximum sur la même page.

To achieve better parity between reporting tools, use the [!UICONTROL Single Page Visits] metric in Adobe Analytics instead of [!UICONTROL Bounces] as part of a calculated metric. The [!UICONTROL Single Page Visits] metric includes the total number of visits that only included one-page view, or visits that enter the website but do not include a click to another page.

Pour plus d’informations sur la mesure [Taux de rebond](/help/components/c-variables/c-metrics/metrics-bounce-rate.md), voir le guide d’utilisation des composants.

## [!UICONTROL Visites et sessions]

[!UICONTROL Les visites] (appelées sessions dans Google Analytics) sont un groupe de vues de page créées par le même utilisateur en peu de temps. [!UICONTROL Sur les deux plateformes, une visite expire généralement après 30 minutes d’inactivité. ] Both platforms allow customization on when a [!UICONTROL Visit] expires. Plusieurs scénarios peuvent provoquer des différences entre les plateformes.

* **Fin de journée :** toutes les sessions de Google Analytics expirent après 23 h 59. Si l’utilisateur est toujours actif sur votre site après minuit, une nouvelle session est créée. Adobe Analytics compte une visite qui se poursuit sur le jour suivant comme une seule visite.
* **Campagnes différentes :** dans Google Analytics, une nouvelle session commence si la source de campagne d’un utilisateur change. If a new [!UICONTROL Tracking Code] value is seen in Adobe Analytics, it is considered part of the same visit.
* **Remplacement manuel de session :** dans Google Analytics, une nouvelle session commence si vous utilisez `sessionControl` pour démarrer ou terminer une session manuellement. [!UICONTROL Dans Adobe Analytics, ce n’est pas possible de terminer une visite manuellement.]
* **Détection des visites aberrantes dans Adobe Analytics :** Une nouvelle [!UICONTROL visite] dans Adobe Analytics se début automatiquement si un utilisateur atteint 12 heures d’activité continue, 2 500 accès ou 100 accès en 100 secondes. Ces comportements indiquent généralement l’activité de bots.

Pour plus d’informations sur la mesure [Visites](/help/components/c-variables/c-metrics/metrics-visit.md), voir le guide d’utilisation des composants.
