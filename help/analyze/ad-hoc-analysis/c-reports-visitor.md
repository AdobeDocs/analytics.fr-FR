---
description: Affiche des informations concernant les visiteurs, notamment leur nombre, leurs caractéristiques et la fidélisation des clients.
title: Rapports sur les visiteurs
topic: Ad hoc analysis
uuid: 3e9b41d1-d6ff-47a8-aa6b-829df1040c34
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Rapports sur les visiteurs

Affiche des informations concernant les visiteurs, notamment leur nombre, leurs caractéristiques et la fidélisation des clients.

## Fréquence des retours {#concept_447A99B71E484D27A7A02888CC51FD3D}

Indique le temps qui s’écoule entre les visites des de retour et le nombre de visites qui entrent dans chaque de durée. Utilisez le rapport pour connaître la durée moyenne pendant laquelle les réguliers passent sans consulter votre site, ainsi que les tendances des clients réguliers.

<!-- 

c_reports_return_freq.xml

 -->

Par exemple, l’affichage de la mesure Commandes dans ce rapport permet à un site de vente au détail de comprendre le temps le plus efficace entre les visites pour générer des conversions. Utilisez ces informations pour commercialiser efficacement les qui ont passé un certain temps sans consulter votre site.

Vous pouvez :

* Identifiez le nombre de visiteurs de retour et la fréquence de leurs visites de retour.
* Évaluez l&#39;attrait de votre site Web et la pertinence pour les au fil du temps.
* Prenez conscience de l&#39;attractivité de votre site sur les visiteurs et de la fréquence à laquelle ils se sentent obligés d&#39;y revenir pour une interaction supplémentaire ou des mises à jour.
* Identifiez l’impact du contenu et des promotions de votre site Web sur vos.

Par défaut, ce rapport a les durées suivantes :

* Moins d’un jour
* Un à trois jours
* Trois à sept jours
* Sept à quatorze jours
* Quatorze jours à un mois
* Plus d’un mois

## Nombre de visites {#concept_BBB614072FD74379B1A8520ACB75AE9A}

Indique le nombre de visites des clients sur votre site qui a le plus influencé vos mesures de réussite. Un qui effectue une première visite sur votre site est comptabilisé à la ligne Nombre de visites 1. Les qui reviennent sur le site pour une seconde visite sont comptabilisés dans la ligne Nombre de visites 2, etc.

<!-- 

c_reports_visit_number.xml

 -->

Vous pouvez utiliser ce rapport comme rapport d’abandons pour savoir si les reviennent. Vous pouvez également ajouter une mesure des recettes pour savoir si vous générez davantage de recettes à partir des visites initiales ou des visites ultérieures.

Par exemple, ce rapport peut répondre à des questions telles que : Les clients qui ont effectué des achats lors de leur quatrième visite ont-ils généré plus de recettes que ceux qui ont effectué des achats lors de leur première visite ?

Vous pouvez ventiler ce rapport en fonction d’un autre rapport ou variable afin de déterminer :

* Combien de visites prend généralement un utilisateur qui a cliqué sur la campagne XYZ pour effectuer un achat ?
* Si les utilisateurs de Tokyo, par exemple, effectuent plus de visites avant de générer une piste que les utilisateurs de Londres.

>[!NOTE] Si un même visiteur se rend plusieurs fois sur votre site Web au cours de la même période, chaque numéro de visite spécifié est incrémenté pour chaque visite.

Ce rapport est basé sur les données d’ID de transmises à Adobe à chaque accès effectué par les. Lorsque ces données sont reçues, Adobe les compare aux données historiques d’ID de afin de déterminer si l’accès est :

* Un nouveau (nombre de visites = 1).
* précédent qui poursuit une visite (le nombre de visites n’est pas incrémenté).
* précédent qui effectue une nouvelle visite (nombre de visites incrémenté d’une unité).

>[!NOTE] Chaque identifiant visiteur Analytics est associé à un profil du visiteur sur les serveurs Adobe. Les profils de visiteur sont supprimés après au moins 13 mois d’inactivité, quelle que soit la date d’expiration des cookies d’identifiant de visiteur.

## Fidélité de la clientèle {#concept_991F758BAA304B7B9D48BD73BBB62FE5}

Utilisez ce rapport pour déterminer si vos recettes sont davantage influencées par les nouveaux clients ou par les clients réguliers.

<!-- 

c_reports_customerloyalty.xml

 -->

Le [!UICONTROL Customer Loyalty] rapport affiche les modèles d’achat des clients en fonction de quatre  de fidélité :

* **Pas un client**: n’ayant jamais effectué d’achat
* **Nouveau client**: ayant effectué un seul achat
* **Client** régulier : ayant effectué 2 achats
* **Client** fidèle : ayant effectué 3 achats ou plus

>[!NOTE] Lorsque vous utilisez ces mesures, toutes les visites de l’utilisateur (ou tous les visiteurs) sont représentées dans ce rapport et ce, qu’un achat ait été effectué ou non.

L’état de fidélité change après la fin de la visite au cours de laquelle un d’achat se produit. Par exemple, un nouveau client (1 achat) effectue un achat, puis s’inscrit à un bulletin d’information après cet achat au cours de la même visite. L’événement d’inscription au bulletin d’information est toujours considéré comme une interaction Nouveau client, car l’état de fidélité du client ne changera pas avant la prochaine visite.

## Profil du visiteur {#concept_4D829198CD144DCDA667E0651F93AFC7}

Affiche des informations sur le type de qui arrive sur votre site. Vous pouvez voir des éléments tels que l&#39;emplacement du, le type de navigateur et de matériel informatique utilisés, les langues utilisées et les données de Internet pour vos.

<!-- 

c_reports_visitor_profile.xml

 -->

**[!UICONTROL Languages]**: Indique les langues préférées des visiteurs, capture la langue par défaut du navigateur et affiche les langues les plus utilisées par les visiteurs de votre site.

**[!UICONTROL Domains]**:  les organisations et les FAI que vos utilisent pour accéder à votre site. This report differs from the [!UICONTROL Full Domains] report in that the Full Domains report registers the full ISP domain, whereas this report lists the secondary domain.

**[!UICONTROL Top Level Domains]**: Identifie les régions du monde d’où proviennent les en fonction de leur extension de domaine d’origine et indique combien de viennent de ces pays. Les domaines se terminant par Commercial (.com), Network (.net), Education (.edu), Government (.gov) et Organization (.org) sont généralement basés aux États-Unis et sont répertoriés séparément des autres domaines.

**[!UICONTROL Visitor ZIP/Postal Code]**: Affiche les codes postaux des clients qui ont eu le plus grand impact sur les mesures de réussite des achats.

## Géosegmentation {#concept_7C1B930F90F945B49205D3855CAE1813}

<!-- 

c_reports_geosegmentation.xml

 -->

Affiche la dynamique géographique de vos en temps réel, y compris les pays, les états et les villes d’où ils naviguent. Vous pouvez également obtenir des informations importantes sur la technologie et les préférences du  de votre site Web.
