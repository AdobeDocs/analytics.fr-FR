---
title: Outils de débogage pour les implémentations Analytics
description: Inspectez les données que votre implémentation envoie à Adobe à l’aide des débogueurs d’Analytics, des outils de développement du navigateur et des proxys de débogage HTTP.
keywords: analyseur de paquets, moniteur de paquets, renifleur de paquets, débogueur, charles, NS_BINDING_ABORTED, sendBeacon
feature: Implementation Basics
exl-id: db077293-f72c-4933-8a30-f1e1963f332e
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/debgxI3FK1fp1Q02GY1-0H40z-L4G2HSmq11Tog97-Y'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e992d880-33bc-4949-a648-aa7d410276cd
    internal-label: Validation
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 319f78bb5f8c2449a7263e3f1c378c49656889a7
workflow-type: tm+mt
source-wordcount: '991'
ht-degree: 3%
---
# Outils de débogage pour les implémentations Analytics

Les outils de débogage, parfois appelés analyseurs de paquets ou renifleurs de paquets, vous permettent d’inspecter les données envoyées par votre implémentation à Adobe. Ils peuvent vous aider à confirmer que les requêtes se déclenchent avec succès, à inspecter les variables et les payloads incluses dans ces requêtes et à résoudre les problèmes de comportement d’implémentation inattendu.

>[!NOTE]
>
>Les outils répertoriés sur cette page ne sont pas complets. Ils représentent des outils que les clients d’Adobe Analytics ont trouvés utiles. À l’exception des outils fournis par Adobe, Adobe ne prend pas en charge ou ne résout pas ces produits. Consultez l’éditeur de l’outil pour plus d’informations sur l’installation, l’utilisation et le support.

## Choisir un outil de débogage

Les catégories suivantes peuvent vous aider à sélectionner un outil en fonction de ce que vous souhaitez inspecter.

| Type d’outil | Utile lorsque |
| --- | --- |
| **Analytics et débogueurs de balises** | Vous souhaitez que les variables Analytics, les balises, les couches de données ou les requêtes de collecte soient interprétées et présentées dans un format lisible par l’utilisateur. |
| **Outils de développement du navigateur** | Vous déboguez une implémentation web et souhaitez inspecter directement les requêtes réseau sans installer d’application de débogage distincte. |
| **Proxy de débogage HTTP(S)** | Vous souhaitez inspecter le trafic HTTP des navigateurs, des applications mobiles, des vues web, des API ou d’autres clients, ou vous avez besoin de fonctionnalités autres que les outils de développement de navigateur. |

## Analytics et les débogueurs de balises

Analytics et les débogueurs de balises reconnaissent les technologies d’analyse et interprètent leurs requêtes. Ces outils peuvent faciliter l’identification des variables Adobe Analytics, des payloads Experience Platform Web SDK, des balises et des informations d’implémentation associées sans décoder manuellement les requêtes réseau.

