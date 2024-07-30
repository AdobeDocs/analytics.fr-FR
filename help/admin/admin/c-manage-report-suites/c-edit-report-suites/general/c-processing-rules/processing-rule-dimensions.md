---
description: Dimensions et mesures disponibles que vous pouvez lire et écrire à l’aide de règles de traitement.
subtopic: Processing rules
title: Dimensions disponibles pour les règles de traitement
feature: Processing Rules
role: Admin
exl-id: ffd7a1d6-2c9d-41e7-9c75-9e47b6f9c283
source-git-commit: d17067b3ab58612cdfc3ac640a7530b326260c89
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 13%

---

# Dimensions et mesures disponibles pour les règles de traitement

Dimensions et mesures disponibles que vous pouvez lire et écrire à l’aide de règles de traitement.

## Valeurs personnalisées et données contextuelles

| Valeur | État de lecture/écriture | Description |
| --- | --- | --- |
| Valeur personnalisée | Lecture seule | Valeurs ou texte personnalisés saisis directement dans l’action d’une règle de traitement. |
| Valeur concaténée | Lecture seule | Valeurs créées en combinant deux valeurs. Par exemple, le canal et le nom de page peuvent être combinés pour créer une sous-catégorie. |

{style="table-layout:auto"}

## Attributs d’accès

| Attribut | État de lecture/écriture | Description |
| --- | --- | --- |
| URL de la page | Lecture + écriture | Dimension [URL de la page](/help/components/dimensions/page-url.md). Les accès de suivi des liens dépouillent cette dimension avant d’atteindre les règles de traitement. Si vous réinsérez une valeur d’URL de page à l’aide de règles de traitement, l’accès est considéré comme une [page vue](/help/components/metrics/page-views.md) au lieu d’un [événement de page](/help/components/metrics/page-events.md). Adobe recommande de rechercher une valeur dans la dimension de page avant de la modifier. |
| Nom de la page | Lecture + écriture | Dimension [Page](/help/components/dimensions/page.md). Les accès de suivi des liens dépouillent cette dimension avant d’atteindre les règles de traitement. Si vous réinsérez une valeur de page à l’aide de règles de traitement, l’accès est considéré comme une [page vue](/help/components/metrics/page-views.md) au lieu d’un [événement de page](/help/components/metrics/page-events.md). Adobe recommande de rechercher une valeur dans la dimension de page avant de la modifier. |
| Identifiant de suite de rapports | Lecture seule | Suite de rapports sur laquelle la règle de traitement est exécutée. Cette suite de rapports peut être différente de la suite de rapports envoyée initialement par AppMeasurement, par exemple lors de l’utilisation de règles VISTA. |
| Version du code AppMeasurement | Lecture seule | Version de la bibliothèque AppMeasurement utilisée pour générer la demande d’image. |
| Adresse IP | Lecture seule | Adresse IP du visiteur. |
| Agent utilisateur | Lecture seule | Agent utilisateur du visiteur. |
| Référent | Lecture seule | La dimension [Référent](/help/components/dimensions/referrer.md). |
| Query String Parameter | Lecture seule | La valeur d’un paramètre de chaîne de requête spécifié dans l’URL actuelle. |
| Paramètre de chaîne de requête de référence | Lecture seule | La valeur d’un paramètre de chaîne de requête spécifié dans l’URL de référence ou une chaîne vide en cas d’absence. |
| Domaine référent | Lecture seule | Domaine de page de l’URL de référence, y compris les sous-domaines. |
| Domaine racine référent | Lecture seule | Domaine de page de l’URL de référence, à l’exception des sous-domaines. |
| Chaîne de requête de page | Lecture seule | Tous les paramètres de chaîne de requête et leurs valeurs dans l’URL active. |
| Chaîne de requête référente | Lecture seule | Tous les paramètres de chaîne de requête et leurs valeurs dans l’URL de référence. |
| Chemin de la page | Lecture seule | Chemin d’accès à la page de l’URL active. Le chemin de page n’inclut pas les paramètres de protocole, de domaine ou de chaîne de requête. |
| Domaine de page | Lecture seule | Domaine de page de l’URL active, y compris les sous-domaines. Le domaine de page n’inclut pas les paramètres de chemin de page ou de chaîne de requête. |
| Domaine racine de page | Lecture seule | Domaine de page de l’URL active, à l’exception des sous-domaines. |
| Perspective client | Lecture + écriture | Indicateur qui détermine si l’accès est un accès mobile en arrière-plan. |

