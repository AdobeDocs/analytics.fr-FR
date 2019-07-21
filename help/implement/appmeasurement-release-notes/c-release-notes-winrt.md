---
description: valeur nulle
seo-description: valeur nulle
seo-title: WinRT pour Windows 8
solution: Analytics, Marketing Cloud
subtopic: Notes de mise à jour
title: WinRT pour Windows 8
topic: Développeur et mise en œuvre
uuid: cec 19 d 63-114 c -4 ef 6-a 55 e-db 6 aad 4 e 948 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# WinRT pour Windows 8{#winrt-for-windows}

>[!NOTE]
>
>Pour trouver la version de la bibliothèque actuelle, activez la journalisation du débogage.

[Les téléchargements](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) de bibliothèque mobile sont disponibles [!DNL Developer Connection].

>[!NOTE]
>
>The [!DNL WinRT] for [!DNL Windows] 8 SDK is replaced by the [Windows 8.1 Universal App Store](../appmeasurement-release-notes/c-release-notes-winu.md#concept_79EEB87B0FEC4F6DB11BE8ED417A970E) SDK. Ce SDK ne sera désormais plus développé.

## Version 4.0 {#section_248BF5A38F1843A5BCF6DBD62A5D3D59}

Date de publication : **17 juin 2014**

Nouvelle version avec de nouvelles fonctionnalités comprenant la géolocalisation, la valeur de durée de vie, les actions temporisées et la prise en charge de l’inclusion.

## Version 3.1.1 {#section_6E925545B72240BB816DA2333CA93E46}

Date de publication : **22 mai 2014**

Correction de bogues et améliorations des performances.

## Version 3.1.0 {#section_F9059928B6FE43C99322A0DA35EB85C3}

Date de publication : **17 octobre 2013**

* [!DNL Windows] Compatibilité 8.1

## Version 3.0.5 {#section_8F163FF1E88142F180091A88C9FD9D12}

Date de publication : **18 avril 2013**

* Correction d’un problème en raison duquel le calcul de la durée de la session précédente était parfois erroné.

## Version 3.0.4 {#section_FD242F9BA3D1481090E45998883E4CDD}

Date de publication : **21 mars 2013**

* `ADMS_Measurement.visitorID` est désormais prérenseignée avec la valeur par défaut.
* Correction d’un problème lors de la récupération des informations sur le périphérique.

## Version 3.0.3 {#section_5865E881249441ADBB03A9637548650F}

Date de publication : **21 février 2013**

* Le paramètre `offlineThrottleDelay` est obsolète car il n’est plus nécessaire en raison de l’optimisation des threads. Ce paramètre existe toujours pour des raisons de compatibilité descendante, mais il n’a plus aucun effet.
* `DayOfWeek` est à présent de base 1 et commence le dimanche pour correspondre aux valeurs collectées sur les autres plateformes.
* Ajout de l’abonnement automatique aux écouteurs d’événements dans le fichier TrackingHelper.js pour simplifier le suivi du cycle de vie.

## Version 3.0.2 {#section_CCFAE5A29FB14DAD9A9F14FE8EE09B75}

Date de publication : **novembre 2012**

* La résolution de l’écran est maintenant récupérée de manière exacte pour les plateformes C#, C++ et HTML5/WinJS.
* `ADMS_Churn` est désormais interne. Pour utiliser de bonnes pratiques pour le suivi du cycle de vie des applications, utilisez les appels suivants :

   ```
   public void ADMS_Measurement.StartSession(); 
   public void ADMS_Measurement.StopSession();
   ```

* Added `public double maxSessionLength` variable to `ADMS_Measurement` to allow you to set a maximum session length for the previous user session. Si la durée de la session enregistrée dépasse la durée maximale, la durée de la session maximale est envoyée. Default `maxSessionLength` is 3600 (seconds).
* Ajout d’une variable de configuration `lifecycleSessionTimeout` qui permet de spécifier la durée, en secondes, qui doit s’écouler entre les lancements d’une application avant qu’un lancement ne soit considéré comme une nouvelle session.
* Ajout de la nouvelle mesure Durée de la session précédente aux mesures de cycle de vie.
* Mise à jour de TrackingHelper pour plus de clarté.
* Correction d’un bogue dans le module média.

## Version 3.0.1 {#section_EA2E5F8550C348BDB948A9236BD35619}

**octobre 2012**

Version initiale.
