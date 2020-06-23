---
description: Vérifiez si la bibliothèque de Dynamic Tag Management se charge correctement sur votre site.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;code;page code;header code;footer code;embed code;verify code;verify header code;verify footer code;embed tab;embed
title: Vérification du code d’en-tête et de pied de page
topic: Developer and implementation
uuid: d395a417-0c61-41a6-a124-d2f400f4626f
translation-type: ht
source-git-commit: ebf149df7974f9f2889b6fe938088eda90c84051

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

* Vous avez ajouté le code d’en-tête complet à la section [!DNL HEAD] de chaque page du site, en le plaçant aussi près que possible de la balise [!DNL <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">] d’ouverture.
* Le fragment de code ne contient pas de caractères inattendus, pouvant provenir de la copie et du collage d’un document mis en forme.

