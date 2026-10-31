---
title: Collecte de données Debug Analytics
description: Vérifiez qu’Adobe Analytics reçoit les données attendues d’AppMeasurement, de l’extension Analytics, de Web SDK, de Mobile SDK et de l’API Data Insertion.
keywords: débogage, validation, analyseur de paquets, moniteur de paquets, /b/ss/, Edge Trace, Assurance, hitdebugger, suite de rapports
feature: Implementation Basics
role: Admin, Developer
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
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
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 049b9b7447c7f91d67eb58fc781898b685bd9d91
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 2%
---
# Collecte de données Debug Analytics

Cet article explique les éléments à vérifier lorsque vous déboguez des données envoyées à Adobe Analytics. Recherchez votre méthode d’implémentation dans le tableau suivant et suivez sa section. Si vous recherchez des données de rapport inattendues, commencez par [Comparer des requêtes avec des rapports](#reports).

Pour connaître les étapes et les outils qui s’appliquent à toutes les collectes de données Adobe, comme la capture des requêtes réseau, l’activation de la journalisation du débogage et l’enquête sur les requêtes annulées, voir [Débogage et dépannage de la collecte de données](https://experienceleague.adobe.com/fr/docs/experience-platform/collection/debugging/overview).

| Méthode de mise en œuvre | Où voir les données reçues par Analytics | Instructions |
| --- | --- | --- |
| AppMeasurement ou l’extension de balise Analytics | Requêtes du navigateur directement aux serveurs de collecte de données Analytics | [AppMeasurement](#appmeasurement) |
| SDK web | Edge Trace, une fois qu’Edge Network a converti votre événement en un accès Analytics | [SDK Web](#web-sdk) |
| SDK mobile | La vue Événements Analytics dans Assurance. Si vous utilisez l’extension Edge Network ou Edge Bridge, activez **[!UICONTROL Vue Edge Analytics]**. | [Vue Événements Adobe Analytics dans Assurance](https://experienceleague.adobe.com/fr/docs/experience-platform/assurance/view/adobe-analytics) |
| API dʼinsertion des données | Les requêtes sortantes de votre serveur et leurs réponses | [Résolution des problèmes liés aux requêtes API d’insertion de données](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting) |

## AppMeasurement et l’extension Analytics {#appmeasurement}

### Rechercher la requête {#appmeasurement-find}

[Capturez les requêtes réseau](https://experienceleague.adobe.com/fr/docs/experience-platform/collection/debugging/inspect-requests#web) et filtrez les `/b/ss/`. Les débogueurs de balises tels qu’Adobe Experience Platform Debugger identifient et décodent ces requêtes pour vous.

Si aucune requête `/b/ss/` n’apparaît :

* Recherchez les erreurs JavaScript dans la console du navigateur.
* Si vous utilisez l’extension de balise Analytics, vérifiez que le code incorporé de balise se trouve dans l’élément `<head>` de la page et que votre bibliothèque est publiée dans l’environnement que vous testez. [Mode de débogage des balises](https://experienceleague.adobe.com/fr/docs/experience-platform/collection/debugging/logging) indique si la règle qui envoie l’accès a été déclenchée.
* Si vous hébergez vous-même AppMeasurement, ouvrez directement l’URL de la bibliothèque pour confirmer que le fichier se charge et contient du code.
* Désactivez les extensions de navigateur, telles que les bloqueurs d’annonces publicitaires, qui peuvent empêcher l’envoi de requêtes.
* Debugger ne reconnaît pas les requêtes envoyées depuis un iframe. Utilisez plutôt les outils de développement du navigateur . Voir [Utilisation d’AppMeasurement avec des iFrames](../use-cases/iframe.md).

### Vérifier ce qu’Analytics a reçu {#appmeasurement-contents}

* **Suites de rapports** : le segment de chemin d’accès après `/b/ss/` répertorie les identifiants de suite de rapports qui reçoivent l’accès. Vérifiez qu’il s’agit bien des suites de rapports attendues, par exemple une suite de rapports de développement sur les pages de développement.
* **Variables** : les requêtes brutes utilisent des noms de paramètres de requête plutôt que des noms de variables ; par exemple, eVar1 apparaît comme `v1` et prop1 comme `c1`. Voir la [référence de variable](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference). Lorsqu’une requête est trop longue, AppMeasurement l’envoie avec des `POST` HTTP, de sorte que les variables apparaissent dans le corps de la requête au lieu de l’URL.
* **Type d’accès** : les requêtes envoyées par [`tl()`](../vars/functions/tl-method.md) incluent le paramètre `pe` et n’incrémentent pas les pages vues. Les demandes envoyées par [`t()`](../vars/functions/t-method.md) n’incluent pas de `pe`.

Si les valeurs sont présentes, mais incorrectes, consultez [Dépannage de l’implémentation de JavaScript](../js/troubleshooting.md) pour des causes courantes, telles que les guillemets, les majuscules et les espaces.

### Vérifier la réponse {#appmeasurement-response}

Une réponse `2xx` confirme uniquement que le serveur de collecte de données a reçu la requête, et non que l’accès a été enregistré. Avec le type de réponse par défaut, une requête peut renvoyer un succès même lorsque l’accès est ignoré. Une réponse `302` à la première demande d’un nouveau visiteur est attendue. Voir [Codes de réponse HTTP](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting#http-response-codes).

AppMeasurement envoie avec `navigator.sendBeacon()` les demandes de lien de sortie et toutes les demandes lorsqu’[`useBeacon`](../vars/config-vars/usebeacon.md) est activé. Les outils de développement peuvent étiqueter ces requêtes comme annulées même lorsque le navigateur les a envoyées. Pour plus d&#39;informations, consultez la section [Demandes abandonnées](https://experienceleague.adobe.com/fr/docs/experience-platform/collection/debugging/inspect-requests#aborted-requests).

## SDK web {#web-sdk}

### Rechercher la requête {#web-sdk-find}

Avec Web SDK, le navigateur envoie les événements à Edge Network plutôt que directement à Analytics, de sorte que vous ne voyez pas de requête `/b/ss/`. [Inspectez la requête Edge Network](https://experienceleague.adobe.com/fr/docs/experience-platform/collection/debugging/inspect-requests#edge-network-requests) et confirmez les éléments suivants :

* Le paramètre `configId` correspond à un flux de données pour lequel le service [Adobe Analytics](https://experienceleague.adobe.com/fr/docs/experience-platform/datastreams/configure#analytics) est activé avec les suites de rapports attendues.
* La payload est qualifiée de page vue ou d’événement de lien. Analytics ignore les payloads qui ne contiennent ni détails de page, ni type d’interaction web. Voir [Types d’événements Edge Network dans Adobe Analytics](../aep-edge/hit-types.md).

### Vérifier ce qu’Analytics a reçu {#web-sdk-contents}

Démarrez une [Edge Trace](https://experienceleague.adobe.com/fr/docs/experience-platform/debugger/edge-trace) et reproduisez l’action. Recherchez la ligne commençant par **[!UICONTROL Mappage automatique Analytics]**, puis développez `mappedQueryParams` et l’identifiant de la suite de rapports en dessous.

* **Variables** : les valeurs mappées utilisent les mêmes noms de paramètres de requête que les requêtes AppMeasurement, parfois sous une forme abrégée, comme `gn` pour le nom de page et `pl` pour les produits. Voir [Mappage des champs d’objet XDM](../aep-edge/xdm-var-mapping.md) et [Mappage des champs d’objet de données](../aep-edge/data-var-mapping.md).
* **Données contextuelles** : les champs XDM qui ne sont pas mappés à une variable Analytics apparaissent comme des données contextuelles avec le préfixe `c.a.x.`. Utilisez des [règles de traitement](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) pour les affecter à des variables.
* **Suites de rapports** : si vous utilisez des remplacements de suite de rapports, la ligne de configuration du flux de données dans Edge Trace affiche les suites de rapports utilisées par Edge Network.

### Traitement des chèques {#web-sdk-processing}

Dans la session Assurance ouverte par Edge Trace, recherchez des `hitdebugger` dans les événements. Ces événements utilisent l’`com.adobe.analytics.hitdebugger` du fournisseur et leurs payloads affichent des valeurs après le traitement d’Analytics, telles que l’Experience Cloud ID (`mcvisId`) et `pageName`.

Pour une présentation guidée, voir [Configuration d’Adobe Analytics avec Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/fr/docs/platform-learn/implement-web-sdk/applications-setup/setup-analytics).

## Comparaison des requêtes avec les rapports {#reports}

Un accès qui atteint Analytics n’apparaît pas immédiatement dans les rapports et les valeurs signalées peuvent différer des valeurs de la requête :

* **Latence** : les données complètes apparaissent généralement dans les rapports environ deux heures après leur collecte. Certaines données, telles que les accès horodatés, peuvent prendre plus de temps. Voir [&#x200B; Disponibilité et latence des données &#x200B;](/help/technotes/latency.md).
* **Traitement** : les règles de traitement, les règles VISTA, les règles de robots et d’autres étapes de traitement peuvent modifier ou exclure des valeurs après la collecte. Voir [&#x200B; Ordre de traitement des données dans Adobe Analytics](/help/technotes/processing-order.md). Les données post-traitées d’Assurance affichent le résultat du traitement d’un accès individuel.
* **Suite de rapports** : vérifiez que vous affichez la même suite de rapports que celle ciblée par la requête ou le flux de données.
* **Valeurs inattendues** : si une dimension affiche des pics ou des valeurs inattendus, consultez [Collisions de hachage](hash-collisions.md).

Pour des modifications de trafic plus larges, voir [Résolution des problèmes liés aux pics et aux baisses de données](/help/technotes/event/spikes-drops.md).
