---
title: ID AMO
description: Identifiant Adobe Media Optimizer, utilisé dans les intégrations Adobe Advertising.
feature: Dimensions
source-git-commit: 408d8db0d1e3c8301a066fe54d611ec7b8e3418a
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 3%

---

# ID AMO

L’**[!UICONTROL AMO ID]** est un ensemble d’identifiants concaténés utilisés dans les intégrations d’Adobe Advertising. Les valeurs stockées dans cette dimension sont automatiquement organisées en dimensions de classification distinctes, plus lisibles par l’utilisateur, à utiliser dans les rapports Analytics. La dimension est automatiquement créée lors de l’activation de l’intégration [Analytics pour Advertising](https://experienceleague.adobe.com/fr/docs/advertising/integrations/analytics/overview).

## Renseignement de cette dimension avec des données

Cette dimension collecte ses valeurs de plusieurs manières :

* Pour le trafic de clics publicitaires, les données sont collectées à partir du paramètre de chaîne de requête `s_kwcid` dans l’[URL de la page](page-url.md), généralement sur la page par laquelle le trafic piloté par les annonces accède au site.
* Le trafic de clics publicitaires peut également être capturé lorsque l’URL ne contient pas de codes de suivi, mais que le JavaScript Adobe Advertising détecte un clic au cours des deux minutes précédentes.
* Pour le trafic d’affichage publicitaire pris en charge, Adobe Advertising complète les valeurs sur le serveur principal à l’aide d’un ID supplémentaire (`SDID`).

## Éléments de dimension

Les éléments Dimension incluent des identifiants AMO, également appelés valeurs `s_kwcid`. Le format exact varie selon que le trafic provient de DSP ou de Search, Social et Commerce. Les identifiants AMO sont moins granulaires que les identifiants EF et sont principalement utilisés pour les classifications et l’ingestion de mesures Adobe Advertising dans Analytics.

### DSP

```text
AC!{ad key}!{placement key}
```

* **`AC`** : indique le canal d’affichage.
* **`ad key`** : identifiant alphanumérique généré par Adobe Advertising pour la publicité.
* **`placement key`** : identifiant alphanumérique généré par Adobe Advertising pour l’emplacement.

Exemple de valeur :

```text
AC!iIMvXqlOa6Nia2lDvtgw!GrVv6o2oV2qQLjQiXLC7
```

### Publicités Search, Social et Commerce

Les identifiants AMO Search, Social et Commerce commencent par `AL`, suivis de l’identifiant utilisateur de l’annonceur, de l’identifiant du compte réseau publicitaire, puis des identifiants spécifiques au réseau. Les identifiants de compte réseau et partagé sont les suivants :

* **`3`** : Google Ads
* **`10`** : MICROSOFT ADVERTISING
* **`45`** : META
* **`86`** : Yahoo ! Afficher le réseau
* **`87`** : Naver
* **`88`** : Baidu
* **`90`** : Yandex
* **`94`** : Yahoo ! Publicités pour le Japon
* **`105`** : Yahoo Native (obsolète)
* **`106`** : Pinterest (obsolète)

#### Google Ads

Google Ads utilise deux formats associés. Les comptes plus récents peuvent inclure l’identifiant de campagne et l’identifiant du groupe publicitaire, qui prennent en charge les rapports au niveau de la campagne et du groupe publicitaire pour les campagnes Performance Max et les campagnes de brouillons/expériences.

```text
AL!{user}!3!{creative}!{matchtype}!{placement}!{network}!{product partition}!{keyword}[!{campaign id}!{ad group id}]
```

* **`creative`** : identifiant créatif Google Ads.
* **`matchtype`** : type de correspondance de mot-clé (`e` pour exact, `p` pour l’expression, `b` pour large).
* **`placement`** : domaine sur lequel l’utilisateur ou l’utilisatrice a cliqué sur l’annonce.
* **`network`** : réseau sur lequel le clic s’est produit (`g` pour la recherche Google, `s` pour un partenaire de recherche, `d` pour l’affichage).
* **`product partition`** : ID de groupe de produits pour les annonces de produits.
* **`keyword`** : déclenchement d’un mot-clé sur les sites de recherche ou mot-clé correspondant le mieux sur les sites de contenu.
* **`campaign id`** : identifiant de la campagne Google Ads, le cas échéant.
* **`ad group id`** : identifiant du groupe publicitaire Google Ads, le cas échéant.

Pour les annonces de recherche dynamique, le champ du mot-clé est renseigné avec le ciblage automatique.

Exemple :

```text
AL!1234!3!569345525675!e!!g!!adobe express!15557590691!136734402131
```

#### Microsoft Advertising

```text
AL!{user}!10!{ad id}!!!!{keyword/order item id}!!{campaign id}!{ad group id}
```

* **`ad id`** : identifiant de contenu créatif Microsoft Advertising.
* **`keyword/order item id`** : identifiant du mot-clé Microsoft Advertising.
* **`campaign id`** : identifiant de la campagne Microsoft Advertising.
* **`ad group id`** : identifiant du groupe publicitaire Microsoft Advertising.

Des formats Microsoft hérités peuvent toujours exister pour certains comptes non migrés.

Exemple :

```text
AL!1234!10!79577297926903!!!!79577437127536!!291647087!1273234845019564
```

#### Baidu

```text
AL!{user}!88!{creative}!{placement}!{keyword id}
```

* **`creative`** : identifiant créatif Baidu.
* **`placement`** : site web sur lequel l’utilisateur a cliqué sur l’annonce.
* **`keyword id`** : identifiant du mot-clé Baidu.

#### Yahoo! Publicités pour le Japon

```text
AL!{user}!94!{creative}!{matchtype}!{network}!{keyword}
```

* **`creative`** : Yahoo ! ID de création des publicités japonaises.
* **`matchtype`** : type de correspondance de mot-clé (`be` exact, expression `bp`, `bb` large).
* **`network`** : réseau sur lequel le clic s’est produit (recherche `n` native `s`).
* **`keyword`** : mot-clé de déclenchement.

#### Yandex

```text
AL!{user}!90!{ad id}!{source type}!!!{phrase id}
```

* **`ad id`** : identifiant de création Yandex.
* **`source type`** : type de site sur lequel la publicité a été affichée (recherche de `b`, contexte/contenu `c`, catégorie de `ct`).
* **`phrase id`** : identifiant du mot-clé Yandex.

## Classifications

Lors de l’activation de l’intégration [Analytics pour Advertising](https://experienceleague.adobe.com/fr/docs/advertising/integrations/analytics/overview), les classifications suivantes sont automatiquement créées. Les valeurs de classification sont automatiquement conservées par l’intégration.

| Classification | Description | DSP | Recherche,<br>Social, &amp;<br>Commerce |
| --- | --- | :---: | :---: |
| **[!UICONTROL Compte]** | Nom du compte. | &check; | &check; |
| **[!UICONTROL URL d’affichage de l’annonce]** | URL affichée dans la publicité. | | &check; |
| **[!UICONTROL Description de l’annonce]** | Description de l’annonce publicitaire (DSP) ou corps de l’annonce publicitaire (Search, Social et Commerce). | &check; | &check; |
| **[!UICONTROL Ajouter une URL de destination]** | URL de destination de la publicité. | | &check; |
| **[!UICONTROL Groupe publicitaire]** | Nom du groupe publicitaire. | | &check; |
| **[!UICONTROL Plateforme publicitaire]** | DSP publicitaire ou nom du moteur de recherche. | &check; | &check; |
| **[!UICONTROL Titre de la publicité]** | Type d’annonce (DSP) ou titre de l’annonce (Search, Social et Commerce). | &check; | &check; |
| **[!UICONTROL Type d’annonce]** | Type d’annonce, tel que `text`, `video`, `display` ou `native`. | &check; | &check; |
| **[!UICONTROL Attribut AdCloud 1]** -<br>**[!UICONTROL Attribut AdCloud 5 &#x200B;]** | Classifications d’espaces réservés réservées aux futurs attributs personnalisés. Actuellement inutilisé. | | |
| **[!UICONTROL Campagne]** | Nom de la campagne. | &check; | &check; |
| **[!UICONTROL Nom d’expérience Creative]** | Nom de l’expérience créative associée à l’interaction publicitaire, représentant un groupe de variations créatives utilisées dans les tests ou la personnalisation. | &check; | |
| **[!UICONTROL Nom de la branche Creative]** | Nom de la branche dans une expérience de création qui représente une variation ou un chemin spécifique dans l’expérience de création. | &check; | |
| **[!UICONTROL ID de branche Creative]** | Identifiant unique attribué à une branche de création dans une expérience de création. | &check; | |
| **[!UICONTROL Nom du Creative]** | Nom de la ressource publicitaire spécifique qui a été diffusée à l’utilisateur. | &check; | |
| **[!UICONTROL Nom De Variante Creative]** | Nom de la variante spécifique d’un contenu créatif utilisé dans une expérience créative ou une branche. | &check; | |
| **[!UICONTROL Mot-clé]** | Le mot-clé . | | &check; |
| **[!UICONTROL Type de correspondance de mot-clé]** | Le mot-clé et le type de correspondance. | | &check; |
| **[!UICONTROL Type d’atterrissage]** | Indique si l’entrée de la page de destination était une vue publicitaire ou un clic publicitaire. | &check; | &check; |
| **[!UICONTROL Type de correspondance]** | Type de correspondance de recherche. | | &check; |
| **[!UICONTROL Réseau]** | RTB (DSP) ou le nom du réseau publicitaire (Search, Social et Commerce). | &check; | &check; |
| **[!UICONTROL Optimisation]** : | Nom du package (DSP) ou nom du portfolio (Search, Social et Commerce). | &check; | &check; |
| **[!UICONTROL Placement]** | Nom de l’emplacement. | &check; | |
| **[!UICONTROL Cible du produit]** | Cible de produit d’une annonce publicitaire dans une liste de produits. | | &check; |
