---
description: Segment IQ (comparaison des segments) est l’une des fonctions les plus utilisées d’Analysis Workspace. Les clients recherchent constamment de nouvelles approches novatrices pour en tirer des informations. Vous trouverez ici quelques cas d’utilisation.
keywords: Segment IQ
seo-description: Segment IQ (comparaison des segments) est l’une des fonctions les plus utilisées d’Analysis Workspace. Les clients recherchent constamment de nouvelles approches novatrices pour en tirer des informations. Vous trouverez ici quelques cas d’utilisation.
seo-title: Cas d'utilisation d'IQ Segment
title: Cas d'utilisation d'IQ Segment
uuid: 2 a 98 b 96 b -5529-4 c 7 f-a 787-27920603 d 5 b 0
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Cas d'utilisation d'IQ Segment

Segment IQ (comparaison des segments) est l’une des fonctions les plus utilisées d’Analysis Workspace. Les clients recherchent constamment de nouvelles approches novatrices pour en tirer des informations. Vous trouverez ici quelques cas d’utilisation.

## Use case 1: compare mobile vs desktop implementations {#section_B3A5983E58D0470895C030EA527C4966}

**« Nous avons comparé les accès d’un site à un autre et relevé un certain nombre d’incohérences en termes de balisage. Nous avons évité ainsi des problèmes liés aux données avant la mise sur le marché d’un produit. »**

**Scénario** : un chef de produit responsable d’un site web mobile et d’un site web d’ordinateur de bureau devait s’assurer que les balises des deux types de sites web étaient cohérentes. Afin de s’assurer qu’il n’avait rien omis d’important, il a comparé avec Segment IQ les accès issus du site mobile à ceux du site d’ordinateur de bureau. Il a constaté qu’il avait oublié de baliser l’événement de passage en caisse sur le site web mobile. Il a ainsi pu placer les balises appropriées avant que le site mobile ne soit publié. Les conversions ayant lieu sur le site mobile ont ainsi bien été enregistrées, ce qui a évité un désastre en termes de données.

**Comment configurer cette comparaison :**

<table id="table_B5FA23CB34DE4331A8BD65ED4B351038"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Segment 1 </th> 
   <th colname="col3" class="entry"> Segment 2 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Utiliser/créer un segment au niveau des accès où </p> <p> </p> <p> 
     <ul id="ul_1F5D5136620E449D93A771CD2576A18A"> 
      <li id="li_CB32DD1033DA4E5CA3B9AD41030800E6">type de périphérique mobile = téléphone mobile ou tablette </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Utiliser/créer un segment au niveau des accès où </p> <p> </p> <p> 
     <ul id="ul_79CC51C4C9494275B3F37B6D2AB0505E"> 
      <li id="li_83BE21AD1FB34195BAFF3F15421DBB3D">type de périphérique mobile ≠ téléphone mobile ou tablette </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Use case 2: compare customers who use a certain feature to those who don't {#section_878B08FDD70A45E186C1F28EBA296636}

**« Nous avons constaté que les clients qui avaient recours à notre fonction de comparaison de produits étaient 10 % plus susceptibles de convertir leur visite en achat. Nous l’avons donc placée en haut de la page et augmenté les commandes de 4 % ! »**

**Scénario :** une équipe chargée de l’optimisation d’un site web de vente au détail cherchait à mieux comprendre les internautes qui utilisaient une nouvelle fonction de comparaison des produits. En créant un segment des visiteurs qui avaient utilisé la fonction, ils ont pu comparer avec Segment IQ ces utilisateurs à tous les autres visiteurs du site. Segment IQ a rapidement identifié plusieurs différences notables, notamment le fait que ces utilisateurs étaient 10 % plus susceptibles d’acheter un produit. L’équipe d’optimisation du site a alors décidé de placer la fonction de comparaison des produits en haut de la page afin de la tester davantage.

**Comment configurer cette comparaison :**

| Segment 1 | Segment 2 |
|--- |--- |
| Utiliser/créer un segment des visiteurs qui ont utilisé l’outil de comparaison des prix | Utiliser le segment Tous les autres qui est généré automatiquement et englobe quiconque n’est pas inclus dans le segment 1. |

## Use case 3: compare news site visitors to other site section visitors {#section_0EAFC90C450244058B161200AC9901B8}

**« Nous avons constaté que les visiteurs de notre section d’actualités étaient deux fois plus susceptibles de regarder des publicités vidéo. Nous avons donc ajouté d’autres options vidéo à cette section. Nous avons alors enregistré une hausse de 7 % des publicités vidéo regardées ! »**

