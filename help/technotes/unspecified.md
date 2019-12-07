---
description: Divers rapports dans Adobe Analytics peuvent afficher Non spécifié, Autre ou Inconnu, selon le rapport spécifique consulté. En règle générale, cet élément de ligne signifie que la variable n’a pas été définie ou n’est pas disponible.
title: Non spécifié, Autre et Inconnu dans les rapports
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# "Non spécifié", "Autre" et "Inconnu" dans les rapports

Divers rapports dans Adobe Analytics peuvent afficher "Non spécifié", "Autre" ou "Inconnu", selon le rapport spécifique consulté. En règle générale, cet élément de ligne signifie que la variable n’a pas été définie ou n’est pas disponible. La liste complète suivante montre comment chaque rapport peut posséder un de ces éléments de ligne.

## Valeur Non spécifié dans les rapports

"Non spécifié" est une ligne assez courante dans les rapports.

* **** Un événement se déclenche sans variable de conversion : Par exemple, un utilisateur se rend sur votre site et effectue un achat sans valeur eVar1. Si vous affichez des commandes à l’aide de la dimension eVar1, il n’y a aucune valeur à attribuer à cette commande. Par conséquent, il est automatiquement attribué à "Non spécifié".
* **** Données non classées dans les rapports de classification : Lors de l’affichage des données de classification, toute valeur pour laquelle aucune donnée n’est associée à cette classification spécifique renvoie "Non spécifié". Pour résoudre ce problème, classifiez la valeur de la variable parente.
* **** Rapports de ventilation dans lesquels une seule variable est déclenchée : Lorsque vous appliquez une ventilation à une variable, chaque instance de cette variable doit être prise en compte. Si la seconde variable n’était pas vue ou si elle persistait à partir d’un accès précédent, la valeur de dimension est "Non spécifié".
* **** Accès non mobiles dans les rapports mobiles : Les accès non mobiles dans les rapports mobiles sont répertoriés comme "Non spécifié" ("Non mobile" dans les rapports et analyses).

## Valeur Autre dans les rapports

Bien que quelque peu rare dans les rapports, "Autre" peut survenir dans plusieurs cas :

* **** Les pages se déclenchent en dehors des filtres d’URL internes : Cette valeur est en place pour vous aider à vous protéger contre la fraude aux données, par exemple si une autre organisation vole votre code source et l’implémente sur son propre site. Pour corriger ce problème, assurez-vous que toutes les URL sur lesquelles votre code est implémenté correspondent aux filtres d’URL internes de vos paramètres de suite de rapports.
* **Visiteurs utilisant un navigateur peu courant :** dans le rapport Types de navigateur, la valeur Autre apparaît comme ventilation lorsque les visiteurs utilisent un type de navigateur peu courant. Nombre d’entreprises créent des navigateurs. Tous les navigateurs que les grandes entreprises n’ont pas créés sont classés dans la catégorie "Autre" afin d’éviter toute confusion dans les rapports.

## Valeur Inconnu dans les rapports

La valeur Inconnu peut s’afficher dans plusieurs cas :

* **** Accès hors navigateur lors de l’affichage des rapports Technologie : Si une bibliothèque AppMeasurement n’est pas en mesure de déterminer si une fonctionnalité est prise en charge, l’option "Inconnu" s’affiche dans les rapports.
* **** Utilisation de segments pour lesquels les composants ne sont pas accessibles : Assurez-vous que les variables utilisées dans un segment sont activées et que les utilisateurs peuvent y accéder. Si un utilisateur n’a pas accès à un composant de segment, ou si une variable est désactivée, "Inconnu" s’affiche.

## Filtrage de ces valeurs dans les rapports {#section_5536E2B419D445D39C932E8F12C0070C}

Dans la plupart des cas, ignorer ces éléments de ligne ne présente aucun problème. Le filtre de recherche peut être utilisé pour les supprimer, le cas échéant.

Some backend data variables use the value `::unspecified::` in reporting, though it is not shown in the interface. Si un filtre de recherche n’exclut pas les données, essayez d’utiliser cette valeur (y compris les deux-points).
