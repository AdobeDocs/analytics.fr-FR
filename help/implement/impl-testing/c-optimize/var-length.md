---
description: La longueur des variables Analytics peut avoir une incidence sur la taille du fragment de code HTML, du fichier de bibliothèque JavaScript et de la demande d’image.
keywords: Analytics Implementation
solution: Analytics
subtopic: Troubleshooting
title: Longueur des variables
topic: Developer and implementation
uuid: 87deabb3-2acb-4797-9a65-769d9e2fbd62
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Longueur des variables

La longueur des variables Analytics peut avoir une incidence sur la taille du fragment de code HTML, du fichier de bibliothèque JavaScript et de la demande d’image.

Si un client possède de nombreuses variables longues (60 caractères ou plus), les valeurs peuvent être remplacées par des identifiants plus courts. Il est possible d’utiliser des classifications de données ou des règles VISTA pour convertir les identifiants en noms conviviaux.

> [!NOTE] La plupart des variables Analytics comportent, au maximum, 100 caractères (la taille maximale des eVars est de 255 caractères). Internet Explorer autorise un maximum de 2 048 caractères dans une URL de demande d’image GET. La limite de demande d’image s’applique non seulement aux variables, mais aussi aux informations sur le navigateur, le système d’exploitation et les plug-ins du navigateur (Netscape/Mozilla uniquement).

