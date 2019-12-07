---
description: Il s’agit de caractères et de chaînes qui sont interdits dans les variables JavaScript.
keywords: Analytics Implementation
subtopic: Variables
title: Caractères JavaScript interdits
topic: Developer and implementation
uuid: 04e3b4b4-7ff5-4673-8060-34302b6ee545
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Caractères JavaScript interdits

Il s’agit de caractères et de chaînes qui sont interdits dans les variables JavaScript.

* Tabulation (0x09)
* Retour chariot (0x0D)
* Nouvelle ligne (0x0A)
* Caractères ASCII dont les codes sont supérieurs à 127 (sauf si les caractères à plusieurs octets sont activés et si *`charSet`* est renseigné de manière appropriée)
* Balises HTML (<b></b> ou &amp;#153, par exemple)

D’autres restrictions ou exigences syntaxiques s’appliquent à de nombreuses variables ; et plus particulièrement à « products », « hierarchy » et « events ». Pour plus d’informations à ce sujet, consultez la section relative aux paramètres de la variable *`s_account`*.
