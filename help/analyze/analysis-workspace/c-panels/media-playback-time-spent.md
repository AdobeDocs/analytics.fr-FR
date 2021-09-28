---
title: Panneau Durée de lecture du média
description: Utilisation et interprétation du panneau Durée de lecture multimédia dans Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: null
source-git-commit: 74ef44c4afba6d2dffb2b10fa473baee3be16a23
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 49%

---

# Panneau Durée de lecture du média

Les clients Media Analytics peuvent analyser le temps de lecture passé pour déterminer où s’est produit le pic d’accès simultanés ou où des abandons ont eu lieu, afin de fournir des informations précieuses sur la qualité du contenu et l’engagement des visiteurs, et pour faciliter la résolution des problèmes ou la planification du volume ou de l’échelle.

Dans Analysis Workspace, la durée de lecture est le temps passé à visionner vos flux multimédia à un moment donné et comprend la mise en pause, la mise en mémoire tampon et le temps de démarrage.

Le panneau Durée de lecture multimédia permet d’analyser la lecture au fil du temps, avec des détails sur la simultanéité la plus élevée et la possibilité de ventiler et de comparer. Pour accéder au panneau Durée de lecture du média , accédez à une suite de rapports avec les composants Media Analytics activés. Cliquez ensuite sur l’icône du panneau située à l’extrémité gauche et faites glisser le panneau dans votre projet Analysis Workspace.

Ce panneau comprend également de nouvelles fonctionnalités du calendrier qui vous permettent de sélectionner et d’afficher moins de 24 heures. Vous pouvez le faire pour l’ensemble du panneau ou créer des segments à l’aide de périodes consécutives afin de pouvoir suivre les prospects et les prospects pour les programmes ou sections de programmes. Une fois que vous avez placé au moins deux de ces segments de date, une option de bouton radio s’affiche pour l’affichage de la séquence de dates. Celle-ci recouvrera les lignes avec un début d’axe x commun ou les affichera de manière séquentielle avec le début de leur axe x spécifique.

## Entrées de panneau {#Input}

Vous pouvez configurer le panneau Durée de lecture du média à l’aide des paramètres d’entrée suivants :

| Paramètre | Description |
|---|---|
| Période du panneau | La période par défaut du panneau est définie sur Aujourd’hui. Vous pouvez la modifier pour afficher un seul jour ou plusieurs mois à la fois.<br>La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes). Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
| Granularité | La granularité par défaut est définie sur Minute.<br>La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes). Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
| Synthèse des chiffres des panneaux | Pour afficher les détails de date ou d’heure pour la durée de lecture, un nombre récapitulatif est disponible. La valeur maximale affiche les détails concernant le pic d’accès simultanés. La valeur minimale affiche les détails du creux. Somme additionne la durée totale de lecture de la sélection. La valeur par défaut du panneau indique Maximum uniquement, mais vous pouvez la modifier pour afficher Minimum, Somme ou toute combinaison des trois.<br>Si vous utilisez des ventilations, une synthèse des chiffres s’affiche pour chacune d’elles. |
| Ventilations de la série | Vous pouvez éventuellement ventiler votre visualisation par segments, dimensions, éléments de dimension ou périodes.<p>- Vous pouvez afficher jusqu’à 10 lignes à la fois. Les ventilations sont limitées à un seul niveau.</p><p>- Lorsque vous faites glisser une dimension, les principaux éléments de dimension sont automatiquement sélectionnés en fonction de la période du panneau sélectionnée.</p>- Pour comparer des périodes, faites glisser deux périodes ou plus dans le filtre de ventilation de la série. |
| Format de l’heure | Vous pouvez afficher le temps de lecture en heures:Minutes:secondes (par défaut) ou en minutes (qui s’affiche en nombres entiers, arrondi à 0,5). |
| Affichage de la séquence de dates | Si vous avez placé au moins deux segments de période sous forme de ventilations de série, vous aurez la possibilité de sélectionner l’option de superposition (par défaut) ou séquentielle. La superposition affiche les lignes avec un axe x commun qui démarrent de sorte qu’elles s’exécutent en parallèle, tandis que l’enchaînement affiche les lignes avec leur axe x spécifique qui démarrent. Si les lignes de données s’affichent (par exemple, le segment 1 se termine à 20 h 44 et le segment 2 à 20 h 45), les lignes s’affichent dans l’ordre. |

### Affichage par défaut

![Affichage par défaut](assets/mpts_default_view.png)

## Sortie de panneau {#Output}

Le panneau Durée de lecture multimédia renvoie un graphique en courbes et des nombres de synthèse afin d’inclure des détails sur la durée maximale, minimale et/ou totale de la lecture. En haut du panneau, une ligne de résumé vous rappelle les paramètres du panneau que vous avez sélectionnés.

À tout moment, vous pouvez modifier et recréer le panneau en cliquant sur l’icône de modification en forme de crayon dans le coin supérieur droit.

Si vous avez sélectionné la ventilation des séries, une ligne du graphique en courbe et une synthèse des chiffres s’affichent pour chacune d’elles :

![sortie du temps de lecture du média](assets/mpts_outputs1.png)

### Source de données

La seule mesure qui peut être utilisée dans ce panneau est Temps de lecture passé.

| Mesure | Description |
|---|---|
| Temps passé sur la lecture | Nombre total d’heures:minutes:secondes (ou minutes) de contenu affiché lors de la granularité sélectionnée, y compris la mise en pause, la mise en mémoire tampon et le temps de démarrage. |

## Questions fréquentes {#FAQ}

| Question | Réponse |
|---|---|
| Où se trouve le tableau à structure libre ? Comment puis-je voir la source de données ? | <p></p><p>Le tableau à structure libre n’est pas disponible dans cet affichage. Vous pouvez télécharger la source de données en cliquant avec le bouton droit sur le graphique en courbes et en téléchargeant le fichier CSV.</p> |
| <p>Pourquoi ma granularité a-t-elle changé ?</p> | <p>La visualisation est limitée à 1 440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes). Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à l’intégralité de la période.</p><p></p><p>Lorsque vous passez d’une période plus grande à une période plus petite, la granularité est mise à jour vers le détail le plus bas possible une fois la période modifiée. Pour afficher une granularité plus élevée, modifiez le panneau et recréez la visualisation.</p> |
| <p></p><p>Comment puis-je comparer les noms de vidéo, les segments, les types de contenu, etc. ?</p> | <p>Pour les comparer dans une visualisation unique, faites glisser des segments, des dimensions ou des éléments de dimension spécifiques dans le filtre de ventilation de série.</p><p></p><p>L’affichage est limité à 10 ventilations. Pour en afficher plus de 10, vous devez utiliser plusieurs panneaux.</p> |
| Comment puis-je comparer des périodes ? | Pour comparer des périodes dans une seule visualisation, utilisez les ventilations des séries en faisant glisser au moins 2 périodes. Ces périodes remplacent alors la période du panneau. |
| Comment puis-je modifier le type de visualisation ? | <p></p><p>Ce panneau permet uniquement la visualisation des lignes pour la série temporelle.</p> |
| Puis-je exécuter la détection des anomalies ? | <p></p><p>Non. La détection des anomalies n’est pas disponible pour ce panneau.</p> |
