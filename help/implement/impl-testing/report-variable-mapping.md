---
description: Le tableau ci-dessous montre l’association des rapports aux variables, ou les rapports et les variables qu’ils utilisent.
keywords: Mise en œuvre d’Analytics
seo-description: Le tableau ci-dessous montre l’association des rapports aux variables, ou les rapports et les variables qu’ils utilisent.
seo-title: Mappage des rapports aux variables
solution: Analytics
title: Mappage des rapports aux variables
topic: Développeur et mise en œuvre
uuid: 4707660c-4be5-425c-a690-7bc6df4cc0fa
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Mappage des rapports aux variables

Le tableau ci-dessous montre l’association des rapports aux variables, ou les rapports et les variables qu’ils utilisent.

**Rapports de conversion** Le tableau suivant répertorie les variables de conversion utilisées pour renseigner chaque rapport :

| Achats |
|---|
| Conversions et moyennes | s.events, s.products, s.purchaseID | Définir s.events sur achat, détails du produit, numéro de commande |
| Recettes | s.events, s.products, s.purchaseID | Définir s.events sur achat, détails du produit, numéro de commande |
| Commandes | s.events, s.products, s.purchaseID | Définir s.events sur achat, détails du produit, numéro de commande |
| Unités | s.events, s.products, s.purchaseID | Définir s.events sur achat, détails du produit, numéro de commande |

| Panier |
|---|
| Conversions et moyennes | s.events, s.products, s.purchaseID |  |
| Panier | s.events | Définir s.events sur scOpen |
| Consultations du panier | s.events | Définir s.events sur scView |
| Ajouts au panier | s.events | Définir s.events sur scAdd |
| Retraits du panier | s.events | Définir s.events sur scRemove |
| Achats | s.events | Définir s.events sur scCheckout |

| Événements personnalisés |
|---|
| Evénement personnalisé 1 | s.events | Renseigner avec event1 à event100 |
| … | … | Renseigner avec event1 à event100 |
| Evénement personnalisé 100 | s.events | Renseigner avec event1 à event100 |

| Produits |
|---|
| Conversions et moyennes | s.events, s.products, s.purchaseID |  |
| Produits | s.products, s.events | Peut varier selon les mesures de la colonne droite |
| Vente croisée | s.products, s.events, s.purchaseID | Peut varier selon les mesures de la colonne droite |
| Catégories | s.products | Peut varier selon les mesures de la colonne droite |

| Campagnes |
|---|
| Conversions et moyennes | s.products, s.events, s.campaign |  |
| Code de suivi | s.campaign |  |
| Eléments créatifs | N/D | Défini dans [!DNL Analytics] |
| Campagnes | N/D | Défini dans [!DNL Analytics] |

| Fidélité de la clientèle |
|---|
| Fidélité de la clientèle | s.products, s.events, s.purchaseID | Variables définies sur la page Confirmation de commande page |

| Cycle de ventes |
|---|
| Jours avant le premier achat | s.products, s.events, s.purchaseID | Variables définies sur la page Confirmation de commande  |
| Jours depuis le dernier achat | s.products, s.events, s.purchaseID | Variables définies sur la page Confirmation de commande  |
| Nombre de visites | s.products, s.events, s.purchaseID | Variables définies sur la page Confirmation de commande  |
| Clients quotidiens uniques | s.products, s.events, s.purchaseID | Variables définies sur la page Confirmation de commande  |
| Clients mensuels uniques | s.products, s.events, s.purchaseID | Variables définies sur la page Confirmation de commande  |
| Clients annuels uniques | s.products, s.events, s.purchaseID | Variables définies sur la page Confirmation de commande  |

| Méthodes de recherche |
|---|
| Domaines référents | N/D | Défini automatiquement par le fichier .JS |
| Domaines référents d’origine | N/D | Défini automatiquement par le fichier .JS |
| Moteurs de recherche | N/D | Défini automatiquement par le fichier .JS |
| Mots-clés de recherche | N/D | Défini automatiquement par le fichier .JS |

| Profil du visiteur |
|---|
| Domaines de haut niveau | N/D | Défini automatiquement par le fichier .JS |
| Langues | N/D | Défini automatiquement par le fichier .JS |
| Fuseaux horaires | N/D | Défini automatiquement par le fichier .JS |
| Etats | s.state | Variable définie sur la page Confirmation de commande  |
| Codes postaux | s.zip | Variable définie sur la page Confirmation de commande  |
| Domaines | N/D | Défini automatiquement par le fichier .JS |

