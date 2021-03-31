---
description: Questions fréquentes sur l’installation, la configuration et l’utilisation de fonctionnalités dans Activity Map.
title: Questions fréquentes sur Activity Map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
feature: Activity Map
role: Professionnel, Administrateur
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 25%

---


# Questions fréquentes sur Activity Map

Questions fréquentes sur l’installation, la configuration et l’utilisation de fonctionnalités dans Activity Map.

## Tous les clients Analytics ont-ils accès à la page d’activation de Carte d’activités des outils d’administration ?

Les entreprises ayant un contrat pour Adobe Analytics Standard, Premium et Ultimate ont accès au Activity Map.

## Le Activity Map fournit-il des données sur les &quot;vues&quot; ?

Non, l’Adobe ne suit pas les liens qui ont été consultés.

## Quels navigateurs et versions le Activity Map prend-il en charge ?

Activity Map prend en charge la dernière version de la plupart des navigateurs modernes.

## Le Activity Map augmente-t-il les appels au serveur ?

Le Activity Map n&#39;envoie pas d&#39;appels serveur en lui-même. En revanche, les variables de données contextuelles du Activity Map sont incluses dans les appels de vue de page Analytics sur la page suivante.

## Pourquoi certaines incrustations d’éléments classés sont-elles manquantes ?**

Certains liens avec classement, tels que les liens de sous-menu, sont masqués dans la page. Par conséquent, les incrustations de liens correspondantes ne s’affichent pas. Le classement est calculé pour tous les liens de la page, y compris les liens masqués.

## Comment le classement des liens est-il déterminé dans le rapport Tous les liens ?**

* **En mode** Dégradé et Bulle : Le classement est déterminé par la colonne de mesures. Pour les liens disposant de la même valeur de mesure, le classement est déterminé selon l’ordre alphabétique des ID de lien.
* **En mode** gagnant et perdant : Le classement est principalement déterminé par la colonne % Gain. Pour les liens avec le même gain, le classement est basé davantage sur l’ordre alphabétique de l’ID de lien.

## Comment le Activity Map fonctionne-t-il avec les pages qui utilisent plusieurs suites de rapports ?

Par défaut, le Activity Map utilise la suite de rapports associée à la première balise envoyée par la page. Vous pouvez sélectionner une suite de rapports balisée différente dans l’onglet **[!UICONTROL Paramètres d’Activity Map]** > **[!UICONTROL Autres]**.

## Combien de temps le Activity Map recherche-t-il Adobe Analytics sur la page ?

La carte de l’Activité recherche la présence d’Adobe Analytics pendant 20 secondes au maximum après un événement de fin de page.

## Comment le Activity Map gère-t-il le contenu dynamique ?

Le Activity Map vérifie toutes les 2 secondes si l’état de la page Web a changé, par exemple :

* le contenu HTML devenu visible ;
* le contenu HTML masqué ;
* le nouveau contenu HTML injecté.

Si le contenu est masqué ou visible, l’application modifie automatiquement l’état des liens affectés (et donc des superpositions) de masqué à visible ou de visible à masqué. Si du nouveau contenu est injecté, l’application récupère les liens associés, extrait les données d’analyse correspondantes et ajoute des superpositions pour ces liens.

## Sur quelle mesure le rapport Flux de page repose-t-il ?

Toutes les données affichées sont basées sur les vues de page.

## Puis-je exporter des variables de données contextuelles Activity Map par le biais de flux de données ?

Les variables de données contextuelles de mappage d’Activités ne sont pas disponibles dans les flux de données.

## Les segments fonctionnent-ils en mode réel ?

Non, les segments ne fonctionnent pas en mode réel. Cette fonctionnalité est équivalente à celle du rapports en temps réel dans les rapports et analyses, qui ne prend pas en charge la segmentation.

## Le Activity Map est-il compatible avec les suites de rapports virtuelles ?

Oui. Cependant, en raison des limitations des suites de rapports virtuelles, le mode réel d’Activity Map n’est pas compatible avec celles-ci.
