---
description: Décrit les étapes à suivre pour permettre à votre implémentation Adobe Analytics de prendre en charge les droits d’accès et de suppression relatifs à la confidentialité des données de vos titulaires de données.
title: Processus de confidentialité
feature: Data Governance
role: Admin
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
TQID: 'https://experienceleague.adobe.com/n0zqbcuPD2lvtgYNtdQx5VsBl-FrmzfqU-z2iIn83hg'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: b99602d0-836e-4dbb-979f-c0dec53f883c
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 333
ht-degree: 59%

---

# Processus de confidentialité

Ce processus décrit les étapes à suivre pour que votre mise en œuvre d’Adobe Analytics soit en mesure de prendre en charge les droits d’accès et de suppression relatifs à la Confidentialité des données pour vos titulaires de données.

1. Commencez par la page [Présentation de Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=fr) dans Adobe Experience Platform pour avoir une idée des questions à poser avant d’étiqueter vos données Analytics.
1. **Définissez votre politique de conservation des données.** Une politique de conservation des données est requise pour qu’Adobe traite les demandes d’accès/de suppression des données relatives à la Confidentialité des données.  Pour plus dʼinformations, voir la [FAQ sur la rétention des données](/help/technotes/data-retention.md). Pour utiliser l’API Privacy Service, vous devez vous assurer que la période de conservation des données est définie dans Adobe Analytics.
1. **Familiarisez-vous avec les étiquettes de confidentialité des données, les identifiants Adobe Analytics et les espaces de noms.** Voir [Étiquettes de confidentialité des données pour les variables Analytics](/help/admin/tools/privacy-labeling/labels.md) et [Bonnes pratiques en matière d’étiquetage](/help/admin/tools/privacy-labeling/best-practices.md).
1. **Attribuez des étiquettes d’identité, de sensibilité et de gouvernance des données à chaque variable dans une suite de rapports.** L’étiquetage doit être révisé chaque fois qu’une nouvelle suite de rapports est créée ou qu’une nouvelle variable est activée dans une suite de rapports existante. Vérifiez également lʼétiquetage lors de lʼactivation de nouvelles intégrations à des solutions puisque celles-ci peuvent exposer de nouvelles variables nécessitant un étiquetage. Une nouvelle implémentation de vos applications mobiles ou sites web peut modifier la manière dont les variables existantes sont utilisées, rendant nécessaire la mise à jour des étiquettes. Voir [Étiquetage des données dʼune suite de rapports](/help/admin/tools/privacy-labeling/namespaces.md).
1. **Connectez-vous à l’API relative à la Confidentialité des données d’Adobe et envoyez des demandes d’accès et de suppression.** En tant que client Adobe Analytics, vous pouvez soumettre des demandes individuelles pour accéder et supprimer des données clients en vertu de la Confidentialité des données, en appelant l’[API Adobe Experience Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=fr). Vous pouvez soumettre tous les identifiants Analytics (comme décrit dans la section [Bonnes pratiques en matière d’étiquetage](/help/admin/tools/privacy-labeling/best-practices.md)) dans les demandes, ainsi que leurs ID d’espace de noms respectifs (ID de source de données).
1. **Afficher et gérer les paramètres relatifs à la Confidentialité des données de votre suite de rapports.** Voir [Afficher les paramètres de gouvernance des données de la suite de rapports](/help/admin/tools/privacy-labeling/view-settings.md).
