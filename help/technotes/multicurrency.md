---
description: Décrit comment définir des codes de devise cible pour la prise en charge de devises multiples.
title: Prise en charge de plusieurs devises
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 63a6ca92ae5fe103648c74bd16bcdf90858c71f3

---


# Prise en charge de plusieurs devises

Ce document décrit comment définir des codes de devise cible pour la prise en charge de devises multiples.

Les codes de devise cible sont définis à trois niveaux :

## Niveau de page

Vous pouvez définir une variable JavaScript pour la devise cible au niveau de la page. Le propriétaire du site définit cette variable avec le code de devise ISO 4217 à trois lettres approprié (comme indiqué ci-dessous dans ce document). Si la variable [currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/vars/config-vars/currencycode.html) n’est pas définie à ce niveau, la devise par défaut est la même que celle spécifiée dans la suite de rapports. Si la variable au niveau de la page est en conflit avec la variable spécifiée dans la suite de rapports, la variable dans la suite de rapports est prioritaire.


## Niveau de suite de rapports

La devise **de** base est spécifiée lors de la [création de suites](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/new-report-suite/new-report-suite.html)de rapports. Il s’agit du paramètre par défaut pour la devise et prévaut sur les codes de devise définis au niveau de la page. Ainsi, si une suite de rapports comporte des commandes acceptant les dollars américains, l’euro et les livres sterling et que le code de devise par défaut de la suite de rapports est &quot;dollars américains&quot;, la base de données principale de création de rapports traduit toutes les transactions en dollars américains.

Les rapports marketing utilisent le taux de change au moment de la demande d’image pour convertir les valeurs de devise au niveau de la page en valeurs de devise par défaut de la suite de rapports. Les suites de rapports utilisent le dollar américain comme devise par défaut.


## Niveau de rapport

Les utilisateurs peuvent définir la devise par défaut des rapports pour la session de connexion utilisateur. Cette fonctionnalité est accessible à partir du lien **Options d’affichage** de tout rapport de conversion. Les rapports marketing utilisent le taux de change au moment de l’exécution du rapport pour traduire les valeurs de devise de la suite de rapports en valeurs de devise spécifiées dans le rapport.

## Codes de devise pris en charge (ISO 4217)

Analytics prend actuellement en charge les formats de devise suivants pour les transactions de conversion :


Afghanistan Afghanis (AFA)

Afghanistan Afghanis (AFN)

&#39;ALL&#39; Albanie Leke (ALL)

&quot;DZD&quot; Algérie Dinars (DZD)

&#39;AOA&#39; Angola Kwanza (AOA)

&#39;ARS&#39; Argentine Pesos (ARS)

&#39;AMD&#39; - Drams arméniens (AMD)

&quot;AWG&quot; Florins Aruba (AWG)

&#39;AUD&#39; Australie Dollars (AUD)

&quot;AZM&quot; (Azéri Manats)

&quot;AZN&quot; (Azerbaïdjan, Nouveau Manat)

BSD (Bahamas Dollars)

&#39;BHD&#39; Dinars de Bahreïn (BHD)

Bangladesh Taka (BDT)

BBD&#39; (Barbade) Dollars (BBD)

&#39;BYR&#39; Roubles Biélorusses (BYR)

BZD (BZD)

BMD (Bermudes Dollars)

Bhoutan Ngultrum (BTN)

&#39;BOB&#39; Bolivia Bolivianos (BOB)

&quot;BAM&quot; Bosnie-Herzégovine Marka convertible (BAM)

&#39;BWP&#39; Botswana Pulas (BWP)

&quot;BRL&quot; Brésil Reais (BRL)

&quot;BND&quot; Dollars Brunei (BND)

Bulgarie : &quot;BGN&quot; Leva (BGN)

&quot;BIF&quot; Burundi Francs (BIF)

&#39;KHR&#39; Riels Cambodgiens (KHR)

Canada Dollars (CAD)

CVE (Cap Vert Escudos)

&#39;KYD&#39; Dollars Des Îles Caïmans (KYD)

&#39;CLP&#39; Chili Pesos (CLP)

&quot;CNY&quot; Chine Yuan Renminbi (CNY)

&#39;COP&#39; Colombia Pesos (COP)

&quot;XOF&quot; Communauté Financière Africaine Francs BCEAO (XOF)

Communauté Financière Africaine Francs BEAC (XAF)

&#39;KMF&#39; Comores Francs (KMF)

Comptoirs &quot;XPF&quot; Français du Pacifique Francs (XPF)

&quot;CDF&quot; Congo/Kinshasa Francs (CDF)

Costa Rica Colones (CRC)

&quot;HRK&quot; Croatie Kuna (HRK)

CUC Cuba Pesos convertibles (CUC)

&quot;CUP&quot; Cuba Pesos (CUP)

CYP Livres chypriotes

&quot;CZK&quot; République Tchèque Couronnes (CZK)

&quot;DKK&quot; Couronne (DKK)

&quot;DJF&quot; Djibouti Francs (DJF)

&quot;DOP&quot; République Dominicaine Pesos (DOP)

XCD : dollars des Caraïbes orientales (XCD)

