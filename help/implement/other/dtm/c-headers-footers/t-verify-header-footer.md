---
description: Vérifiez si la bibliothèque de Dynamic Tag Management se charge correctement sur votre site.
keywords: Mise en œuvre d’Analytics;méthode de mise en œuvre;Dynamic Tag Management;dtm;code;code page;code d’en-tête;code de pied de page;code intégré;vérifier le code;vérifier le code d’en-tête;vérifier le code de pied de page;onglet incorporer;incorporer
title: Vérification du code d’en-tête et de pied de page
topic: Developer and implementation
uuid: d395a417-0c61-41a6-a124-d2f400f4626f
translation-type: tm+mt
source-git-commit: 82cf5ddfd4d18af09c2dbedba20514e4b643a94b
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 100%

---


# Vérification du code d’en-tête et de pied de page

Vérifiez si la bibliothèque de Dynamic Tag Management se charge correctement sur votre site.

1. Ouvrez votre site dans votre navigateur.
1. Pour ouvrir la [!UICONTROL console de développement], cliquez avec le bouton droit, puis sélectionnez **[!UICONTROL Contrôler un élément]** > **[!UICONTROL Console]**.
1. Appuyez sur **[!UICONTROL Entrée]**.

   Si le code a été correctement installé, vous verrez *`true`* s’afficher dans la console.

   Si le code n’a pas été correctement installé, l’erreur de référence suivante s’affiche :

   `_satellite is not defined`

   Si cette erreur s’affiche, vérifiez les points suivants :

* Vous avez ajouté le code d’en-tête complet à la section [!DNL HEAD] de chaque page du site, en le plaçant aussi près que possible de la balise `<head>` d’ouverture.
* Le fragment de code ne contient pas de caractères inattendus, pouvant provenir de la copie et du collage d’un document mis en forme.

