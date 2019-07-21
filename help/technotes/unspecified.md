---
description: Divers rapports dans Adobe Analytics peuvent afficher Non spécifié, Autre ou Inconnu, selon le rapport spécifique consulté. En règle générale, cette ligne signifie que la variable n'a pas été définie ou autrement indisponible.
seo-description: Divers rapports dans Adobe Analytics peuvent afficher Non spécifié, Autre ou Inconnu, selon le rapport spécifique consulté. En règle générale, cette ligne signifie que la variable n'a pas été définie ou autrement indisponible.
seo-title: Non spécifié, Autre et Inconnu dans les rapports
solution: Analytics
title: Non spécifié, Autre et Inconnu dans les rapports
translation-type: tm+mt
source-git-commit: 1fdd14497171dbf5850ec1b1d873a06931d58435

---


# Non spécifié, Autre et Inconnu dans les rapports

Divers rapports dans Adobe Analytics peuvent afficher Non spécifié, Autre ou Inconnu, selon le rapport spécifique consulté. En règle générale, cette ligne signifie que la variable n'a pas été définie ou autrement indisponible. La liste complète suivante montre comment chaque rapport peut posséder un de ces éléments de ligne.

## « Non spécifié » dans les rapports

« Non spécifié » est une ligne relativement courante dans les rapports.

* **Un événement se déclenche sans variable de conversion :** Par exemple, un utilisateur se rend sur votre site et effectue un achat sans valeur evar 1. Si vous affichez les commandes à l'aide de la dimension evar 1, il n'y a aucune valeur pour attribuer cette commande. Par conséquent, il est automatiquement attribué à « Non spécifié ».
* **Données non classifiées dans les rapports de classification :** lors de la consultation des données de classification, les valeurs dont les données ne sont pas associées à cette classification donnée renvoient la valeur Non spécifié. Pour résoudre ce problème, classez la valeur de la variable parent.
* **Rapports de ventilation où seule une variable a été déclenchée :** Lorsque vous appliquez une ventilation à une variable, chaque instance de cette variable doit être prise en compte. Si la seconde variable n'a pas été vue, la valeur de dimension est « Non spécifié ».
* **Accès non mobiles dans les rapports mobiles :** Tous les accès non mobiles dans les rapports mobiles sont répertoriés « Non spécifié » (« Non mobile » dans les rapports et analyses).

## « Autre » dans les rapports

Bien qu'un peu rare dans les rapports, « Autre » peut se produire dans plusieurs cas :

* **Les pages se déclenchent en dehors des filtres d'URL internes :** Cette valeur est en place pour vous protéger contre la fraude des données, par exemple si une autre organisation vole votre code source et l'implémente sur son propre site. Pour corriger ce problème, assurez-vous que toutes les URL que votre code est implémenté correspondent aux filtres d'URL internes dans les paramètres de votre suite de rapports.
* **Visiteurs utilisant un navigateur peu courant :** dans le rapport Types de navigateur, la valeur Autre apparaît comme ventilation lorsque les visiteurs utilisent un type de navigateur peu courant. Nombre d’entreprises créent des navigateurs. Tous les navigateurs qui n'ont pas été créés par les grandes entreprises sont classés dans « Autres » pour éviter tout encombrement.

## Inconnu dans les rapports

« Inconnu » peut se produire dans plusieurs cas :

* **Accès non navigateur lors de l'affichage des rapports technologiques :** Si une bibliothèque appmeasurement ne parvient pas à déterminer si une fonctionnalité est prise en charge, « Inconnu » s'affiche dans les rapports.
* **Utilisation de segments où les composants ne sont pas accessibles :** Assurez-vous que les variables utilisées dans un segment sont activées et que les utilisateurs y ont accès. Si un utilisateur n'a pas accès à un composant de segment ou si une variable est désactivée, « Inconnu » s'affiche.

## Filtrage de ces valeurs dans les rapports {#section_5536E2B419D445D39C932E8F12C0070C}

Dans la plupart des cas, ignorer ces éléments de ligne ne présente aucun problème. Le filtre de recherche peut être utilisé pour les supprimer si nécessaire.

Some backend data variables use the value `::unspecified::` in reporting, though it is not shown in the interface. Si un filtre de recherche ne permet pas d'exclure les données, essayez d'utiliser cette valeur (y compris les deux-points).
