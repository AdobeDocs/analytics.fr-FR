---
description: Spécifiez un lien d’exclusion et personnalisez-le. Il se peut que les visiteurs de votre site Web ne souhaitent pas que leurs activités fassent l’objet d’un suivi dans les produits d’analyse d’Adobe. Dans ce cas, ils peuvent consulter la page d’exclusion de votre domaine de collecte de données.
keywords: Mise en œuvre d’Analytics
seo-description: Spécifiez un lien d’exclusion et personnalisez-le. Il se peut que les visiteurs de votre site Web ne souhaitent pas que leurs activités fassent l’objet d’un suivi dans les produits d’analyse d’Adobe. Dans ce cas, ils peuvent consulter la page d’exclusion de votre domaine de collecte de données.
seo-title: Ajout d'un lien d'exclusion
solution: Analytics
subtopic: Résolution des problèmes
title: Ajout d'un lien d'exclusion
topic: Développeur et mise en œuvre
uuid: c 12092 be -3 be 7-4621-b 838-d 6 b 78 d 074 f 84
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Ajout d'un lien d'exclusion

Spécifiez un lien d’exclusion et personnalisez-le. Il se peut que les visiteurs de votre site Web ne souhaitent pas que leurs activités fassent l’objet d’un suivi dans les produits d’analyse d’Adobe. Dans ce cas, ils peuvent consulter la page d’exclusion de votre domaine de collecte de données.

Si un utilisateur choisit de ne pas faire l’objet d’un suivi et qu’un cookie d’exclusion est défini, votre fichier JavaScript continue à envoyer des données aux serveurs Adobe. Cependant, ces données ne seront ni traitées, ni reprises dans des rapports.

La section domaine_collecte de la structure URL correspond au serveur de suivi (trackingServer) utilisé dans votre fichier JavaScript. Le domaine de collecte de votre mise en œuvre Adobe Analytics est visible dans le DigitalPulse Debugger, dans la première ligne du tableau Adobe Analytics, libellée « Cookies propriétaires » ou « Cookies tiers » en fonction de votre mise en œuvre. Le domaine de collecte de votre site Web peut contenir 2o7.net, omtrdc.net ou le domaine de votre site Web ; metrics.exemple.com, par exemple.

Pour s’exclure, les visiteurs doivent cliquer sur le lien de la page d’exclusion, ce qui entraîne le placement d’un cookie dans leur navigateur. Compte tenu de la définition du cookie `omniture_optout` pour le domaine de suivi concerné, les activités de l’utilisateur ne feront pas l’objet d’un suivi dans Adobe Analytics. Vous pouvez fournir votre propre lien vers le cookie d’exclusion ou suivre la procédure ci-dessous pour définir ce cookie.

Adobe propose des exclusions pour tous les types d’implémentation. Vous êtes responsable de votre propre politique de confidentialité, ainsi que du respect continu des conditions que vous avez signées. Notez que le lien vers la page d’exclusion varie en fonction de votre type d’implémentation, comme indiqué ici.

Si vous implémentez des services et produits Adobe Analytics avec des cookies définis sur des domaines dont Adobe est propriétaire (à savoir, 207.net ou omtrdc.net), vous pouvez diriger les visiteurs de votre site Web vers le mécanisme d’exclusion fourni dans le [Centre de traitement des données personnelles d’Adobe](https://www.adobe.com/privacy/opt-out.html) pour tous les sites qui utilisent des cookies Adobe pour les produits et services Adobe Analytics. The direct link to the Adobe opt-out mechanism is `https:// *collection_domain* /optout.html`.

More information about Adobe Analytics privacy practices can be found at [https://www.adobe.com/privacy/advertising-services.html](https://www.adobe.com/privacy/advertising-services.html).

* [Structure de l’URL de la page d’exclusion](../../../implement/js-implementation/data-collection/opt-out-link.md#section_E0462428D2E440E7863E24D2F6DBF748)
* [Exemples d’URL d’exclusion](../../../implement/js-implementation/data-collection/opt-out-link.md#section_258DE5226AA0483CA790D2C9C5318B2E)
* [Personnalisation de l’URL d’exclusion](../../../implement/js-implementation/data-collection/opt-out-link.md#section_674AB62E810B414AB8F1615C0E3061F8)

## Structure de l’URL de la page d’exclusion {#section_E0462428D2E440E7863E24D2F6DBF748}

Votre page d’exclusion se trouve à l’adresse URL suivante :

```
https://collection_domain/optout.html[?optional_parameters]
```

The `optional_parameters` include:

`locale=[code]`: Fournit une version traduite de la page d'exclusion. Les paramètres régionaux ci-dessous sont pris en charge :

* en_US (par défaut)
* de_DE
* es_ES
* fr_FR
* jp_JP
* ko_KR
* zh_CN
* zh_TW

`popup=1` : considère la page comme s’il s’agissait d’une fenêtre contextuelle et propose un bouton « Fermer la fenêtre ».

## Exemples d’URL d’exclusion {#section_258DE5226AA0483CA790D2C9C5318B2E}

Page Web en anglais affichée dans une fenêtre entière. Elle contient un lien qui, en cas de sélection, désactive le suivi du visiteur sur metrics.example.com :

```
https://metrics.example.com/optout.html
```

Page Web en français affichée dans une fenêtre entière. Elle contient un lien qui, en cas de sélection, désactive le suivi du visiteur sur example.d3.sc.omtrdc.net :

```
https://example.d3.sc.omtrdc.net/optout.html?locale=fr_FR
```

Page Web en allemand affichée dans une fenêtre contextuelle. Elle contient un lien qui, en cas de sélection, désactive le suivi du visiteur sur example.112.2o7.net :

```
https://example.112.2o7.net/optout.html?popup=1&locale=de_DE
```

## Personnalisation de l’URL d’exclusion {#section_674AB62E810B414AB8F1615C0E3061F8}

Vous pouvez ajouter à votre site Web un lien, comme ci-après :

```
 <a href=" https://stats.adobe.com/optout.html?optout=1&confirm_change=1">
Click Here to Opt Out! </a>
```

où *`stats.adobe.com`* est remplacée par *`s.trackingServer`* la variable définie.

Additionally, if you want like to provide a link to opt-in, use the same URL, but replace `?optout=1` with `?optin=1`, and keep the `confirm_change=1`.
