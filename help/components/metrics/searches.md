---
title: Recherches
description: Le nombre de fois qu’un accès correspond à des critères de recherche externes.
feature: Metrics
exl-id: b84c895d-e678-47a1-9e41-500970e0a80c
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 88%

---

# Recherches

Les &quot;recherches&quot; [metric](overview.md) indique le nombre d’accès qui correspondent à la détection de recherche externe d’Adobe. Cette mesure s’avère utile lorsque vous souhaitez consulter les éléments de dimension hors recherche et déterminer la manière dont ils ont contribué au trafic des moteurs de recherche.

## Méthode de calcul de cette mesure

Cette mesure tient compte du nombre d’accès correspondant à la détection de référencement externe d’Adobe. Elle doit correspondre aux deux éléments suivants :

* La valeur de référence de l’accès est un domaine de recherche reconnu par Adobe.
* L’URL de référence de l’accès contient un paramètre de chaîne de requête de mot-clé. En raison des pratiques de confidentialité modernes, cette valeur de chaîne de requête est généralement vide. Adobe reconnaît les chaînes de requête de mot-clé vides dans le cadre de la détection de référencement.
