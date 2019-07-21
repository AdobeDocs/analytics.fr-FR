---
description: La longueur des variables Analytics peut avoir une incidence sur la taille du fragment de code HTML, du fichier de bibliothèque JavaScript et de la demande d’image.
keywords: Mise en œuvre d’Analytics
seo-description: La longueur des variables Analytics peut avoir une incidence sur la taille du fragment de code HTML, du fichier de bibliothèque JavaScript et de la demande d’image.
seo-title: Longueur de variable
solution: Analytics
subtopic: Résolution des problèmes
title: Longueur de variable
topic: Développeur et mise en œuvre
uuid: 87 deabb 3-2 acb -4797-9 a 65-769 d 9 e 2 fbd 62
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# Longueur de variable

La longueur des variables Analytics peut avoir une incidence sur la taille du fragment de code HTML, du fichier de bibliothèque JavaScript et de la demande d’image.

Si un client possède de nombreuses variables longues (60 caractères ou plus), les valeurs peuvent être remplacées par des identifiants plus courts. Il est possible d’utiliser des classifications de données ou des règles VISTA pour convertir les identifiants en noms conviviaux.

>[!NOTE]
>
>La plupart des variables Analytics comportent un maximum de 100 caractères (les evars ont un maximum de 255). Internet Explorer autorise un maximum de 2 048 caractères dans une URL de demande d’image GET. La limite de demande d’image s’applique non seulement aux variables, mais aussi aux informations sur le navigateur, le système d’exploitation et les plug-ins du navigateur (Netscape/Mozilla uniquement).

