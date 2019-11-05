---
title: Différences de traitement et d’architecture entre les plateformes Analytics
description: Découvrez comment certaines données sont collectées et affichées différemment entre des plateformes telles qu’Adobe Analytics et Google Analytics.
translation-type: tm+mt
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# Différences de traitement et d’architecture entre les plateformes Analytics

Bien qu’Adobe Analytics et Google Analytics soient tous deux des outils Analytics, la manière dont les données sont collectées et traitées entre les plateformes est très différente. Utilisez cette page pour comprendre certaines des principales différences dans la manière dont certaines dimensions et mesures sont collectées et pourquoi elles peuvent afficher des nombres différents dans des rapports similaires.

## Taux de rebond

Le taux de rebonds est un indicateur de performance clé courant qui permet de mesurer l’efficacité et la pertinence des pages d’entrée dans la plupart des outils d’analyse. Cela est généralement défini comme les visites qui accèdent au site Web mais n’incluent pas un clic sur une autre page.

* Dans Adobe Analytics, le taux de rebonds est calculé à l’aide de la formule **Retours divisés par les entrées**.
* Dans Google Analytics, le taux de rebonds est calculé à l’aide de la formule Sessions **mono-page divisées par Sessions**.

Sur les deux plates-formes, si plusieurs accès sont envoyés au cours d’une même visite ou session, il n’est pas considéré comme un rebond. Dans Adobe Analytics, des liens personnalisés sont disponibles et assez courants, ce qui peut empêcher une visite de se compter comme un rebond. Google Analytics n’envoie généralement pas plusieurs requêtes de données sur la même page.

Pour obtenir une meilleure parité entre les outils de création de rapports, utilisez la mesure Visites mono-page dans Adobe Analytics au lieu de Rebonds dans le cadre d’une mesure calculée. La mesure Visites mono-page inclut le nombre total de visites qui incluaient uniquement une page vue ou de visites qui accèdent au site Web sans inclure un clic sur une autre page.

Pour plus d’informations, voir la mesure [Taux](/help/components/c-variables/c-metrics/metrics-bounce-rate.md) de rebonds dans le guide de l’utilisateur Composants.

## Visites et sessions

Les visites (appelées sessions dans Google Analytics) sont un groupe de pages vues effectuées par le même utilisateur en peu de temps. Les visites sur les deux plateformes expirent généralement après 30 minutes d’inactivité. Les deux plateformes permettent la personnalisation à l’expiration d’une visite. Plusieurs scénarios peuvent provoquer des différences sur chaque plateforme.

* **** Fin de journée : Toutes les sessions de Google Analytics expirent après 23h59 un jour donné. Si l’utilisateur est toujours actif sur votre site après 12 heures, une nouvelle session est créée. Dans le cadre de la même visite, Adobe Analytics poursuit les visites le jour suivant.
* **** Campagnes différentes : Une nouvelle session dans Google Analytics commence si la source de campagne d’un utilisateur change. Si une nouvelle valeur Code de suivi est affichée dans Adobe Analytics, elle est considérée comme faisant partie de la même visite.
* **** Remplacement manuel de session : Une nouvelle session dans Google Analytics commence si vous utilisez `sessionControl` pour démarrer ou terminer une session manuellement. Les visites ne peuvent pas se terminer manuellement dans Adobe Analytics.
* **** Détection des visites aberrantes dans Adobe Analytics : Une nouvelle visite dans Adobe Analytics démarre automatiquement si un utilisateur atteint 12 heures d’activité continue, 2 500 accès ou 100 accès en 100 secondes. Chacun de ces critères de détection est généralement déclenché par l’activité des robots.

Pour plus d’informations, voir la mesure [Visites](/help/components/c-variables/c-metrics/metrics-visit.md) dans le guide de l’utilisateur Composants.