**Scénario :** une importante société de médias cherchait à optimiser l’engagement du contenu pour les visiteurs de sa section d’actualités. Afin de mieux appréhender cette audience, ils ont créé un segment de visiteurs qui avaient consulté la section Actualités du site. Segment IQ a analysé chaque mesure et dimension et immédiatement révélé que ces utilisateurs étaient deux fois plus susceptibles de regarder des publicités vidéo que les visiteurs d’une autre section du site. L’équipe vidéo a alors ajouté une section de vidéos recommandées sur son rail des actualités, et a ainsi enregistré une hausse de 7 % des publicités vidéo regardées. En raison des nombreuses variables impliquées, ils auraient pu passer beaucoup de temps et d’énergie à cette tâche. Cet outil a permis d’obtenir rapidement des résultats mesurables.

**Comment configurer cette comparaison :**

| Segment 1 | Segment 2 |
|--- |--- |
| Utiliser/créer un segment des visiteurs de la section Actualités du site | Utiliser le segment Tous les autres qui est généré automatiquement et englobe quiconque n’est pas inclus dans le segment 1. |

## Use case 4: compare visitors from paid search to everyone else {#section_73912670409349CAB131FE9D8B4FB11C}

**« Les visiteurs sur notre site issus des moteurs de recherche étaient trois fois plus susceptibles de répondre aux ventes incitatives que les autres. Nous avons donc renforcé nos efforts sur des mots-clés spécifiques et constaté une hausse de 56 % des ventes incitatives. »**

**Scénario :** une grande société de services B2B souhaitait comprendre le type de trafic sur son site issu des mots-clés de recherche payante. Les recherches payantes n’engendraient pas directement de nombreuses conversions et les responsables du marketing envisageaient de réduire le budget de ce poste. L’équipe marketing a alors créé un segment de visiteurs du site issus d’une recherche payante et l’a comparé, avec l’outil Segment IQ, à tous les autres visiteurs. Ils ont constaté que même si ces visiteurs n’étaient pas aussi susceptibles de convertir directement leur visite en achat, ils étaient toutefois trois fois plus susceptibles d’acheter la gamme supérieure d’un service déjà acheté. L’équipe marketing a alors pu concentrer son budget simplement sur les mots-clés liés aux ventes incitatives et a enregistré une hausse de 56 % des ventes incitatives de service.

**Comment configurer cette comparaison :**

| Segment 1 | Segment 2 |
|--- |--- |
| Utiliser/créer un segment des visiteurs pour les visiteurs référencés par une recherche naturelle ou issus d’une campagne SEM. | Utiliser le segment Tous les autres qui est généré automatiquement et englobe quiconque n’est pas inclus dans le segment 1. |

## Use case 5: compare Fitbit purchasers to everyone else {#section_9142B8A270764545B0A516AA309F1785}

**« Nous avons constaté que les personnes achetant des objets connectés Fitbit étaient six fois plus susceptibles de recevoir un message « article épuisé » que les autres clients. Nous avons donc commandé plus d’articles Fitbit afin d’éviter les ruptures de stock. »**

**Scénario :** Un grand détaillant en ligne souhaitait savoir comment l'un des produits de vacances de hottest logiciel - Fitbit - vendait et ce qui rendait Fitbit acheteurs unique chez d'autres clients. L’équipe marketing a simplement cliqué avec le bouton droit de la souris sur la ligne « Fitbit » de son rapport des produits, puis a exécuté une analyse rapide avec Segment IQ. Ils ont découvert que les acheteurs des objets connectés Fitbit étaient six fois plus susceptibles de recevoir un message « article épuisé » que n’importe quel autre client. Suite à une analyse plus poussée, l’équipe marketing a réussi à diriger ces visiteurs vers leurs magasins traditionnels en attendant que le service des achats commande davantage d’articles Fitbit. Le détaillant a ainsi évité la multiplication des messages de « rupture de stock » et a pu satisfaire la plus grande partie de la demande des Fêtes.

**Comment configurer cette comparaison :**

<table id="table_9018BEB4C2DE429FA773B250CB5C3E58"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Segment 1 </th> 
   <th colname="col3" class="entry"> Segment 2 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Utiliser/créer un segment des visiteurs où, </p> <p> 
     <ul id="ul_52E8ED6F4F7241D5ABE4EE7EA1E556D8"> 
      <li id="li_33750601AB2A43728834B29AF86D5CCF">commandes ≥ 1, ET </li> 
      <li id="li_4E09D1286DAE4BABA49E4834E73BDC28">marque = Fitbit </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Utiliser le segment <span class="wintitle">Tous les autres</span> qui est généré automatiquement et englobe quiconque n’est pas inclus dans le segment 1. </p> </td> 
  </tr> 
 </tbody> 
</table>

