---
title: Paramètres de requête de la collecte de données
description: Répertorie tous les paramètres de chaîne de requête utilisés dans les demandes d’image.
translation-type: tm+mt
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440

---


# Paramètres de requête de la collecte de données

Le tableau suivant répertorie tous les paramètres de chaîne de requête utilisés par Adobe dans les demandes d’image. Ces informations peuvent être utilisées lors du débogage à l’aide des analyseurs [de](packet-monitor.md)paquets, lors du [codage en dur des demandes](../other/hardcoded.md)d’image ou lors de l’utilisation de variables [](../vars/page-vars/dynamic-variables.md)dynamiques.

| Paramètre | Variable d’implémentation Analytics | Description |
| --- | --- | --- |
| `aamlh` | Aucun | Indicateur d’emplacement d’Audience Manager. Utilisé dans l’intégration du profil partagé Experience Cloud. |
| `aamb` | Aucun | BLOB Audience Manager. Utilisé dans l’intégration du profil partagé Experience Cloud. |
| `aid` | Aucun | Identifiant visiteur Analytics. |
| `AQB` | Aucun | Indique le début d’une chaîne de requête de demande d’image. |
| `AQE` | Aucun | Indique la fin d’une demande d’image, ce qui signifie que la demande n’a pas été tronquée. |
| `bh` | Aucun | Hauteur du navigateur (en pixels). Utilisé dans la dimension Hauteur du navigateur. |
| `bw` | Aucun | Largeur du navigateur (en pixels). Utilisé dans la dimension Largeur du navigateur. |
| `c` | Aucun | Qualité des couleurs (en bits). Utilisé dans la dimension Profondeur de couleur. |
| `c.` | `contextData` | Indique le début des variables de données contextuelles. Ne contient jamais de valeur. |
| `.c` | `contextData` | Indique la fin des variables de données contextuelles. Ne contient jamais de valeur. |
| `c1` - `c75` | `prop1` - `prop75` | Variables de trafic personnalisées. |
| `cc` | `currencyCode` | Type de devise utilisé dans l’accès. |
| `cdp` | `cookieDomainPeriods` | Nombre de points dans un domaine. Permet de stocker correctement les cookies. |
| `ce` | `charSet` | Codage de caractères de la demande d’image. |
| `cl` | `cookieLifetime` | Durée de vie du cookie visiteur. |
| `ch` | `channel` | Utilisé dans la dimension Sections du site. |
| `cp` | Aucun | Utilisée dans la dimension Type d’accès. |
| `ct` | Aucun | Utilisé dans la dimension Type de connexion. |
| `D` | `dynamicVariablePrefix` | Indique ce qu’il faut utiliser pour les variables dynamiques. |
| `ev` | `events` | Raccourci pour la chaîne de `events` requête. |
| `events` | `events` | Liste d’événements séparés par des virgules sur la page. |
| `g` | `pageURL` | URL de la page activejusqu’à 255 octets |
| `-g` | `pageURL` | Les URL de plus de 255 octets sont fractionnées. Les 255 premiers octets apparaissent dans le `g` paramètre et tous les autres dans le `-g` paramètre. |
| `gn` | `pageName` | Raccourci pour la chaîne de `pageName` requête. |
| `gt` | `pageType` | Raccourci pour la chaîne de `pageType` requête. |
| `h1` - `h5` | `hier1` - `hier5` | Variables de hiérarchie. |
| `hp` | Aucun | N’est plus utilisé. Dans les versions précédentes d’Adobe Analytics, déterminez si l’URL active était la page d’accueil du navigateur. |
| `j` | Aucun | Version JavaScript installée dans le navigateur. |
| `k` | Aucun | Utilisé dans la dimension Prise en charge des cookies. |
| `l1` - `l3` | `list1` - `list3` | Répertorier les variables. |
| `mid` | Aucun | Identifiant visiteur Experience Cloud. |
| `ndh` | Aucun | Indicateur précisant si la demande d’image provient d’AppMeasurement. |
| `ns` | `visitorNameSpace` | Permet de déterminer l’emplacement des cookies. |
| `oid` | `objectID` | Identificateur d’objet de la dernière page. Utilisée dans Carte d’activités. |
| `ot` | Aucun | Nom d’objet de la dernière page. Utilisé dans les versions précédentes de Carte d’activités. |
| `p` | Aucun | N’est plus utilisé. Liste des plug-ins utilisés dans le navigateur. |
| `pageName` | `pageName` | Utilisé dans la dimension Page. |
| `pageType` | `pageType` | Utilisé dans la dimension Pages introuvables. |
| `pccr` | Aucun | Défini uniquement pour les nouveaux visiteurs et toujours sur `true`. Empêche les redirections infinies. |
| `pe` | `linkType` | Détermine le type de lien personnalisé. |
| `pev1` | Aucun | URL sur laquelle le lien personnalisé s’est produit. |
| `pev2` | Aucun | Nom convivial du lien personnalisé. |
| `pev3` | Aucun | N’est plus utilisé. jalons suivis dans les versions précédentes des rapports vidéo. |
| `pf` | Aucun | Indicateur de plateforme; pour utilisation par Adobe uniquement. Ne pas modifier. |
| `pid` | Aucun | Identifiant de page pour la dernière page. Utilisé dans les versions précédentes de Carte d’activités. |
| `pidt` | Aucun | Type d’identificateur de page pour la dernière page. Utilisé dans les versions précédentes de Carte d’activités. |
| `pl` | `products` | Raccourci pour la chaîne de `products` requête. |
| `products` | `products` | Variable products. |
| `purchaseID` | `purchaseID` | Permet de dédupliquer les achats. |
| `r` | `referrer` | URL de référence de l’accès. |
| `s` | Aucun | Utilisé dans la dimension Résolutions de l’écran. Résolution d’écran, dans `width x height`. |
| `server` | `server` | Dimension serveur. |
| `sv` | `server` | Raccourci pour la chaîne de `server` requête. |
| `state` | `state` | Dimension d’état. |
| `t` | Aucun | Date/heure générée de l’accès. Utilise le format `dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss` est date/heure dans JavaScript. Le mois `0` est janvier, tandis que le mois `11` est décembre.<br>- `w` est le jour de la semaine. `0` est le dimanche, tandis que `6` le samedi.<br>- `o` est le décalage GMT négatif en minutes. Par exemple, `420` est GMT-7. |
| `ts` | `timestamp` | L’horodatage personnalisé défini avec l’accès. Généralement utilisé pour le suivi hors ligne. |
| `v` | Aucun | Utilisé dans la dimension Java Enabled. |
| `v0` | `campaign` | Dimension Code de suivi. |
| `v1` - `v250` | `evar1` - `eVar250` | Dimensions de conversion personnalisées. |
| `vid` | `visitorID` | Variable d’identifiant visiteur. |
| `vmk` | `vmk` | N’est plus utilisé. Permet la migration de cookies tiers vers des cookies propriétaires. |
| `vvp` | `variableProvider` | Utilisé dans les connecteurs de données. |
| `xact` | `transactionID` | Utilisé avec la fonctionnalité Sources de données pour lier des données ensemble. |
| `zip` | `zip` | Utilisé dans la dimension Code postal. |
