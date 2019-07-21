---
title: Différences de traitement et d'architecture entre les plateformes Analytics
description: Découvrez comment certaines données sont collectées et affichées différemment entre les plateformes telles qu'Adobe Analytics et Google Analytics.
translation-type: tm+mt
source-git-commit: a5f612ba5e8446a56bc2bd252a8781e8ab1de403

---


# Différences de traitement et d'architecture entre les plateformes Analytics

Bien qu'Adobe Analytics et Google Analytics soient tous deux des outils Analytics, la manière dont les données sont collectées et traitées entre les plateformes est très différente. Utilisez cette page pour comprendre quelques-unes des principales différences de collecte de certaines dimensions et mesures et pour quelle raison elles peuvent afficher des nombres différents dans des rapports similaires.

## Taux de rebond

Le taux de rebonds est un IPC commun qui permet de mesurer l'efficacité et la pertinence des pages d'entrée dans la plupart des outils d'analyse. Il s'agit généralement de visites qui entrent sur le site Web mais qui n'incluent pas de clic sur une autre page.

* In Adobe Analytics, Bounce Rate is calculated using the formula **Bounces divided by Entries**.
* In Google Analytics, Bounce Rate is calculated using the formula **Single-page sessions divided by Sessions**.

Sur les deux plateformes, si plusieurs accès sont envoyés lors de la même visite ou session, il n'est pas considéré comme un retour. Dans Adobe Analytics, des liens personnalisés sont disponibles et assez courants, ce qui peut empêcher une visite de compter comme un retour. En règle générale, Google Analytics n'envoie pas plus d'une requête de données sur la même page.

Pour obtenir une meilleure parité entre les outils de création de rapports, utilisez la mesure Visites mono-page d'Adobe Analytics plutôt que les Rebonds dans le cadre d'une mesure calculée. La mesure Visites mono-page inclut le nombre total de visites qui incluent uniquement une page vue ou les visites qui entrent sur le site Web mais qui n'incluent pas de clic sur une autre page.

See the [Bounce Rate](../../components/c-variables/c-metrics/metrics-bounce-rate.md) metric in the Components user guide for more information.

## Visites et sessions

Les visites (appelées sessions dans Google Analytics) sont un groupe de pages vues effectuées par le même utilisateur dans un court temps. Les visites sur les deux plateformes expirent généralement après 30 minutes d'inactivité. Les deux plateformes permettent de personnaliser le moment où une visite expire. Plusieurs scénarios peuvent entraîner des différences sur chaque plateforme.

* **Fin de journée :** Toutes les sessions dans Google Analytics expirent après 23 h 59 après un jour donné. Si l'utilisateur est toujours actif sur votre site après 12 heures, une nouvelle session est créée. Adobe Analytics continue les visites le jour suivant dans le cadre de la même visite.
* **Différentes campagnes :** Une nouvelle session dans Google Analytics commence si la source de campagne d'un utilisateur change. Si une nouvelle valeur Code de suivi est visible dans Adobe Analytics, elle est considérée comme faisant partie de la même visite.
* **Remplacement manuel de la session :** Une nouvelle session dans Google Analytics commence si vous utilisez `sessionControl` pour démarrer ou terminer manuellement une session. Les visites ne peuvent pas être manuellement terminées dans Adobe Analytics.
* **Détection des visites sortante dans Adobe Analytics :** Une nouvelle visite dans Adobe Analytics commence automatiquement si un utilisateur atteint 12 heures d'activité continue, 2 500 accès ou 100 accès sous 100 secondes. Chacun de ces critères de détection est généralement déclenché par l'activité de robots.

See the [Visits](../../components/c-variables/c-metrics/metrics-visit.md) metric in the Components user guide for more information.
