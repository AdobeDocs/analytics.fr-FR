---
title: Qu’est-ce que la variable currencyCode et comment l’utiliser ?
description: Pour les sites d’e-commerce, définit la devise utilisée par la page.
feature: Appmeasurement Implementation
exl-id: 3332c366-c472-4778-96c8-ef0aa756cca8
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 98%

---

# currencyCode

Pour les sites qui utilisent le commerce, les recettes et la devise constituent une partie importante d’Analytics. De nombreux sites, notamment ceux qui s’étendent sur plusieurs pays, utilisent des devises différentes. Utilisez la variable `currencyCode` pour vous assurer que les attributs de chiffre d’affaires correspondent à la devise appropriée.

La conversion de devise applique la logique suivante à chaque accès. Ces étapes s’appliquent aux valeurs de chiffre d’affaires définies par la variable [`products`](../page-vars/products.md) et tous les événements répertoriés comme « Devise » dans [Événements de succès](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) sous Paramètres de la suite de rapports.

* Si `currencyCode` n’est pas défini, Adobe suppose que toutes les valeurs de devise sont la devise de la suite de rapports. Consultez [Paramètres généraux du compte](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) dans les paramètres de la suite de rapports pour afficher la devise de la suite de rapports.
* Si `currencyCode` est défini et correspond à la devise de la suite de rapports, aucune conversion de devise n’est appliquée.
* Si `currencyCode` est défini et différent de la devise de la suite de rapports, Adobe applique une conversion de devise basée sur le taux de change du jour en cours. Adobe collabore avec [XE](https://xe.com) pour convertir chaque jour des devises. Toutes les valeurs stockées dans la suite de rapports ont la devise de la suite de rapports.
* Si `currencyCode` est défini sur une valeur non valide, **l’accès complet est ignoré, ce qui entraîne une perte de données.** Assurez-vous que cette variable est correctement définie lorsqu’elle est utilisée.

Cette variable ne persiste pas entre les accès. Assurez-vous que cette variable est définie sur chaque page qui implique des chiffres d&#39;affaires ou des événements de devise qui ne correspondent pas à la devise par défaut de la suite de rapports.

>[!NOTE]
>
>Bien que les codes de devise puissent changer d’une page à l’autre, toutes les mesures de devise d’un seul accès doivent utiliser la même devise.

Un point **doit** doit être utilisé comme séparateur de devise pour toutes les devises lors de la mise en place de cette variable. Par exemple, la couronne suédoise, qui utilise généralement un séparateur à virgules, doit être modifiée pour utiliser un point dans la variable `products` et dans tous les événements de devise. Adobe affiche le bon séparateur de devise dans les rapports.

## Code de devise utilisant le SDK Web

Le code de devise est mappé aux variables suivantes :

* [Objet XDM](/help/implement/aep-edge/xdm-var-mapping.md) : `xdm.commerce.order.currencyCode`
* [Objet de données](/help/implement/aep-edge/data-var-mapping.md) : `data.__adobe.analytics.currencyCode` ou `data.__adobe.analytics.cc`

## Code de devise utilisant l’extension Adobe Analytics

Le code de devise correspond à un champ sous l’accordéon [!UICONTROL Général] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [Collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
1. Développez l’accordéon [!UICONTROL Général], qui affiche le champ [!UICONTROL Code de devise].

Vous pouvez utiliser un code de devise prédéfini ou un code de devise personnalisé. Si vous utilisez un code de devise personnalisé, assurez-vous que le code est valide.

## Code de devise dans le SDK Adobe Experience Platform Mobile

Le code de devise est transmis aux SDK Adobe Experience Platform Mobile par le biais de variables de données contextuelles dans l’extension Adobe Analytics.

1. Définissez le code de devise dans une variable de données contextuelles pendant `trackState` ou `trackAction`.
1. Créez une règle de traitement dans les outils d’administration d’Adobe Analytics pour la suite de rapports. Définissez la règle pour remplacer la variable du code de devise.
1. Transmettez le code de devise à la variable `products` dans votre appel à `trackState` ou `trackAction`.

Vous pouvez utiliser un code de devise prédéfini ou un code de devise personnalisé. Si vous utilisez un code de devise personnalisé, assurez-vous que le code est valide.

## s.currencyCode dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.currencyCode` est une chaîne contenant un code en majuscules de 3 lettres représentant la devise sur la page. Les valeurs sont sensibles à la casse.

```js
s.currencyCode = "USD";
```

Les codes de devise suivants sont valides :

| Code de devise | Étiquette |
| --- | --- |
| `AED` | Émirats arabes unis, dirams |
| `AFA` | Afghanistan, afghanis |
| `ALL` | Albanie, leks |
| `AMD` | Arménie, drams |
| `ANG` | Antilles néerlandaises, florins |
| `AOA` | Angola, kwanza |
| `ARS` | Argentine, pesos |
| `AUD` | Australie, dollars |
| `AWG` | Aruba, florins |
| `AZM` | Azerbaïdjan, manats |
| `BAM` | Bosnie-Herzégovine, marks convertibles |
| `BBD` | Barbade, dollars |
| `BDT` | Bangladesh, taka |
| `BGN` | Bulgarie, leva |
| `BHD` | Bahreïn, dinars |
| `BIF` | Burundi, francs |
| `BMD` | Bermudes, dollars |
| `BND` | Brunei, dollars |
| `BOB` | Bolivie, bolivianos |
| `BRL` | Brésil, réaux |
| `BSD` | Bahamas, dollars |
| `BTN` | Bhoutan, ngultrum |
| `BWP` | Botswana, pulas |
| `BYR` | Biélorussie, roubles |
| `BZD` | Belize, dollars |
| `CAD` | Canada, dollars |
| `CDF` | Congo/Kinshasa, francs |
| `CHF` | Suisse, francs |
| `CLP` | Chili, pesos |
| `CNY` | Chine, yuan renminbi |
| `COP` | Colombie, pesos |
| `CRC` | Costa Rica, colons |
| `CSD` | Serbie, dinars |
| `CUP` | Cuba, pesos |
| `CVE` | Cap-Vert, escudos |
| `CYP` | Chypre, livres |
| `CZK` | République tchèque, couronnes |
| `DJF` | Djibouti, francs |
| `DKK` | Danemark, couronnes |
| `DOP` | République dominicaine, pesos |
| `DZD` | Algérie, dinars |
| `EEK` | Estonie, couronnes |
| `EGP` | Égypte, livres |
| `ERN` | Érythrée, nakfa |
| `ETB` | Éthiopie, birr |
| `EUR` | Euro |
| `FJD` | Fidji, dollars |
| `FKP` | Îles Malouines, livres |
| `GBP` | Royaume-Uni, livres |
| `GEL` | Géorgie, laris |
| `GGP` | Guernesey, livres |
| `GHC` | Ghana, cedis |
| `GIP` | Gibraltar, livres |
| `GMD` | Gambie, dalasi |
| `GNF` | Guinée, francs |
| `GTQ` | Guatemala, quetzals |
| `GYD` | Guyana, dollars |
| `HKD` | Hong Kong, dollars |
| `HNL` | Honduras, lempiras |
| `HRK` | Croatie, kuna |
| `HTG` | Haïti, gourdes |
| `HUF` | Hongrie, forint |
| `IDR` | Indonésie, rupiahs |
| `ILS` | Israël, nouveaux shékels |
| `IMP` | Île de Man, livres |
| `INR` | Inde, roupies |
| `IQD` | Irak, dinars |
| `IRR` | Iran, rials |
| `ISK` | Islande, couronne |
| `JEP` | Jersey, livres |
| `JMD` | Jamaïque, dollars |
| `JOD` | Jordanie, dinars |
| `JPY` | Japon, yen |
| `KES` | Kenya, shillings |
| `KGS` | Kirghizistan, soms |
| `KHR` | Cambodge, riels |
| `KMF` | Comores, francs |
| `KPW` | Corée du Nord, won |
| `KRW` | Corée du Sud, won |
| `KWD` | Koweït, dinars |
| `KYD` | Îles Caïmans, dollars |
| `KZT` | Kazakhstan, tenge |
| `LAK` | Laos, kips |
| `LBP` | Liban, livres |
| `LKR` | Sri Lanka, roupies |
| `LRD` | Libéria, dollars |
| `LSL` | Lesotho, maloti |
| `LTL` | Lituanie, litas |
| `LVL` | Lettonie, lats |
| `LYD` | Libye, dinars |
| `MAD` | Maroc, dirhams |
| `MDL` | Moldavie, lei |
| `MGA` | Madagascar, ariary |
| `MKD` | Macédoine, denars |
| `MMK` | Myanmar, kyats |
| `MNT` | Mongolie, tugriks |
| `MOP` | Macao, patacas |
| `MRO` | Mauritanie, ouguiyas |
| `MTL` | Malte, lires |
| `MUR` | Maurice, roupies |
| `MVR` | Maldives, rufiyaa |
| `MWK` | Malawi, kwachas |
| `MXN` | Mexique, pesos |
| `MYR` | Malaisie, ringgits |
| `MZM` | Mozambique, meticais |
| `NAD` | Namibie, dollars |
| `NGN` | Nigéria, nairas |
| `NIO` | Nicaragua, cordobas d’or |
| `NOK` | Norvège, couronnes |
| `NPR` | Népal, roupies |
| `NZD` | Nouvelle-Zélande, dollars |
| `OMR` | Oman, rials |
| `PAB` | Panama, balboas |
| `PEN` | Pérou, nouveaux sols |
| `PGK` | Papouasie-Nouvelle-Guinée, kina |
| `PHP` | Philippines, pesos |
| `PKR` | Pakistan, roupies |
| `PLN` | Pologne, zlotych |
| `PYG` | Paraguay, guarani |
| `QAR` | Qatar, rials |
| `ROL` | Roumanie, lei |
| `RUR` | Russie, roubles |
| `RWF` | Rwanda, francs |
| `SAR` | Arabie saoudite, rials |
| `SBD` | Îles Salomon, dollars |
| `SCR` | Seychelles, roupies |
| `SDD` | Soudan, dinars |
| `SEK` | Suède, couronne |
| `SGD` | Singapour, dollars |
| `SHP` | Sainte-Hélène, livres |
| `SIT` | Slovénie, tolars |
| `SKK` | Slovaquie, couronnes |
| `SLL` | Sierra Leone, leones |
| `SOS` | Somalie, shillings |
| `SPL` | Seborga, luigino |
| `SRD` | Surinam, dollars |
| `SRG` | Suriname, livres |
| `STD` | Sao Tomé-et-Principe, dobras |
| `SVC` | El Salvador, colons |
| `SYP` | Syrie, livres |
| `SZL` | Swaziland, emalangeni |
| `THB` | Thaïlande, baht |
| `TJS` | Tadjikistan, somoni |
| `TMM` | Turkménistan, manats |
| `TND` | Tunisie, dinars |
| `TOP` | Tonga, pa’anga |
| `TRL` | Turquie, lires |
| `TTD` | Trinité-et-Tobago, dollars |
| `TVD` | Tuvalu, dollars |
| `TWD` | Taïwan, nouveaux dollars |
| `TZS` | Tanzanie, shillings |
| `UAH` | Ukraine, hryvnia |
| `UGX` | Ouganda, shillings |
| `USD` | Dollar US |
| `UYU` | Uruguay, pesos |
| `UZS` | Ouzbékistan, soums |
| `VEB` | Venezuela, bolivars |
| `VND` | Vietnam, dong |
| `VUV` | Vanuatu, vatu |
| `WST` | Samoa, tala |
| `XAF` | Communauté Financière Africaine, francs B |
| `XAG` | Argent, onces |
| `XAU` | Or, onces |
| `XCD` | Caraïbes orientales, dollars |
| `XDR` | Unité panier de compte du FMI |
| `XOF` | Communauté Financière Africaine, francs B |
| `XPD` | Palladium, onces |
| `XPF` | Comptoirs Français du Pacifique Francs |
| `XPT` | Platine, onces |
| `YER` | Yémen, rials |
| `ZAR` | Afrique du Sud, rands |
| `ZMK` | Zambie, kwacha |
| `ZWD` | Zimbabwe, dollar |
