---
description: Vérifiez si la bibliothèque de Dynamic Tag Management se charge correctement sur votre site.
keywords: Implémentation d'Analytics ; implementation method ; gestion dynamique des balises ; dtm ; code ; code de page ; code d'en-tête ; code de pied de page ; code incorporé ; vérifier le code ; verify header code ; vérifier le code de pied de page ; embed, panneau ; embed
seo-description: Vérifiez si la bibliothèque de Dynamic Tag Management se charge correctement sur votre site.
seo-title: Vérification du code d’en-tête et de pied de page
solution: Analytics
title: Vérification du code d’en-tête et de pied de page
topic: Développeur et mise en œuvre
uuid: d 395 a 417-0 c 61-41 a 6-a 124-d 2 f 400 f 4626 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Vérification du code d’en-tête et de pied de page

Vérifiez si la bibliothèque de Dynamic Tag Management se charge correctement sur votre site.

1. Ouvrez votre site dans votre navigateur.
1. Open the [!UICONTROL Developer Console] by right-clicking and choosing **[!UICONTROL Inspect Element]** &gt; **[!UICONTROL Console]**.
1. Press **[!UICONTROL Enter]**.

   If the code was properly installed, you will see *`true`* display in the console.

   Si le code n’a pas été correctement installé, l’erreur de référence suivante s’affiche :

   `_satellite is not defined`

   Si cette erreur s’affiche, vérifiez les points suivants :

* You have included the full header code on every page of the site in the [!DNL HEAD] section, as close to the [!DNL <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">] d’ouverture.
* Le fragment de code ne contient pas de caractères inattendus, pouvant provenir de la copie et du collage d’un document mis en forme.

