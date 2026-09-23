---
title: Identification des visiteurs à l’aide de l’API Data Insertion
description: Identifiez les visiteurs pour la collecte de données Adobe Analytics côté serveur et directe avec l’API Data Insertion.
feature: Implementation Basics
role: Admin, Developer, Leader
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 0%
---
# Identification des visiteurs à l’aide de l’API Data Insertion

L’[API Data Insertion](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/) envoie les accès aux serveurs de collecte d’Adobe Analytics sans bibliothèque côté client telle qu’AppMeasurement ou le SDK Web. Étant donné qu’aucune bibliothèque n’est présente pour gérer l’identité à votre place, vous définissez vous-même l’identifiant du visiteur, dans le navigateur pour les demandes d’images directes ou sur votre serveur pour la collecte côté serveur.

>[!NOTE]
>
>Cette page couvre l’identité du visiteur. Pour créer et envoyer les requêtes elles-mêmes, reportez-vous à la documentation de l’API [Data Insertion](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/) sur Adobe Developer.

Adobe identifie un visiteur ou une visiteuse à l’aide de la norme [ordre des opérations](overview.md) : le `vid`, puis le `aid`, le `mid`, le `fid` et enfin l’adresse IP et l’agent utilisateur. Avec l’API Data Insertion, vous définissez généralement directement l’un des trois identifiants suivants : l’ECID (`mid`), l’identifiant visiteur Analytics (`aid`) ou un identifiant visiteur personnalisé (`vid`).

## Utilisation de l’ECID (recommandé)

L’ECID (envoyé en tant que `mid`) est l’identifiant visiteur moderne inter-solutions, partagé dans Adobe Analytics, Adobe Target et Adobe Audience Manager. Adobe recommande de l’utiliser autant que possible.

Obtenez l’ECID avec le [service d’identification des visiteurs](https://experienceleague.adobe.com/fr/docs/id-service/using/home) (`VisitorAPI.js`). Dans un navigateur, initialisez le service avec votre identifiant d’organisation IMS à l’aide de [`getInstance`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getinstance), puis lisez l’ECID avec [`getMarketingCloudVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getmcvid) :

```js
var visitor = Visitor.getInstance("YOUR_ORG_ID@AdobeOrg");
var ecid = visitor.getMarketingCloudVisitorID();
```

Envoyez cette valeur à chaque accès en tant que paramètre de requête `mid` ou balise XML `<marketingCloudVisitorId>`. Si vos données sont transférées vers Audience Manager, envoyez également la région de [`getLocationHint`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getlocationhint) comme paramètre de `aamlh` (ou balise `<imsRegion>`). Pour associer vos propres identifiants de client au visiteur, utilisez [`setCustomerIDs`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/setcustomerids).

Pour la collecte côté serveur, obtenez l’ECID sur le client et transmettez-le à votre serveur pour qu’il soit envoyé à chaque accès. Pour générer un ECID entièrement côté serveur, sans client, utilisez l’intégration [directe](https://experienceleague.adobe.com/en/docs/id-service/using/implementation/direct-integration) du service d’ID.

## Utilisation de l’identifiant visiteur Analytics

L’identifiant visiteur Analytics (`aid`) est stocké dans le cookie [`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics). Lorsqu’un accès arrive sans identifiant, le serveur de collecte attribue un `aid` et le renvoie dans le corps de la réponse. Certains [types de réponse](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/response-types) incluent également cet identifiant dans le corps de la réponse. La différence entre les deux styles d’implémentation réside dans le fait de savoir qui stocke cet identifiant et qui le renvoie.

* **Côté client (demandes d’image directes).** Le navigateur stocke le cookie `s_vi` que le serveur renvoie et l’envoie à chaque demande ultérieure au même domaine de collecte, de sorte que le visiteur soit automatiquement reconnu. Pour que cela fonctionne, le domaine de collection doit être en mesure de définir et de lire le cookie — utilisez un serveur de suivi CNAME propriétaire. Comme ce modèle dépend des cookies, il se trouve à un endroit où les navigateurs les limitent (blocage des cookies tiers, prévention intelligente du suivi) ; préférez l’ECID pour une identité durable.

  >[!NOTE]
  >
  >Si vous lisez l’identifiant visiteur directement à partir du cookie de `s_vi`, celui-ci inclut l’identifiant dans des données supplémentaires (par exemple, `[CS]v1|<id>[CE]`) - extrayez uniquement la partie `<id>`. La lecture de l’identifiant à partir d’une réponse du visiteur le renvoie directement, sans analyse.

* **Côté serveur.** Un serveur n’a pas de fichier jar de cookie. Vous stockez donc et renvoyez le `aid` vous-même, saisi à l’utilisateur :

  1. Recherche du `aid` stocké pour l’utilisateur.
  1. Si vous en avez un, envoyez-le comme paramètre de requête `aid`.
  1. Dans le cas contraire, envoyez l’accès sans identifiant et demandez un type de réponse qui renvoie le `aid` affecté, puis stockez-le pour la prochaine fois.

  Le premier accès sans identifiant est déjà attribué au `aid` renvoyé par le serveur. Vous ne perdez donc aucune donnée en l’envoyant avant d’avoir un identifiant. Pour les types de réponse qui renvoient l’identifiant (`3` pour JavaScript, `11` pour XML, `10` pour JSON) et le format de requête, consultez [Type de réponse](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/response-types) dans la documentation de l’API Data Insertion.

  Étant donné qu’une requête côté serveur ne comporte aucun cookie visiteur et que sa propre adresse IP et son propre agent utilisateur appartiennent à l’expéditeur, transmettez également l’adresse IP réelle du visiteur (l’en-tête `X-Forwarded-For`) et l’agent utilisateur (l’en-tête `User-Agent`) pour que les accès soient correctement attribués.

## Utiliser un identifiant visiteur personnalisé

Si vous disposez déjà d’un identifiant durable que vous contrôlez entièrement, vous pouvez l’envoyer en tant que [`visitorID`](/help/implement/vars/config-vars/visitorid.md) (`vid`) sur chaque accès et votre propre identité de bout en bout. Cela convient aux plateformes autres que les navigateurs qui fournissent un identifiant d’appareil stable. Par exemple, une application Unity peut envoyer son identifiant d’appareil en tant que `vid`.

>[!IMPORTANT]
>
>N’utilisez `vid` que lorsque vous pouvez garantir une valeur stable pour chaque accès :
>
>* **Les navigateurs sont mal adaptés.** Un navigateur ne possède pas d’identifiant durable que vous pouvez renseigner de manière fiable. Par conséquent, un `vid` défini par le navigateur a tendance à se fragmenter ou à entrer en conflit. Utilisez plutôt le modèle côté client basé sur les cookies .
>* **Faites attention avec les identifiants d’authentification.** Vous ne disposez d’aucun identifiant avant la connexion d’un utilisateur et si l’utilisateur se déconnecte, les accès ultérieurs sont attribués à un autre visiteur. Ces actions répartissent l’activité d’une personne sur plusieurs visiteurs.

Voir [`visitorID`](/help/implement/vars/config-vars/visitorid.md) pour le format et les contraintes d’un identifiant visiteur personnalisé.
