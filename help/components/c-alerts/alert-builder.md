---
description: Utilisation des alertes dans Analysis Workspace.
title: Présentation du Générateur d’alertes
feature: Alerts
exl-id: 82e51357-4a32-4db1-bc56-95a72dbaa1be
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 97%

---

# Générateur d’alertes

>[!IMPORTANT]
>
>Les alertes intelligentes ne sont disponibles que pour les clients Adobe [!DNL Analytics] Prime et Adobe [!DNL Analytics] Ultimate.

Accédez au Générateur d’alertes de l’une des trois façons suivantes :

* En utilisant le raccourci clavier suivant dans Analysis Workspace :

  `ctrl (or cmd) + shift + a`
* En sélectionnant **[!UICONTROL Workspace]** > **[!UICONTROL Composants]** > **[!UICONTROL Nouvelle alerte]**.
* En sélectionnant une ou plusieurs lignes de tableau à structure libre, en cliquant avec le bouton droit de la souris puis en sélectionnant **[!UICONTROL Créer une alerte d’après la sélection]**.

Les utilisateurs qui ont déjà créé des segments ou calculé des mesures dans [!DNL Analytics] ne seront pas dépaysés par l’interface du Générateur d’alertes :

![](assets/alert_builder.png)

**Nom d’alerte**

Spécifiez le nom de l’alerte. Le nom de l’alerte doit contenir le nom du rapport ou le seuil des mesures.

**Granularité du temps**

Spécifiez quand vérifier la mesure : chaque heure, chaque jour, chaque semaine ou chaque mois.

>[!NOTE]
>
>Dans le Générateur d’alertes, il n’est pas possible de sélectionner la granularité mensuelle pour les suites de rapports dotées d’un calendrier personnalisé.

**Destinataires**

Spécifiez où envoyer l’alerte. Une alerte peut être envoyée à un utilisateur [!DNL Analytics] ou à un groupe [!DNL Analytics], à une adresse e-mail brute ou à un numéro de téléphone.

>[!IMPORTANT]
>
>Le numéro de téléphone doit être précédé d’un « + » et d’un [code de pays](https://countrycode.org/).

**Date d’expiration**

Spécifiez la date d’expiration de l’alerte.

**Envoyer une alerte lorsque...**

*Pour l’un de ces déclencheurs de mesure*

* Faites glisser et déplacez les mesures dans la zone de travail des déclencheurs.

  Notez qu’un message **« composants incompatibles »** s’affiche si certains composants (mesures/dimensions/segments) de l’alerte ne sont pas compatibles avec la suite de rapports actuellement sélectionnée.

* Déterminez le seuil que la mesure doit dépasser avant l’envoi d’une alerte. Vous pouvez définir un seuil, puis l’une des conditions suivantes :

   * il existe une anomalie
   * l’anomalie est supérieure à celle prévue
   * l’anomalie est inférieure à celle prévue
   * l’anomalie dépasse
   * est supérieur ou égal
   * est inférieur ou égal
   * change de

* Le paramètre « l’anomalie dépasse » est une nouvelle condition, qui va au-delà des seuils (statiques) actuels. Il applique les algorithmes de détection des anomalies qui définissent le déclencheur de manière dynamique. Le seuil peut être défini à 90 %, 95 %, 99 %, 99,75 % ou 99,90 %.
* Il est défini à 99,75 % pour les granularités horaires et à 99 % pour les granularités quotidiennes.
* Vous pouvez également utiliser les mesures calculées.

*Avec tous ces filtres*

Faites glisser et déplacez les segments ou dimensions pour ajouter des filtres. Par exemple, ajoutez un segment « Appareils mobiles seulement » afin de signifier que la règle se déclenche uniquement pour les appareils mobiles.

Pour ajouter d’autres filtres, utilisez une instruction AND.

**Ajouter une règle**

Pour ajouter des règles AND ou OR, cliquez sur l’icône d’engrenage.

## Prévisualisation des alertes {#section_10D75BA7B77E4C5FAF58A719C082E070}

Dans l’aperçu interactif des alertes, vous pouvez déterminer à quelle fréquence, approximativement, une alerte sera déclenchée en fonction d’une expérience antérieure.

Si, par exemple, vous définissez une granularité temporelle quotidienne, l’aperçu indique que, pour une certaine mesure, l’alerte aurait été déclenchée x fois durant les 30 ou 31 derniers jours.

Pour réduire le nombre d’alertes déclenchées, réglez le seuil dans le [Gestionnaire d’alertes](/help/components/c-alerts/alert-manager.md).

![](assets/alert_preview.png)
