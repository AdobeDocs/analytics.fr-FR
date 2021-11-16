---
title: Panneau Durée de lecture des médias
description: Comment utiliser et interpréter le panneau Durée de lecture des médias dans Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: null
source-git-commit: 6347601c5c1b8e84f37db308717799dea43bd26d
workflow-type: tm+mt
source-wordcount: '989'
ht-degree: 99%

---

# Panneau Durée de lecture des médias

Les clients Media Analytics peuvent analyser la durée de la lecture pour déterminer où sʼest produit le pic dʼaccès simultanés ou à quel moment des abandons ont eu lieu. Cela permet de mieux comprendre la qualité du contenu et lʼengagement des observateurs, et contribue également à résoudre les problèmes ou à planifier le volume ou lʼéchelle.

Voici un aperçu vidéo du panneau :

>[!VIDEO](https://video.tv.adobe.com/v/338699/?quality=12&learn=on)

Dans Analysis Workspace, la Durée de lecture est le temps passé à visionner vos flux multimédia à un moment donné. Elle comprend la mise en pause, la mise en mémoire tampon et le temps jusquʼau démarrage.

Le panneau Durée de lecture des médias permet dʼanalyser la lecture au fil du temps. Il fournit également des informations détaillées sur le pic dʼaccès simultanés et la possibilité de ventiler et de comparer. Pour accéder au panneau Durée de lecture des médias, naviguez vers une suite de rapports dans laquelle les composants Media Analytics sont activés. Cliquez ensuite sur l’icône du panneau située à l’extrémité gauche et faites glisser le panneau dans votre projet Analysis Workspace.

Ce panneau comprend également de nouvelles fonctionnalités de calendrier qui permettent de sélectionner et dʼafficher moins de 24 heures. Vous pouvez appliquer cette nouvelle fonctionnalité à lʼensemble du panneau, ou créer des segments de périodes consécutives, afin de pouvoir suivre les délais dʼentrée/sortie des observateurs sur lʼensemble des programmes ou sections de programmes. Une fois que vous avez placé au moins deux de ces segments de date, une case dʼoption apparaît pour lʼAffichage de la séquence de dates. Deux choix sʼoffrent à vous : la superposition des lignes avec un point de départ commun sur lʼaxe X, ou leur affichage de manière séquentielle avec leur point de départ spécifique sur lʼaxe X.

## Entrées de panneau {#Input}

Vous pouvez configurer le panneau Durée de lecture des médias à lʼaide des paramètres dʼentrée suivants :

| Paramètre | Description |
|---|---|
| Période du panneau | La période par défaut du panneau est définie sur Aujourd’hui. Vous pouvez la modifier pour afficher un seul jour ou plusieurs mois à la fois.<br>La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes). Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
| Granularité | La granularité par défaut est définie sur Minute.<br>La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes). Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la période complète. |
| Synthèse des chiffres des panneaux | Pour afficher les détails de date ou dʼheure relatifs à la durée de la lecture, une synthèse des chiffres est disponible. La valeur maximale affiche les détails concernant le pic d’accès simultanés. La valeur minimale affiche les détails du creux. La somme additionne la durée de lecture totale de la sélection. Le panneau nʼindique par défaut que la valeur maximale, mais vous pouvez modifier cette valeur par défaut et afficher la valeur minimale, la valeur totale ou une combinaison des trois valeurs.<br>Si vous utilisez des ventilations, une synthèse des chiffres s’affiche pour chacune d’elles. |
| Ventilations de la série | Vous pouvez éventuellement ventiler votre visualisation par segments, dimensions, éléments de dimension ou périodes.<p>- Vous pouvez afficher jusqu’à 10 lignes à la fois. Les ventilations sont limitées à un seul niveau.</p><p>- Lorsque vous faites glisser une dimension, les principaux éléments de dimension sont automatiquement sélectionnés en fonction de la période du panneau sélectionnée.</p>- Pour comparer des périodes, faites glisser deux périodes ou plus dans le filtre de ventilation de la série. |
| Format de l’heure | Vous pouvez afficher la durée de lecture en heures:Minutes:secondes (par défaut) ou en minutes (sʼaffiche en nombres entiers, arrondis à 0,5). |
| Affichage de la séquence de dates | Si vous avez placé au moins deux segments de période en tant que ventilations de série, lʼoption permettant de sélectionner superposition (par défaut) ou séquentiel sʼaffiche. La superposition affiche les lignes avec un point de départ commun sur lʼaxe X afin quʼelles se déroulent en parallèle. Séquentiel affiche les lignes avec leur point de départ spécifique sur lʼaxe X. Si les données se suivent (par exemple, le segment 1 se termine à 20 h 44 et le segment 2 à 20 h 45), les lignes sʼaffichent de manière séquentielle. |

### Affichage par défaut

![Affichage par défaut](assets/mpts_default_view.png)

## Sortie de panneau {#Output}

Le panneau Durée de lecture des médias renvoie un graphique en courbes et des numéros de synthèse, qui incluent des détails sur la durée maximale, minimale et/ou totale de la lecture. En haut du panneau, une ligne de résumé vous rappelle les paramètres du panneau que vous avez sélectionnés.

À tout moment, vous pouvez modifier et recréer le panneau en cliquant sur l’icône de modification en forme de crayon dans le coin supérieur droit.

Si vous avez sélectionné la ventilation des séries, une ligne du graphique en courbe et une synthèse des chiffres s’affichent pour chacune d’elles :

![sortie de durée de lecture des médias](assets/mpts_outputs1.png)

### Source de données

La seule mesure pouvant être utilisée dans ce panneau est Durée de la lecture.

| Mesure | Description |
|---|---|
| Durée de la lecture | Nombre total dʼheures:minutes:secondes (ou minutes) de contenu affiché lors de la granularité sélectionnée, y compris la mise en pause, la mise en mémoire tampon et le temps de démarrage. |

## Questions fréquentes {#FAQ}

| Question | Réponse |
|---|---|
| Où se trouve le tableau à structure libre ? Comment puis-je voir la source de données ? | <p></p><p>Le tableau à structure libre n’est pas disponible dans cet affichage. Vous pouvez télécharger la source de données en effectuant un clic droit sur le graphique en courbes et en téléchargeant le fichier CSV.</p> |
| <p>Pourquoi ma granularité a-t-elle changé ?</p> | <p>La visualisation est limitée à 1 440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes). Si une combinaison de période et de granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à l’intégralité de la période.</p><p></p><p>Lorsque vous passez d’une période plus grande à une période plus petite, la granularité est mise à jour vers le détail le plus bas possible une fois la période modifiée. Pour afficher une granularité plus élevée, modifiez le panneau et recréez la visualisation.</p> |
| <p></p><p>Comment puis-je comparer les noms de vidéo, les segments, les types de contenu, etc. ?</p> | <p>Pour les comparer dans une visualisation unique, faites glisser des segments, des dimensions ou des éléments de dimension spécifiques dans le filtre de ventilation des séries.</p><p></p><p>L’affichage est limité à 10 ventilations. Pour en afficher plus de 10, vous devez utiliser plusieurs panneaux.</p> |
| Comment puis-je comparer des périodes ? | Pour comparer des périodes dans une seule visualisation, utilisez les ventilations des séries en faisant glisser au moins 2 périodes. Ces périodes remplacent alors la période du panneau. |
| Comment puis-je modifier le type de visualisation ? | <p></p><p>Ce panneau permet uniquement la visualisation des lignes pour la série temporelle.</p> |
| Puis-je exécuter la détection des anomalies ? | <p></p><p>Non. La détection des anomalies n’est pas disponible pour ce panneau.</p> |
