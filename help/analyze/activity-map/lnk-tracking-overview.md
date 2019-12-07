---
description: 'Activity Map effectue le suivi des liens à l’aide d’un algorithme plus robuste qui '
title: Suivi des liens robuste
topic: Activity map
uuid: a72b1652-2e69-41c7-8cf2-d39e9c705302
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Suivi des liens robuste

Activity Map effectue le suivi des liens à l’aide d’un algorithme plus robuste qui:

* comprend le suivi des régions de page pour éviter la confusion d’un même lien entre différents appareils car le lien ne s’affiche pas au même endroit sur la page ;
* garantit l’unicité du lien, ce qui signifie que des liens distincts ne peuvent pas être confondus à cause de problèmes liés à l’ID de lien ou à plusieurs navigateurs différents.

Pour plus d’informations sur le suivi des liens dans Activity Map, rendez-vous [ici](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md).

## Méthodes de collecte des données relatives aux informations d’identification personnelles (PII) par le suivi des liens d’Activity Map {#section_AEE57510D17B4C21A7D49D32D21D67B9}

> [!CAUTION] En activant le suivi Activity Map, vous pouvez collecter des données d’informations d’identification personnelle (PII). Ces données peuvent être utilisées seules ou avec d’autres informations pour identifier, contacter ou localiser une seule personne, ou pour identifier une personne dans son contexte.

Vous trouverez ci-dessous certains cas connus de collecte des données relatives aux informations d’identification personnelles à l’aide du suivi Activity Map :

* Liens `Mailto`. Un lien mailto est un type de lien HTML qui active le client de messagerie par défaut sur l’ordinateur afin d’envoyer un message électronique.
* Liens `User ID` qui peuvent s’afficher dans l’en-tête ou le pied de page d’un site web une fois l’utilisateur connecté.
* Dans le cas des établissements financiers, le numéro de compte peut s’afficher sous la forme d’un lien. Le fait de cliquer dessus collecte le texte du lien.
* Les sites web du secteur des soins de santé peuvent également afficher des données relatives aux informations d’identification personnelles sous la forme de liens. Le fait de cliquer sur ces liens collecte le texte du lien, et donc les données relatives aux informations d’identification personnelles.
