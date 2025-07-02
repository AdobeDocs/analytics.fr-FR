---
description: Découvrez comment identifier les anomalies statistiques à l’aide de techniques de détection des anomalies.
title: Techniques Statistiques Utilisées Pour La Détection Des Anomalies
feature: Anomaly Detection
role: User, Admin
exl-id: e9868296-e453-45ec-b874-b2aa1b37a1bf
source-git-commit: 24dd47e995523aedba1385ee8882af5e11c7b128
workflow-type: tm+mt
source-wordcount: '1080'
ht-degree: 70%

---

# Techniques statistiques

Dans Analysis Workspace, la détection des anomalies applique différentes techniques statistiques avancées afin de déterminer si une observation doit être considérée comme anormale.

Selon la granularité de date du rapport, trois différentes techniques statistiques sont utilisées, en particulier pour la détection des anomalies horaire, quotidienne, hebdomadaire ou mensuelle. Chacune de ces techniques statistiques est décrite ci-dessous.

## Détection des anomalies avec une granularité quotidienne

Dans les rapports avec une granularité quotidienne, l’algorithme prend en compte plusieurs facteurs importants afin de produire les résultats les plus exacts possible. Tout d’abord, l’algorithme détermine le type de modèle à appliquer en fonction des données disponibles pour lesquelles l’algorithme sélectionne l’une des deux classes : un modèle basé sur une série temporelle ou un modèle de détection d’aberrations (appelé filtrage fonctionnel).