| Outil | Disponibilité | Utile pour | Considérations |
| --- | --- | --- | --- |
| **[&#128279;](https://experienceleague.adobe.com/fr/docs/experience-platform/debugger/home)** | Extension de navigateur | Déboguer les implémentations de Adobe Experience Platform et de CX Enterprise, y compris Adobe Analytics, les balises, les couches de données et Experience Platform Web SDK | Outil fourni par Adobe axé sur les technologies Adobe |
| **[Omnibug &#x200B;](https://omnibug.io)** | Navigateurs basés sur Chromium et Firefox | Décodage d’Adobe Analytics, d’Experience Platform Web SDK, des balises Adobe et des requêtes de nombreux autres fournisseurs d’analyse et de marketing | Utile pour les implémentations contenant des technologies de plusieurs fournisseurs |
| **[ObservePoint Debugger](https://www.observepoint.com/solutions/observepoint-debugger/)** | Chrome et Edge | Inspection et décodage des balises d’analyse, de marketing et de mesure, y compris des requêtes Adobe Analytics | Débogueur basé sur un navigateur ; ObservePoint propose également des produits distincts de validation et d’implémentation automatisée |
| **[&#128279;](https://experienceleague.adobe.com/fr/docs/experience-platform/assurance/home)** | Application web dans CX Enterprise | Inspecter et valider les événements des implémentations de Mobile SDK et voir comment Edge Network a traité les événements | Outil fourni par Adobe ; connectez votre application à une session Assurance pour afficher ses événements. |

## Outils de développement de navigateur

Chaque navigateur moderne comprend des outils de développement qui peuvent inspecter les requêtes réseau. Vous n’avez donc souvent pas besoin d’un outil distinct pour déboguer une implémentation web. Appuyez sur **F12** ou **Ctrl+Maj+I** (Windows et Linux) ou **Cmd+Option+I** (macOS), puis sélectionnez l’onglet **Réseau**. Dans Safari, commencez par activer les fonctionnalités de développement dans les paramètres **avancés** de Safari.

## Proxy de débogage HTTP(S)

Les proxys de débogage HTTP interceptent le trafic HTTP et HTTPS entre un client et un serveur. Ils sont utiles lorsque les outils de développement du navigateur ne fournissent pas suffisamment de visibilité ou lorsque l’implémentation s’exécute en dehors d’un navigateur web traditionnel.

L’inspection HTTPS nécessite généralement la configuration du client pour qu’il approuve un certificat fourni par le proxy de débogage. Suivez les politiques de sécurité de votre entreprise lors de l’installation de certificats ou de l’interception du trafic chiffré.

| Outil | Utile pour |
| --- | --- |
| **[Charles](https://www.charlesproxy.com/)** | Inspection du navigateur, de l’application, de l’appareil mobile et d’autre trafic HTTP(S) |
| **[Fiddler Partout](https://www.telerik.com/fiddler/fiddler-everywhere)** | Capture et inspection du trafic HTTP(S) entre les applications et les appareils. Distinct de l’ancien produit Fiddler Classic. |
| **[Proxyman &#x200B;](https://proxyman.com/)** | Inspection et modification du trafic HTTP(S) provenant des navigateurs, des applications et des appareils mobiles |
| **[boîte à outils HTTP](https://httptoolkit.com/)** | Inspection du trafic provenant des applications, des API, des environnements de développement et des appareils mobiles, avec des workflows orientés vers le débogage des applications et des API |
| **[mitmproxy](https://www.mitmproxy.org/)** | Interception, inspection et modification HTTP(S) scriptable via des interfaces de ligne de commande et web. Convient mieux aux utilisateurs qui maîtrisent les workflows de ligne de commande. |

## Localisation des requêtes Adobe Analytics

Pour les implémentations qui envoient directement des données à Adobe Analytics, telles qu’AppMeasurement, filtrez les requêtes réseau pour :

```text
/ss/
```

Les requêtes de collecte Adobe Analytics contiennent des variables Analytics dans l’URL de requête ou la payload. Les requêtes brutes utilisent des noms de paramètres de requête plutôt que des noms de variables ; par exemple, eVar1 apparaît comme `v1` et prop1 comme `c1`. Les débogueurs Analytics décodent ces noms pour vous. Pour les décoder vous-même, consultez la [référence de variable](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference) dans la documentation de l’API Data Insertion.

Pour les codes d’état HTTP renvoyés par les serveurs de collecte de données Analytics, consultez [Codes de réponse HTTP](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting#http-response-codes) dans la documentation de l’API Data Insertion.

Pour les implémentations qui utilisent Adobe Experience Platform Web SDK, filtrez les requêtes réseau pour :

```text
/ee/
```

Sélectionnez la requête et examinez sa payload pour afficher les données envoyées à Adobe Experience Platform Edge Network. Le SDK Web envoie des données à Edge Network, qui peut ensuite les transférer vers Adobe Analytics et d’autres services configurés. L’inspection de la requête du client vérifie ce que le navigateur a envoyé à Edge Network ; elle ne confirme pas en elle-même que les données ont été traitées avec succès par chaque service en aval. Pour voir comment Edge Network a traité un événement, utilisez [Adobe Experience Platform Assurance](https://experienceleague.adobe.com/fr/docs/experience-platform/assurance/home).

## Requêtes abandonnées

Lorsqu’une page quitte l’application, le navigateur peut annuler les requêtes qui sont toujours en cours. Firefox classe ces requêtes `NS_BINDING_ABORTED` ; Chrome et Edge les classent `(canceled)`. Pour que les requêtes restent visibles après la navigation, activez **Conserver le journal** (Chrome et Edge) ou **Conserver les journaux** (Firefox).

Une demande annulée ne signifie pas nécessairement que des données ont été perdues. Le navigateur a peut-être envoyé la requête complète et cessé d’attendre uniquement la réponse. Les outils de développement de navigateur ne peuvent généralement pas afficher la différence, mais un proxy de débogage HTTP peut l’afficher.

Les requêtes envoyées avec `navigator.sendBeacon()` ne sont pas annulées lors de la navigation. AppMeasurement utilise des `sendBeacon` pour les liens de sortie et chaque fois que le [`useBeacon`](/help/implement/vars/config-vars/usebeacon.md) est activé. Le Web SDK l’utilise pour les événements envoyés avec [`documentUnloading`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/sendevent/documentunloading). Si les demandes de suivi des liens sont fréquemment annulées, utilisez ces options.
