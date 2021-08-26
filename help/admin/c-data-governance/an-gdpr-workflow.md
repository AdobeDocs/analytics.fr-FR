---
description: Décrit les étapes à suivre pour permettre à votre implémentation Adobe Analytics de prendre en charge les droits d’accès et de suppression relatifs à la confidentialité des données de vos titulaires de données.
title: Processus de confidentialité
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
source-git-commit: 7cb2489c2deaf8e75c71589895314067a010caf8
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 58%

---

# Processus de confidentialité

Ce processus décrit les étapes à suivre pour que votre mise en œuvre d’Adobe Analytics soit en mesure de prendre en charge les droits d’accès et de suppression relatifs à la Confidentialité des données pour vos sujets des données.

1. **Définissez votre politique de conservation des données.** Une politique de conservation des données est requise pour que l’Adobe à la demande d’accès/de suppression des données relatives à la Confidentialité des données soit en mesure de les traiter.  Pour plus d’informations, voir la [FAQ sur la rétention des données](/help/technotes/data-retention.md).
1. **Familiarisez-vous avec les étiquettes DULE/Confidentialité des données, les identifiants Adobe Analytics, les espaces de noms et l’extension d’ID.** Voir  [Étiquettes relatives à la Confidentialité des données pour les ](/help/admin/c-data-governance/gdpr-labels.md) variables Analytics et  [Bonnes pratiques en matière d’étiquetage](/help/admin/c-data-governance/gdpr-analytics-ids.md).
1. **Attribuez des étiquettes d’identité, de sensibilité et de gouvernance des données à chaque variable dans une suite de rapports.** L’étiquetage doit être vérifié chaque fois qu’une nouvelle suite de rapports est créée ou qu’une nouvelle variable est activée dans une suite de rapports existante. Examinez également l’étiquetage lorsque de nouvelles intégrations de solution sont activées, car elles peuvent exposer de nouvelles variables qui peuvent nécessiter un étiquetage. Une nouvelle implémentation de vos applications mobiles ou sites web peut modifier la manière dont les variables existantes sont utilisées, ce qui peut également nécessiter des mises à jour des étiquettes. Voir [Étiqueter les données d’une suite de rapports](/help/admin/c-data-governance/gdpr-setup-reportsuite.md).
1. **Connectez-vous à l’API relative à la Confidentialité des données d’Adobe et soumettez les demandes d’accès et de suppression.** En tant que client Adobe Analytics, vous pouvez soumettre des demandes individuelles pour accéder et supprimer des données clients en vertu de la Confidentialité des données, en appelant l’[API relative à la Confidentialité des données d’Adobe Experience Cloud](https://www.adobe.io/apis/experienceplatform/gdpr.html). Vous pouvez soumettre tous les identifiants Analytics (comme décrit dans la section [Bonnes pratiques en matière d’étiquetage](/help/admin/c-data-governance/gdpr-analytics-ids.md)) dans les demandes, ainsi que leurs ID d’espace de noms respectifs (ID de source de données).
1. **Afficher et gérer les paramètres relatifs à la Confidentialité des données pour votre suite de rapports.** Voir  [Afficher les paramètres de gouvernance des données de la suite de rapports](/help/admin/c-data-governance/gdpr-view-settings.md).
