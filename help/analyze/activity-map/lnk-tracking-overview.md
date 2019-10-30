---
description: '[!Carte d’activités DNL] effectue le suivi des liens avec un algorithme plus robuste qui '
seo-description: '[!Carte d’activités DNL] effectue le suivi des liens avec un algorithme plus robuste qui '
seo-title: Suivi des liens robuste
solution: Analytics
title: Suivi des liens robuste
topic: Activity Map
uuid: a72b1652-2e69-41c7-8cf2-d39e9c705302
translation-type: tm+mt
source-git-commit: ae18932eda59c059e2aa635cc30f233b88840031

---


# Suivi des liens robuste

[!DNL Activity Map] effectue le suivi des liens avec un algorithme plus robuste qui :

* comprend le suivi des régions de page pour éviter la confusion d’un même lien entre différents appareils car le lien ne s’affiche pas au même endroit sur la page ;
* garantit l’unicité du lien, ce qui signifie que des liens distincts ne peuvent pas être confondus à cause de problèmes liés à l’ID de lien ou à plusieurs navigateurs différents.

For more on link tracking in [!DNL Activity Map], go [here](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md).

## Comment le suivi des [!DNL Activity Map] liens peut-il collecter des données d’identification personnelle ? {#section_AEE57510D17B4C21A7D49D32D21D67B9}

> [!CAUTION] En activant le [!DNL Activity Map] suivi, vous collectez peut-être des données d’identification personnelle. Ces données peuvent être utilisées indépendamment ou conjointement à d’autres informations afin d’identifier, de contacter ou de localiser une personne, ou encore d’identifier une personne en contexte.

Here are some known cases where PII data might be collected using [!DNL Activity Map] Tracking:

* `Mailto` liens. Un lien mailto est un type de lien HTML qui active le client de messagerie par défaut sur l’ordinateur afin d’envoyer un message électronique.
* `User ID` liens pouvant s’afficher dans l’en-tête/le pied de page d’un site Web une fois que l’utilisateur s’est connecté.
* Dans le cas des établissements financiers, le numéro de compte peut s’afficher sous la forme d’un lien. Le fait de cliquer dessus collecte le texte du lien.
* Les sites web du secteur des soins de santé peuvent également afficher des données relatives aux informations d’identification personnelles sous la forme de liens. Le fait de cliquer sur ces liens collecte le texte du lien, et donc les données relatives aux informations d’identification personnelles.
