---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: aac32bdda365ce4534f1d4c04e816eb6f03b991c
workflow-type: tm+mt
source-wordcount: '1351'
ht-degree: 96%

---

# Notes de mise à jour actuelles d’Adobe Analytics (mars 2024)

**Dernière mise à jour** : jeudi 3 avril 2024

Ces notes de mise à jour portent sur la période du 12 mars 2024 à avril 2024. Les mises à jour dʼAdobe Analytics suivent une [modèle de diffusion continue](releases.md), ce qui permet un déploiement plus flexible et progressif des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Modification du protocole de suppression pour les projets Espace de travail** | Auparavant, les projets supprimés n’étaient jamais purgés du système. Nous commencerons maintenant à purger les projets supprimés après 180 jours. Pendant les 180 jours suivant la suppression, les utilisateurs peuvent toujours accéder à un projet supprimé via l’interface web s’ils disposent d’une URL vers le projet. | | 14 mars 2024 |
| **Mise à jour d’AppMeasurements** | [La version v2.26.0 d’AppMeasurement](/help/implement/appmeasurement-updates.md) est disponible. | | 4 mars 2024 |
| **Nouvelle colonne disponible sur la page de destination des projets** | La colonne **[!UICONTROL Dernière utilisation]** est désormais disponible lorsque vous affichez l’onglet Projets dans la [Page de destination d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/landing.html?lang=fr). <p>Ces informations peuvent vous aider à déterminer si un projet est utile aux utilisateurs et utilisatrices de votre entreprise en indiquant la date et l’heure de la dernière ouverture du projet.</p> <p>Auparavant, la colonne **[!UICONTROL Dernière utilisation]** était uniquement disponible dans le gestionnaire de mesures calculées, le gestionnaire de segments et le gestionnaire d’alertes.</p> |  | 13 mars 2024 |
| **Prise en charge d’Analytics pour les indicateurs de consentement requis par Google pour DMA** | En raison de la nouvelle réglementation européenne sur la protection de la vie privée, Google exige que les données collectées en Europe qui leur ont été envoyées indiquent si deux types particuliers de consentement ont été accordés.**À compter du 6 mars**, Google n’acceptera plus les données d’événement qui n’indiquent pas que le consentement approprié a été accordé. Adobe Analytics prend désormais en charge la capture de ces données au moyen d’une nouvelle variable adConsent. La nouvelle variable est répertoriée dans l’[Interface utilisateur du compte rendu des performances sur la confidentialité](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md). Si vous souhaitez activer cette fonctionnalité et que la confidentialité est déjà activée pour les variables de consentement précédentes, vous devez à nouveau activer la confidentialité.<p>La [dimension Consentement pour la plateforme publicitaire](/help/components/dimensions/ad-consent.md) indique si le consentement est collecté pour envoyer des données à des fournisseurs publicitaires tiers tels que Google. |  | 13 mars 2024 |
| **Utilisation de Report Builder incluse dans la colonne « Utilisation dans » du gestionnaire de mesures calculées et du gestionnaire de segments** | Lors de l’affichage de la colonne **Utilisation dans** dans le gestionnaire de mesures calculées ou le gestionnaire de segments, les données d’utilisation sont désormais disponibles pour Report Builder.<p>Auparavant, les données d’utilisation du gestionnaire de segments n’étaient disponibles que pour les alertes, les projets, les projets planifiés et les mesures calculées. Les données d’utilisation du gestionnaire de mesures calculées n’étaient disponibles que pour les alertes, les projets et les projets planifiés.</p> |  | Juillet |
| **Utilisez les mêmes comptes cloud pour les flux de données, Data Warehouse et les ensembles de classifications** | Les comptes et emplacements cloud que vous créez peuvent désormais être utilisés pour exporter des données (avec des flux de données et Data Warehouse) et importer des données (avec des ensembles de classifications).<p> **Modifications lors de la configuration de comptes :** les utilisateurs et utilisatrices peuvent configurer des comptes d’import et d’export dans le cloud et configurer des emplacements d’import et d’export dans le cloud qui peuvent être utilisés pour les usages suivants :<ul><li>Import de données avec des ensembles de classifications</li><li>Export de données avec des flux de données</li><li>Export de données avec Data Warehouse.</li></ul><p>**Modifications lors de la gestion des comptes** : les utilisateurs et utilisatrices peuvent utiliser la page Emplacements (sous Composants > Emplacements) pour afficher et gérer tous les comptes et emplacements qu’ils ou elles créent, quel que soit l’endroit où ils ont été créés. <p>Auparavant, la page Emplacements s’appliquait uniquement aux comptes créés pour importer des données avec des ensembles de classifications.</p> | | Avril 2024 |
| **Les administrateurs et les administratrices peuvent gérer l’ensemble des emplacements et des comptes de leur organisation.** | Une nouvelle option de l’onglet Emplacements (page Composants > Emplacements) permet aux administrateurs et administratrices d’afficher et de gérer tous les emplacements de l’organisation.<p>Une nouvelle option de l’onglet Comptes d’emplacement (page Composants > Emplacements) permet aux administrateurs et administratrices d’afficher et de gérer tous les comptes de l’organisation.</p> <p>Auparavant, les administrateurs et administratrices ne pouvaient afficher et gérer que les emplacements et comptes qu’ils avaient créés.</p> |  | Avril 2024 |
| **Activity Map utilise moins d’appels au serveur pour le SDK Web** | Actuellement, les événements de lien d’Activity Map sont comptabilisés comme leurs propres événements et engendrent des coûts supplémentaires. <p>Cette amélioration applique certains événements de lien et les regroupe dans l’accès suivant, comme la manière dont les événements sont gérés par AppMeasurement.</p> |  | 31 avril 2024 |
| **Augmentation des seuils de faible trafic par défaut** | À la **mi-avril 2024**, Adobe commencera à augmenter les seuils de faible trafic de la suite de rapports par défaut comme suit : ![seuils de faible trafic](assets/thresholds.png). Cela n’aura d’impact que sur les variables actuellement définies sous les nouveaux seuils. Ces modifications seront apportées de manière incrémentielle. Nous prévoyons que le travail sera terminé d’ici **fin mai**. Au fur et à mesure que ces augmentations sont déployées, vous remarquerez peut-être des modifications pour les variables de cardinalité élevée :<ul><li>D’autres valeurs de dimension peuvent être disponibles pour la création de rapports.</li><li>Les segments et les mesures calculées peuvent inclure davantage de données.</li><li>Les suites de rapports virtuelles basées sur des segments peuvent inclure davantage de données.</li><li>Les exports de classifications peuvent inclure davantage de données.</li></ul> | | Mi-avril 2024 |

