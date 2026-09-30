---
description: Découvrez comment les tests statistiques sont utilisés dans la comparaison de segments.
keywords: Analysis Workspace ; Segment IQ
title: Tests Statistiques Utilisés Dans La Comparaison De Segments
feature: Segmentation
role: User, Admin
exl-id: b1c235ca-2eab-48d2-bf11-e8a8c4067d03
TQID: 'https://experienceleague.adobe.com/49kZ6LC9OMizQvqxE2PCq1LtqhUHtf5iKQUgpgqSmmE'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
    internal-label: Panels
  - id: c47a19a5-f47b-4e53-afe0-e230da195ebe
    internal-label: Segmentation
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 43%
---
# Tests statistiques utilisés dans la comparaison de segments

Chacun des principaux tableaux de comparaison affiche un score de différence. Ce score est calculé par plusieurs tests statistiques en fonction de la comparaison effectuée. Cependant, quel que soit le test utilisé, le score de différence s’affiche sous la forme d’une valeur comprise entre 0 et 1.

Un score de 0 signifie qu’il n’y a aucune différence entre les deux segments et un score de 1 signifie qu’il y a une très grande différence entre les deux segments. Deux types de tests statistiques sont utilisés pour générer ces scores de différence :

* Pour le tableau **[!UICONTROL Mesures principales]** un test U de Mann-Whitney est utilisé,
* Une comparaison des différences de risque est utilisée pour les tableaux **[!UICONTROL Principaux éléments de Dimension]** et **[!UICONTROL Principaux segments]**.

## Score de différence des top mesures

Dans le tableau Mesures principales , l’outil de comparaison des segments utilise deux exemples de test U de Mann-Whitney. Ce test est un test d’égalité non paramétrique utilisé pour comparer les distributions de probabilité unidimensionnelles de chaque mesure pour chaque segment pris en compte. Le score de différence dans le tableau de mesures est une combinaison de la valeur p de la statistique U calculée (qui représente le degré stochastique (aléatoire) de différence de distribution des deux segments pour une mesure particulière) et la magnitude relative de la différence observée. Un score de différence élevé (proche de 1) signifie que la mesure particulière présente une différence relative importante ainsi qu’une confiance statistique élevée quant à la différence des segments.

## Scores de différences des top éléments de dimension et des top segments

Pour calculer le score de différence des tableaux Top éléments de dimension et Top segments, un algorithme de différenciation des risques relatifs est appliqué (semblable au ratio de risque, bien qu’une différence soit utilisée à la place d’un ratio). Une différence de risque est calculée en soustrayant les incidences cumulées d’un élément de dimension (ou le chevauchement avec un segment du tableau de segments) du segment sélectionné par rapport à un autre. Un score de différence élevé (proche de 1) signifie que l’élément de dimension ou le segment tertiaire particulier était très important dans l’un des segments sélectionnés et pas dans l’autre.

>[!NOTE]
>
>Dans les trois tableaux, la statistique de différence repose sur un échantillon approprié de visiteurs afin que le processus s’exécute aussi rapidement que possible tout en restant statistiquement exact. Même si le score de différence repose sur un échantillon, les résultats présentés dans le tableau ne sont pas échantillonnés. Pour garantir une signification statistique, chaque test statistique s’appuie sur un algorithme d’affectation dynamique de sorte que le segment le plus petit contienne une taille d’échantillon garantissant une marge d’erreur de moins de 3 %. Si un segment contient très peu de visiteurs (moins de 1 000), toutes les données disponibles sont utilisées à la place de l’exemple pour calculer le score de différence.
