---
title: Panneau Visionneuses simultanées
description: Utilisation et interprétation du panneau Visionneuses simultanées dans Analysis Workspace.
translation-type: tm+mt
source-git-commit: 807c5e31b376799f4494ecc24cebfd9498c39e63
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 9%

---


# Panneau Visionneuses simultanées

>[!IMPORTANT]
>
>Cette fonctionnalité est en cours de déploiement échelonné pour les clients Media Analytics.

Les clients Media Analytics peuvent analyser les visionneuses simultanées pour déterminer où s’est produit un pic d’accès simultané ou où des abandons se sont produits afin de fournir des informations précieuses sur la qualité du contenu et l’engagement des visiteurs, ainsi que pour vous aider à résoudre les problèmes ou à planifier le volume ou l’échelle.

En Analysis Workspace, les visionneuses simultanées représentent le nombre de visiteurs uniques qui visualisent vos flux de médias à un moment donné, quel que soit le nombre de sessions.

Le panneau Visionneuses simultanées de médias permet l’analyse de visionneuses simultanées au fil du temps, avec des informations détaillées sur la simultanéité maximale et la possibilité de ventiler et de comparer.  Pour accéder au panneau Visionneuses de contenu simultané multimédia, accédez à une suite de rapports dans laquelle les composants Media Analytics sont activés. Cliquez ensuite sur l’icône de panneau située à l’extrême gauche et faites glisser le panneau dans votre projet Analysis Workspace.

## Entrées de panneau {#Input}

Vous pouvez configurer le panneau Visionneuses de contenu multimédia simultané à l’aide des paramètres d’entrée suivants :

| Paramètre | Description |
|---|---|
| Période du panneau | La plage de dates du panneau par défaut est Aujourd’hui.  Vous pouvez le modifier en vue un seul jour ou plusieurs mois à la fois. <br> <br> La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes).  Si une combinaison plage de dates et granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la plage complète de dates. |
| Granularité | La granularité par défaut est Minute. <br> <br>La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes).  Si une combinaison plage de dates et granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la plage complète de dates. |
| Synthèse des chiffres des panneaux | Pour afficher les détails sur la date ou l’heure des visionneuses simultanées, un numéro de résumé est disponible. Le paramètre Maximum affiche les détails concernant la concurrence maximale. La valeur minimale affiche les détails du creux.  Le panneau par défaut affiche Maximum uniquement, mais vous pouvez le modifier pour afficher Minimum ou Maximum et Minimum.<br><br>Si vous utilisez des ventilations, un numéro de résumé s’affiche pour chacune d’elles. |
| Ventilation des séries | Vous pouvez éventuellement ventiler votre visualisation par segments, dimensions, éléments de dimension ou plages de dates. <br><br>- Vous pouvez vue jusqu&#39;à 10 lignes à la fois. Les ventilations sont limitées à un seul niveau.<br><br>- Lorsque vous faites glisser une dimension, les principaux éléments de dimension sont automatiquement sélectionnés en fonction de la plage de dates du panneau sélectionné.<br><br>- Pour comparer des plages de dates, faites glisser 2 plages de dates ou plus dans le filtre de ventilation des séries. |

### Vue par défaut

![Vue par défaut](assets/concurrent-viewers-default.png)


### Vue de ventilation des séries

![vue de ventilation des séries](assets/concurrent-viewers-series-breakdown.png)

## Sortie de panneau {#Output}

Le panneau Visionneuses simultanées de médias renvoie un graphique en courbes et des chiffres de synthèse pour inclure des détails sur les visionneuses simultanées maximales et/ou minimales.  En haut du panneau, une ligne de résumé vous rappelle les paramètres du panneau que vous avez sélectionnés.

A tout moment, vous pouvez modifier et recréer le panneau en cliquant sur le crayon de modification en haut à droite.

Si vous avez sélectionné la ventilation par série, une ligne du graphique en courbes et un numéro de synthèse s’affichent pour chacun d’eux :

