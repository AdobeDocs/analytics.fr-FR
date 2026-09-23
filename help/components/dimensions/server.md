---
title: Serveur
description: Le nom du serveur.
feature: Dimensions
exl-id: c2454c0d-497e-46f8-8569-7d0517097cab
TQID: https://experienceleague.adobe.com/BDVwwy3jCtHrcWLy2nOHVnDRbFiAoR-EeOzp-35XjBs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 61%
---
# Serveur

La dimension [Serveur](overview.md) répertorie généralement le nom d’hôte du site. Pour les suites de rapports combinant plusieurs domaines ou sous-domaines, cette dimension est utile pour identifier les domaines ou sous-domaines les plus performants.

Cette dimension est liée aux dimensions [Page](page.md) et [Section du site](site-section.md). Page est la dimension la plus granulaire, Serveur est la moins granulaire et Section du site est comprise entre les deux.

## Renseignement de cette dimension avec des données

AppMeasurement collecte ces données à l’aide de la variable [`server`](/help/implement/vars/page-vars/server.md), qui est fonctionnellement identique à une prop.

| Propriété | Valeur |
| --- | --- |
| **Variable** | [`server`](/help/implement/vars/page-vars/server.md) |
| **Champ Web SDK/XDM** | [`web.webPageDetails.server`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/webpage-details) |
| **Paramètre de requête** | [`server`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Balise XML** | [`<server>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite d’octets** | 100 octets |
| **Persistance** | Hit |

## Éléments de dimension

Les éléments de dimension incluent les serveurs de votre site. Votre entreprise détermine les éléments de dimension spécifiques à utiliser. Certaines organisations utilisent `window.location.hostname`, tandis que d’autres formulent des valeurs personnalisées. Quelle que soit la méthode utilisée, assurez-vous qu’elle est cohérente et que vous l’enregistrez dans un [document de conception de solution](/help/implement/prepare/solution-design.md).
