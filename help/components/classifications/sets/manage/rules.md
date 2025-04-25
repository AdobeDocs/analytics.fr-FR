---
title: Règles de jeu de classifications
description: Affichez et modifiez les règles d’un ensemble de classifications individuel.
exl-id: 1ccb6a20-1993-4fd3-90eb-9154d12d0ec7
feature: Classifications
source-git-commit: de12253f6db798f49d0cae34bf9cb6b7a3de17db
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 1%

---

# Règles de jeu de classifications

Les règles des ensembles de classifications vous permettent de classer automatiquement les valeurs en fonction de la valeur sur laquelle la variable est définie. Ces règles s’appliquent à toutes les valeurs de variable entrantes pour tous les abonnements de l’ensemble de classifications.

**[!UICONTROL Composants]** > **[!UICONTROL Ensembles de classifications]** > **[!UICONTROL Ensembles]** > Cliquez sur le nom de l’ensemble de classifications de votre choix > **[!UICONTROL Règles]**

![interface utilisateur des règles des jeux de classifications](../../assets/csets-rules.png)

## Paramètres des règles

Paramètres qui s’appliquent à l’ensemble des règles.

* **[!UICONTROL Remplacement des règles]** : détermine le comportement de toutes les règles dans les cas où il existe une valeur de classification.
   * **[!UICONTROL Appliquer à toutes les valeurs]** : si une règle correspond, remplacez toujours la valeur de classification.
   * **[!UICONTROL Appliquer uniquement aux valeurs non définies]** : si une règle correspond, n’écrivez la valeur de classification que si elle est vide. S’il existe une valeur de classification, ne rien faire.
* **[!UICONTROL Intervalle de recherche en amont]** : lorsque cette règle est activée, toutes les règles s’exécutent sur toutes les valeurs uniques affichées dans l’intervalle de recherche en amont défini ici.

## Règles

Liste des règles exécutées pour chaque valeur unique.

* **[!UICONTROL Recherche]** : zone de recherche qui vous permet de filtrer les règles en fonction des critères de correspondance.
* **[!UICONTROL Ajouter une règle]** : ajoute une ligne vide au tableau des règles.
* **[!UICONTROL Jeu de règles de test]** : affiche une interface utilisateur de test qui vous permet de valider vos règles. Sur la gauche, vous pouvez saisir manuellement des valeurs clés ou faire glisser et déposer un fichier de classification pour importer de nombreuses valeurs en fonction desquelles effectuer un test. À droite se trouve un tableau qui montre les résultats préliminaires de ce à quoi les valeurs classées ressembleraient si l’ensemble de règles était activé. Comme cette interface est uniquement destinée à la validation, aucune valeur n’est classée.

Sélectionnez une ou plusieurs règles en cochant la case en regard de la règle souhaitée. La sélection d’une règle affiche les options suivantes :

* **[!UICONTROL Supprimer]** : supprime la ligne de la table des règles.
* **[!UICONTROL Dupliquer]** : copie les lignes sélectionnées dans de nouvelles lignes du tableau de règles.

## Table des règles

Le tableau des règles est séparé verticalement en deux parties principales : la condition correspondante et l’action de classification. Chaque ligne (une règle individuelle) contient une condition correspondante et une action de classification.

* **Numéro de règle** : les règles s’exécutent dans l’ordre dans lequel vous configurez la table des règles. Si l’option [!UICONTROL Remplacer les règles] est définie sur [!UICONTROL Appliquer à toutes les valeurs], la dernière règle correspondante remplace toutes les règles précédentes pour la même dimension de classification. Si [!UICONTROL Remplacement des règles] est défini sur [!UICONTROL Appliquer uniquement aux valeurs non définies], la première règle qui définit une valeur de classification s’applique.
* **[!UICONTROL Sélectionner le type de règle]** : les critères de la règle. Les options incluent [!UICONTROL Contient], [!UICONTROL Se termine par], [!UICONTROL Expression régulière], [!UICONTROL Expression régulière] et [!UICONTROL Commence par].
* **[!UICONTROL Saisir les critères de correspondance]** : chaîne de texte à faire correspondre. Si vous sélectionnez [!UICONTROL Expression régulière] comme type de règle, un recouvrement s’affiche, vous permettant de saisir la valeur, de tester l’expression régulière et de fournir un exemple de syntaxe.
* **[!UICONTROL Définir la classification]** : une liste déroulante qui définit la dimension de classification à laquelle vous souhaitez affecter une valeur. Les options valides incluent des éléments dans votre [schéma](schema.md).
* **[!UICONTROL To]** : chaîne de texte sur laquelle définir la valeur classée. Si le type de règle est [!UICONTROL Expression régulière], vous pouvez inclure une combinaison de texte et de groupes de correspondances.
