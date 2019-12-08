---
description: Affiche des informations concernant les visiteurs, notamment le nombre de visiteurs, la fidélité des clients et les caractéristiques des visiteurs.
title: Rapports sur les visiteurs
topic: Ad hoc analysis
uuid: 3e9b41d1-d6ff-47a8-aa6b-829df1040c34
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Rapports sur les visiteurs

Affiche des informations concernant les visiteurs, notamment le nombre de visiteurs, la fidélité des clients et les caractéristiques des visiteurs.

## Fréquence des retours {#concept_447A99B71E484D27A7A02888CC51FD3D}

Ce rapport indique le délai qui s’écoule entre chaque visite des visiteurs qui reviennent sur votre site, ainsi que le nombre de visites repris dans chaque catégorie de durée. Utilisez ce rapport pour afficher la période moyenne pendant laquelle les visiteurs réguliers n’ont pas visité votre site, ainsi que les tendances au niveau des clients réguliers.

<!-- 

c_reports_return_freq.xml

 -->

Dans le cas d’un site de vente au détail, le fait d’afficher la mesure Commandes dans ce rapport permet de déterminer le moment le plus efficace pour générer une conversion entre des visites. Utilisez ces informations pour proposer plus efficacement vos produits aux visiteurs qui n’ont plus consulté votre site depuis un certain temps.

Vous pouvez:

* Identifier le nombre de visiteurs récurrents et la fréquence de leurs visites.
* Évaluer l’attrait de votre site web et l’intérêt qu’il présente pour les visiteurs au fil du temps.
* Prendre conscience de l’attractivité de votre site sur les visiteurs et de la fréquence à laquelle ils se sentent obligés d’y revenir pour une interaction supplémentaire ou des mises à jour.
* Identifier l’impact du contenu et des promotions de votre site web sur vos visiteurs.

Par défaut, les durées de ce rapport sont les suivantes :

* Moins d’une journée
* Un à trois jours
* Trois à sept jours
* Sept à quatorze jours
* Quatorze jours à un mois
* Plus d’un mois

## Nombre de visites {#concept_BBB614072FD74379B1A8520ACB75AE9A}

Indique les numéros des visites effectuées sur votre site dont l’incidence a été la plus importante sur vos mesures de succès. Un utilisateur qui effectue une première visite sur votre site est comptabilisé à la ligne « Visite numéro 1 ». Ceux qui reviennent sur votre site une seconde fois sont comptabilisés à la ligne « Visite numéro 2 », et ainsi de suite.

<!-- 

c_reports_visit_number.xml

 -->

Vous pouvez utiliser ce rapport comme rapport d’abandons afin de déterminer si les visiteurs reviennent sur votre site. Vous pouvez également ajouter une mesure de recette au rapport afin de déterminer si vous générez plus de recettes à partir des visites initiales ou à partir des visites suivantes.

Ce rapport peut, par exemple, répondre à des questions du type : « Les clients qui ont effectué un achat au cours de leur quatrième visite génèrent-ils plus de recettes que ceux qui ont acheté un produit lors de leur première visite ? »

Vous pouvez ventiler ce rapport selon tout autre rapport ou variable afin de déterminer :

* le nombre de visites effectuées généralement par un utilisateur qui a parcouru la campagne XYZ avant d’effectuer un achat.
* si les utilisateurs tokyoïtes, par exemple, effectuent davantage de visites que les utilisateurs londoniens avant de générer une piste.

> [!NOTE] Si le même visiteur consulte votre site Web plusieurs fois au cours de la même période, chaque nombre de visites spécifié est incrémenté pour chaque visite.

Ce rapport s’articule autour des données d’identifiant des visiteurs transmises à Adobe lors chaque accès à votre site. A la réception de ces données, Adobe les compare aux identifiants des visiteurs historiques afin de déterminer si l’accès correspond à :

* un nouveau visiteur (nombre de visites égal à 1).
* un visiteur précédent qui continue une visite en cours (nombre de visites non incrémenté),
* un visiteur précédent qui effectue une nouvelle visite (nombre de visites incrémenté d’une unité).

> [!NOTE] Chaque identifiant visiteur Analytics est associé à un profil du visiteur sur les serveurs Adobe. Les profils de visiteur sont supprimés après au moins 13 mois d’inactivité, quelle que soit la date d’expiration des cookies d’identifiant de visiteur.

## Fidélité de la clientèle {#concept_991F758BAA304B7B9D48BD73BBB62FE5}

Utilisez ce rapport pour déterminer si vos recettes sont davantage influencées par les nouveaux clients ou par les clients réguliers.

<!-- 

c_reports_customerloyalty.xml

 -->

Le rapport [!UICONTROL Fidélité de la clientèle] affiche des schémas de clients sur la base de quatre catégories de fidélité :

* **Pas un client** : visiteurs n’ayant jamais effectué d’achat
* **Nouveau client** : visiteurs qui ont effectué un seul achat
* **Client régulier** : visiteurs qui ont effectué deux achats
* **Client fidèle** : visiteurs qui ont effectué trois achats ou plus

> [!NOTE] Lors de l’utilisation de ces mesures, toutes les visites des utilisateurs (ou tous les visiteurs) sont représentées dans ce rapport, que la visite (ou le visiteur) ait inclus un achat ou non.

L’état de fidélité change à la fin de la visite au cours de laquelle s’est produit un événement d’achat. Par exemple, un nouveau client (1 achat) effectue un achat, puis s’inscrit ensuite au bulletin d’information, au cours de la même visite. L’événement d’inscription au bulletin d’information est toujours considéré comme une interaction Nouveau client, car l’état de fidélité du client ne changera pas avant la prochaine visite.

## Profil du visiteur {#concept_4D829198CD144DCDA667E0651F93AFC7}

Affichent des informations sur le type de visiteurs qui se rendent sur votre site. Ils présentent des renseignements tels que l’emplacement des visiteurs, le type de navigateur et de matériel informatique utilisés, la langue employée, ainsi que des informations sur leurs fournisseurs de services Internet.

<!-- 

c_reports_visitor_profile.xml

 -->

**[!UICONTROL Langues]**: Affiche les langues préférées des visiteurs, capture la langue par défaut du navigateur et affiche les langues que les visiteurs utilisent le plus souvent sur votre site.

**[!UICONTROL Domaines]** : répertorie les organisations et les fournisseurs de services Internet que les visiteurs utilisent pour accéder à votre site. Ce rapport diffère du rapport [!UICONTROL Domaines complets], en ce sens qu’il répertorie le domaine secondaire. Le rapport des domaines complets, lui, enregistre le domaine complet des fournisseurs d’accès Internet.

**[!UICONTROL Domaines de haut niveau]** : présente les régions du monde d’où viennent les visiteurs sur la base de l’extension de leur domaine d’origine et indique combien de visiteurs viennent de ces pays. Les domaines finissant par Commercial (.com), Network (.net), Education (.edu), Government (.gov) et Organization (.org) sont généralement basés aux États-Unis et sont répertoriés différemment des autres domaines.

**[!UICONTROL Code postal du visiteur]** : indique les codes postaux des visiteurs qui ont le plus influencé les mesures de succès d’achats.

## Géosegmentation {#concept_7C1B930F90F945B49205D3855CAE1813}

<!-- 

c_reports_geosegmentation.xml

 -->

Affiche la dynamique géographique de vos visiteurs en temps réel, notamment les pays, les départements et les villes à partir desquels ils naviguent. Ce type de rapport vous donne également une bonne idée de la technologie dont dispose votre public Internet, ainsi que de leurs préférences.
