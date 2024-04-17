---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d2b2ebdbc6a3c0f20b8684ba5c1b4b89cefb8e5a
workflow-type: tm+mt
source-wordcount: '1240'
ht-degree: 51%

---

# Notes de mise à jour actuelle d’Adobe Analytics (avril 2024)

**Dernière mise à jour** : jeudi 17 avril 2024

Ces notes de mise à jour portent sur la période du 17 avril 2024 au mois de mai. Les mises à jour dʼAdobe Analytics suivent une [modèle de diffusion continue](releases.md), ce qui permet un déploiement plus flexible et progressif des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Média en flux continu : envoi de données Roku à Adobe Experience Platform Edge Network** | Maintenant que [installation de Media Analytics avec Experience Platform Edge](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge), vous pouvez utiliser le SDK Adobe Experience Platform Roku pour envoyer des données de médias en flux continu à Adobe Experience Platform. |  | 12 avril 2024 |
| **Amélioration du workflow de migration du SDK Web** | La collecte de données Adobe Experience Platform mappe désormais automatiquement de nombreux champs de l’objet de données directement vers Adobe Analytics. Ce workflow amélioré offre les avantages suivants :<ul><li>Il permet à votre entreprise de migrer vers le SDK Web sans se soucier de créer ou de respecter une [!UICONTROL Schéma XDM]. Voir [Mappage des variables d’objet de données](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping) pour plus d’informations. (Autres liens vers la documentation à suivre)</li><li>Une fois la migration vers le SDK Web effectuée, votre entreprise est mieux placée pour migrer d’Adobe Analytics vers Customer Journey Analytics. En effet, le SDK Web permet une migration plus transparente vers Customer Journey Analytics.</li></ul> (Des informations supplémentaires à ce sujet et sur d’autres options de migration seront bientôt disponibles.) |  | Avril 2024 |
| **Amélioration des autorisations pour les projets uniquement [!UICONTROL Workspace] components** | Auparavant, si un utilisateur (l’utilisateur A) partageait un projet avec un autre utilisateur (l’utilisateur B) et autorisait l’utilisateur B à modifier le projet, l’utilisateur B pouvait le modifier. Cependant, l’utilisateur B ne peut pas modifier [!UICONTROL Segments rapides] incorporé dans le projet. Cette limitation a été supprimée. L’utilisateur B peut la modifier. [!UICONTROL Segments rapides] et d’autres composants de projet uniquement qui sont incorporés dans le projet partagé. |  | 17 avril 2024 |
| **Utilisez les mêmes comptes cloud pour [!UICONTROL Flux de données], [!UICONTROL Data Warehouse], et [!UICONTROL Jeux de classifications]** | Les comptes et emplacements cloud que vous créez peuvent désormais être utilisés pour exporter des données (avec [!UICONTROL Flux de données] et [!UICONTROL Data Warehouse]) et d’importer des données (avec [!UICONTROL Jeux de classifications]).<p> **Modifications lors de la configuration de comptes :** Les utilisateurs peuvent [Configuration de comptes d’importation et d’exportation dans le cloud](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts) et [Configuration des emplacements d’importation et d’exportation dans le cloud](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-locations) qui peut être utilisé à l’un des usages suivants :<ul><li>Importer des données avec [!UICONTROL Jeux de classifications]</li><li>Exporter des données avec [!UICONTROL Flux de données]</li><li>Exporter des données avec [!UICONTROL Data Warehouse].</li></ul><p>**Changements lors de la gestion des comptes**: les utilisateurs peuvent utiliser la variable [Emplacements](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) (sous [!UICONTROL Composants] > Locactions) pour afficher et gérer tous les comptes et emplacements qu’ils créent, quel que soit l’endroit où ils ont été créés. <p>Auparavant, la variable [!UICONTROL Emplacements] page appliquée uniquement aux comptes créés pour importer des données avec [!UICONTROL Jeux de classifications].</p> | | 17 avril 2024 |
| **Les administrateurs et les administratrices peuvent gérer l’ensemble des emplacements et des comptes de leur organisation.** | Une nouvelle option de l’onglet Emplacements (page Composants > Emplacements) permet aux administrateurs et administratrices d’afficher et de gérer tous les emplacements de l’organisation.<p>Une nouvelle option de la variable [Emplacement](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) l’onglet Comptes (sur la page Composants > Emplacements ) permet aux administrateurs d’afficher et de gérer tous les comptes de l’organisation.</p> <p>Auparavant, les administrateurs et administratrices ne pouvaient afficher et gérer que les emplacements et comptes qu’ils avaient créés.</p> |  | 17 avril 2024 |
| **Augmentation des seuils de faible trafic par défaut** | À la **mi-avril 2024**, Adobe commencera à augmenter les seuils de faible trafic de la suite de rapports par défaut comme suit : ![seuils de faible trafic](assets/thresholds.png). Cela n’aura d’impact que sur les variables actuellement définies sous les nouveaux seuils. Ces modifications seront apportées de manière incrémentielle. Nous prévoyons que le travail sera terminé d’ici **fin mai**. Au fur et à mesure que ces augmentations sont déployées, vous remarquerez peut-être des modifications pour les variables de cardinalité élevée :<ul><li>D’autres valeurs de dimension peuvent être disponibles pour la création de rapports.</li><li>Les segments et les mesures calculées peuvent inclure davantage de données.</li><li>Les suites de rapports virtuelles basées sur des segments peuvent inclure davantage de données.</li><li>Les exports de classifications peuvent inclure davantage de données.</li></ul> | Mi-avril 2024 | samedi 31 mai 2024 |
| **Activity Map utilise moins d’appels au serveur pour le SDK Web** | Actuellement, les événements de lien d’Activity Map sont comptabilisés comme leurs propres événements et engendrent des coûts supplémentaires. <p>Cette amélioration applique certains événements de lien et les regroupe dans l’accès suivant, comme la manière dont les événements sont gérés par AppMeasurement.</p> |  | samedi 31 mai 2024 |

