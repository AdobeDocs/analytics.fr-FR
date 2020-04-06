---
description: 'Activity Map effectue le suivi des liens à l’aide d’un algorithme plus robuste qui '
title: Suivi des liens robuste
topic: Activity map
uuid: a72b1652-2e69-41c7-8cf2-d39e9c705302
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Suivi des liens robuste

Activity Map effectue le suivi des liens à l’aide d’un algorithme plus robuste qui:

* Inclut le suivi des régions de page afin d’éviter que des cas de confusion entre des périphériques différents soient associés au même lien, car celui-ci s’affiche à des emplacements différents sur la page ;
* Garantit l’unicité des liens, ce qui signifie que des liens distincts ne peuvent pas être confondus pour un lien en raison de problèmes liés à LinkID ou à d’autres navigateurs.

Pour plus d&#39;informations sur le suivi des liens dans  Carte , [cliquez ici](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md).

## Méthodes de collecte des données relatives aux informations d’identification personnelles (PII) par le suivi des liens d’Activity Map {#section_AEE57510D17B4C21A7D49D32D21D67B9}

>[!CAUTION] En activant le suivi Activity Map, vous pouvez collecter des données d’informations d’identification personnelle (PII). Ces données peuvent être utilisées seules ou avec d’autres informations pour identifier, contacter ou localiser une seule personne, ou pour identifier une personne dans son contexte.

Vous trouverez ci-dessous certains cas connus de collecte des données relatives aux informations d’identification personnelles à l’aide du suivi Activity Map :

* Liens `Mailto`. Un lien mailto est un type de lien HTML qui active le client de messagerie par défaut sur l’ordinateur afin d’envoyer un message électronique.
* Liens `User ID` qui peuvent s’afficher dans l’en-tête ou le pied de page d’un site web une fois l’utilisateur connecté.
* Pour les institutions financières, le numéro de compte peut être indiqué sous la forme d’un lien. Cliquez dessus pour collecter le texte du lien.
* Les sites web de soins de santé peuvent également afficher des données PII sous forme de liens. Cliquez sur ces liens pour collecter le texte du lien, collectant ainsi les données PII.
