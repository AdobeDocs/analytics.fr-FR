---
title: FAQ sur les analyses inter-périphériques
description: Questions fréquentes sur les analyses inter-périphériques
translation-type: tm+mt
source-git-commit: c104fbda3dc4a6be6b596c60c6e1973407d94f80

---


# Questions fréquentes

**Comment utiliser CDA pour voir comment les visiteurs passent d'un type de périphérique à un autre ?**

Vous pouvez utiliser une visualisation Flux avec la dimension Type de périphérique mobile.

1. Connectez-vous à Adobe Analytics et créez un nouveau projet Workspace vide.
2. Cliquez sur l'onglet Visualisations à gauche, puis faites glisser une visualisation du flux sur la trame à droite.
3. Cliquez sur l'onglet Composants à gauche, puis faites glisser la dimension Type de périphérique mobile vers l'emplacement du centre intitulé Dimension ou Elément.
4. Ce rapport de flux est interactif. Cliquez sur l'une des valeurs pour développer les flux vers les pages suivantes ou précédentes. Utilisez le menu contextuel pour développer ou réduire les colonnes. Différentes dimensions peuvent également être utilisées dans le même rapport de flux.

**Puis-je voir comment les visiteurs se déplacent entre différentes expériences d'utilisateurs (navigateur de bureau par rapport au navigateur mobile par rapport à l'application mobile) ?**

L'utilisation de type de périphérique mobile comme illustré ci-dessus vous permet de voir comment les visiteurs se déplacent entre les types de périphériques mobiles et les types de périphériques de bureau. Cependant, vous pouvez distinguer les navigateurs de bureau des navigateurs mobiles. Pour ce faire, vous pouvez créer une evar qui enregistre si l'expérience s'est produite sur un navigateur de bureau, un navigateur mobile ou une application mobile. Créez ensuite un diagramme Flux comme décrit ci-dessus, à l'aide de votre evar « expérience » plutôt que de la dimension Type de périphérique mobile. Ceci fournit une vue légèrement différente sur le comportement inter-périphériques.

**Quel est le niveau de retour des visiteurs CDA ?**

* Adobe conserve les données d'assemblage des périphériques pendant 30 jours environ. Si un périphérique n'est pas identifié par le graphique Co-op ou le graphique privé, mais qu'il est identifié par la suite dans les 30 jours, CDA revient et redéclare ce périphérique comme appartenant à la personne identifiée jusqu'à 30 jours auparavant. Si le comportement non identifié d'un utilisateur est hors de la fenêtre de recherche de 30 jours, cette partie du parcours de l'utilisateur n'est pas assemblée.
* Adobe conserve les correspondances de périphériques dans le graphique Co-op et le graphique privé pendant 6 mois environ. Un ECID sans activité pendant plus de six mois est supprimé du graphique. Les données déjà assemblées dans CDA n'ont pas d'incidence, mais les accès suivants pour cet ECID sont traités comme une nouvelle personne.

**Comment CDA gère-t-il les accès horodatés ?**

Adobe traite les accès horodatés comme s'ils étaient reçus au moment de l'horodatage, et non lorsqu'Adobe avait reçu l'accès. Les accès horodatés plus anciens qu'un mois ne peuvent pas être assemblés car ils sont considérés en dehors de la plage Adobe et les données utilisées pour l'assemblage sont conservées.
