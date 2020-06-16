---
description: 'null'
title: Processus de confidentialité
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
translation-type: ht
source-git-commit: dcb07f8717337da904b252864eb7f800f1728231

---


# Processus de confidentialité

Ce processus décrit les étapes à suivre pour que votre mise en œuvre d’Adobe Analytics soit en mesure de prendre en charge les droits d’accès et de suppression relatifs à la Confidentialité des données pour vos sujets des données.

| Description de tâche | Liens vers les instructions et informations supplémentaires |
|--- |--- |
| **Étape 1** : assurez-vous que toutes vos suites de rapports susceptibles de contenir des données relatives à la Confidentialité des données sont mappées à votre organisation Experience Cloud (ou IMS).  Les demandes relatives à la Confidentialité des données sont soumises à l’aide d’une organisation Experience Cloud et seront appliquées à toutes les suites de rapports revendiquées par cette organisation. Les demandes ne s’appliqueront pas aux suites de rapports non mappées à cette organisation, même si elles font partie de votre société de connexion. | Reportez-vous à [Mapper les suites de rapports à une organisation](https://docs.adobe.com/content/help/fr-FR/core-services/interface/about-core-services/report-suite-mapping.html). |
| **Étape 2** : définissez votre politique de conservation des données. | Une politique de conservation des données doit être mise en place afin qu’Adobe puisse traiter les demandes d’accès/de suppression de données relatives à la Confidentialité des données.  Pour plus d’informations, voir la [FAQ sur la conservation des données Analytics](/help/technotes/data-retention.md). |
| **Étape 3** : familiarisez-vous avec les étiquettes DULE/Confidentialité des données, les identifiants Adobe Analytics, les espaces de noms et l’extension d’ID. | Lisez ces rubriques contenues dans ces documents :<ul><li>[Étiquettes relatives à la Confidentialité des données pour les variables Analytics](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[Bonnes pratiques en matière d’étiquetage](/help/admin/c-data-governance/gdpr-analytics-ids.md)</li></ul> |
| **Étape 4** : attribuez des étiquettes d’identité, de sensibilité et de gouvernance des données à chaque variable dans une suite de rapports.  Remarque : souvenez-vous que l’étiquetage doit être vérifié chaque fois qu’une nouvelle suite de rapports est créée ou qu’une nouvelle variable est activée dans une suite de rapports existante. Il peut également être nécessaire de vérifier l’étiquetage lors de l’activation de nouvelles intégrations à des solutions puisque celles-ci peuvent exposer de nouvelles variables nécessitant un étiquetage. Une nouvelle implémentation de vos applications mobiles ou sites web peut modifier la manière dont les variables existantes sont utilisées, rendant nécessaire la mise à jour des étiquettes. | Suivez les instructions de la section [Étiqueter les données d’une suite de rapports](/help/admin/c-data-governance/gdpr-setup-reportsuite.md). |
| **Étape 5** : Connectez-vous à l’API relative à la Confidentialité des données d’Adobe et soumettez les demandes d’accès et de suppression. | En tant que client Adobe Analytics, vous pouvez soumettre des demandes individuelles pour accéder et supprimer des données clients en vertu de la Confidentialité des données, en appelant l’[API relative à la Confidentialité des données d’Adobe Experience Cloud](https://www.adobe.io/apis/experienceplatform/gdpr.html). Vous pouvez soumettre tous les identifiants Analytics (comme décrit dans la section [Bonnes pratiques en matière d’étiquetage](/help/admin/c-data-governance/gdpr-analytics-ids.md)) dans les demandes, ainsi que leurs ID d’espace de noms respectifs (ID de source de données). |
| **Étape 6** : Afficher et gérer les paramètres relatifs à la Confidentialité des données pour votre suite de rapports. | Suivez les instructions de la section [Afficher les paramètres de gouvernance des données de la suite de rapports](/help/admin/c-data-governance/gdpr-view-settings.md). |