&#39;EGP&#39; Egypte Livres (EGP)

&quot;SVC&quot; Colones du Salvador (SVC)

ERN (ERN) Erythrée Nakfa (ERN)

ERR &quot;XBT&quot; (XBT)

&quot;EEK&quot; Estonie Couronne (EEK)

&quot;ETB&quot; Birr (ETB)

Euro &quot;EUR&quot; (EUR)

FKP (FKP)

&quot;FJD&quot; dollars fidjiens (FJD)

Gambie Dalasi (GMD)

&quot;GEL&quot; Georgia Lari (GEL)

&#39;GHC&#39; (Ghana Cedis)

&quot;GHS&quot; (Ghana Cedis)

Gibraltar Livres (GIP)

Onces Or &quot;XAU&quot; (XAU)

Guetzales du Guatemala (GTQ)

&#39;GGP&#39; Guernesey Livres (GGP)

&#39;GNF&#39; Guinée Francs (GNF)

&#39;GYD&#39; Dollars Guyaniens (GYD)

&#39;HTG&#39; Haiti Gourdes (HTG)

&quot;HNL&quot; Honduras Lempiras (HNL)

&quot;HKD&quot; Dollars De Hong Kong (HKD)

&quot;HUF&quot; Hongrie Forint (HUF)

&quot;ISK&quot; Couronne d&#39;Islande (ISK)

&#39;INR&#39; roupies indiennes (INR)

&#39;IDR&#39; Indonésie Roupiahs (IDR)

&quot;XDR&quot; Droits de tirage spéciaux (XDR) du Fonds Monétaire International

&#39;IRR&#39; Iran Rials (IRR)

&#39;IQD&#39; Dinars Irakiens (IQD)

IMP (IMP) Livre (IMP)

&#39;ILS&#39; Israël Nouveaux shekels (ILS)

&quot;JMD&quot; dollars jamaïcains (JMD)

JPY (JPY) Yen (JPY)

JEP Jersey Livres (JEP)

JOD (JOD) Jordan Dinars (JOD)

&quot;KZT&quot; Kazakhstan Tenge (KZT)

&#39;KES&#39; (Kenya Shillings) (KES)

KWD (KWD) Koweït Dinars (KWD)

&quot;KGS&quot; Soms Kirghizistan (KGS)

&#39;LAK&#39; Kips Laos (LAK)

LVL (LVL) Lettonie (LVL)

&quot;LBP&quot; Liban Livres (LBP)

&quot;LSL&quot; Lesotho Maloti (LSL)

&quot;LRD&quot; Dollars Liberia (LRD)

&#39;LYD&#39; Libye Dinars (LYD)

&quot;LTL&quot; Lituanie Litai (LTL)

&quot;MOP&quot; Macao Patacas (MOP)

&#39;MKD&#39; Macédoine Denars (MKD)

&quot;MGA&quot; Ariary (MGA)

&#39;MWK&#39; Malawi Kwachas (MWK)

&#39;MYR&#39; Malaisie Ringgits (MYR)

&#39;MVR&#39; Roufiyaa (MVR) des Maldives

&quot;MTL&quot; Malte Liri (MTL)

&quot;MRO&quot; Mauritanie Ouguiyas (MRO)

&#39;MUR&#39; Roupies mauriciennes (MUR)

&#39;MXN&#39; Pesos Mexicains (MXN)

&quot;MDL&quot; Moldavie Lei (MDL)

Tugriks (MNT) de Mongolie

&#39;MAD&#39; (Maroc Dirhams)

Mozambique Meticais (MZN)

Mozambique Meticais (MZM)

&quot;MMK&quot; Kyats (MMK)

&quot;NAD&quot; Namibie Dollars (NAD)

&#39;NPR&#39; Roupies Népalaises (NPR)

&#39;ANG&#39; Florins des Antilles Néerlandaises (ANG)

&quot;NZD&quot; Dollars Nouvelle-Zélande (NZD)

&quot;NIO&quot; Nicaragua Cordobas (NIO)

&quot;NGN&quot; Nigeria Nairas (NGN)

KPW (Corée du Nord) Won (KPW)

&quot;NOK&quot; Couronne de Norvège (NOK)

OMR (Oman Rials)

&#39;PKR&#39; Roupies Pakistanaises (PKR)

Onces Palladium &quot;XPD&quot; (XPD)

&quot;PAB&quot; Panama Balboas (PAB)

PGK, Papouasie-Nouvelle-Guinée, Chine

Paraguay Guarani (PYG)

&#39;PEN&#39; Pérou Nuevos Soles (PEN)

&#39;PHP&#39; Pesos (PHP)

Onces Platine &quot;XPT&quot; (XPT)

&quot;PLN&quot; Pologne Zlotych (PLN)

QAR : Riyals du Qatar (QAR)

&quot;ROL&quot; Roumanie Lei (ROL)

&quot;RON&quot; Roumanie Nouveau Lei (RON)

&#39;RUB&#39; Russie Roubles (RUB)

&#39;RUR&#39; Russie Roubles (RUR)

&#39;RWF&#39; Rwanda Francs (RWF)

