---
description: Décrit comment définir des codes de devise cible pour permettre une prise en charge multidevise.
title: Prise en charge multidevise
topic: null
uuid: null
translation-type: ht
source-git-commit: 63a6ca92ae5fe103648c74bd16bcdf90858c71f3

---


# Prise en charge multidevise

Ce document décrit comment définir des codes de devise cible pour permettre une prise en charge multidevise.

Les codes de devise cible sont définis à trois niveaux :

## Niveau de page

Vous pouvez définir une variable JavaScript pour la devise cible au niveau de la page. Le propriétaire du site définit cette variable avec le code de devise ISO 4217 à trois lettres approprié (comme indiqué ci-dessous dans ce document). Si la variable [currencyCode](https://docs.adobe.com/content/help/fr-FR/analytics/implementation/vars/config-vars/currencycode.translate.html) n’est pas définie à ce niveau, la devise par défaut est la même que celle spécifiée dans la suite de rapports. Si la variable au niveau de la page est en conflit avec la variable spécifiée dans la suite de rapports, la variable dans la suite de rapports est prioritaire.


## Niveau de la suite de rapports

La **devise de base** est spécifiée lors de la [création de suites de rapports](https://docs.adobe.com/content/help/fr-FR/analytics/admin/manage-report-suites/new-report-suite/new-report-suite.html). Ce paramètre de devise par défaut est prioritaire sur les codes de devise définis au niveau de la page. Par conséquent, si une suite de rapports inclut des commandes qui acceptent les dollars américains, l’euro et la livre sterling, et si, dans la suite de rapports, le code de devise par défaut est défini sur les dollars américains, la base de données dorsale de rapports traduit toutes les transactions en dollars américains.

Les rapports marketing utilisent le taux de change en vigueur au moment de la demande d’image afin de traduire les valeurs en devise au niveau de la page en valeurs dans la devise par défaut de la suite de rapports. Les suites de rapports utilisent le dollar américain comme devise par défaut.


## Niveau de rapport

Les utilisateurs peuvent définir la devise par défaut des rapports pour une session de connexion utilisateur. Cette fonctionnalité est accessible à partir du lien **Options d’affichage** de chaque rapport de conversion. Les rapports marketing utilisent le taux de change en vigueur au moment de l’exécution du rapport pour traduire les valeurs en devise de la suite de rapports en valeurs dans la devise spécifiée dans le rapport.

## Codes de devise pris en charge (ISO 4217)

Actuellement, Analytics prend en charge les formats de devise suivants pour les transactions de conversion :


« AFA » Afghanistan, afghanis (AFA)

« AFN » Afghanistan, afghanis (AFN)

« ALL » Albanie, leks (ALL)

« DZD » Algérie, dinars (DZD)

« AOA » Angola, kwanzas (AOA)

« ARS » Argentine, pesos (ARS)

« AMD » Arménie, drams (AMD)

« AWG » Aruba, florins (AWG)

« AUD » Australie, dollars (AUD)

« AZM » Azerbaïdjan, manats (AZM)

« AZN » Azerbaïdjan, manats nouveaux (AZN)

« BSD » Bahamas, dollars (BSD)

« BHD » Bahreïn, dinars (BHD)

« BDT » Bangladesh, takas (BDT)

« BBD » Barbade, dollars (BBD)

« BYR » Biélorussie, roubles (BYR)

« BZD » Belize, dollars (BZD)

« BMD » Bermudes, dollars (BMD)

« BTN » Bhoutan, ngultrum (BTN)

« BOB » Bolivie, bolivianos (BOB)

« BAM » Bosnie-Herzégovine, marks convertibles (BAM)

« BWP » Botswana, pulas (BWP)

« BRL » Brésil, réaux (BRL)

« BND » Brunei, dollars (BND)

« BGN » Bulgarie, leva (BGN)

« BIF » Burundi, francs (BIF)

« KHR » Cambodge, riels (KHR)

« CAD » Canada, dollars (CAD)

« CVE » Cap-Vert, escudos (CVE)

« KYD » Îles Caïmans, dollars (KYD)

« CLP » Chili, pesos (CLP)

« CNY » Chine, yuans renminbi (CNY)

« COP » Colombie, pesos (COP)

« XOF » Communauté Financière Africaine, francs BCEAO (XOF)

« XAF » Communauté Financière Africaine, francs BEAC (XAF)

« KMF » Comores, francs (KMF)

« XPF » Collectivités françaises du Pacifique, francs (XPF)

« CDF » Congo/Kinshasa, francs (CDF)

« CRC » Costa Rica, colons (CRC)

« HRK » Croatie, kunas (HRK)

« CUC » Cuba, pesos convertibles (CUC)

« CUP » Cuba, pesos (CUP)

« CYP » Chypre, livres (CYP)

« CZK » République tchèque, couronnes (CZK)

« DKK » Danemark, couronnes (DKK)

« DJF » Djibouti, francs (DJF)

« DOP » République dominicaine, pesos (DOP)

« XCD » Caraïbes orientales, dollars (XCD)

« EGP » Égypte, livres (EGP)

« SVC » El Salvador, colons (SVC)

« ERN » Érythrée, nakfa (ERN)

« XBT » ERR (XBT)

« EEK » Estonie, couronnes (EEK)

« ETB » Éthiopie, birrs (ETB)

« EUR » Euro (EUR)

« FKP » Îles Malouines, livres (FKP)

« FJD » Fidji, dollars (FJD)

« GMD » Gambie, dalasis (GMD)

« GEL » Géorgie, laris (GEL)

« GHC » Ghana, cedis (GHC)

« GHS » Ghana, cedis (GHS)

« GIP » Gibraltar, livres (GIP)

« XAU » Or, onces (XAU)

« GTQ » Guatemala, quetzals (GTQ)

« GGP » Guernesey, livres (GGP)

« GNF » Guinée, francs (GNF)

« GYD » Guyane, dollars (GYD)

« HTG » Haïti, gourdes (HTG)

« HNL » Honduras, lempiras (HNL)

« HKD » Hong Kong, dollars (HKD)

« HUF » Hongrie, forints (HUF)

« ISK » Islande, couronnes (ISK)

« INR » Inde, roupies (INR)

« IDR » Indonésie, rupiahs (IDR)

« XDR » Fonds Monétaire International, droits de tirage spéciaux (XDR)

« IRR » Iran, rials (IRR)

« IQD » Irak, dinars (IQD)

« IMP » Île de Man, livres (IMP)

« ILS » Israël, nouveaux shekels (ILS)

« JMD » Jamaïque, dollars (JMD)

« JPY » Japon, yens (JPY)

« JEP » Jersey, livres (JEP)

« JOD » Jordanie, dinars (JOD)

« KZT » Kazakhstan, tenges (KZT)

« KES » Kenya, shillings (KES)

« KWD » Koweït, dinars (KWD)

« KGS » Kirghizistan, soms (KGS)

« LAK » Laos, kips (LAK)

« LVL » Lettonie, lats (LVL)

« LBP » Liban, livres (LBP)

« LSL » Lesotho, maloti (LSL)

« LRD » Libéria, dollars (LRD)

« LYD » Libye, dinars (LYD)

« LTL » Lituanie, litas (LTL)

« MOP » Macao, patacas (MOP)

« MKD » Macédoine, denars (MKD)

« MGA » Madagascar, ariary (MGA)

« MWK » Malawi, kwachas (MWK)

« MYR » Malaisie, ringgits (MYR)

« MVR » Maldives, rufiyaa (MVR)

« MTL » Malte, lires (MTL)

« MRO » Mauritanie, Ouguiyas (MRO)

« MUR » Maurice, roupies (MUR)

« MXN » Mexique, pesos (MXN)

« MDL » Moldavie, lei (MDL)

« MNT » Mongolie, tugriks (MNT)

« MAD » Maroc, dirhams (MAD)

« MZN » Mozambique, meticais (MZN)

« MZM » Mozambique, meticais (MZM)

« MMK » Myanmar, kyats (MMK)

« NAD » Namibie, dollars (NAD)

« NPR » Népal, roupies (NPR)

« ANG » Antilles néerlandaises, florins (ANG)

« NZD » Nouvelle-Zélande, dollars (NZD)

« NIO » Nicaragua, cordobas d’or (NIO)

« NIO » Nigéria, nairas (NGN)

« KPW » Corée du Nord, wons (KPW)

« NOK » Norvège, couronnes (NOK)

« OMR » Oman, rials (OMR)

« PKR » Pakistan, roupies (PKR)

« XPD » Palladium, onces (XPD)

« PAB » Panama, balboas (PAB)

« PGK » Papouasie-Nouvelle-Guinée, kinas (PGK)

« PYG » Paraguay, guaranis (PYG)

« PEN » Pérou, nouveaux soles (PEN)

« PHP » Philippines, pesos (PHP)

« XPT » Platine, onces (XPT)

« PLN » Pologne, złotys (PLN)

« QAR » Qatar, rials (QAR)

« ROL » Roumanie, lei (ROL)

« RON » Roumanie, nouveaux lei (RON)

« RUB » Russie, roubles (RUB)

« RUR » Russie, roubles (RUR)

« RWL » Rwanda, francs (RWF)

« SHP » Sainte-Hélène, livres (SHP)

« WST » Samoa, talas (WST)

« STD » São Tomé-et-Principe, dobras (STD)

« SAR » Arabie saoudite, rials (SAR)

« SPL » Seborga, luigini (SPL)

« RSD » Serbie, dinars (RSD)

« CSD » Serbie, dinars (CSD)

« SCR » Seychelles, roupies (SCR)

« SLL » Sierra Leone, leones (SLL)

« XAG » onces d’argent (XAG)

« SGD » Singapour, dollars (SGD)

« SKK » Slovaquie, couronnes (SKK)

« SIT » Slovénie, tolars (SIT)

« SBD » Îles Salomon, dollars (SBD)

« SOS » Somalie, shillings (SOS)

« ZAR » Afrique du Sud, rands (ZAR)

« KRW » Corée du Sud, wons (KRW)

« LKR » Sri Lanka, roupies (LKR)

« SDD » Soudan, dinars (SDD)

« SDG » Soudan, livres (SDG)

« SRD » Surinam, dollars (SRD)

« SRG » Suriname, livres (SRG)

« SZL » Swaziland, emalangenis (SZL)

« SEK » Suède, couronnes (SEK)

« CHF » Suisse, francs (CHF)

« SYP » Syrie, livres (SYP)

« TWD » Taïwan, nouveaux dollars (TWD)

« TJS » Tadjikistan, somonis (TJS)

« TZS » Tanzanie, shillings (TZS)

« THB » Thaïlande, bahts (THB)

« TOP » Tonga, pa’angas (TOP)

« TTD » Trinidad et Tobago, dollars (TTD)

« TND » Tunisie, dinars (TND)

« TRY » Turquie, lire (TRY)

« TRL » Turquie, lires (TRL)

« TMM » Turkménistan, manats (TMM)

« TMT » Turkménistan, nouveaux manats (TMT)

« TVD » Tuvalu, dollars (TVD)

« UGX » Ouganda, shillings (UGX)

« UAH » Ukraine, hryvnia (UAH)

« AED » Émirats arabes unis, dirhams (AED)

« GBP » Royaume-Uni, livres (GBP)

« USD » États-Unis, dollars (USD)

« UYU » Uruguay, pesos (UYU)

« UZS » Ouzbékistan, soums (UZS)

« VUV » Vanuatu, vatu (VUV)

« VEB » Vénézuela, bolivars (VEB)

« VEF » Vénézuela, bolivars fuertes (VEF)

« VND » Vietnam, dong (VND)

« YER » Yémen, rials (YER)

« ZMK » Zambie, kwacha (ZMK)

« ZMW » Zambie, kwacha (ZMW)

« ZWD » Zimbabwe, dollars (ZWD)


## Exemple AppMeasurement.js

La variable `currencyCode` peut être définie globalement dans le fichier AppMeasurement.js. Le fait de définir la variable currencyCode dans ce fichier garantit que toutes les transactions de devises utilisent un code de devise uniforme. L’exemple ci-dessous indique l’euro comme variable `currencyCode` dans la `CONFIG SECTION` du fichier AppMeasurement.js. Tous les événements d’achat seront interprétés comme des transactions en « euro » pour la création de rapports.

```
/************************** CONFIG SECTION **************************/ 
/* You may add or alter any code config here. */ 
s.account="devnow"
s.currencyCode="EUR"
s.trackInlineStats=true 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
***
    
```

Pour plus d’informations sur la modification du fichier AppMeasurement.js, voir [Insertion de code dans le fichier AppMeasurement.js](https://docs.adobe.com/content/help/fr-FR/analytics/implementation/other/dtm/analytics-tool/t-appmeasurement-code.translate.html).

## Autres remarques concernant la mise en œuvre

* Gardez à l’esprit que, alors que les codes de devise peuvent changer d’une page à l’autre, tous les éléments de ligne de conversion définis sur une demande de page donnée doivent utiliser la même devise (par exemple, il est impossible de définir des euros, des livres sterling et des dollars US sur une même page vue). Si vous ne souhaitez pas effectuer de conversion de devise, laissez la valeur de la variable currencyCode vide. Les valeurs envoyées sont ainsi transmises directement aux rapports sans conversion.

* Si vous définissez une valeur non valide dans la variable currencyCode (toute valeur ne figurant pas dans la liste des codes de devise pris en charge), l’accès complet est exclu et les données ne sont pas collectées pour cette transaction. Avant de définir `currencyCode` en production, utilisez une suite de rapports de test pour vérifier que les données sont collectées et que la conversion de devise est correcte.

* Les devises qui n’utilisent pas un point (.) comme séparateur doivent être modifiées afin d’utiliser un point plutôt que leur séparateur habituel. Par exemple, la couronne suédoise qui utilise la virgule (,) devra être modifiée pour utiliser un point comme séparateur des décimales. Dans le cas contraire, comme Analytics utilise la virgule pour séparer les valeurs, les données ne seraient pas transmises correctement. Le point, au contraire, permet de transmettre les valeurs aux rapports.
