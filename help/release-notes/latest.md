---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 2a79bd4a752217c8c7b129700bc230952b5739df
workflow-type: tm+mt
source-wordcount: '1223'
ht-degree: 38%

---

# Notes de mise à jour actuelles d’Adobe Analytics (mars 2024)

**Dernière mise à jour** : jeudi 20 mars 2024

Ces notes de mise à jour portent sur la période du 12 mars 2024 au mois d’avril 2024. Les mises à jour dʼAdobe Analytics suivent une [modèle de diffusion continue](releases.md), ce qui permet un déploiement plus flexible et progressif des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Mise à jour des AppMeasurements** | [AppMeasurement de version v2.26.0](/help/implement/appmeasurement-updates.md) est disponible. | | mardi 4 mars 2024 |
| **Nouvelle colonne disponible sur la page d’entrée Projets** | La variable **[!UICONTROL Dernière utilisation]** est désormais disponible lorsque vous affichez l’onglet Projets dans la [Page d’entrée Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/landing.html?lang=fr). <p>Ces informations peuvent vous aider à déterminer si un projet est utile aux utilisateurs de votre entreprise en indiquant la date et l’heure de la dernière ouverture du projet.</p> <p>Auparavant, la variable **[!UICONTROL Dernière utilisation]** était uniquement disponible dans le gestionnaire de mesures calculées, le gestionnaire de segments et le gestionnaire d’alertes.</p> |  | 13 mars 2024 |
| **Prise en charge d’Analytics pour les indicateurs de consentement requis par Google pour DMA** | En raison de la nouvelle réglementation européenne sur la protection de la vie privée, Google exige que les données collectées en Europe qui leur ont été envoyées indiquent si deux types particuliers de consentement ont été accordés. **Début le 6 mars**, Google n’accepte plus les données d’événement qui n’indiquent pas que le consentement approprié a été accordé. Adobe Analytics prend désormais en charge la capture de ces données au moyen d’une nouvelle variable adConsent. La nouvelle variable est répertoriée dans la variable [Interface utilisateur des rapports de confidentialité](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md). Si vous souhaitez activer cette fonctionnalité et que la confidentialité est déjà activée pour les variables de consentement précédentes, vous devez à nouveau activer la confidentialité.<p>La variable [Dimension Consentement de la plateforme publicitaire](/help/components/dimensions/ad-consent.md) indique si le consentement est collecté pour envoyer des données à des fournisseurs de publicité tiers, tels que Google, Meta, etc. |  | 13 mars 2024 |
| **Utilisation des Reports Builder incluse dans la colonne &quot;Utilisé(e) dans&quot; du gestionnaire de mesures calculées et du gestionnaire de segments** | Lors de l’affichage de la variable **Utilisé dans** dans le gestionnaire de mesures calculées ou le gestionnaire de segments, les données d’utilisation sont désormais disponibles pour le Report Builder.<p>Auparavant, les données d’utilisation du gestionnaire de segments n’étaient disponibles que pour les mesures Alertes, Projets, Projets planifiés et Calculées ; tandis que les données d’utilisation du gestionnaire de mesures calculées n’étaient disponibles que pour les alertes, les projets et les projets planifiés.</p> |  | Fin mars ou début avril |
| **Utilisation des mêmes comptes cloud pour les flux de données, les Data Warehouse et les ensembles de classifications** | Les comptes et emplacements cloud que vous créez peuvent désormais être utilisés pour exporter des données (avec des flux de données et des Data Warehouse) et importer des données (avec des jeux de classifications).<p> **Modifications lors de la configuration de comptes :** Les utilisateurs peuvent configurer des comptes d’importation et d’exportation dans le cloud et configurer des emplacements d’importation et d’exportation dans le cloud qui peuvent être utilisés à l’un des usages suivants :<ul><li>Importation de données avec des jeux de classifications</li><li>Exportation de données avec des flux de données</li><li>Exporter des données avec Data Warehouse.</li></ul><p>**Changements lors de la gestion des comptes**: les utilisateurs peuvent utiliser la page Emplacements (sous Composants > Emplacements) pour afficher et gérer tous les comptes et emplacements qu’ils créent, quel que soit l’endroit où ils ont été créés. <p>Auparavant, la page Emplacements s’appliquait uniquement aux comptes créés pour importer des données avec des jeux de classifications.</p> | | Avril 2024 |
| **Les administrateurs peuvent gérer tous les emplacements et comptes de leur organisation.** | Une nouvelle option de l’onglet Emplacements (dans la page Composants > Emplacements ) permet aux administrateurs d’afficher et de gérer tous les emplacements de l’organisation.<p>Une nouvelle option de l’onglet Comptes d’emplacement (sur la page Composants > Emplacements ) permet aux administrateurs d’afficher et de gérer tous les comptes de l’organisation.</p> <p>Auparavant, les administrateurs pouvaient afficher et gérer uniquement les emplacements et les comptes qu’ils avaient créés.</p> |  | Avril 2024 |
| **Activity Map utilise moins d’appels au serveur pour le SDK Web** | Actuellement, les événements de lien de Activity Map sont comptabilisés comme leurs propres événements et engendrent des coûts supplémentaires. <p>Cette amélioration applique certains événements de lien et les regroupe dans l’accès suivant, comme la manière dont les événements sont gérés par AppMeasurement.</p> |  | jeudi 3 avril 2024 |
| **Augmentation des seuils de faible trafic par défaut** | À la **mi-avril 2024**, Adobe commencera à augmenter les seuils de faible trafic de la suite de rapports par défaut comme suit : ![seuils de faible trafic](assets/thresholds.png). Cela n’aura d’impact que sur les variables actuellement définies sous les nouveaux seuils. Ces modifications seront apportées de manière incrémentielle. Nous prévoyons que le travail sera terminé d’ici **fin mai**. Au fur et à mesure que ces augmentations sont déployées, vous remarquerez peut-être des modifications pour les variables de cardinalité élevée :<ul><li>D’autres valeurs de dimension peuvent être disponibles pour la création de rapports.</li><li>Les segments et les mesures calculées peuvent inclure davantage de données.</li><li>Les suites de rapports virtuelles basées sur des segments peuvent inclure davantage de données.</li><li>Les exports de classifications peuvent inclure davantage de données.</li></ul> | | Mi-avril 2024 |

