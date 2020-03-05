---
description: Analytics et Audience Manager utilisent tous deux les segments. Cependant, un segment Analytics ne représente pas exactement la même chose qu’un segment Audience Manager. Ces différences contribuent en partie aux incohérences que vous constaterez dans vos rapports Analytics et Audience Manager. C’est pourquoi il est important et utile d’essayer de comprendre ces différences lorsque vous commencerez à travailler avec les segments dans ces deux solutions.
title: Présentation des segments dans Analytics et Audience Manager
uuid: 13f7d1d7-6a3f-42f1-822e-8d3523999efa
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Présentation des segments dans Analytics et Audience Manager

Analytics et Audience Manager utilisent tous deux les segments. Cependant, un segment Analytics ne représente pas exactement la même chose qu’un segment Audience Manager. Ces différences contribuent en partie aux incohérences que vous constaterez dans vos rapports Analytics et Audience Manager. C’est pourquoi il est important et utile d’essayer de comprendre ces différences lorsque vous commencerez à travailler avec les segments dans ces deux solutions.

## Segments Audience Manager {#section_417DC4B5648547778A27E42CE1D09900}

Un segment Audience Manager est un groupe de visiteurs (ID d’utilisateur) qui correspondent à un ensemble de caractéristiques définies unies par des règles logiques. Quatre critères déterminent si un visiteur (ID d’utilisateur) appartient à un segment dans Audience Manager :

* Règles définies sur les segments proprement dits et sur les caractéristiques qui constituent chaque segment. Ces règles définissent les conditions auxquelles un ID d’utilisateur doit satisfaire pour être admissible pour un segment.
* La modélisation algorithmique. Les utilisateurs qui répondent aux critères d’admission pour un segment particulier peuvent être admissibles pour d’autres segments sur la base de l’analyse et de la modélisation algorithmique.
* Intervalles de durée de vie (TTL). L’appartenance aux segments peut expirer après un intervalle défini ou persister indéfiniment.
* Récence et fréquence. La définition du moment et de la fréquence à laquelle les utilisateurs ont une interaction (réalisation d’une caractéristique) peut permettre de créer des segments en fonction du niveau d’intérêt réel (ou perçu) pour un site, une section ou une création publicitaire particulière.

L’appartenance aux segments Audience Manager est fluctuante. Les utilisateurs peuvent être inclus dans un segment ou en être exclus selon qu’ils répondent ou non aux critères de ce segment à un moment donné. Cela signifie que la population d’un segment Audience Manager peut augmenter ou diminuer au fil du temps.

Un segment Audience Manager est désigné en tant qu’audience dans Analytics.

Pour plus d’informations, voir les sections [Données de population des caractéristiques et des segments dans le Créateur de segments](https://docs.adobe.com/content/help/fr-FR/audience-manager/user-guide/features/segments/segment-builder-data.html) et [Signaux, caractéristiques et segments](https://docs.adobe.com/content/help/fr-FR/audience-manager/user-guide/reference/signal-trait-segment.html).

## Segments Analytics {#section_62EC584BB7134E10923BCBA7F9BD89A8}

Un segment Analytics est un mécanisme de filtrage des données dans vos rapports. Le filtrage peut survenir au niveau des visiteurs, des visites ou des accès, plutôt qu’au niveau des visiteurs uniquement comme dans Audience Manager. Plusieurs facteurs importants doivent être pris en considération lors de la comparaison d’un segment Analytics à un segment Audience Manager :

* Les segments Analytics reposent sur un jeu de données différent des segments Audience Manager. Lors de la collecte de données, Analytics applique aux données un grand nombre d’opérations de post-traitement auxquelles Audience Manager n’a pas accès. Les opérations de post-traitement possibles sont très variées : persistance des variables eVar, règles de traitement, recherches (géolocalisation, appareil mobile), règles VISTA, etc. Audience Manager reçoit les données prétraitées via la redirection côté serveur (ou le DIL).

   Les incohérences entre les données les plus courantes surviennent lorsque l’utilisateur compare des segments sur la base de dimensions qui n’expirent jamais dans Analytics, par rapport aux mêmes dimensions dans Audience Manager. Par exemple, des listVars ou des eVars de marchandisage qui n’expirent jamais.

   Par exemple, si eVar = bleu et est défini pour ne jamais expirer dans Analytics, tous les segments assortis du critère « eVar = bleu » dans Analytics incluront toujours ce visiteur. En revanche, dans Audience Manager, ce visiteur pourrait être exclu d’un segment défini de la même façon après une période donnée.

* Les segments Analytics ont plus de fonctionnalités que les segments AAM. Les segments Audience Manager sont toujours évalués au niveau des visiteurs. Les segments Analytics peuvent être définis au niveau des visiteurs, des visites ou des accès (ou une combinaison de ces niveaux). En outre, Analytics prend en charge des fonctionnalités de segmentation avancées non prises en charge par Audience Manager, p. ex. la segmentation séquentielle.
* Comme mentionné précédemment, les visiteurs Audience Manager peuvent être inclus dans un segment ou en être exclus selon qu’ils répondent ou non aux critères de ce segment à un moment donné.

   À l’inverse, dans Analytics, les visiteurs sont inclus ou exclus d’un segment en fonction de la plage de dates du rapport. Par exemple, un visiteur unique a effectué un achat le mois dernier. Dans AAM, ce visiteur sera inclus dans un segment « acheteur », indépendamment de la plage de dates. Dans Analytics, un rapport basé sur ce mois-ci n’inclura pas le visiteur dans le segment. Cependant, un rapport basé sur ce mois-ci et le mois dernier inclura le visiteur dans le segment.

Pour plus d’informations, voir le [Guide de segmentation d’Analytics](https://marketing.adobe.com/resources/help/fr_FR/analytics/segment/).
