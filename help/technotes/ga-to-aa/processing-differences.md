---
title: Différences de traitement et d’architecture entre les plateformes Analytics
description: Découvrez les différentes façons dont certaines données sont collectées et affichées dans différentes plateformes, telles qu’Adobe Analytics et Google Analytics.
translation-type: ht
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# Différences de traitement et d’architecture entre les plateformes Analytics

Bien qu’Adobe Analytics et Google Analytics soient deux outils d’analyse, la manière dont ces plateformes collectent et traitent les données est très différente. Grâce à cette page, vous comprendrez quelques-unes des principales différences dans la manière dont certaines dimensions et mesures sont collectées et pourquoi elles peuvent afficher des résultats différents dans des rapports similaires.

## Taux de rebond

Le taux de rebond est un IPC courant qui permet de mesurer l’efficacité et la pertinence des pages d’entrée dans la plupart des outils d’analyse. Il est généralement défini comme étant le nombre de visiteurs qui accèdent au site web et le quittent sans cliquer sur une autre page.

* Dans Adobe Analytics, le taux de rebond est calculé à l’aide de la formule : **rebonds divisés par les entrées**.
* Dans Google Analytics, le taux de rebond est calculé à l’aide de la formule : **nombre de sessions avec consultation d’une seule page divisé par l’ensemble des sessions**.

Sur les deux plateformes, si plusieurs accès sont envoyés au cours d’une même visite ou session, ce n’est pas considéré comme un rebond. Dans Adobe Analytics, des liens personnalisés sont disponibles et assez courants, ce qui peut empêcher une visite d’être comptée comme un rebond. Google Analytics envoie généralement une seule requête de données maximum sur la même page.

Pour obtenir une meilleure parité entre les outils de création de rapports, utilisez la mesure Visites sur une seule page dans Adobe Analytics au lieu de Rebonds dans le cadre d’une mesure calculée. La mesure Visites sur une seule page inclut le nombre total de visites qui incluaient uniquement une page vue, ou de visites qui accèdent au site web sans inclure un clic sur une autre page.

Pour plus d’informations sur la mesure [Taux de rebond](/help/components/c-variables/c-metrics/metrics-bounce-rate.md), voir le guide d’utilisation des composants.

## Visites et sessions

Une visite (appelée session dans Google Analytics) est un groupe de pages vues par le même utilisateur sur un court laps de temps. Sur les deux plateformes, une visite expire généralement après 30 minutes d’inactivité. Les deux plateformes permettent la personnalisation de l’expiration d’une visite. Plusieurs scénarios peuvent provoquer des différences entre les plateformes.

* **Fin de journée :** toutes les sessions de Google Analytics expirent après 23 h 59. Si l’utilisateur est toujours actif sur votre site après minuit, une nouvelle session est créée. Adobe Analytics compte une visite qui se poursuit sur le jour suivant comme une seule visite.
* **Campagnes différentes :** dans Google Analytics, une nouvelle session commence si la source de campagne d’un utilisateur change. Dans Adobe Analytics, en cas d’une nouvelle valeur de code de suivi, elle est considérée comme faisant partie de la même visite.
* **Remplacement manuel de session :** dans Google Analytics, une nouvelle session commence si vous utilisez `sessionControl` pour démarrer ou terminer une session manuellement. Dans Adobe Analytics, ce n’est pas possible de terminer une visite manuellement.
* **Détection des visites aberrantes dans Adobe Analytics :** dans Adobe Analytics, une nouvelle visite démarre automatiquement si un utilisateur atteint 12 heures d’activité continue, 2 500 accès ou 100 accès en 100 secondes. Ces comportements indiquent généralement l’activité de bots.

Pour plus d’informations sur la mesure [Visites](/help/components/c-variables/c-metrics/metrics-visit.md), voir le guide d’utilisation des composants.
