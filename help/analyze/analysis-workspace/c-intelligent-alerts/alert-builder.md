---
description: valeur nulle
seo-description: valeur nulle
seo-title: Générateur d’alertes
title: Générateur d’alertes
uuid: ebc 2 d 457-4 abd -4 b 1 a -9357-489 b 5 aeb 3 f 64
translation-type: tm+mt
source-git-commit: 4b47e33d964c040cf94dc1c4ad97e43958d9d94a

---


# Générateur d’alertes

>[!IMPORTANT]
>
>Les alertes intelligentes sont disponibles uniquement pour les clients Adobe Analytics Prime et Adobe Analytics Ultimate.

## Accès au générateur d'alertes

Le Générateur d’alertes peut être ouvert de l’une des quatre façons suivantes :

* En utilisant le raccourci clavier suivant dans Analysis Workspace :

   `ctrl (or cmd) + shift + a`
* By going to **[!UICONTROL Workspace]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL New Alert]**.
* En sélectionnant une ou plusieurs lignes de tableau à structure libre, en cliquant avec le bouton droit de la souris puis en sélectionnant **[!UICONTROL Créer une alerte d’après la sélection]**.
* From within a Reports &amp; Analytics report, by going to **[!UICONTROL More]** &gt; **[!UICONTROL Add Alert]**.

## Créer des alertes

Les utilisateurs qui ont déjà créé des segments ou calculé des mesures dans Analytics ne seront pas dépaysés par l’interface du Générateur d’alertes :

![](assets/alert_builder.png)

<!--Meike, I edited this table for validation -->

**Nom d’alerte**

Spécifiez le nom de l’alerte. Le nom de l’alerte doit contenir le nom du rapport ou le seuil des mesures.

**Granularité du temps**

Spécifiez quand vérifier la mesure : chaque heure, chaque jour, chaque semaine ou chaque mois.

>[!NOTE]
>
>Pour les suites de rapports avec calendrier personnalisé, nous ne prenons pas en charge la granularité mensuelle dans le Générateur d'alertes.

**Destinataires**

Spécifiez où envoyer l’alerte. Une alerte peut être envoyée à un utilisateur ou à un groupe Analytics, à une adresse électronique brute ou à un numéro de téléphone.

>[!IMPORTANT]
>
>The phone number must be preceded by a "+" and a [country code](https://countrycode.org/).

Le courrier électronique reçu par un utilisateur une fois qu'une alerte a été déclenchée ressemble à ceci :

![](assets/alerts-email.PNG)

**Date d’expiration**

Spécifiez la date d’expiration de l’alerte.

**Envoyer une alerte lorsque...**

*Pour l’un de ces déclencheurs de mesure*

* Faites glisser et déplacez les mesures dans la zone de travail des déclencheurs.

   An **"incompatible components”** message will appear if not all the components (metrics/dimensions/segments) in the alert are compatible with the currently selected report suite.
* Déterminez le seuil que la mesure doit dépasser avant l’envoi d’une alerte. Vous pouvez définir un seuil, puis l’une des conditions suivantes :

   * il existe une anomalie
   * l’anomalie est supérieure à celle prévue
   * l’anomalie est inférieure à celle prévue
   * est supérieur ou égal
   * est inférieur ou égal
   * change de
   * Le seuil peut être défini à 90 %, 95 %, 99 %, 99,75 % ou 99,90 %.
   Vous pouvez également utiliser les mesures calculées.

*Avec tous ces filtres*

* Faites glisser et déplacez les segments ou dimensions pour ajouter des filtres. Par exemple, ajoutez un segment « Appareils mobiles seulement » afin de signifier que la règle se déclenche uniquement pour les appareils mobiles.
* Pour ajouter d’autres filtres, utilisez une instruction ET.

**Ajouter une règle**

Pour ajouter des règles ET ou OU, cliquez sur l’icône d’engrenage.

## Preview Alerts {#section_10D75BA7B77E4C5FAF58A719C082E070}

Dans l’aperçu interactif des alertes, vous pouvez déterminer à quelle fréquence, approximativement, une alerte sera déclenchée en fonction d’une expérience antérieure.

Si, par exemple, vous définissez une granularité temporelle quotidienne, l’aperçu indique que, pour une certaine mesure, l’alerte aurait été déclenchée x fois durant les 30 ou 31 derniers jours.

Pour réduire le nombre d’alertes déclenchées, réglez le seuil dans le [Gestionnaire d’alertes](/help/components/c-alerts/alert-manager.md).

![](assets/alert_preview.png)
