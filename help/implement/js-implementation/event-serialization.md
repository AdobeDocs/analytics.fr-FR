---
description: La sérialisation des événements est le processus consistant à implémenter des mesures pour empêcher les événements en double d’entrer dans la création de rapports d’Analytics. Les doublons apparaissent généralement lorsqu’un utilisateur actualise la page plusieurs fois, navigue sur une certaine page à plusieurs reprises ou enregistre la page Web sur son ordinateur (par exemple, si un client enregistrait une page de confirmation d’achat sur son ordinateur, chaque fois qu’il la consulterait, les commandes et les recettes seraient comptabilisées à nouveau si la sérialisation des événements n’était pas en place).
keywords: Mise en œuvre d’Analytics
seo-description: La sérialisation des événements est le processus consistant à implémenter des mesures pour empêcher les événements en double d’entrer dans la création de rapports d’Analytics. Les doublons apparaissent généralement lorsqu’un utilisateur actualise la page plusieurs fois, navigue sur une certaine page à plusieurs reprises ou enregistre la page Web sur son ordinateur (par exemple, si un client enregistrait une page de confirmation d’achat sur son ordinateur, chaque fois qu’il la consulterait, les commandes et les recettes seraient comptabilisées à nouveau si la sérialisation des événements n’était pas en place).
seo-title: Présentation de la sérialisation d'événements
solution: Analytics
title: Présentation de la sérialisation d'événements
topic: Développeur et mise en œuvre
uuid: 8 c 7883 bb -5 ba 4-4440-af 80-c 0 d 15867570 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Présentation de la sérialisation d'événements

La sérialisation des événements est le processus consistant à implémenter des mesures pour empêcher les événements en double d’entrer dans la création de rapports d’Analytics. Les doublons apparaissent généralement lorsqu’un utilisateur actualise la page plusieurs fois, navigue sur une certaine page à plusieurs reprises ou enregistre la page Web sur son ordinateur (par exemple, si un client enregistrait une page de confirmation d’achat sur son ordinateur, chaque fois qu’il la consulterait, les commandes et les recettes seraient comptabilisées à nouveau si la sérialisation des événements n’était pas en place).

Elle s’avère très utile dans les cas suivants :

* Une page peut être rechargée ou actualisée et envoyer de manière répétée un événement. La [!UICONTROL sérialisation d’événements] empêche une nouvelle comptabilisation des événements en utilisant un numéro de série pour chaque événement.
* L’utilisateur enregistre la page sur son ordinateur en vue d’une consultation ultérieure. Ce scénario est assez courant sur les pages de confirmation d’achat afin de vérifier les tickets d’achat. La [!UICONTROL sérialisation d’événements] empêche le rechargement suivant de la page de recomptabiliser les événements.

>[!NOTE]
>
>La fonctionnalité Sources de données ne prend pas en charge la sérialisation ou la déduplication d'événements.

Ce document décrit le processus de mise en œuvre de la [!UICONTROL sérialisation d’événements] pour les événements de [!UICONTROL conversion] et [!UICONTROL personnalisés]. To use [!UICONTROL Event serialization], you must first enable it in  **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suite]** &gt; **[!UICONTROL[select report suite]]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Success Events]** . Sélectionnez ensuite les événements que vous voulez enregistrer dans la colonne [!UICONTROL Enregistrement d’événement unique].

## Comportement par défaut {#section_892BB2BEFC434B69869D4504A8B54308}

Le comportement par défaut est la comptabilisation de chaque instance d’un événement. Un événement est défini pour chaque [!UICONTROL pageview] comptabilisé, même lors des rechargements ou des actualisations de la page. La variable [!UICONTROL s.purchaseID] est utilisée pour identifier de façon unique chaque commande (achat). Cela permet à un utilisateur de recharger la page de commande sans que la commande, les recettes ou les produits ne soient recomptabilisés. Une fonctionnalité similaire est disponible pour tous les événements, notamment les événements prédéfinis tels que [!UICONTROL prodView] et [!UICONTROL scCheckout], ainsi que les événements personnalisés.

<!-- 

event_serialization_impl.xml

 -->

To use [!UICONTROL Event serialization], you must first enable it in  **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suite]** &gt; **[!UICONTROL[select report suite]]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Success Events]** . Sélectionnez ensuite les événements que vous voulez enregistrer dans la colonne [!UICONTROL Enregistrement d’événement unique]. Vous pouvez définir un événement sur trois paramètres différents.