&quot;SHP&quot; Livre (SHP)

Samoa Tala (WST)

&#39;STD&#39; Dobras de São Tomé-et-Principe (STD)

Arabie Saoudite : rials (SAR)

&quot;SPL&quot; Seborga Luigini (SPL)

&quot;RSD&quot; dinars serbes (RSD)

&quot;CSD&quot; Serbe Dinars (CSD)

&quot;SCR&quot; roupies des Seychelles (SCR)

&quot;SLL&quot; Sierra Leone Leones (SLL)

Onces Argent &quot;XAG&quot; (XAG)

&#39;SGD&#39; Dollars de Singapour (SGD)

&quot;SKK&quot; Slovaquie Koruny (SKK)

&quot;SIT&quot; Slovénie Tolars (SIT)

&quot;SBD&quot; Dollars (SBD)

&quot;SOS&quot; Somalie Shillings (SOS)

&#39;ZAR&#39; Rand (ZAR)

&#39;KRW&#39; Corée du Sud Won (KRW)

&quot;LKR&quot; Roupies du Sri Lanka (LKR)

&quot;SDD&quot; Dinars soudanais (SDD)

&quot;SDG&quot; Soudan Livres (SDG)

&quot;SRD&quot; Dollars Surinam (SRD)

&#39;SRG&#39; Surinam Guilders (SRG)

&quot;SZL&quot; Swaziland Emalangeni (SZL)

&quot;SEK&quot; Couronne suédoise (SEK)

&quot;CHF&quot; Suisse Francs (CHF)

SYP (SYP) Livres Syriennes

TWD (TWD) Nouveaux dollars (TWD)

&#39;TJS&#39; Tajikistan Somoni (TJS)

&#39;TZS&#39; Tanzanie Shillings (TZS)

&#39;THB&#39; Thailand Baht (THB)

&#39;TOP&#39; Tonga Pa&#39;anga (TOP)

&quot;TTD&quot; Dollars (TTD)

&#39;TND&#39; Tunisie Dinars (TND)

&#39;TRY&#39; Turquie Lira (TRY)

&#39;TRL&#39; Turquie Liras (TRL)

&#39;TMM&#39; Turkménistan Manats (TMM)

&#39;TMT&#39; Turkménistan Nouveau Manat (TMT)

&quot;TVD&quot; Dollars Tuvalu (TVD)

UGX (Ouganda) Shillings (UGX)

&quot;UAH&quot; Ukraine Hryvnia (UAH)

&quot;AED&quot; Dirhams (AED) des Émirats arabes unis

&quot;GBP&quot; Livre (GBP)

&quot;USD&quot; sélectionné Dollars des États-Unis (USD)

&quot;UYU&quot; Uruguay Pesos (UYU)

UZS (UZS)

Vanuatu Vatu (VUV)

&#39;VEB&#39; Venezuela Bolivares (VEB)

Venezuela Bolivares Fuertes (VEF)

Vietnam Dong (VND)

YER Rials Yemen (YER)

&quot;ZMK&quot; Zambie Kwacha (ZMK)

&#39;ZMW&#39; Zambie Kwacha (ZMW)

ZWD (ZWD) Dollars du Zimbabwe (ZWD)


## Exemple d’AppMeasurement.js

La `currencyCode` variable peut être définie globalement dans le fichier AppMeasurement.js. La définition de la variable currencyCode dans ce fichier garantit que toutes les transactions de devise utilisent un code de devise uniforme. L’exemple ci-dessous spécifie Euros comme `currencyCode` variable dans le fichier `CONFIG SECTION` AppMeasurement.js. Tous les événements d&#39;achat seront interprétés en déclarant comme des transactions en &quot;euro&quot;.

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

Pour plus d’informations sur la modification du fichier AppMeasurement.js, voir [Insertion de code dans le fichier](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html)AppMeasurement.js.

## Autres remarques concernant l’implémentation

* Gardez à l’esprit que si les codes de devise peuvent changer d’une page à l’autre, tous les éléments de ligne de conversion définis dans une requête de page donnée doivent utiliser la même devise (par exemple, vous ne pouvez pas définir les euros, les livres sterling et les dollars US sur la même page vue). Si vous ne souhaitez pas effectuer de conversion de devise, laissez la valeur currencyCode vide. Les valeurs envoyées sont ainsi transmises directement aux rapports sans conversion.

* Si vous définissez un code de devise non valide (toute valeur ne figurant pas dans la liste Codes de devise pris en charge), l’accès complet est exclu et les données ne sont pas collectées pour cette transaction. Avant de définir `currencyCode` en production, utilisez une suite de rapports de test pour vérifier que les données sont collectées et que la conversion de devise est correcte.

* Les devises qui n’utilisent pas un point (.) comme séparateur doivent être modifiées afin d’utiliser un point plutôt que leur séparateur habituel. Par exemple, la couronne suédoise, qui utilise la virgule (,), devra être modifiée pour utiliser un point comme séparateur des décimales. Analytics utilise la virgule pour séparer les valeurs et les données ne seront pas transmises correctement. La période transmet correctement la valeur aux rapports.