| Technologie |
|---|
| Navigateurs | N/D | Défini automatiquement par le fichier .JS |
| Systèmes d’exploitation | N/D | Défini automatiquement par le fichier .JS |
| Résolutions d’écran | N/D | Défini automatiquement par le fichier .JS |

| Chemin du site |
|---|
| Valeur de la page | s.pageName, s.products, s.events, s.purchaseID |  |
| Pages d’entrée | s.pageName |  |
| Pages d’entrée originales | s.pageName |  |
| Pages par visite | N/D | Calculé par les règles de fonctionnement dans [!DNL Analytics] |
| Durée de la visite du site | N/D | Calculé par les règles de fonctionnement dans [!DNL Analytics] |
| Sections du site | [!UICONTROL s.channel] | Identique au rapport [!UICONTROL Canal] dans la section des rapports sur le [!UICONTROL trafic] |

| Variables personnalisées |
|---|
| EVar personnalisée 1 | [!UICONTROL s.eVar] 1 |  |
| EVar personnalisée 2 | [!UICONTROL s.eVar] 2 |  |
| EVar personnalisée 3 | [!UICONTROL s.eVar] 3 |  |
| … |  |  |
| EVar personnalisée 75 | [!UICONTROL s.eVar] 75 |  |

## Rapports sur le trafic {#section_76A74C3D7B60461D9ADE0E5E183DD777}

Le tableau suivant répertorie les variables de [!UICONTROL trafic] utilisées pour renseigner chaque rapport :

| Mesures calculées |
|---|
| N/D | N/D | N/D |

| Trafic du site |
|---|
| Pages vues | N/D | Calculé par les règles de fonctionnement dans [!DNL Analytics] |
| Visiteurs uniques par heure | N/D | Calculé par les règles de fonctionnement dans [!DNL Analytics] |
| Visiteurs uniques par jour | N/D | Calculé par les règles de fonctionnement dans [!DNL Analytics] |
| Visiteurs uniques par mois | N/D | Calculé par les règles de fonctionnement dans [!DNL Analytics] |
| Visiteurs uniques par an | N/D | Calculé par les règles de fonctionnement dans [!DNL Analytics] |
| Visites | N/D | Calculé par les règles de fonctionnement dans [!DNL Analytics] |
| Téléchargements de fichiers | N/D | Suivi automatiquement par le fichier .JS (dépend des paramètres de variables du fichier .JS) |

| Méthodes de recherche |
|---|
| Domaines référents | N/D | Défini automatiquement par le fichier .JS |
| Référents | N/D | Défini automatiquement par le fichier .JS |
| Moteurs de recherche | N/D | Défini automatiquement par le fichier .JS |
| Mots-clés de recherche | N/D | Défini automatiquement par le fichier .JS |
| Fréquence des retours | N/D | Calculé par les règles de fonctionnement dans [!DNL Analytics] |
| Visites retours quotidiennes | N/D | Calculé par les règles de fonctionnement dans [!DNL Analytics] |
| Visites retours | N/D | Calculé par les règles de fonctionnement dans [!DNL Analytics] |
| Nombres de visites | N/D | Calculé par les règles de fonctionnement dans [!DNL Analytics] |

| Profil du visiteur |
|---|
| Domaines | N/D | Défini automatiquement par le fichier .JS |
| Domaines de haut niveau | N/D | Défini automatiquement par le fichier .JS |
| Langues | N/D | Défini automatiquement par le fichier .JS |
| Fuseaux horaires | N/D | Défini automatiquement par le fichier .JS |
| Détails du visiteur | N/D | Défini automatiquement par le fichier .JS |
| 100 derniers visiteurs | N/D | Calculé par les règles de fonctionnement dans [!DNL Analytics] |
| Page d’accueil de l’utilisateur | N/D | Défini automatiquement par le fichier .JS |
| Visiteurs clés | N/D | Basé sur l’adresse IP du visiteur |
| Pages vues par visiteurs clés | N/D | Basé sur l’adresse IP du visiteur |

| Géosegmentation |
|---|
| Pays | N/D | Basé sur l’adresse IP du visiteur |
| Etats (E.-U.) | N/D | Basé sur l’adresse IP du visiteur |
| Zone desservie (DMA) | N/D | Basé sur l’adresse IP du visiteur |
| Villes internationales | N/D | Basé sur l’adresse IP du visiteur |
| Villes des Etats-Unis | N/D | Basé sur l’adresse IP du visiteur |

