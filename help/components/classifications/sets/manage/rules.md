---
title: Règles de jeu de classifications
description: Afficher et modifier des règles pour un jeu de classifications individuel.
source-git-commit: 496b4891d447ed9dd091a6498a792146a2d5aceb
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 0%

---

# Règles de jeu de classifications

Les règles de jeu de classifications vous permettent de classer automatiquement les valeurs en fonction de la valeur de la variable. Ces règles s’appliquent à toutes les valeurs de variable entrante pour tous les abonnements du jeu de classifications.

**[!UICONTROL Composants]** > **[!UICONTROL Jeux de classifications]** > **[!UICONTROL Visionneuses]** > Cliquez sur le nom du jeu de classifications de votre choix > **[!UICONTROL Règles]**

## Paramètres des règles

Paramètres qui s’appliquent à l’ensemble des règles.

* **[!UICONTROL Remplacement des règles]**: Détermine le comportement de toutes les règles lorsqu’il existe une valeur de classification.
   * **[!UICONTROL Appliquer à toutes les valeurs]**: Si une règle correspond, remplacez toujours la valeur de classification.
   * **[!UICONTROL Appliquer uniquement aux valeurs non définies]**: Si une règle correspond, écrivez uniquement la valeur de classification si elle est vide. S’il existe une valeur de classification, ne faites rien.
* **[!UICONTROL Intervalle de recherche en amont]**: Lorsque cette règle est activée, toutes les règles s’exécutent sur toutes les valeurs uniques affichées dans l’intervalle de recherche en amont défini ici.

## Règles

Liste des règles qui s’exécutent pour chaque valeur unique.

* **[!UICONTROL Rechercher]**: Zone de recherche qui vous permet de filtrer les règles selon des critères de correspondance.
* **[!UICONTROL Ajouter une règle]**: Ajoute une ligne vierge au tableau de règles.
* **[!UICONTROL Tester le jeu de règles]**: Permet d’afficher une interface utilisateur de test qui vous permet de valider vos règles. À gauche, vous pouvez saisir manuellement des valeurs de clé ou faire glisser un fichier de classification pour importer de nombreuses valeurs à tester. À droite se trouve un tableau qui affiche les résultats préliminaires de ce à quoi ressembleraient les valeurs classées si le jeu de règles était activé. Cette interface étant réservée à la validation, aucune valeur n’est classée.

Sélectionnez une ou plusieurs règles en cochant la case en regard de la règle souhaitée. La sélection d’une règle fait apparaître les options suivantes :

* **[!UICONTROL Supprimer]**: Supprime la ligne du tableau de règles.
* **[!UICONTROL Dupliquer]**: Copie les lignes sélectionnées dans de nouvelles lignes du tableau de règles.

## Tableau des règles

Le tableau des règles est divisé verticalement en deux parties principales : condition et action de classification correspondantes. Chaque ligne (une règle individuelle) contient une condition correspondante et une action de classification.

* **Numéro de règle**: Les règles s’exécutent dans l’ordre dans lequel vous configurez le tableau des règles. If [!UICONTROL Remplacement des règles] est défini sur [!UICONTROL Appliquer à toutes les valeurs], la dernière règle correspondante remplace toutes les règles précédentes pour la même dimension de classification. If [!UICONTROL Remplacement des règles] est défini sur [!UICONTROL Appliquer uniquement aux valeurs non définies], la première règle qui définit une valeur de classification s’applique.
* **[!UICONTROL Sélectionner le type de règle]**: Critères de la règle. Les options incluent [!UICONTROL Contient], [!UICONTROL Se termine par], [!UICONTROL Expression régulière], [!UICONTROL Expression régulière], et [!UICONTROL Commence par].
* **[!UICONTROL Entrer les critères de correspondance]**: Chaîne de texte à faire correspondre. Si vous sélectionnez [!UICONTROL Expression régulière] comme type de règle, une superposition s’affiche, vous permettant de saisir la valeur, de tester l’expression régulière et de fournir un exemple de syntaxe.
* **[!UICONTROL Définir la classification]**: Liste déroulante qui définit la dimension de classification à laquelle vous souhaitez affecter une valeur. Les options valides incluent des éléments dans votre [schema](schema.md).
* **[!UICONTROL À]**: Chaîne de texte à laquelle définir la valeur classée. Si le type de règle est [!UICONTROL Expression régulière], vous pouvez inclure une combinaison de texte et de groupes de correspondance.