{style="table-layout:auto"}

## Correctifs dans Adobe Analytics

* Correction des problèmes de classifications suivants : AN-335632 ; AN-337559 ; AN-340164 ; AN-340370 ; AN-341089 ; AN-341211 ; AN-341284 ; AN-341469 ; AN-341481 ; AN-341760 ; AN-; AN-341778 ; AN-342144 ; AN- ; AN-, AN-
* Correction des problèmes suivants du Créateur de règles de classifications : AN-340921 ; AN-341269 ; AN-341292 ; AN-341467 ; AN-341666 ; AN-342145 ; AN-342329
* Correction du problème d’alertes intelligentes suivant : AN-340736
* Correction du problème de segmentation suivant : AN-336242
* Correction des problèmes de Data Warehouse suivants : AN-335354 ; AN-339446 ; AN-339774 ; AN-340221 ; AN-340599 ; AN-341277 ; AN-342009 ; AN-342088 ; AN-342592
* Correction des problèmes de flux de données suivants : AN-335508 ; AN-340887 ; AN-341050 ; AN-341208 ; AN-341403 ; AN-341479 ; AN-; AN-341524 ; AN-341661 ; AN-342000 ; AN-342125 ; AN-342256 ; AN-342301 ; AN-342410 ; AN-; AN- ; AN-
* Correction du problème de Report Builder suivant : AN-340540
* Correction des problèmes Analysis Workspace suivants : AN-295889 ; AN-330981 ; AN-338818 ; AN-339730 ; AN-341114 ; AN-341520 ;

### Autres correctifs d’Analytics

AN-312198; AN-338009; AN-339549; AN-333970; AN-334790; AN-336461; AN-336572; AN-339549; AN-341119; AN-; AN-341246; AN-341268; AN-341272; AN-; AN-; AN-2; AN-; AN-; AN-2; AN-; AN-2; AN-;

## Avis importants pour les administrateurs d’Adobe Analytics {#admin}

| Avis | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **Ajout d’objets membres de l’API Adobe** | 17 janvier 2024 | Adobe peut ajouter des membres de requête et de réponse facultatifs (paires nom/valeur) aux objets d’API existants sans préavis ni modification du contrôle de version. Adobe vous recommande de vous référer à la documentation de l’API de tout outil tiers que vous intégrez à nos API, afin que ces ajouts soient ignorés dans le traitement s’ils ne sont pas compris. S’ils sont correctement implémentés, ces ajouts sont des modifications incessantes pour votre mise en œuvre. Adobe ne supprimera pas de paramètres ni n’ajoutera de paramètres requis sans d’abord fournir une notification standard via les notes de mise à jour. |
| **`getPageLoadTime`plugin deprecated** | 10 janvier 2024 | Ce plug-in n’est plus pris en charge. Son code utilise la méthode performance.timing, qui (selon MDN) est à présent [obsolète](https://developer.mozilla.org/fr-FR/docs/Web/API/PerformanceTiming). Le travail sur un plug-in mis à jour a commencé. |

{style="table-layout:auto"}

## Avis de fin de vie {#eol}

| Produit ou fonctionnalité en fin de vie | Date d’ajout ou de mise à jour | Description |
| --- | --- | --- |
| **Migration vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O** | 11 mai 2023 | Les clients et clientes de l’API Adobe Analytics et de Livestream qui utilisent les informations d’identification JWT d’Adobe I/O doivent migrer vers les informations d’identification de serveur à serveur OAuth d’Adobe I/O avant le **1er janvier 2025**. Adobe I/O n’autorisera pas la création d’informations d’identification JWT à compter du 1er mai 2024. Les clients et clientes utilisant JWT doivent créer des informations d’identification de serveur à serveur OAuth ou migrer leurs informations d’identification JWT existantes vers des informations d’identification de serveur à serveur OAuth. Ils ou elles doivent également mettre à jour leurs applications clientes afin d’utiliser les nouvelles informations d’identification de serveur à serveur OAuth. <ul><li>[Migration des informations d’identification du compte de service (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guide de mise en œuvre pour les nouvelles et les anciennes applications avec OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilisation des nouvelles informations d’identification de serveur à serveur OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Questions fréquentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Pour connaître les dernières mises à jour des versions d’AppMeasurement (version 2.26.0), reportez-vous à la section [Notes de mise à jour d’AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=fr).


## Ressources connexes

* [Notes de mise à jour précédentes pour 2023](/help/release-notes/2023.md)
* [Notes de mise à jour de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=fr)
* [Notes de mise à jour de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=fr)
* Dernières mises à jour des [produits Adobe Experience Cloud](https://business.adobe.com/fr/products/adobe-experience-cloud-products.html)
