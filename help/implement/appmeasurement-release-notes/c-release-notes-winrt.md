---
description: valeur nulle
seo-description: valeur nulle
seo-title: WinRT pour Windows 8
solution: Analytics,Experience Cloud
subtopic: Notes de mise à jour
title: WinRT pour Windows 8
topic: Développeur et mise en œuvre
uuid: cec19d63-114c-4ef6-a55e-db6aad4e948b
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# WinRT pour Windows 8{#winrt-for-windows}

> [!NOTE] Pour connaître la version de la bibliothèque actuelle, activez la journalisation du débogage.

Mobile library [downloads](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) are available on [!DNL Developer Connection].

> [!NOTE] Le SDK [!DNL WinRT] pour [!DNL Windows] 8 est remplacé par le SDK [Windows 8.1 Universal App Store](../appmeasurement-release-notes/c-release-notes-winu.md#concept_79EEB87B0FEC4F6DB11BE8ED417A970E). Ce SDK ne sera désormais plus développé.

## Version 4.0 {#section_248BF5A38F1843A5BCF6DBD62A5D3D59}

Date de publication : **17 juin 2014**

Nouvelle version avec de nouvelles fonctionnalités comprenant la géolocalisation, la valeur de durée de vie, les actions temporisées et la prise en charge de l’inclusion.

## Version 3.1.1 {#section_6E925545B72240BB816DA2333CA93E46}

Date de publication : **22 mai 2014**

Correction de bogues et améliorations des performances.

## Version 3.1.0 {#section_F9059928B6FE43C99322A0DA35EB85C3}

Date de publication : **17 octobre 2013**

* [!DNL Windows]Compatibilité de 8.1

## Version 3.0.5 {#section_8F163FF1E88142F180091A88C9FD9D12}

Date de publication : **18 avril 2013**

* Correction d’un problème en raison duquel le calcul de la durée de la session précédente était parfois erroné.

## Version 3.0.4 {#section_FD242F9BA3D1481090E45998883E4CDD}

Date de publication : **21 mars 2013**

* `ADMS_Measurement.visitorID` est maintenant prérenseigné avec la valeur par défaut.
* Correction d’un problème lors de la récupération des informations sur le périphérique.

## Version 3.0.3 {#section_5865E881249441ADBB03A9637548650F}

Date de publication : **21 février 2013**

* Le paramètre `offlineThrottleDelay` est obsolète car il n’est plus nécessaire en raison de l’optimisation des threads. Ce paramètre existe toujours pour des raisons de compatibilité descendante, mais il n’a plus aucun effet.
* `DayOfWeek` est à présent de base 1 et commence le dimanche pour correspondre aux valeurs collectées sur les autres plateformes.
* Ajout de l’abonnement automatique aux écouteurs d’événements dans le fichier TrackingHelper.js pour simplifier le suivi du cycle de vie.

## Version 3.0.2 {#section_CCFAE5A29FB14DAD9A9F14FE8EE09B75}

Date de publication : **novembre 2012**

* La résolution de l’écran est maintenant récupérée de manière exacte pour les plateformes C#, C++ et HTML5/WinJS.
* La classe `ADMS_Churn` est maintenant interne. Pour utiliser de bonnes pratiques pour le suivi du cycle de vie des applications, utilisez les appels suivants :

   ```
   public void ADMS_Measurement.StartSession(); 
   public void ADMS_Measurement.StopSession();
   ```

* Ajout de la variable `public double maxSessionLength` à `ADMS_Measurement` afin que vous puissiez définir une durée de session maximale pour la session d’utilisateur précédente. Si la durée de la session enregistrée dépasse la durée maximale, la durée de la session maximale est envoyée. La valeur `maxSessionLength` par défaut est de 3 600 (secondes).
* Ajout d’une variable de configuration `lifecycleSessionTimeout` qui permet de spécifier la durée, en secondes, qui doit s’écouler entre les lancements d’une application avant qu’un lancement ne soit considéré comme une nouvelle session.
* Ajout de la nouvelle mesure Durée de la session précédente aux mesures de cycle de vie.
* Mise à jour de TrackingHelper pour plus de clarté.
* Correction d’un bogue dans le module média.

## Version 3.0.1 {#section_EA2E5F8550C348BDB948A9236BD35619}

**octobre 2012**

Version initiale.