La sélection du modèle de série temporelle repose sur les combinaisons suivantes de type d’erreur, de tendance et de caractère saisonnier, comme décrit par [Hyndman et al. (2008)](https://link.springer.com/book/10.1007/978-3-540-71918-2). Plus particulièrement, l’algorithme tente les combinaisons suivantes :

1. Erreur additive, aucune tendance, caractère saisonnier additif (ANA)
1. Erreur additive, tendance additive, caractère saisonnier additif (AAA)
1. Erreur multiplicative, aucune tendance, caractère saisonnier multiplicatif (MNM)
1. Erreur multiplicative, aucune tendance, caractère saisonnier additif (MNA)
1. Erreur additive, tendance additive, aucun caractère saisonnier (AAN)

L&#39;algorithme teste l&#39;adéquation de chacune des combinaisons en sélectionnant celle qui présente la meilleure erreur moyenne absolue en pourcentage (EMPA). Toutefois, le filtrage fonctionnel est appliqué si l’erreur en pourcentage absolu de la moyenne du meilleur modèle de série temporelle est supérieure à 15 %. En règle générale, les données à haut degré de répétition (par exemple, semaine par semaine ou mois par mois) sont les mieux adaptées à un modèle de série temporelle.

Une fois le modèle sélectionné, l’algorithme adapte les résultats en fonction des jours fériés et du caractère saisonnier d’un exercice à l’autre. En ce qui concerne les jours fériés, l’algorithme vérifie si les jours fériés suivants sont présents dans la période de création de rapports :

* Jour du Souvenir (États-Unis)
* 4 juillet (États-Unis)
* Thanksgiving (États-Unis)
* Black Friday (États-Unis)
* Cyber Monday (États-Unis)
* 24-26 décembre
* Janvier 1
* 31 décembre

Ces jours fériés ont été choisis en fonction d’une analyse statistique approfondie de nombreux points de données de clients afin d’identifier les jours fériés les plus importants pour le plus grand nombre de groupes de tendances des clients. Bien que la liste ne soit certainement pas exhaustive pour tous les clients ou cycles économiques, l’application de ces jours fériés améliore considérablement les performances de l’algorithme dans son ensemble pour presque tous les jeux de données des clients.

Une fois le modèle sélectionné et les jours fériés identifiés dans la période de création des rapports, l’algorithme s’exécute comme suit :

1. Créez la période de référence des anomalies. Cette période comprend jusqu’à 35 jours avant la période de création des rapports, ainsi qu’une période correspondante un an auparavant. Et tient compte des jours bissextiles lorsque cela est nécessaire et inclut tous les jours fériés applicables qui peuvent avoir eu lieu un autre jour civil de l’année précédente.
1. Vérifie si les jours fériés de la période actuelle (à l’exclusion de l’année précédente) sont anormaux en fonction des données les plus récentes.
1. Si le jour férié dans la période actuelle est anormal, adapte la valeur attendue et l’intervalle de confiance du jour férié actuel étant donné le jour férié de l’année précédente (avec une marge de deux jours avant et après). La correction des jours fériés actuels repose sur l’erreur en pourcentage absolu de la moyenne la plus faible de :

   1. Effets additifs
   1. Effets multiplicatifs
   1. Différence d’une année sur l’autre

Dans l’exemple suivant, observez l’amélioration drastique des performances le jour de Noël et du Nouvel An :

![](assets/anomaly_statistics.png)

## Détection des anomalies avec une granularité horaire

Pour les données horaires, on applique le même algorithme de série temporelle qu’avec l’algorithme de granularité quotidienne. Toutefois, il repose principalement sur deux modèles de tendance : un cycle de 24 heures ainsi qu’un cycle week-end/jour de semaine. Afin de capturer ces deux effets saisonniers, l’algorithme horaire crée deux modèles distincts (week-end et jour de semaine) en appliquant la même approche que celle décrite ci-dessus.

Le créneau de formation des tendances horaires repose sur un intervalle de recherche en amont de 336 heures.

## Détection des anomalies avec une granularité horaire ou mensuelle

Les tendances hebdomadaires et mensuelles diffèrent des tendances hebdomadaires ou quotidiennes déterminées avec une granularité quotidienne ou horaire, de sorte qu’un algorithme distinct est appliqué. Pour les tests hebdomadaires et mensuels, une approche de détection des valeurs aberrantes en deux étapes est connue sous le nom de test de déviation généralisée extrémiste et identifiée (DGSE). Ce test tient compte du nombre maximum d’anomalies attendues combiné à l’approche ajustée de diagrammes en boîte (méthode non paramétrique de détection des valeurs aberrantes) afin de déterminer le nombre maximum de valeurs aberrantes. Les deux étapes sont les suivantes :

1. Fonction ajustée de diagrammes en boîte : détermine le nombre maximum d’anomalies étant donné les données d’entrée.
1. Fonction GESD : appliquée aux données d’entrée avec le résultat de l’étape 1.

L’étape de détection des anomalies de saisonnalité des vacances et de la période YoY soustrait ensuite les données de l’année dernière des données de cette année. Il effectue ensuite une nouvelle itération sur les données à l’aide du processus en deux étapes ci-dessus pour vérifier que les anomalies sont appropriées pour la saison. Chacune de ces granularités de date utilise une recherche en amont de 15 périodes, y compris la période de création de rapports sélectionnée (15 mois ou 15 semaines) et une période correspondante un an auparavant pour la formation.

## Techniques statistiques de l’analyse des contributions

L’analyse des contributions est un processus intensif de machine learning, conçu pour déterminer quels facteurs sont à l’origine d’une anomalie observée dans Adobe Analytics. Elle permet à l’utilisateur de repérer, bien plus rapidement qu’il ne serait normalement possible, les opportunités ou les centres d’intérêt justifiant une analyse supplémentaire.

L’analyse des contributions exécute un algorithme en deux parties pour chaque élément de dimension disponible pour le rapport Analyse des contributions de l’utilisateur ou de l’utilisatrice. L’algorithme s’exécute dans cet ordre :

1. Pour chaque dimension, il calcule le V de Cramer. Dans l’exemple suivant, on utilise une table de contingence avec les pages vues par pays au cours de deux périodes :

   ![](assets/contingency_table.png)

   Dans le tableau 1, la valeur V de Cramer peut être utilisée pour mesurer l’association entre les pages vues par les pays pour la période 1 (par exemple, historique) et la période 2 (par exemple, le jour où l’anomalie se produit). Une valeur faible implique un faible niveau de l’association. Le V de Cramer est compris entre 0 (aucune association) et 1 (association terminée). Le V de Cramer peut être calculé comme suit :

   ![](assets/cramers-v.png)

1. Pour chaque élément de dimension, le résidu de Pearson sert à mesurer l’association entre la mesure anormale et chaque élément de dimension. Le résiduel par personne applique une distribution normale standard, ce qui permet à l’algorithme de comparer cette valeur pour deux variables aléatoires même si l’écart n’est pas comparable. En pratique, l’erreur est indéterminée et est estimée en appliquant une correction d’échantillonnage finie.

   Dans l’exemple précédent du tableau 1, la RP, avec correction d’échantillon finie pour le pays i et la période 2, est donnée par

   ![](assets/persons-residual.png)

   où

   ![](assets/pr-example.png)

   (Une formule similaire peut être obtenue pour la période 1.)

   Afin de calculer les résultats finaux, le score pour chaque élément de dimension est ensuite pondéré par le V de Cramer et remis à l’échelle en fonction d’un facteur compris entre 0 et 1 afin de générer le score de contribution.
