---
title: Notes de mise à jour actuelles d’Adobe Analytics
description: Afficher les notes de mise à jour actuelles dʼAdobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 49e7e64254a6466af852ee6dd48c7b37a15c744c
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 79%

---

# Notes de mise à jour actuelles d’Adobe Analytics (mai 2024)

**Dernière mise à jour** : jeudi 22 mai 2024

Ces notes de mise à jour portent sur la période du 15 mai 2024 à juin 2024. Les mises à jour dʼAdobe Analytics suivent une [modèle de diffusion continue](releases.md), ce qui permet un déploiement plus flexible et progressif des fonctionnalités. Par conséquent, ces notes de mise à jour sont mises à jour plusieurs fois par mois. Veuillez les vérifier régulièrement.

## Nouvelles fonctionnalités ou améliorations {#features}

| Fonctionnalité | Description | [Le déploiement commence](releases.md) | [Disponibilité générale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Nouvelle documentation pour la mise à niveau d’Adobe Analytics vers Customer Journey Analytics** | Pour les entreprises qui passent d’Adobe Analytics à Customer Journey Analytics, il existe plusieurs options de mise à niveau et de nombreux points à prendre en compte en fonction de la mise en œuvre actuelle d’Adobe Analytics et des objectifs à long terme de l’entreprise. De nouvelles ressources documentaires sont désormais disponibles pour vous aider à mieux comprendre ce qui suit :<ul><li>Les différentes voies de mise à niveau existantes</li><li>Les voies de mise à niveau disponibles en fonction de l’implémentation actuelle d’Adobe Analytics par l’entreprise</li><li>Les avantages et les inconvénients de chaque voie de mise à niveau</li><li>Guide étape par étape pour chaque voie de mise à niveau</li><li>Considérations relatives au traitement des données historiques</li></ul>[Commencer avec la mise à niveau vers Customer Journey Analytics](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | Disponible maintenant |
| **Définir des champs `contextData` via XDM** | Les clientes et clients qui envoient des données à Adobe Analytics via Experience Edge Network peuvent [définir des valeurs de données contextuelles](https://experienceleague.adobe.com/fr/docs/analytics/implementation/vars/page-vars/contextdata) directement dans XDM ou dans les parties « données » de la payload. |  | Disponible maintenant |
| **API 2.0 de création de rapports en temps réel dans Analytics** | La nouvelle API 2.0 de création de rapports en temps réel d’Adobe Analytics optimise l’intégration des clientes et clients et délivre des résultats de rapports rapides. Ces résultats peuvent être utilisés par programmation pour travailler avec des rapports de base, des rapports sur les tendances et des rapports de ventilation. [En savoir plus](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/real-time/) | | 30 mai 2024 |
| **Médias en streaming : envoyer des données web à l’Edge Network d’Adobe Experience Platform avec le SDK web** | Vous pouvez désormais utiliser le SDK web d’Adobe Experience Platform pour envoyer des données web de médias en streaming à l’Edge Network d’Adobe Experience Platform. Grâce à cette amélioration, vous pouvez créer des campagnes sur mesure et offrir un contenu davantage personnalisé, ce qui se traduit par une quantité plus importante de données de suivi pour vos rapports.<p>Avec cette modification, vous disposez d’une méthode de collecte unifiée pour les implémentations web couvrant toutes les solutions de la plateforme, notamment Customer Journey Analytics, Adobe Real-Time Customer Data Platform, Adobe Journey Optimizer et le transfert d’événements. Auparavant, la seule manière d’envoyer des données web de médias en flux continu à l’Edge Network était d’utiliser l’API Media Edge. <p>(Mise à jour du lien vers la documentation à suivre)</p> | | 31 mai 2024 |
| **Augmentation des seuils de faible trafic par défaut** | À la **mi-avril 2024**, Adobe commencera à augmenter les seuils de faible trafic de la suite de rapports par défaut comme suit : ![seuils de faible trafic](assets/thresholds.png). Cela n’aura d’impact que sur les variables actuellement définies sous les nouveaux seuils. Ces modifications seront apportées de manière incrémentielle. Nous prévoyons que le travail sera terminé d’ici **fin mai**. Au fur et à mesure que ces augmentations sont déployées, vous remarquerez peut-être des modifications pour les variables de cardinalité élevée :<ul><li>D’autres valeurs de dimension peuvent être disponibles pour la création de rapports.</li><li>Les segments et les mesures calculées peuvent inclure davantage de données.</li><li>Les suites de rapports virtuelles basées sur des segments peuvent inclure davantage de données.</li><li>Les exports de classifications peuvent inclure davantage de données.</li></ul> | Mi-avril 2024 | 31 mai 2024 |
| **Paramètres de l’administrateur pour contrôler les comptes et les emplacements utilisés pour l’exportation et l’importation** | Un nouvel onglet &quot;Paramètres d’administration&quot; dans le gestionnaire des emplacements permet aux administrateurs de contrôler si les utilisateurs peuvent créer et modifier des comptes et des emplacements. Ces paramètres s’appliquent lorsque les utilisateurs configurent des comptes d’importation et d’exportation dans le cloud et configurent des emplacements d’importation et d’exportation dans le cloud. <p>Les administrateurs peuvent également limiter les types de comptes (Google Cloud Platform, Azure RBAC, Amazon S3, etc.) que les utilisateurs peuvent créer et utiliser.</p><p>Auparavant, tout utilisateur pouvait créer, modifier et utiliser des comptes et des emplacements pour n’importe quel type de compte.</p><p>(Mise à jour du lien vers la documentation à suivre)</p> | Juin 2024 | Juin 2024 |
| **Partage des comptes et des emplacements utilisés pour l’exportation et l’importation** | Les utilisateurs peuvent désormais mettre les comptes et emplacements qu’ils créent à la disposition de tous les utilisateurs de leur entreprise. Seuls les propriétaires de compte et d’emplacement et les administrateurs système peuvent modifier et supprimer des comptes et des emplacements.<p>Auparavant, les comptes et emplacements ne pouvaient être utilisés que par l’utilisateur qui les avait créés.</p><p>Ces paramètres sont disponibles lorsque les utilisateurs configurent des comptes d’importation et d’exportation dans le cloud et configurent des emplacements d’importation et d’exportation dans le cloud. </p> <p>(Mise à jour du lien vers la documentation à suivre)</p> | Juin 2024 | Juin 2024 |
| **Activity Map utilise moins d’appels au serveur pour le SDK web.** | Actuellement, les événements de lien d’Activity Map sont comptabilisés comme leurs propres événements et engendrent des coûts supplémentaires. Cette amélioration applique certains événements de lien et les regroupe dans l’accès suivant, comme la manière dont les événements sont gérés par AppMeasurement. <p>(Mise à jour du lien vers la documentation à suivre)</p> | La version bêta commence le 31 mai 2024. | À confirmer |

{style="table-layout:auto"}

## Correctifs dans Adobe Analytics

* Correction des problèmes de classifications suivants : AN-343186 ; AN-344711 ; AN-344856 ; AN-345094 ; AN-345179 ; AN-346265 ; AN-345288 ; AN-346339 ; AN-346560 ; AN-347572 ; AN-347681 ; AN-347768 ; AN-348024
* Correction des problèmes d’entrepôt de données suivants : AN-346789 ; AN-347031 ; AN-347568 ;
* Correction des problèmes de flux de données suivants : AN-343616 ; AN-345831 ; AN-345988 ; AN-346124 ; AN-346232 ; AN-346972 ; AN-347680 ; AN-347755 ; AN-347954
* Correction du problème de sources de données suivant : AN-347890 ;
* Correction des problèmes Analysis Workspace suivants : AN-321503 ; AN-343103 ; AN-343471 ; AN-345171 ; AN-345223 ; AN-345912 ; AN-346026 ; AN-346330 ; AN-346839 ; AN-347679
* Correction du problème A4T suivant : AN-345118 ;

### Autres correctifs d’Analytics

AN-327749 ; AN-332949 ; AN-342881 ; AN-343171 ; AN-343708 ; AN-344034 ; AN-345559 ; AN-346023 ; AN-346230 ; AN-346330 ; AN-346469 ; AN-346606 ; AN-346750 ; AN-346973 ; AN-347026 ; AN-347110 ; AN-347439 ;

## Avis importants pour les administrateurs d’Adobe Analytics {#admin}

| Avis | Date d’ajout ou de mise à jour | Description |
| ----------- | ---------- | ---------- |
| **Expiration après 13 mois des`cust_visids`** enregistrés | jeudi 22 mai 2024 | Une prochaine version du moteur de traitement des accès Analytics, **prévue pour juillet 2024**, commence à appliquer une expiration de 13 mois de l’ enregistré. `cust_visids`. Si « Activer la connexité des visiteurs » est activé dans la suite de rapports, ce paramètre est utilisé pour rechercher le `cust_visid` pour une `visid_high/visid_low value` sans `cust_visid` sur l’accès. Actuellement, il n’existe aucune expiration du mappage d’un `cust_visid` pour `visid_high/visid_low`. Avec cette version, si 13 mois ou plus se sont écoulés depuis que `visid_high/visid_low` a eu un `cust_visid` sur un accès, le mappage expire. |
| **Mises à jour des zones géographiques ISO** | 10 mai 2024 | Adobe effectuera les mises à jour 2024 des zones géographiques ISO le 7 juin 2024. Attendez-vous à voir des mises à jour mineures des informations géographiques après cette version. |

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
