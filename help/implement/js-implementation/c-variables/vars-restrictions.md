---
description: Il s’agit de caractères et de chaînes qui sont interdits dans les variables JavaScript.
keywords: Mise en œuvre d’Analytics
seo-description: Il s’agit de caractères et de chaînes qui sont interdits dans les variables JavaScript.
seo-title: Caractères JavaScript interdits
solution: Analytics
subtopic: Variables
title: Caractères JavaScript interdits
topic: Développeur et mise en œuvre
uuid: 04 e 3 b 4 b 4-7 ff 5-4673-8060-34302 b 6 ee 545
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Caractères JavaScript interdits

Il s’agit de caractères et de chaînes qui sont interdits dans les variables JavaScript.

* Tabulation (0x09)
* Retour chariot (0x0D)
* Nouvelle ligne (0x0A)
* Caractères ASCII dont les codes sont supérieurs à 127 (sauf si les caractères à plusieurs octets sont activés et si *`charSet`* est renseigné de manière appropriée)
* HTML tags (e.g. <b></b> or &amp;#153)

D’autres restrictions ou exigences syntaxiques s’appliquent à de nombreuses variables ; et plus particulièrement à « products », « hierarchy » et « events ». Pour plus d’informations à ce sujet, consultez la section relative aux paramètres de la variable *`s_account`*.
