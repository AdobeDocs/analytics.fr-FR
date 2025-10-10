---
title: Différences de traitement et d’architecture entre les plateformes Analytics
description: Découvrez les différentes façons dont certaines données sont collectées et affichées dans différentes plateformes, telles qu’Adobe Analytics et Google Analytics.
feature: Third-party Integration
exl-id: 3e457915-3c2d-49f7-9b77-df18c04d49cd
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 96%

---

# Différences de traitement et d’architecture entre les plateformes Analytics

Bien qu’Adobe Analytics et Google Analytics soient deux outils d’analyse, la manière dont ces plateformes collectent et traitent les données est très différente. Grâce à cette page, vous comprendrez quelques-unes des principales différences dans la manière dont certaines dimensions et mesures sont collectées et pourquoi elles peuvent afficher des résultats différents dans des rapports similaires.

## [!UICONTROL Taux de rebond]

Le [!UICONTROL taux de rebond] est un IPC courant qui permet de mesurer l’efficacité et la pertinence des pages de destination dans la plupart des outils d’analyse. Il est généralement défini comme étant le nombre de visiteurs qui accèdent au site web et le quittent sans cliquer sur une autre page.

* Dans Adobe Analytics, le [!UICONTROL taux de rebond] est calculé à lʼaide de la formule : **rebonds divisés par les entrées**.
* Dans Google Analytics, le [!UICONTROL taux de rebond] est calculé à lʼaide de la formule : **nombre de sessions avec consultation dʼune seule page divisé par lʼensemble des sessions**.

Sur les deux plateformes, si plusieurs accès sont envoyés au cours d’une même visite ou session, ce n’est pas considéré comme un rebond. Dans Adobe Analytics, des liens personnalisés sont disponibles et assez courants, ce qui peut empêcher une visite d’être comptée comme un rebond. Google Analytics envoie généralement une seule requête de données maximum sur la même page.

Pour obtenir une meilleure parité entre les outils de reporting, utilisez la mesure [!UICONTROL Visites de page unique] dans Adobe Analytics au lieu de [!UICONTROL Rebonds] dans le cadre dʼune mesure calculée. La mesure [!UICONTROL Visites de page unique] inclut le nombre total de visites qui incluaient uniquement une page vue, ou de visites qui accèdent au site web sans inclure un clic sur une autre page.

Pour plus d’informations sur la mesure [Taux de rebond](/help/components/metrics/bounce-rate.md), voir le guide d’utilisation des composants.

## [!UICONTROL Visites et sessions]

[!UICONTROL Une visite] (appelée session dans Google Analytics) est un groupe de pages vues par le même utilisateur sur un court laps de temps. Sur les deux plateformes, une [!UICONTROL visite] expire généralement après 30 minutes d’inactivité. Les deux plateformes permettent la personnalisation de lʼexpiration dʼune [!UICONTROL visite]. Plusieurs scénarios peuvent provoquer des différences entre les plateformes.

* **Fin de journée :** toutes les sessions dans Google Analytics expirent après 23 :59 un jour donné. Si l’utilisateur est toujours actif sur votre site après minuit, une nouvelle session est créée. Adobe Analytics compte une visite qui se poursuit sur le jour suivant comme une seule visite.
* **Campagnes différentes :** dans Google Analytics, une nouvelle session commence si la source de campagne d’un utilisateur change. Dans Adobe Analytics, en cas dʼune nouvelle valeur de [!UICONTROL code de suivi], elle est considérée comme faisant partie de la même visite.
* **Remplacement manuel de session :** dans Google Analytics, une nouvelle session commence si vous utilisez `sessionControl` pour démarrer ou terminer une session manuellement. [!UICONTROL Dans Adobe Analytics, ce n’est pas possible de terminer une visite manuellement.]
* **Détection des visites aberrantes dans Adobe Analytics :** dans Adobe Analytics, une nouvelle [!UICONTROL visite] démarre automatiquement si un utilisateur atteint 12 heures dʼactivité continue, 2 500 accès ou 100 accès en 100 secondes. Ces comportements indiquent généralement l’activité de robots.

Pour plus d’informations sur la mesure [Visites](/help/components/metrics/visits.md), voir le guide d’utilisation des composants.
