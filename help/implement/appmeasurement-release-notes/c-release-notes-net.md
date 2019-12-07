---
description: valeur nulle
subtopic: Release notes
title: Windows Silverlight, NET, IIS, XBOX
topic: Developer and implementation
uuid: 15c20bca-4886-4d57-9957-fe99743851ea
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Windows Silverlight, NET, IIS, XBOX{#windows-silverlight-net-iis-xbox}

>[!IMPORTANT]
>
>Ces kits SDK ont été supprimés et ne sont plus pris en charge ou distribués par Adobe.

> [!NOTE] Pour connaître la version de la bibliothèque actuelle, activez la journalisation du débogage.

## Version 1.4.2 {#section_2B70F52C4D214A43844CCEC6B45037F0}

Date de publication : **août 2014**

* Suppression de la prise en charge pour [!DNL Microsoft Silverlight Analytics Framework]. Adobe ne prend plus en charge et ne distribue plus l’intégration de [!DNL Microsoft Silverlight Analytics Framework] pour [!DNL AppMeasurement].

* Changements internes pour la prise en charge des fonctions à venir.

## Version 1.4.1 {#section_9134F77804BF472291DA7243FAC89C2B}

Date de publication : **mars 2013**

* Correction de l’exception lors de l’obtention du référent par défaut dans [!DNL Silverlight] en dehors d’un contexte de navigateur et correctement exposé à la propriété SSL dans le composant [!DNL Microsoft Silverlight Analytics Framework].

## Version 1.4 {#section_2F4ADA4628EC43B480177C3DDB3D1CFA}

Date de publication : **février 2013**

* Prise en charge de l’envoi d’URL de plus de 255 octets pour gérer l’extension du champ URL de page dans les serveurs de collecte de données Adobe. Les URL de page de plus de 255 octets sont fractionnées, les 255 premiers octets apparaissant dans le paramètre `g=`, les autres apparaissant plus tard dans la chaîne de requête dans le paramètre de `-g=`. Ceci permet d’éviter que les longues URL ne prévalent sur d’autres données en cas de troncation de navigateur, tout en permettant la saisie de longues URL.

* Ajout d’une nouvelle méthode d’identification des visiteurs de secours. Voir [Identification des visiteurs uniques](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_identifying_unique_visitors.html).
* Ajout d’un nouvel indicateur `abort` qui peut être défini dans `doPlugins`. Si ce paramètre est défini sur vrai, la bibliothèque [!DNL AppMeasurement] ne poursuit pas cet appel de suivi. L’indicateur abort est réinitialisé à chaque appel de suivi, de sorte que si un appel de suivi consécutif doit également être abandonné, l’indicateur devra être redéfini dans `doPlugins`.

   ```js
   s.doPlugins = function(s) { 
        s.campaign = s.getQueryParam("cid"); 
        if ((!s.campaign) && (!s.events)) { 
             s.abort = true; 
        } 
   };
   ```

   Ceci vous permet de centraliser la logique à utiliser pour identifier l’activité que vous ne souhaitez pas suivre, comme certains liens personnalisés ou liens externes dans les annonces affichées.

## Version 1.3.8 {#section_03089199E2DE4199B32F6821DDAED7BD}

Date de publication : **septembre 2012**

* Correction d’un problème en raison duquel l’événement vidéo terminé n’était parfois pas envoyé lors de l’utilisation d’une méthode `media.monitor` personnalisée qui contrôle l’événement de fermeture multimédia :

   ```
   If(media.event=="CLOSE") { 
   … 
   } 
   ```

## Version 1.3.7 {#section_32AA8AE0CED4495496D25BF9246AE8AB}

Date de publication : **avril 2012**

* Ajout de la prise en charge de la [!DNL XBOX].

## Version 1.3.6 {#section_9F2738FA31CD48C4877AB92281EC67A9}

Date de publication : **février 2012**

* [!DNL iOS] Phone 7 : correction d’un problème en raison duquel le paramètre offlineThrottleDelay ne s’appliquait pas correctement.
* Ajout d’un horodatage aux variables utilisées avec les appels de suivi légers (trackLight).

## Version 1.3.5 {#section_28BBDE7D187547A4AACCA60E5154DCD2}

Date de publication : **janvier 2012**

* Mise à jour du suivi vidéo avec une nouvelle méthode permettant le suivi des affichages complets de vidéos. Voir [Mesure de vidéos dans Adobe Analytics](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/index.html).

## Version 1.3.4 {#section_43788EE6B57E4B2DBEED68BE6954D9CA}

* Nouvelle prise en charge et version pour la plateforme [!DNL iOS] Phone incluant le suivi hors ligne.
* Prise en charge du remplacement de l’envoi des requêtes par le délégué doRequest pour le suivi des données.
* Prise en charge des données contextuelles qui pilotent les règles de traitement côté serveur (v15 uniquement).
* Prise en charge des appels de serveur léger (bêta).
* Prise en charge de l’affectation d’une valeur autre que 1 pour un compteur d’événement dans la liste des événements.
* Prise en charge d’une nouvelle méthode de suivi vidéo utilisant les eVars et événements de conversion (bêta).

