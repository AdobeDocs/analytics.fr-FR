---
description: Dimensions et mesures disponibles que vous pouvez lire et écrire à l’aide des règles de traitement.
subtopic: Processing rules
title: Dimensions et mesures disponibles pour les règles de traitement
feature: Processing Rules
role: Admin
exl-id: ffd7a1d6-2c9d-41e7-9c75-9e47b6f9c283
source-git-commit: d62d4699418278bc9f0c7d69846ef12b5f2345d1
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 10%

---

# Dimensions et mesures disponibles pour les règles de traitement

Dimensions et mesures disponibles que vous pouvez lire et écrire à l’aide des règles de traitement.

## Valeurs personnalisées et données contextuelles

| Valeur | Statut en lecture/écriture | Description |
| --- | --- | --- |
| **Valeur personnalisée** | Lecture seule | Texte ou valeurs personnalisés saisis directement dans l’action d’une règle de traitement. |
| **Valeur concaténée** | Lecture seule | Valeurs créées en combinant deux valeurs. Par exemple, le canal et le nom de page peuvent être combinés pour créer une sous-catégorie. |

## Attributs d’accès

| Attribut | Statut en lecture/écriture | Description |
| --- | --- | --- |
| **URL de la page** | Lecture + écriture | La dimension [URL de la page](/help/components/dimensions/page-url.md). Les accès de suivi des liens suppriment cette dimension avant d’atteindre les règles de traitement. Si vous réinsérez une valeur d’URL de page à l’aide de règles de traitement, l’accès est considéré comme un [Page vue](/help/components/metrics/page-views.md) au lieu d’un [Événement de page](/help/components/metrics/page-events.md). Adobe recommande de rechercher une valeur dans la dimension de page avant de la modifier. |
| **Nom de la page** | Lecture + écriture | La dimension [ Page ](/help/components/dimensions/page.md). Les accès de suivi des liens suppriment cette dimension avant d’atteindre les règles de traitement. Si vous réinsérez une valeur de page à l’aide de règles de traitement, l’accès est considéré comme un [Page vue](/help/components/metrics/page-views.md) au lieu d’un [Événement de page](/help/components/metrics/page-events.md). Adobe recommande de rechercher une valeur dans la dimension de page avant de la modifier. |
| **Identifiant de suite de rapports** | Lecture seule | Suite de rapports sur laquelle la règle de traitement est exécutée. Cette suite de rapports peut être différente de la suite de rapports initialement envoyée via AppMeasurement, par exemple lors de l’utilisation de règles VISTA. |
| **Version du code AppMeasurement** | Lecture seule | Version de la bibliothèque AppMeasurement utilisée pour générer la demande d’image. |
| **adresse IP** | Lecture seule | Adresse IP du visiteur. |
| **Agent utilisateur** | Lecture seule | Agent utilisateur du visiteur. |
| **Référent** | Lecture seule | La dimension [Référent](/help/components/dimensions/referrer.md). |
| **Paramètre de chaîne de requête** | Lecture seule | Valeur d’un paramètre de chaîne de requête spécifié dans l’URL actuelle. |
| **Paramètre de chaîne de requête référent** | Lecture seule | La valeur d’un paramètre de chaîne de requête spécifié dans l’URL de référence ou une chaîne vide s’il n’en existe aucune. |
| **Domaine référent** | Lecture seule | Domaine de page de l’URL de référence, y compris les sous-domaines. |
| **Domaine racine de référence** | Lecture seule | Domaine de page de l’URL de référence, à l’exclusion des sous-domaines. |
| **Chaîne de requête de page** | Lecture seule | Tous les paramètres de chaîne de requête et leurs valeurs dans l’URL actuelle. |
| **Chaîne de requête référente** | Lecture seule | Tous les paramètres de chaîne de requête et leurs valeurs dans l’URL de référence. |
| **Chemin de la page** | Lecture seule | Chemin d’accès à la page de l’URL active. Le chemin d’accès de la page n’inclut pas les paramètres de protocole, de domaine ou de chaîne de requête. |
| **Domaine de page** | Lecture seule | Domaine de page de l’URL active, y compris les sous-domaines. Le domaine de page n’inclut pas de chemin de page ni de paramètres de chaîne de requête. |
| **Domaine racine de la page** | Lecture seule | Domaine de page de l’URL actuelle, à l’exclusion des sous-domaines. |
| **Point de vue du client** | Lecture + écriture | Indicateur qui détermine si l’accès est un accès en arrière-plan mobile. |

