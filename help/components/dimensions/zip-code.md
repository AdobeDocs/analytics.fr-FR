---
title: Code postal
description: Le code postal du visiteur.
feature: Dimensions
exl-id: 597619f8-a581-4491-beb2-c14b1f7b7bec
TQID: https://experienceleague.adobe.com/XHrUXKHrXiH0wsUr0klmPmA-DEq5T5yu18KLNT7oYeo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
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
source-wordcount: '330'
ht-degree: 61%
---
# Code postal

La dimension « Code postal » [dimension](overview.md) indique le code postal du visiteur. Vous pouvez utiliser cette dimension pour mieux comprendre les résultats positifs de la publicité locale ou déterminer les régions du monde dans lesquelles votre site est plus performant.

## Renseignement de cette dimension avec des données

Cette dimension est unique dans la mesure où elle présente plusieurs manières de la renseigner avec des données. Vous pouvez utiliser l’une des options ou une combinaison des deux :

* Définissez le code postal directement à l’aide de la variable [`zip`](/help/implement/vars/page-vars/zip.md) .
* Configurez-le pour extraire les données de géolocalisation. Lorsque le code postal géolocalisé est utilisé, aucune variable n’est définie. Pour les implémentations d’AppMeasurement, cette dimension est prête à l’emploi. Pour les implémentations de Web SDK, activez [!UICONTROL Recherche géographique] lors de la [configuration d’un flux de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr).

L’[!UICONTROL option de code postal] sous [Paramètres généraux du compte](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) contrôle la manière dont vous souhaitez renseigner cette dimension. Le tableau de référence ci-dessous s’applique lorsque vous définissez directement la variable `zip`.

| Propriété | Valeur |
| --- | --- |
| **Variable** | [`zip`](/help/implement/vars/page-vars/zip.md) |
| **Champ Web SDK/XDM** | [`placeContext.geo.postalCode`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/geo) |
| **Paramètre de requête** | [`zip`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Balise XML** | [`<zip>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite d’octets** | 50 octets |
| **Persistance** | Hit |

## Éléments de dimension

Les éléments de dimension comprennent le code postal (ZIP) de la visiteuse ou du visiteur.

## Pays pour lesquels les codes postaux sont pris en charge

* Îles Åland
* Albanie
* Algérie
* Argentine
* Arménie
* Autriche
* Australie
* Bangladesh
* Barbade
* Belgique
* Brésil
* Bulgarie
* Canada
* Chili
* Chine
* Colombie
* Costa Rica
* Croatie
* République tchèque
* Danemark
* Équateur
* Égypte
* Estonie
* Finlande
* France
* Géorgie
* Allemagne
* Gibraltar
* Grèce
* Grenade
* Guatemala
* Hong Kong (RAS de la Chine)
* Hongrie
* Inde
* Indonésie
* Irlande
* Israël
* Italie
* Japon
* Jordanie
* Kazakhstan
* Kirghizistan
* Lettonie
* Liban
* Lituanie
* Luxembourg
* Malaisie
* Malte
* Maurice
* Mexique
* Maroc
* Mozambique
* Népal
* Pays-bas
* Nouvelle-Zélande
* Norvège
* Pakistan
* Panama
* Pérou
* Philippines
* Pologne
* Portugal
* Porto Rico
* Qatar
* Roumanie
* Fédération de Russie
* Arabie saoudite
* Sénégal
* Serbie
* Singapour
* Slovénie
* Afrique du Sud
* Corée du Sud
* Espagne
* Sri Lanka
* Suède
* Suisse
* Région de Taïwan
* Thaïlande
* Tunisie
* Turquie
* Ukraine
* Émirats arabes unis
* Royaume-Uni
* États-Unis
* Uruguay
* Ouzbékistan
* Venezuela
* Vietnam
