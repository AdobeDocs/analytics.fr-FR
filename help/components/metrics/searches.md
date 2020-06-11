---
title: Recherches
description: Nombre de fois où un accès correspondait à des critères de recherche externe.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 1%

---


# Recherches

La mesure Recherches indique le nombre d’accès qui correspondent à la détection de recherche externe Adobe. Cette mesure s’avère utile lorsque vous souhaitez examiner les valeurs de dimension autres que la recherche et voir comment elles ont contribué au trafic des moteurs de recherche.

## Méthode de calcul de cette mesure

Cette mesure comptabilise le nombre d’accès qui correspondent à la détection de recherche externe Adobe. Elle doit correspondre aux deux éléments suivants :

* La valeur de parrain de l’accès est un domaine de recherche reconnu par Adobe.
* L’URL de référence de l’accès contient un paramètre de chaîne de requête de mot-clé. En raison des pratiques modernes de confidentialité, cette valeur de chaîne de requête est généralement vide. Adobe reconnaît les chaînes de requête de mots-clés vides dans le cadre de la détection de la recherche.