## Variables de conversion

| Variable | Statut en lecture/écriture | Description |
| --- | --- | --- |
| **eVar 1-250** | Lecture + écriture | [dimensions eVar](/help/components/dimensions/evar.md). |
| **Campaign** | Lecture + écriture | La dimension [Code de suivi](/help/components/dimensions/tracking-code.md). |
| **ID d’achat** | Lecture + écriture | Variable d’implémentation [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md). |
| **État** | Lecture + écriture | (Retiré) Variable d’implémentation [`state`](/help/implement/vars/page-vars/state.md). |
| **Zip** | Lecture + écriture | La dimension [ Code postal ](/help/components/dimensions/zip-code.md). |
| **Code de devise** | Lecture + écriture | Variable d’implémentation [`currencyCode`](/help/implement/vars/config-vars/currencycode.md). IMPORTANT : si vous définissez cette variable sur une valeur non valide, l’accès est ignoré. |
| **ID de transaction** | Lecture + écriture | Variable d’implémentation [`transactionID`](/help/import/data-sources/transactionid.md). |

>[!NOTE]
>Adobe ne prend pas en charge la définition de la variable d’implémentation [`products`](/help/implement/vars/page-vars/products.md) à l’aide de règles de traitement.

## Variables de trafic

| Variable | Statut en lecture/écriture | Description |
| --- | --- | --- |
| **Prop 1-75** | Lecture + écriture | Dimensions [prop](/help/components/dimensions/prop.md). |
| **Hiérarchie 1-5** | Lecture + écriture | (Supprimé) [Hiérarchie](/help/components/dimensions/hierarchy.md) dimensions. |
| **Serveur** | Lecture + écriture | La dimension [Serveur](/help/components/dimensions/server.md). |
| **Canal** | Lecture + écriture | La dimension [Section du site](/help/components/dimensions/site-section.md). |

## Variables contextuelles

Toutes les [ variables de données contextuelles ](/help/implement/vars/page-vars/contextdata.md) que cette suite de rapports a vues au cours des 30 derniers jours. Voir [Cas d’utilisation des règles de traitement](pr-use-cases.md) pour des exemples d’utilisation.

>[!IMPORTANT]
>
>Si les règles de traitement ne mappent pas une variable de données contextuelles donnée à une autre variable (telle qu’une prop ou une eVar), la valeur de la variable de données contextuelles est définitivement perdue.

## Événements de succès

Les règles de traitement peuvent définir des événements, mais ne peuvent pas les lire en tant que conditions. Définissez la liste déroulante d’actions de règle sur **[!UICONTROL Définir l’événement]** pour afficher les mesures disponibles à incrémenter.

| Variable | Statut en lecture/écriture | Description |
| --- | --- | --- |
| **Commandes** | En écriture seule | La mesure [Commandes](/help/components/metrics/orders.md). |
| **Paniers** | En écriture seule | La mesure [Paniers](/help/components/metrics/carts.md). |
| **Consultations du panier** | En écriture seule | La mesure [Vues du panier](/help/components/metrics/cart-views.md). |
| **Paiements** | En écriture seule | La mesure [ Passages en caisse ](/help/components/metrics/checkouts.md). |
| **Ajouts au panier** | En écriture seule | La mesure [Ajouts au panier](/help/components/metrics/cart-additions.md). |
| **Retraits du panier** | En écriture seule | La mesure [Retraits du panier](/help/components/metrics/cart-removals.md). |
| **Événement 1-1000** | En écriture seule | [ Événements personnalisés ](/help/components/metrics/custom-events.md). |
| **Consultations produits** | En écriture seule | La mesure [Vues des produits](/help/components/metrics/product-views.md). |
