---
title: Règles de jeu de classifications
description: Afficher et modifier des règles pour un jeu de classifications individuel.
exl-id: 1ccb6a20-1993-4fd3-90eb-9154d12d0ec7
feature: Classifications
source-git-commit: 9f70dbeb9dfe54897915213480f05cbdfaf920ef
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 1%

---

# Règles de jeu de classifications

Les règles de jeu de classifications vous permettent de classer automatiquement les valeurs en fonction de la valeur de la variable. Ces règles s’appliquent à toutes les valeurs de variable entrante pour tous les abonnements du jeu de classifications.

**[!UICONTROL Composants]** > **[!UICONTROL Jeux de classifications]** > **[!UICONTROL Jeux]** > Cliquez sur le nom du jeu de classifications souhaité > **[!UICONTROL Règles]**

## Paramètres des règles

Paramètres qui s’appliquent à l’ensemble des règles.

* **[!UICONTROL Les règles remplacent]** : détermine le comportement de toutes les règles dans les cas où il existe une valeur de classification.
   * **[!UICONTROL Appliquer à toutes les valeurs]** : si une règle correspond, remplacez toujours la valeur de classification.
   * **[!UICONTROL Appliquer uniquement aux valeurs non définies]** : si une règle correspond, n’écrivez la valeur de classification que si elle est vide. S’il existe une valeur de classification, ne faites rien.
* **[!UICONTROL Intervalle de recherche en amont]** : lorsque cette règle est activée, toutes les règles s’exécutent par rapport à toutes les valeurs uniques affichées dans l’intervalle de recherche en amont défini ici.

## Règles

Liste des règles qui s’exécutent pour chaque valeur unique.

* **[!UICONTROL Recherche]** : une zone de recherche qui vous permet de filtrer les règles par critères de correspondance.
* **[!UICONTROL Ajouter une règle]** : ajoute une ligne vide au tableau des règles.
* **[!UICONTROL Ensemble de règles de test]** : ouvre une interface utilisateur de test qui vous permet de valider vos règles. À gauche, vous pouvez saisir manuellement des valeurs de clé ou faire glisser un fichier de classification pour importer de nombreuses valeurs à tester. À droite se trouve un tableau qui affiche les résultats préliminaires de ce à quoi ressembleraient les valeurs classées si le jeu de règles était activé. Cette interface étant réservée à la validation, aucune valeur n’est classée.

Sélectionnez une ou plusieurs règles en cochant la case en regard de la règle souhaitée. La sélection d’une règle fait apparaître les options suivantes :

* **[!UICONTROL Supprimer]** : supprime la ligne de la table des règles.
* **[!UICONTROL Dupliquer]** : copie les lignes sélectionnées sur les nouvelles lignes de la table des règles.

## Tableau des règles

Le tableau de règles est divisé verticalement en deux parties principales : condition correspondante et action de classification. Chaque ligne (une règle individuelle) contient une condition correspondante et une action de classification.

* **Numéro de règle** : les règles s’exécutent dans l’ordre dans lequel vous configurez la table des règles. Si [!UICONTROL Les règles remplacent] est défini sur [!UICONTROL Appliquer à toutes les valeurs], la dernière règle correspondante remplace toutes les règles précédentes pour la même dimension de classification. Si [!UICONTROL Les règles remplacent] est défini sur [!UICONTROL Appliquer uniquement aux valeurs non définies], la première règle qui définit une valeur de classification s’applique.
* **[!UICONTROL Sélectionner le type de règle]** : critères de règle. Les options incluent [!UICONTROL Contains], [!UICONTROL Ends with], [!UICONTROL Regular expression], [!UICONTROL Regular expression] et [!UICONTROL Starts with].
* **[!UICONTROL Entrez les critères de correspondance]** : chaîne de texte à faire correspondre. Si vous sélectionnez [!UICONTROL Expression régulière] comme type de règle, une superposition s’affiche, vous permettant de saisir la valeur, de tester l’expression régulière et de fournir un exemple de syntaxe.
* **[!UICONTROL Définir la classification]** : liste déroulante qui définit la dimension de classification à laquelle vous souhaitez affecter une valeur. Les options valides incluent des éléments dans votre [schéma](schema.md).
* **[!UICONTROL To]** : chaîne de texte à laquelle définir la valeur classée. Si le type de règle est [!UICONTROL Expression régulière], vous pouvez inclure une combinaison de texte et de groupes de correspondance.
