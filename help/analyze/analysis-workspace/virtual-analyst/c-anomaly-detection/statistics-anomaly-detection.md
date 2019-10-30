---
description: Dans Analysis Workspace, la détection des anomalies applique différentes techniques statistiques avancées afin de déterminer si une observation doit être considérée comme anormale.
seo-description: Dans Analysis Workspace, la détection des anomalies applique différentes techniques statistiques avancées afin de déterminer si une observation doit être considérée comme anormale.
seo-title: Techniques statistiques de la détection des anomalies
title: Techniques statistiques de la détection des anomalies
uuid: b6ef6a2e-0836-4c9a-bf7e-01910199bb92
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Techniques statistiques de la détection des anomalies

Dans Analysis Workspace, la détection des anomalies applique différentes techniques statistiques avancées afin de déterminer si une observation doit être considérée comme anormale.

Selon la granularité de date utilisée dans le rapport, trois techniques statistiques différentes sont utilisées, en particulier pour la détection des anomalies horaire, quotidienne, hebdomadaire ou mensuelle. Chacune de ces techniques statistiques est décrite ci-dessous.

## Anomaly detection for daily granularity {#section_758ACA3C0A6B4D399563ECABFB8316FA}

Dans les rapports avec une granularité quotidienne, l’algorithme prend en compte plusieurs facteurs importants afin de produire les résultats les plus exacts possibles. Tout d’abord, l’algorithme détermine le type de modèle à appliquer en fonction des données disponibles dont nous sélectionnons l’une des deux classes : un modèle basé sur les séries chronologiques ou un modèle de détection des valeurs aberrantes (appelé filtrage fonctionnel).

Le modèle de série chronologique repose sur les combinaisons suivantes de type d’erreur, de tendance et de caractère saisonnier, comme décrit par [Hyndman et al. (2008)](https://www.springer.com/us/book/9783540719168). Plus particulièrement, l’algorithme tente les combinaisons suivantes :

1. Erreur additive, aucune tendance, caractère saisonnier additif (ANA)
1. Erreur additive, tendance additive, caractère saisonnier additif (AAA)
1. Erreur multiplicative, aucune tendance, caractère saisonnier multiplicatif (MNM)
1. Erreur multiplicative, aucune tendance, caractère saisonnier additif (MNA)
1. Erreur additive, tendance additive, aucun caractère saisonnier (AAN)

L’algorithme teste l’adéquation de chacune de ces combinaisons en sélectionnant celle qui génère la meilleure erreur en pourcentage absolu de la moyenne. Toutefois, le filtrage fonctionnel est appliqué si l’erreur en pourcentage absolu de la moyenne du meilleur modèle de série chronologique est supérieure à 15 %. En général, les données présentant un degré de répétition élevé (par ex. semaine après semaine ou mois après mois) sont mieux adaptées à un modèle de série chronologique.

Une fois le modèle sélectionné, l’algorithme adapte les résultats en fonction des jours fériés et du caractère saisonnier d’un exercice à l’autre. En ce qui concerne les jours fériés, l’algorithme vérifie si les jours fériés suivants sont présents dans la période de création de rapports :

* Jour du Souvenir (États-Unis)
* 4 juillet (États-Unis)
* Thanksgiving (États-Unis)
* Black Friday (États-Unis)
* Cyber Monday (États-Unis)
* 24-26 décembre
* 1er janvier
* 31 décembre

Ces jours fériés ont été sélectionnés sur la base d'une analyse statistique approfondie sur de nombreux points de données clients afin d'identifier les jours fériés qui importaient le plus au plus grand nombre de tendances des clients. Bien que la liste ne soit certainement pas exhaustive pour tous les clients ou cycles économiques, nous avons constaté que l’application de ces jours fériés améliorait considérablement les performances globales de l’algorithme pour presque tous les jeux de données des clients.

Une fois le modèle sélectionné et les jours fériés identifiés dans la période de création des rapports, l’algorithme s’exécute comme suit :

1. Construisez la période de référence de l'anomalie : cela inclut jusqu'à 35 jours avant la période du rapport et une période correspondante 1 an avant (en tenant compte des jours bissextiles au besoin et des jours fériés applicables qui peuvent avoir eu lieu un jour calendaire différent l'année précédente).
1. Vérifiez si les jours fériés de la période actuelle (à l’exclusion de l’année précédente) sont anormaux en fonction des données les plus récentes.
1. Si le jour férié de la période actuelle est anormal, ajustez la valeur attendue et l’intervalle de confiance du jour férié actuel en fonction du jour férié de l’année précédente (en tenant compte des deux jours précédant et suivant). La correction des jours fériés actuels repose sur l’erreur en pourcentage absolu de la moyenne la plus faible de :

   1. Effets additifs
   1. Effets multiplicatifs
   1. Différence d’une année sur l’autre

Remarquez l'amélioration spectaculaire des performances le jour de Noël et le jour de l'an dans l'exemple suivant :

![](assets/anomaly_statistics.png)

## Anomaly detection for hourly granularity {#section_014C9E9209AF43F8A03D5D46E3B3AEE7}

Pour les données horaires, on applique le même algorithme de série chronologique qu’avec l’algorithme de granularité quotidienne. Toutefois, il repose principalement sur deux modèles de tendance : un cycle de 24 heures ainsi qu’un cycle week-end/jour de semaine. Afin de capturer ces deux effets saisonniers, l’algorithme horaire crée deux modèles distincts (week-end et jour de semaine) en appliquant la même approche que celle décrite ci-dessus.

Le créneau de formation des tendances horaires repose sur un intervalle de recherche en amont de 336 heures.

## Anomaly detection for weekly and monthly granularities {#section_5D421576BFBC4B24A58DFCC0A6407545}

Les tendances hebdomadaires et mensuelles diffèrent des tendances hebdomadaires ou quotidiennes déterminées avec une granularité quotidienne ou horaire, de sorte qu’un algorithme distinct est appliqué. Pour les tendances hebdomadaires et mensuelles, une approche en deux étapes de détection des valeurs aberrantes est appliquée, connue sous le nom de test GESD (Generalized Extreme Studentized Deviate). Ce test tient compte du nombre maximum d’anomalies attendues combiné à l’approche ajustée de diagrammes en boîte (méthode non paramétrique de détection des valeurs aberrantes) afin de déterminer le nombre maximum de valeurs aberrantes. Les deux étapes sont les suivantes :

1. Fonction ajustée de diagrammes en boîte : détermine le nombre maximum d’anomalies étant donné les données d’entrée.
1. Fonction GESD : appliquée aux données d’entrée avec le résultat de l’étape 1.

L'étape de détection des anomalies saisonnières des fêtes et de l'année 2009 soustrait ensuite les données de l'année dernière des données de cette année, puis réitère les données en utilisant le processus en deux étapes ci-dessus pour vérifier que les anomalies sont appropriées sur le plan saisonnier. Chacune de ces granularités de date utilise une recherche en amont de 15 périodes, y compris la période de création de rapports sélectionnée (15 mois ou 15 semaines) et une période correspondante un an auparavant pour la formation.