{style="table-layout:auto"}

## Variables de conversion

| Variable | Description de l’état de lecture/écriture |
| --- | --- | --- |
| eVar 1-250 | Lecture + écriture | Dimensions [eVar](/help/components/dimensions/evar.md). |
| Campagne | Lecture + écriture | La dimension [Code de suivi](/help/components/dimensions/tracking-code.md). |
| Identifiant d’achat | Lecture + écriture | La variable de mise en oeuvre [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md). |
| État | Lecture + écriture | La variable de mise en oeuvre [`state`](/help/implement/vars/page-vars/state.md) a été abandonnée. |
| Zip | Lecture + écriture | Dimension [Code postal](/help/components/dimensions/zip-code.md). |
| Code de devise | Lecture + écriture | La variable de mise en oeuvre [`currencyCode`](/help/implement/vars/config-vars/currencycode.md). IMPORTANT : si vous définissez cette variable sur une valeur non valide, l’accès est ignoré. |
| ID de transaction | Lecture + écriture | La variable de mise en oeuvre [`transactionID`](/help/import/data-sources/transactionid.md). |

{style="table-layout:auto"}

>[!NOTE]
>Adobe ne prend pas en charge la définition de la variable d’implémentation [`products`](/help/implement/vars/page-vars/products.md) à l’aide de règles de traitement.

## Variables de trafic

| Variable | État de lecture/écriture | Description |
| --- | --- | --- |
| Prop 1-75 | Lecture + écriture | Dimensions [Prop](/help/components/dimensions/prop.md). |
| Hiérarchie 1-5 | Lecture + écriture | Dimensions [Hiérarchie](/help/components/dimensions/hierarchy.md). |
| Serveur | Lecture + écriture | La dimension [Serveur](/help/components/dimensions/server.md). |
| Canal | Lecture + écriture | Dimension [Section du site](/help/components/dimensions/site-section.md). |

{style="table-layout:auto"}

## Variables contextuelles

Toutes les [variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md) que cette suite de rapports a vues dans les demandes d’image précédentes. Si les règles de traitement ne placent pas de données contextuelles dans une autre variable, ces données sont définitivement perdues. Voir [Copier une variable de données contextuelles dans un eVar](processing-rules-examples/processing-rules-copy-context-data.md) et [Définir un événement à l’aide d’une variable de données contextuelles](processing-rules-examples/processing-rules-copy-context-data-event.md) pour consulter des exemples d’utilisation.

## Événements de succès

Les règles de traitement peuvent définir des événements, mais ne peuvent pas les lire en tant que conditions. Définissez la liste déroulante des actions de règle sur **[!UICONTROL Définir l’événement]** pour afficher les mesures disponibles à incrémenter.

| Variable | État de lecture/écriture | Description |
| --- | --- | --- |
| Commandes | Ecrire uniquement | Mesure [Commandes](/help/components/metrics/orders.md). |
| Paniers | Ecrire uniquement | La mesure [Paniers](/help/components/metrics/carts.md). |
| Consultations du panier | Ecrire uniquement | La mesure [Consultations du panier](/help/components/metrics/cart-views.md) . |
| Achats | Ecrire uniquement | La mesure [Passages en caisse](/help/components/metrics/checkouts.md). |
| Ajouts au panier | Ecrire uniquement | La mesure [Ajouts au panier](/help/components/metrics/cart-additions.md) . |
| Retraits du panier | Ecrire uniquement | La mesure [Retraits du panier](/help/components/metrics/cart-removals.md) . |
| Événement 1-1 000 | Ecrire uniquement | [Événements personnalisés](/help/components/metrics/custom-events.md). |
| Consultations de produit | Ecrire uniquement | Mesure [Consultations de produit](/help/components/metrics/product-views.md). |

{style="table-layout:auto"}
