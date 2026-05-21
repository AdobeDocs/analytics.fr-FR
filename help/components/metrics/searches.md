---
title: Recherches
description: Le nombre de fois qu’un accès correspond à des critères de recherche externes.
feature: Metrics
exl-id: b84c895d-e678-47a1-9e41-500970e0a80c
TQID: https://experienceleague.adobe.com/bcK-h9tkOKRHFoZ5EbX05ppNtV5S8Kok8dhMJZxf-ao
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 118
ht-degree: 88%

---

# Recherches

La mesure « Recherches » [mesure](overview.md) indique le nombre d’accès qui correspondent à la détection de recherche externe Adobe. Cette mesure s’avère utile lorsque vous souhaitez consulter les éléments de dimension hors recherche et déterminer la manière dont ils ont contribué au trafic des moteurs de recherche.

## Méthode de calcul de cette mesure

Cette mesure tient compte du nombre d’accès correspondant à la détection de référencement externe d’Adobe. Elle doit correspondre aux deux éléments suivants :

* La valeur de référence de l’accès est un domaine de recherche reconnu par Adobe.
* L’URL de référence de l’accès contient un paramètre de chaîne de requête de mot-clé. En raison des pratiques de confidentialité modernes, cette valeur de chaîne de requête est généralement vide. Adobe reconnaît les chaînes de requête de mot-clé vides dans le cadre de la détection de référencement.
