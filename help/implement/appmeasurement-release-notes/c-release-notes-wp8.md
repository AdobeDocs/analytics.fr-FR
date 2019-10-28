---
description: valeur nulle
seo-description: valeur nulle
seo-title: Windows Phone 8
solution: Analytics,Experience Cloud
subtopic: Notes de mise à jour
title: Windows Phone 8
topic: Développeur et mise en œuvre
uuid: 7378969a-d219-42bf-9750-141acc9e4b7d
translation-type: ht
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Windows Phone 8{#windows-phone}

>[!NOTE]
>
>Pour connaître la version de la bibliothèque actuelle, activez la journalisation du débogage.

Les [téléchargements]( de la bibliothèque mobile https://marketing.adobe.com/developer/fr/get-started/mobile/c-measuring-mobile-applications) sont disponibles sur [!DNL Developer Connection].

>[!NOTE]
>
>Le SDK [!DNL Windows] Phone 8 est remplacé par le SDK [Windows 8.1 Universal App Store](../appmeasurement-release-notes/c-release-notes-winu.md). Ce SDK ne sera désormais plus développé.

## Version 3.0.4 {#section_51A8A53CDFB24F6F9D882E9C30ECDB49}

Date de publication : **21 août 2013**

* Les clés de données contextuelles acceptent maintenant les traits de soulignement.

## Version 3.0.5 {#section_DFE58939E33C447FBBF8B04E612A96B5}

Date de publication : **22 mai 2013**

* Correction de bogues et améliorations des performances.

## Version 3.0.4 {#section_F303B6E5955248CF8BDA6C7CB994BAD5}

Date de publication : **18 avril 2013**

* Correction d’un problème en raison duquel le calcul de la durée de la session précédente était parfois erroné.

## Version 3.0.3 {#section_0159586C3EC94865A485A8E586862DF6}

Date de publication : **21 mars 2013**

* Correction d’un problème de localisation avec les objets `DateTime`.

## Version 3.0.2 {#section_296C375729EA4474BDF3FD6ADD4BEAFB}

Date de publication : **26 février 2013**

* `ADMS_Measurement.visitorID` est maintenant prérenseigné avec la valeur par défaut.
* Correction d’un problème en raison duquel des réponses automatiques étaient parfois envoyées à partir de la mémoire cache.

## Version 3.0.1 {#section_5865E881249441ADBB03A9637548650F}

Date de publication : **21 février 2013**

* Le paramètre `offlineThrottleDelay` est obsolète car il n’est plus nécessaire en raison de l’optimisation des threads. Ce paramètre existe toujours pour des raisons de compatibilité descendante, mais il n’a plus aucun effet.
* `DayOfWeek` est à présent de base 1 et commence le dimanche pour correspondre aux valeurs collectées sur les autres plateformes.
* Correction d’un problème lié au stockage hors ligne qui entraînait parfois un blocage de l’application.

