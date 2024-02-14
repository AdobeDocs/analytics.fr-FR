---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 55c08fd64b2fbac0e21af10896773c2530fa64a8
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 42%

---

# Notes de mise à jour actuelles d’Adobe Analytics (février 2024)

**Dernière mise à jour** : le jeudi 14 février 2024

Ces notes de mise à jour portent sur la période du 14 février 2024 au 11 mars 2024. Les mises à jour dʼAdobe Analytics suivent une [modèle de diffusion continue](releases.md), ce qui permet un déploiement plus flexible et progressif des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Activity Map pour SDK Web sans frais supplémentaires** | Actuellement, les événements de lien de Activity Map sont comptabilisés comme leurs propres événements et engendrent des coûts supplémentaires. Cette amélioration applique certains événements de lien et les regroupe dans l’accès suivant, comme la manière dont les événements sont gérés par AppMeasurement. |  | jeudi 14 février 2024 |
| **Augmentation des seuils de faible trafic par défaut** | Dans **mi-avril 2024**, Adobe commencera à augmenter les seuils de faible trafic de la suite de rapports par défaut comme suit : ![seuils de faible trafic](assets/thresholds.png) Cela n&#39;aura d&#39;impact que sur les variables actuellement définies sous les nouveaux seuils. Ces modifications seront apportées de manière incrémentielle. Nous prévoyons que les travaux soient terminés par le **fin mai**. Au fur et à mesure que ces augmentations sont déployées, vous remarquerez peut-être des modifications pour les variables de cardinalité élevée :<ul><li>D’autres valeurs de dimension peuvent être disponibles pour la création de rapports.</li><li>Les segments et les mesures calculées peuvent inclure davantage de données.</li><li>Les suites de rapports virtuelles basées sur des segments peuvent inclure davantage de données.</li></ul> | Mid avril 2024 | Fin mai 2024 |

{style="table-layout:auto"}

## Correctifs dans Adobe Analytics

* Correction des problèmes de classifications suivants : AN-319515 ; AN-337559 ; AN-338149 ; AN-338702 ; AN-338769 ; AN-338891 ; AN-339327 ; AN-339649 ; AN-339668 ; AN-339669 ; AN-; AN-339776 ; AN-339822 ; AN- ; AN-; AN- ; AN-;
* Correction des problèmes suivants du Créateur de règles de classifications : AN-338385 ; AN-338399 ; AN-338592 ; AN-338810 ; AN-338893 ; AN-339431 ; AN-339894 ; AN-339933 ; AN-340201 ; AN-340309 ;
* Correction des problèmes A4T suivants : AN-334830 ; AN-336194 ; AN-338309 ; AN-338650 ;
* Correction du problème de collecte de données suivant : AN-339323
* Correction des problèmes de Data Warehouse suivants : AN-335542 ; AN-331425 ; AN-337215 ; AN-338445 ; AN-338643 ; AN-338651 ; AN-339461 ; AN-340066 ; AN-340207 ; AN-340460
* Correction des problèmes de flux de données suivants : AN-335952 ; AN-338653 ; AN-339508 ; AN-339681 ; AN-340418
* Correction des problèmes de sources de données suivants : AN-338648
* Correction des problèmes Analysis Workspace suivants : AN-326509 ; AN-336186 ; AN-336190 ; AN-336309 ; AN-337922 ; AN-338094 ; AN-338323 ; AN-338556 ; AN-339600 ; AN-340445

### Autres correctifs d’Analytics

AN-328239; AN-332908; AN-335449; AN-335517; AN-336075; AN-336100; AN-336128; AN-338088; AN-338270; AN-; AN-338393; AN-338494; AN-339326; AN-; AN-; AN-; AN-; AN-; AN-2; AN-2;

## Avis importants pour les administrateurs d’Adobe Analytics {#admin}

| Avis | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| Ajout de membres aux objets d’API Adobe | 17 janvier 2024 | Adobe peut ajouter des membres de requête et de réponse facultatifs (paires nom/valeur) aux objets API existants à tout moment et sans préavis ni modification du contrôle de version. Adobe vous recommande de vous référer à la documentation de l’API de tout outil tiers que vous intégrez à nos API afin que ces ajouts soient ignorés dans le traitement, s’ils ne sont pas compris. S’ils sont correctement implémentés, ces ajouts sont des modifications incessantes pour votre mise en oeuvre. Adobe ne supprimera pas de paramètres ni n’ajoutera de paramètres requis sans d’abord fournir une notification standard via les notes de mise à jour. |
| Plug-in `getPageLoadTime` obsolète | 10 janvier 2024 | Ce plug-in n’est plus pris en charge. Son code utilise la méthode performance.timing, qui (selon MDN) est à présent [obsolète](https://developer.mozilla.org/fr-FR/docs/Web/API/PerformanceTiming). Le travail sur un plug-in mis à jour a commencé. |

{style="table-layout:auto"}

## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Migration vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O** | 11 mai 2023 | Les clients et clientes de l’API Adobe Analytics et de Livestream qui utilisent les informations d’identification JWT d’Adobe I/O doivent migrer vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O avant le **1er janvier 2025**. Adobe I/O n’autorisera pas la création d’informations d’identification JWT à compter du 1er mai 2024. Les clients et clientes utilisant JWT doivent créer des informations d’identification de serveur à serveur OAuth ou migrer leurs informations d’identification JWT existantes vers des informations d’identification de serveur à serveur OAuth. Ils ou elles doivent également mettre à jour leurs applications clientes afin d’utiliser les nouvelles informations d’identification de serveur à serveur OAuth. <ul><li>[Migration des informations d’identification du compte de service (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guide de mise en œuvre pour les nouvelles et les anciennes applications avec OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilisation des nouvelles informations d’identification de serveur à serveur OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Questions fréquentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.25.0), reportez-vous aux [Notes de mise à jour d’AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).


## Ressources connexes

* [Notes de mise à jour précédentes pour 2023](/help/release-notes/2023.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)
