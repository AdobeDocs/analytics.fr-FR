---
title: Type de connexion
description: La méthode de connexion du visiteur à Internet.
feature: Dimensions
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
TQID: https://experienceleague.adobe.com/5kdDrW5vGzc4EKpLOF4VWzXish439t-aGp6q-XcK3Fs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 76%
---
# Type de connexion

La [dimension](overview.md) « Type de connexion » indique comment le visiteur s’est connecté à Internet. Cette dimension est utile pour déterminer la méthode de connexion à Internet utilisée par les visiteurs pour parcourir votre site. Vous pouvez lʼutiliser pour optimiser le contenu du site en fonction de la vitesse de connexion des visiteurs.

## Renseignement de cette dimension avec des données

Cette dimension est déterminée par une combinaison des données collectées et de la logique côté serveur d’Adobe, et non par une variable que vous définissez.

| Propriété | Valeur |
| --- | --- |
| **Variable** | Aucun |
| **Champ Web SDK/XDM** | Aucun |
| **Paramètre de requête** | [`ct`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Balise XML** | [`<connectionType>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite d’octets** | S.O. |
| **Persistance** | S.O. |

Adobe utilise les règles suivantes pour déterminer sa valeur :

1. Si la chaîne de requête `ct` est égale à `"modem"`, définissez lʼélément de dimension sur `"Modem"`. AppMeasurement collecte uniquement ces données sur les navigateurs Internet Explorer non pris en charge, cet élément de dimension est donc peu courant.
1. Vérifiez lʼadresse IP du hit et référencez-la à une table de recherche interne à Adobe. Si lʼadresse IP provient dʼun opérateur de téléphonie mobile, définissez lʼélément de dimension sur `"Mobile Carrier"`.
1. Si la chaîne de requête `ct` est égale à `"lan"`, définissez lʼélément de dimension sur `"LAN/Wifi"`.
1. Si le hit provient dʼune [source de données](/help/import/data-sources/overview.md) ou est considéré comme un type de hit spécial, définissez lʼélément de dimension sur `"Not specified"`.
1. Si aucune des règles ci-dessus nʼest respectée, la valeur par défaut est `"LAN/Wifi"`.

## Éléments de dimension

Les éléments de dimension comprennent `LAN/Wifi`, `Mobile Carrier`, `Modem` et `Not Specified`.

* **`LAN/Wifi`** : la connexion à Internet a été établie par le biais dʼune ligne fixe ou dʼun point dʼaccès Wi-Fi.
* **`Mobile Carrier`** : le visiteur sʼest connecté à Internet par le biais dʼun opérateur de téléphonie mobile.
* **`Modem`** : le visiteur sʼest connecté à Internet par lʼintermédiaire dʼun modem avec un navigateur Internet Explorer non pris en charge.
* **`Not Specified`** : le hit ne présentait pas de type de connexion.
