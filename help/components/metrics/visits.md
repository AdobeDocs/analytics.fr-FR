---
title: Visites
description: Séquence de pages vues lors d’une session unique.
translation-type: tm+mt
source-git-commit: 0328de560185e716a3913080feda9cd078e0f206
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 5%

---


# Visites

La mesure Visites indique le nombre de sessions sur tous les visiteurs de votre site.

## Méthode de calcul de cette mesure

Une visite est toujours liée à une période ; vous savez donc si une nouvelle visite doit être comptabilisée si la même personne revient sur votre site. Une visite début lorsque l’utilisateur arrive pour la première fois sur votre site. Une visite se termine lorsqu’elle répond à l’un des critères suivants :

* **30 minutes d&#39;inactivité**: Presque toutes les sessions se terminent ainsi. Si plus de 30 minutes s’écoulent entre les accès, une nouvelle visite commence.
* **12 heures d&#39;activité**: Si un utilisateur déclenche systématiquement des demandes d’image sans intervalle de 30 minutes pendant plus de 12 heures, une nouvelle visite s’début automatiquement.
* **2 500 accès**: Si un utilisateur génère un grand nombre d’accès sans commencer une nouvelle session, une nouvelle visite est comptabilisée après 2 500 demandes d’image.
* **100 accès en 100 secondes** : si une visite consiste de plus de 100 accès se produisant en moins de 100 secondes, la visite se termine automatiquement. Ce comportement indique généralement l’activité des robots et cette restriction est appliquée afin d’augmenter les performances des rapports.

Une visite ne coïncide pas nécessairement avec une session de navigateur en raison des critères ci-dessus. L’une des différences les plus courantes est l’endroit où un visiteur accède à votre site, laisse l’onglet ouvert pendant plus de 30 minutes, puis reprend la navigation. Bien que cette action fasse techniquement partie de la même session de navigation, Adobe considère cette action comme deux visites distinctes.

## Modification de la définition d’une visite

Vous pouvez modifier la définition d’une visite à une heure autre que 30 minutes.

* Pour les suites [de rapports](../vrs/vrs-about.md)virtuelles, vous pouvez modifier le délai d’expiration de la visite à l’aide de la liste déroulante [!UICONTROL Délai d’expiration] de lavisite. Vous pouvez définir le délai d’expiration de la visite sur n’importe quelle valeur raisonnable.
* Pour les suites de rapports standard, contactez le service à la clientèle pour demander que la durée de la visite soit raccourcie pour une suite de rapports donnée. La durée de visite des suites de rapports standard ne peut pas dépasser 30 minutes. Vous ne pouvez donc que la raccourcir.

## Comportement affectant les visites

Si un visiteur effectue l’une des actions suivantes, une nouvelle visite début :

* Efface leur cache en cours de session et continue à parcourir votre site.
* Permet de laisser votre site ouvert dans un onglet pendant plus de 30 minutes, puis de poursuivre la navigation
* Ouvre un autre navigateur et accède à votre site sur le même ordinateur
* Même personne qui consulte votre site sur différents périphériques

Si un visiteur effectue l’une de ces actions, une nouvelle visite **ne début pas** tant qu’il y a moins de 30 minutes entre des accès consécutifs :

* Ferme leur navigateur, puis accède à nouveau à votre site
* Redémarre l’ordinateur, ouvre le même navigateur et accède de nouveau à votre site.
* Transitions à un autre réseau, comme la déconnexion d&#39;une station d&#39;accueil réseau câblée à un réseau sans fil
* Parcourez votre site dans plusieurs onglets. Si un visiteur bascule d’un onglet à l’autre, chaque accès est comptabilisé comme faisant partie de la même visite.

## Visites s’étendant sur une limite de date

Une visite compte pour chaque période impliquée. Par exemple, si vous avez un visiteur qui début la navigation sur votre site le lundi à 23h45, puis envoie sa dernière demande d&#39;image le mardi à 12h10, une visite est attribuée à la fois au lundi et au mardi. Cependant, la mesure de visite totale est dédupliquée, ce qui montre une visite unique pour la période du projet.
