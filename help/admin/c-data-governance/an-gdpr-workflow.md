---
description: Décrit les étapes à suivre pour permettre à votre implémentation Adobe Analytics de prendre en charge les droits d’accès et de suppression relatifs à la confidentialité des données de vos titulaires de données.
title: Processus de confidentialité
feature: Privacy
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
source-git-commit: f6199620033af9c8e304bd0f537d4e0b052ed64d
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 100%

---

# Processus de confidentialité

Ce processus décrit les étapes à suivre pour que votre mise en œuvre d’Adobe Analytics soit en mesure de prendre en charge les droits d’accès et de suppression relatifs à la Confidentialité des données pour vos sujets des données.

1. **Définissez votre politique de conservation des données.** Une politique de rétention des données est nécessaire pour quʼAdobe puisse répondre aux demandes dʼaccès/de suppression des données relatives à la confidentialité des données.  Pour plus dʼinformations, voir la [FAQ sur la rétention des données](/help/technotes/data-retention.md).
1. **Familiarisez-vous avec les étiquettes DULE/Confidentialité des données, les identifiants Adobe Analytics, les espaces de noms et l’extension d’ID.** Voir les [Étiquettes relatives à la confidentialité des données pour les variables Analytics](/help/admin/c-data-governance/gdpr-labels.md) et les [Bonnes pratiques en matière dʼétiquetage](/help/admin/c-data-governance/gdpr-analytics-ids.md).
1. **Attribuez des étiquettes d’identité, de sensibilité et de gouvernance des données à chaque variable dans une suite de rapports.** Lʼétiquetage doit être vérifié chaque fois quʼune nouvelle suite de rapports est créée ou quʼune nouvelle variable est activée dans une suite de rapports existante. Vérifiez également lʼétiquetage lors de lʼactivation de nouvelles intégrations à des solutions puisque celles-ci peuvent exposer de nouvelles variables nécessitant un étiquetage. Une nouvelle implémentation de vos applications mobiles ou sites Web peut modifier la manière dont les variables existantes sont utilisées, rendant nécessaire la mise à jour des étiquettes. Voir [Étiquetage des données dʼune suite de rapports](/help/admin/c-data-governance/gdpr-setup-reportsuite.md).
1. **Connectez-vous à l’API relative à la Confidentialité des données d’Adobe et soumettez les demandes d’accès et de suppression.** En tant que client Adobe Analytics, vous pouvez soumettre des demandes individuelles pour accéder et supprimer des données clients en vertu de la Confidentialité des données, en appelant l’[API relative à la Confidentialité des données d’Adobe Experience Cloud](https://www.adobe.io/apis/experienceplatform/gdpr.html). Vous pouvez soumettre tous les identifiants Analytics (comme décrit dans la section [Bonnes pratiques en matière d’étiquetage](/help/admin/c-data-governance/gdpr-analytics-ids.md)) dans les demandes, ainsi que leurs ID d’espace de noms respectifs (ID de source de données).
1. **Afficher et gérer les paramètres relatifs à la Confidentialité des données pour votre suite de rapports.** Voir [Afficher les paramètres de gouvernance des données de la suite de rapports](/help/admin/c-data-governance/gdpr-view-settings.md).