{style="table-layout:auto"}

## Correctifs dans Adobe Analytics

* Correction des problèmes de classifications suivants : AN-343439 ; AN-343503 ; AN-343504 ; AN-343986 ; AN-344262 ; AN-344564 ; AN-345204 ; AN-345234
* Correction des problèmes suivants du Créateur de règles de classifications : AN-341488 ; AN-342501 ; AN-345751
* Correction du problème d’alertes intelligentes suivant : AN-343466;
* Correction du problème de segmentation suivant : AN-342313.
* Correction du problème de Data Warehouse suivant : AN-344292
* Correction des problèmes de flux de données suivants : AN-339545 ; AN-340092 ; AN-342124 ; AN-342862 ; AN-343737 ; AN-344035 ; AN-; AN-344329 ; AN-344703 ; AN-344721 ; AN-344940 ; AN-345180 ; AN-345196 ; AN- ; AN-; AN- ; AN-; AN-
* Correction du problème de sources de données suivant : AN-343541
* Correction des problèmes Analysis Workspace suivants : AN-336303 ; AN-336472 ; AN-338422 ; AN-338556 ; AN-339718 ; AN-340147 ; AN-; AN-340301 ; AN-340421 ; AN-340951 ; AN-341172 ; AN-342905 ; AN-342909 ; AN- ; AN- ; AN-; AN- ; AN-; AN-; AN- ; AN-;
* Correction des problèmes d’administration Analytics suivants : AN-342519 ; AN-342523 ; AN-343623 ; AN-343882 ; AN-344237 ; AN-344829 ; AN-345235 ;
* Correction des problèmes A4T suivants : AN-341619 ; AN-344402
* Correction du problème d’application mobile suivant : AN-342010

### Autres correctifs d’Analytics

AN-336099; AN-337474; AN-337993; AN-339718; AN-339901; AN-340014; AN-341356; AN-343021; AN-343102; AN-; AN-343353; AN-343416; AN-340014; AN-; AN-; AN-

## Avis importants pour les administrateurs d’Adobe Analytics {#admin}

| Avis | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **Expiration après 13 mois des`cust_visids`** enregistrés | 20 mars 2024 | Une prochaine version du moteur de traitement des accès Analytics, prévue pour avril ou mai, introduit l’expiration après 13 mois des `cust_visids` enregistrés. Si « Activer la connexité des visiteurs » est activé dans la suite de rapports, ce paramètre est utilisé pour rechercher le `cust_visid` pour une `visid_high/visid_low value` sans `cust_visid` sur l’accès. Actuellement, il n’existe aucune expiration du mappage d’un `cust_visid` pour `visid_high/visid_low`. Avec cette version, si 13 mois ou plus se sont écoulés depuis que `visid_high/visid_low` a eu un `cust_visid` sur un accès, le mappage expire. |
| **Ajout de membres aux objets d’API Adobe** | 17 janvier 2024 | Adobe peut ajouter des membres de requête et de réponse facultatifs (paires nom/valeur) aux objets d’API existants sans préavis ni modification du contrôle de version. Adobe vous recommande de vous référer à la documentation de l’API de tout outil tiers que vous intégrez à nos API, afin que ces ajouts soient ignorés dans le traitement s’ils ne sont pas compris. S’ils sont correctement implémentés, ces ajouts sont des modifications incessantes pour votre mise en œuvre. Adobe ne supprimera pas de paramètres ni n’ajoutera de paramètres requis sans d’abord fournir une notification standard via les notes de mise à jour. |

{style="table-layout:auto"}

## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Migration vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O** | 11 mai 2023 | Les clients et clientes de l’API Adobe Analytics et de Livestream qui utilisent les informations d’identification JWT d’Adobe I/O doivent migrer vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O avant le **1er janvier 2025**. Adobe I/O n’autorisera pas la création d’informations d’identification JWT à compter du 1er mai 2024. Les clients et clientes utilisant JWT doivent créer des informations d’identification de serveur à serveur OAuth ou migrer leurs informations d’identification JWT existantes vers des informations d’identification de serveur à serveur OAuth. Ils ou elles doivent également mettre à jour leurs applications clientes afin d’utiliser les nouvelles informations d’identification de serveur à serveur OAuth. <ul><li>[Migration des informations d’identification du compte de service (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guide de mise en œuvre pour les nouvelles et les anciennes applications avec OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilisation des nouvelles informations d’identification de serveur à serveur OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Questions fréquentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.26.0), reportez-vous aux [Notes de mise à jour d’AppMeasurement pour JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).


## Ressources connexes

* [Notes de mise à jour précédentes pour 2023](/help/release-notes/2023.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)
