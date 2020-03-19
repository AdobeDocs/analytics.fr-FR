---
title: currencyCode
desciption: For eCommerce sites, set the currency the page deals in.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# currencyCode

Pour les sites qui utilisent le commerce, les recettes et la devise constituent une partie importante d’Analytics. De nombreux sites, en particulier ceux qui s’étendent sur plusieurs pays, utilisent des devises différentes. Utilisez la `currencyCode` variable pour vous assurer que les attributs de recettes correspondent à la devise appropriée.

Si `currencyCode` n’est pas défini, les valeurs monétaires définies pour la [`products`](../page-vars/products.md) variable et les  de devise sont traitées comme si elles étaient identiques à la devise de la suite de rapports. Voir Paramètres [du compte](/help/admin/admin/general-acct-settings-admin.md) général dans le guide de l’utilisateur Admin pour consulter la devise de la suite de rapports.

Si `currencyCode` est défini et correspond à la devise de la suite de rapports, aucune conversion de devise n’est appliquée.

Si `currencyCode` est défini et différent de la devise de la suite de rapports, Adobe applique une conversion de devise basée sur le taux de change du jour en cours. Adobe collabore avec [XE](https://xe.com) pour convertir chaque jour des devises. Toutes les valeurs stockées dans les serveurs de collecte de données sont stockées en fin de compte dans la devise de la suite de rapports.

> [!IMPORTANT] Si `currencyCode` contient une valeur non valide, l’accès complet est ignoré, ce qui entraîne une perte de données. Assurez-vous que cette variable est correctement définie si vous l’utilisez dans votre implémentation.

Cette variable ne persiste pas entre les accès. Assurez-vous que cette variable est définie sur chaque page qui implique des recettes ou des  de devise.

## Code de devise dans Adobe Experience Platform Launch

Le code de devise est un champ sous l’ [!UICONTROL General] accordéon lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’ [!UICONTROL Extensions] onglet, puis cliquez sur le [!UICONTROL Configure] bouton sous Adobe Analytics.
4. Développez l’ [!UICONTROL General] accordéon, ce qui révèle le [!UICONTROL Currency Code] champ.

Vous pouvez utiliser un code de devise prédéfini ou un code de devise personnalisé. Si vous utilisez un code de devise personnalisé, assurez-vous que le code est valide.

## s.currencyCode dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.currencyCode` variable est une chaîne contenant un code en majuscules de 3 lettres représentant la devise sur la page.

```js
s.currencyCode = "USD";
```

Les codes de devise suivants sont valides :

| Code de devise | Description de la devise |
| --- | --- |
| `AED` | Émirats arabes unis, dirams |
| `AFA` | Afghanistan, afghanis |
| `ALL` | Albanie, leks |
| `AMD` | Arménie, drams |
| `ANG` | Florin des Antilles néerlandaises |
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
| `NIO` | Nicaragua Cordobas doré |
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
| `STD` | Sao Tomé-et-Principe Dobras |
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
| `XAF` | Communauté Financière Africaine Francs B |
| `XAG` | Argent, onces |
| `XAU` | Or, onces |
| `XCD` | Caraïbes orientales, dollars |
| `XDR` | Unité panier de compte du FMI |
| `XOF` | Communauté Financière Africaine Francs B |
| `XPD` | Palladium, onces |
| `XPF` | Comptoirs Français du Pacifique Francs |
| `XPT` | Platine, onces |
| `YER` | Yémen, rials |
| `ZAR` | Afrique du Sud, rands |
| `ZMK` | Zambie, kwacha |
| `ZWD` | Zimbabwe Dollar |