{style="table-layout:auto"}

## Correctifs dans Adobe Analytics

* Correction des problèmes de classifications suivants : AN-335632 ; AN-337559 ; AN-340164 ; AN-340370 ; AN-341089 ; AN-341211 ; AN-341284 ; AN-341469 ; AN-341481 ; AN-341760 ; AN-341778 ; AN-342144 ; AN-342258 ; AN-342338 ; AN-342400.
* Correction des problèmes suivants du créateur de règles de classifications : AN-340921 ; AN-341269 ; AN-341292 ; AN-341467 ; AN-341666 ; AN-342145 ; AN-342329.
* Correction du problème d’alertes intelligentes suivant : AN-340736.
* Correction du problème de segmentation suivant : AN-336242.
* Correction des problèmes liés à Data Warehouse suivants : AN-335354 ; AN-339446 ; AN-339774 ; AN-340221 ; AN-340599 ; AN-341277 ; AN-342009 ; AN-342088 ; AN-342592.
* Correction des problèmes de flux de données suivants : AN-335508 ; AN-340887 ; AN-341050 ; AN-341208 ; AN-341403 ; AN-341479 ; AN-341524 ; AN-341661 ; AN-342000 ; AN-342125 ; AN-342256 ; AN-342301 ; AN-342410 ; AN-342502 ; AN-342525.
* Correction du problème lié à Report Builder suivant : AN-340540.
* Correction des problèmes liés à Analysis Workspace suivants : AN-295889 ; AN-330981 ; AN-338818 ; AN-339730 ; AN-341114 ; AN-341520.

### Autres correctifs d’Analytics

AN-312198 ; AN-338009 ; AN-339549 ; AN-333970 ; AN-334790 ; AN-336461 ; AN-336572 ; AN-339549 ; AN-341119 ; AN-341246 ; AN-341268 ; AN-341272 ; AN-341475 ; AN-341547 ; AN-341558 ; AN-341680 ; AN-342017.

## Avis importants pour les administrateurs d’Adobe Analytics {#admin}

| Avis | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **Expiration après 13 mois des`cust_visids`** enregistrés | 20 mars 2024 | Une prochaine version du moteur de traitement des accès Analytics, prévue pour avril ou mai, introduit l’expiration après 13 mois des `cust_visids` enregistrés. Si « Activer la connexité des visiteurs » est activé dans la suite de rapports, ce paramètre est utilisé pour rechercher le `cust_visid` pour une `visid_high/visid_low value` sans `cust_visid` sur l’accès. Actuellement, il n’existe aucune expiration du mappage d’un `cust_visid` pour `visid_high/visid_low`. Avec cette version, si 13 mois ou plus se sont écoulés depuis que `visid_high/visid_low` a eu un `cust_visid` sur un accès, le mappage expire. |
| **Ajout de membres aux objets d’API Adobe** | 17 janvier 2024 | Adobe peut ajouter des membres de requête et de réponse facultatifs (paires nom/valeur) aux objets d’API existants sans préavis ni modification du contrôle de version. Adobe vous recommande de vous référer à la documentation de l’API de tout outil tiers que vous intégrez à nos API, afin que ces ajouts soient ignorés dans le traitement s’ils ne sont pas compris. S’ils sont correctement implémentés, ces ajouts sont des modifications incessantes pour votre mise en œuvre. Adobe ne supprimera pas de paramètres ni n’ajoutera de paramètres requis sans d’abord fournir une notification standard via les notes de mise à jour. |
| Plug-in **`getPageLoadTime`obsolète** | 10 janvier 2024 | Ce plug-in n’est plus pris en charge. Son code utilise la méthode performance.timing, qui (selon MDN) est à présent [obsolète](https://developer.mozilla.org/fr-FR/docs/Web/API/PerformanceTiming). Le travail sur un plug-in mis à jour a commencé. |

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