![sortie de visionneuses simultanées](assets/concurrent-viewers-output.png)

### Source de données

La seule mesure qui peut être utilisée dans ce panneau est Visionneuses simultanées :

| Mesure | Description |
|---|---|
| Nombre de viewers simultanés | Nombre de visiteurs uniques qui visualisent vos flux de médias à un moment donné, quel que soit le nombre de sessions.<br><br>Il s’agit d’un rapports différent de celui de la visionneuse simultanée dans la section Rapports, qui utilise les sessions Principales simultanées.  L’utilisation de comptes de visiteurs uniques permet de supprimer les &quot;pics&quot; indésirables aux limites de l’affichage (où les sessions se terminent et commencent en même temps). |

Un tableau à structure libre n’est pas disponible dans cette vue.  Pour vue de la source de données, vous pouvez cliquer avec le bouton droit de la souris sur le graphique en courbes et télécharger le fichier au format .csv.  Les ventilations de série seront incluses.


![sortie de visionneuses simultanées](assets/concurrent-viewers-download-csv.png)

## Questions fréquentes {#FAQ}

| Question | Réponse |
|---|---|
| Où se trouve le tableau à structure libre ? Comment puis-je voir la source de données ? | Le tableau à structure libre n’est pas disponible dans cette vue.  Vous pouvez télécharger la source de données en cliquant avec le bouton droit sur le graphique en courbes et en téléchargeant le fichier CSV. |
| Pourquoi ma granularité a-t-elle changé ? | La visualisation est limitée à 1440 lignes de données (par exemple, 24 heures à une granularité au niveau des minutes).  Si une combinaison plage de dates et granularité génère plus de 1 440 lignes, la granularité est automatiquement mise à jour pour s’adapter à la plage complète de dates.<br><br>Lorsque vous passez d’une plage de dates plus grande à une plage de dates plus petite, la granularité est mise à jour vers le détail le plus bas possible une fois la plage modifiée. Pour vue d’une granularité plus élevée, modifiez le panneau et recréez-le. |
| Comment comparer les noms de vidéo, les segments, les types de contenu, etc. ? | Pour les comparer dans une visualisation unique, faites glisser des segments, des dimensions ou des éléments de dimension spécifiques dans le filtre de ventilation de série.<br><br>La vue est limitée à 10 ventilations.  Pour vue plus de 10, vous devez utiliser plusieurs panneaux. |
| Comment comparer des plages de dates ? | Pour comparer des plages de dates dans une seule visualisation, utilisez les ventilations de série en faisant glisser au moins 2 plages de dates.  Ces plages de dates remplaceront la plage de dates du panneau. |
| Comment puis-je modifier le type de visualisation ? | Ce panneau permet uniquement la visualisation des lignes pour la série chronologique. |
| Puis-je exécuter la détection des anomalies ? | Non.  La détection des anomalies n’est pas disponible pour ce panneau. |
| Pourquoi utiliser des visiteurs uniques plutôt que des sessions principales ? | L’utilisation de visiteurs uniques permet de supprimer les pics indésirables aux limites d’affichage (où les sessions se terminent et commencent simultanément). |
| Qu’est-ce que cela signifie d’avoir des visionneuses simultanées avec une granularité supérieure à la minute ? | Avec une granularité supérieure à une minute, les visionneuses simultanées représentent la somme des visionneuses simultanées uniques pour toutes les minutes de cette période.  Par exemple, les visionneuses simultanées de granularité au niveau de l’heure représentent la somme des visionneuses simultanées uniques pour toutes les minutes de l’heure. |
| Que se passe-t-il si je souhaite afficher plus d’un jour avec la granularité au niveau de la minute ? | Pour accéder aux données avec une granularité de niveau minute pendant un maximum de 1 mois à la fois, vous pouvez utiliser l’API du Rapports Analytics (2.0 ou 1.4). Pour plus d’informations sur les API Analytics, consultez le Guide [de l’utilisateur des rapports API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-guide.md)Analytics. |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->
