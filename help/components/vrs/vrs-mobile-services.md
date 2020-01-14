---
description: L’interface utilisateur d’Adobe Mobile Services combine les données sur les applications mobiles de vos suites de rapports Adobe Analytics et permet d’envoyer des notifications push et de générer des messages in-app.
title: Prise en charge des suites de rapports virtuelles dans Mobile Services
uuid: 1b11279e-d0d8-48c5-a5b5-8020d5ed39da
translation-type: tm+mt
source-git-commit: 9193a520b13a0717a3383a32b39936f278c49d49

---


# Prise en charge des suites de rapports virtuelles dans Mobile Services

L’interface utilisateur d’Adobe Mobile Services combine les données sur les applications mobiles de vos suites de rapports Adobe Analytics et permet d’envoyer des notifications push et de générer des messages in-app.

## Prise en charge des suites de rapports virtuelles dans Mobile Services {#topic_1D0BABFA64EF42DE9C09B7AA37CACEC5}

L’interface utilisateur d’Adobe Mobile Services combine les données sur les applications mobiles de vos suites de rapports Adobe Analytics et permet d’envoyer des notifications push et de générer des messages in-app.

Adobe Mobile Services prend en charge les suites de rapports virtuelles. Si, toutefois, vous prévoyez de créer une suite de rapports virtuelle avec plusieurs applications et d’exécuter une activité de messagerie, spécifiez comme paramètre l’identifiant d’application individuel. Si vous créez un message Push, l’identifiant d’application doit être l’un des paramètres du segment que vous utilisez. Si vous créez un message in-app, l’identifiant d’application doit être l’un des paramètres des caractéristiques que vous établissez pour le message. Sinon, le message sera envoyé/déclenché vers tous les utilisateurs de toutes les applications qui répondent aux critères de segmentation/déclenchement.

Pour en savoir plus, voir [Suites de rapports virtuelles](https://docs.adobe.com/content/help/en/mobile-services/using/manage-apps-ug/c-mob-vrs.html) dans la documentation Adobe Mobile Services.