**Toujours enregistrer l’événement** : il s’agit du comportement par défaut de tous les événements lors de l’activation initiale. Tous les événements figurant dans les demandes d’image sont envoyés directement à Analytics, y compris les rechargements de page.

**Enregistrer une fois par visite** : lorsque ce paramètre est activé, le suivi porte uniquement sur la première instance de l’événement dans une visite donnée. Après le début d’une nouvelle visite, chaque événement pour lequel ce paramètre est activé peut à nouveau faire l’objet d’un suivi. C’est un moyen efficace d’atténuer la duplication des événements lors de l’actualisation du navigateur.

**Utiliser l’ID de l’événement** : ce paramètre permet d’associer chaque événement à un identifiant unique. Si Analytics repère un ID d’événement qu’il a déjà rencontré auparavant avec cette variable, il ne sera pas comptabilisé dans la création de rapports.

L’événement d’achat est le seul événement pour lequel la sérialisation des événements ne peut pas être activée car il utilise la variable s.purchaseID. Ces paramètres peuvent être activés sur tous les autres événements de commerce électronique et personnalisés.

* Utilisez un identifiant unique pour qu’un événement se déclenche une fois par identifiant unique.
* Envoyez plusieurs événements, puis configurez Analytics pour qu’un événement se déclenche une fois par visite.

Pour implémenter la [!UICONTROL sérialisation d’événements], fournissez un ID unique pour l’événement (event1:1234ABCD, par exemple).

## Sérialisation d’événements : une fois par ID unique {#section_8806E48B497546F5A335383FB8627694}

Une fois que la [!UICONTROL sérialisation d’événements] est implémentée et qu’[!DNL Analytics] reçoit un nombre dupliqué, il ignore l’événement. Un événement est comptabilisé une seule fois par valeur unique. Si le nombre est unique, une autre instance d’événement est comptabilisée, comme illustré dans l’exemple suivant :

| Nom d’utilisateur | Description | Syntaxe de l’événement | Analytics Comptabilisation totale d’event1 |
|---|---|---|---|
| John | L’utilisateur consulte la page pour la première fois. | event1:1000 | 1 |
| John | L’utilisateur recharge la page (un envoi de formulaire peut échouer, ce qui entraîne le rechargement de la page). | event1:1000 | 1 |
| Stacy | L’utilisateur consulte la page pour la première fois. | event1:1001 | 2 |
| Stacy | L’utilisateur recharge la page (un envoi de formulaire peut échouer, ce qui entraîne le rechargement de la page). | event1:1001 | 2 |
| Jill | L’utilisateur consulte la page pour la première fois, saisit les informations correctement et passe à la page suivante. | event1:1002 | 3 |
| Jamie | L’utilisateur consulte la page pour la première fois. | event 1 | 4 |
| Jamie | L’utilisateur oublie de renseigner le champ du nom du formulaire. Le formulaire est affiché de nouveau pour signaler l’information manquante. | event 1 | 5 |

Veuillez prendre note des points suivants lors de la sélection d’identifiants de sérialisation :

* Les identifiants de sérialisation doivent comporter au maximum 20 caractères.
* Les identifiants de sérialisation doivent être composés de caractères alphanumériques.
* Les identifiants de sérialisation sont séparés pour chaque événement de succès. Au besoin, vous pouvez donc utiliser le même identifiant pour plusieurs événements de succès.
* Les identifiants de sérialisation sont liés à la suite de rapports. Veuillez en tenir compte si vous utilisez le balisage multi-suite pour envoyer des données à plusieurs suites de rapports.
* Aucune date d’expiration n’est appliquée aux identifiants de sérialisation. Par conséquent, même si le même identifiant est utilisé des années plus tard, l’événement de succès n’est pas comptabilisé à nouveau.
* La suppression des cookies n’empêche pas la sérialisation des identifiants d’événement, car ces identifiants sont stockés sur des serveurs Adobe et ne reposent pas sur des cookies.
* L’événement d’achat est le seul événement de succès avec lequel il est impossible d’utiliser la sérialisation des identifiants d’événement. Il utilise, en effet, une variable s.purchaseID spéciale pour la sérialisation.

## Sérialisation d’événements : une fois par visite {#section_C919D44F321A47FBBF043D0C57A2A050}

[!DNL Analytics] propose une fonctionnalité qui permet à un événement de se déclencher une fois par visite.

This can be enabled from the UI:  **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suite]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL Success Events]** .
