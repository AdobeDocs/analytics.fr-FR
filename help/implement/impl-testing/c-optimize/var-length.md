---
description: La longueur des variables Analytics peut avoir une incidence sur la taille du fragment de code HTML, du fichier de bibliothèque JavaScript et de la demande d’image.
keywords: Mise en œuvre d’Analytics
seo-description: La longueur des variables Analytics peut avoir une incidence sur la taille du fragment de code HTML, du fichier de bibliothèque JavaScript et de la demande d’image.
seo-title: Longueur des variables
solution: Analytics
subtopic: Résolution des problèmes
title: Longueur des variables
topic: Développeur et mise en œuvre
uuid: 87deabb3-2acb-4797-9a65-769d9e2fbd62
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Longueur des variables

La longueur des variables Analytics peut avoir une incidence sur la taille du fragment de code HTML, du fichier de bibliothèque JavaScript et de la demande d’image.

Si un client possède de nombreuses variables longues (60 caractères ou plus), les valeurs peuvent être remplacées par des identifiants plus courts. Il est possible d’utiliser des classifications de données ou des règles VISTA pour convertir les identifiants en noms conviviaux.

> [!NOTE] La plupart des variables Analytics comportent, au maximum, 100 caractères (la taille maximale des eVars est de 255 caractères). Internet Explorer autorise un maximum de 2 048 caractères dans une URL de demande d’image GET. La limite de demande d’image s’applique non seulement aux variables, mais aussi aux informations sur le navigateur, le système d’exploitation et les plug-ins du navigateur (Netscape/Mozilla uniquement).

