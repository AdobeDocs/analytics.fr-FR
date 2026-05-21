---
title: Durée totale en secondes
description: Le nombre total agrégé de secondes passées sur l’élément de dimension.
feature: Metrics
exl-id: 02302982-ce8c-44e9-9967-0a4f226f5e9e
TQID: https://experienceleague.adobe.com/FQ5FGTOKnJph7C0jWwbcAHA31yUwz7ewQRPykUD6R0E
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 201
ht-degree: 90%

---

# Durée totale en secondes

La [mesure « Durée totale en secondes » indique le nombre agrégé de secondes passées par un visiteur sur un élément de dimension donné](overview.md) Cette mesure s’avère utile lorsque vous souhaitez connaître le temps brut passé sur un élément de dimension donné, et non pas des moyennes comme le proposent d’autres mesures de durée.

Dans Report Builder, cette mesure est intitulée « Durée totale de la visite ».

## Méthode de calcul de cette mesure

Cette mesure utilise les étapes suivantes pour mesurer le calcul :

1. Pour un accès donné, consultez la date et l’heure.
2. Comparez cet accès à l’horodatage du prochain accès de la visite. L’accès de suivi des pages vues et des liens est important.
3. Le nombre de secondes écoulées entre les deux accès contribue à l’élément de dimension.

Les variables persistantes, telles que les [eVars](../dimensions/evar.md), sont comptabilisées dans la durée totale en secondes. Les variables de trafic, telles que [props](../dimensions/prop.md), comprennent les secondes passées lors des appels de suivi des liens suivants.

>[!TIP]
>
>Le temps passé n’est pas mesuré pour le dernier accès de la visite, puisqu’il n’existe aucune demande d’image ultérieure pour mesurer le temps écoulé. Ce concept s’applique également aux visites composées d’un seul accès (un rebond).

Consultez [Présentation de la durée de consultation](time-spent.md) pour obtenir des informations plus générales sur la durée de consultation.