| Technologie |
|---|
| Types de navigateur | N/D | Défini automatiquement par le fichier .JS |
| Navigateurs | N/D | Défini automatiquement par le fichier .JS |
| Appareils mobiles | N/D | Défini automatiquement par le fichier .JS |
| Largeur du navigateur | N/D | Défini automatiquement par le fichier .JS |
| Hauteur du navigateur | N/D | Défini automatiquement par le fichier .JS |
| Systèmes d’exploitation | N/D | Défini automatiquement par le fichier .JS |
| Intensité de couleur de l’écran | N/D | Défini automatiquement par le fichier .JS |
| Résolutions d’écran | N/D | Défini automatiquement par le fichier .JS |
| Modules Netscape | N/D | Défini automatiquement par le fichier .JS |
| Java | N/D | Défini automatiquement par le fichier .JS |
| JavaScript | N/D | Défini automatiquement par le fichier .JS |
| Version JavaScript | N/D | Défini automatiquement par le fichier .JS |
| Cookies | N/D | Défini automatiquement par le fichier .JS |
| Types de connexion | N/D | Défini automatiquement par le fichier .JS |
| Segmentation |

| Segmentation |
|---|
| Pages les plus populaires | s.pageName |  |
| Sections du site les plus populaires | s.channel |  |
| Serveurs les plus populaires | s.server |  |

| Insight personnalisé |
|---|
| Liens personnalisés | s.linkName | Nécessite une implémentation personnalisée |
| Aperçu personnalisé 1 | s.prop1 |  |
| … | … |  |
| Aperçu personnalisé 75 | s.prop75 |  |

| Hiérarchies |
|---|
| Hiérarchie 1 | s.hier1 |  |
| … | … |  |
| Hiérarchie 5 | s.hier5 |  |

## Rapports de cheminement {#section_85E0A2396B894659A6BE572819263E95}

Le tableau suivant répertorie les variables de cheminement qui sont utilisées pour renseigner chaque rapport dans [!DNL Analytics] :

| Pages |
|---|
| Résumé de la page | s.pageName (ou autre variable de chemin) | Dépend également des règles de fonctionnement internes |
| Valeur de la page | s.pageName (ou autre variable de chemin) | Dépend également des règles de fonctionnement internes |
| Pages les plus populaires | s.pageName (ou autre variable de chemin) | Dépend également des règles de fonctionnement internes |
| Actualisations | s.pageName (ou autre variable de chemin) | Dépend également des règles de fonctionnement internes |
| Clics jusqu’à la page | s.pageName (ou autre variable de chemin) | Dépend également des règles de fonctionnement internes |
| Durée de consultation de la page | s.pageName (ou autre variable de chemin) | Dépend également des règles de fonctionnement internes |
| Pages introuvables | s.pageName (ou autre variable de chemin) | Dépend également des règles de fonctionnement internes |

| Entrées et sorties |
|---|
| Pages d’entrée | s.pageName (ou autre variable de chemin) | Dépend également des règles de fonctionnement internes |
| Pages de sortie | s.pageName (ou autre variable de chemin) | Dépend également des règles de fonctionnement internes |
| Liens de sortie | s.pageName (ou autre variable de chemin) | Dépend également des règles de fonctionnement internes |

| Chemins complets |
|---|
| Chemins complets | s.pageName (ou autre variable de chemin) | Dépend également des règles de fonctionnement internes |
| Chemins les plus longs | s.pageName (ou autre variable de chemin) | Dépend également des règles de fonctionnement internes |
| Longueur de chemin | s.pageName (ou autre variable de chemin) | Dépend également des règles de fonctionnement internes |
| Durée de la visite | s.pageName (ou autre variable de chemin) | Dépend également des règles de fonctionnement internes |
| Visites page unique | s.pageName (ou autre variable de chemin) | Dépend également des règles de fonctionnement internes |

| Analyse avancée |
|---|
| Page précédente | s.pageName (ou autre variable de chemin) | Dépend également des règles de fonctionnement internes |
| Page suivante | s.pageName (ou autre variable de chemin) | Dépend également des règles de fonctionnement internes |
| Flux Page précédente | s.pageName (ou autre variable de chemin) | Dépend également des règles de fonctionnement internes |
| Flux page suivante | s.pageName (ou autre variable de chemin) | Dépend également des règles de fonctionnement internes |
| PathFinder | s.pageName (ou autre variable de chemin) | Dépend également des règles de fonctionnement internes |
| Abandons | s.pageName (ou autre variable de chemin) | Dépend également des règles de fonctionnement internes |
