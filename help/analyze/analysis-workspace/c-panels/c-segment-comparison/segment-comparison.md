---
description: L’outil de comparaison des segments (Segment IQ) détecte les différences les plus importantes sur le plan statistique parmi un nombre illimité de segments par l’intermédiaire d’une analyse automatisée de chaque mesure et dimension auxquelles vous avez accès. Les principales caractéristiques des segments d’audience qui stimulent les indicateurs clés de performances de votre entreprise sont ainsi détectées et vous pouvez savoir de cette façon à quel point des segments se chevauchent.
keywords: Analysis Workspace ; Segment IQ
seo-description: L’outil de comparaison des segments (Segment IQ) détecte les différences les plus importantes sur le plan statistique parmi un nombre illimité de segments par l’intermédiaire d’une analyse automatisée de chaque mesure et dimension auxquelles vous avez accès. Les principales caractéristiques des segments d’audience qui stimulent les indicateurs clés de performances de votre entreprise sont ainsi détectées et vous pouvez savoir de cette façon à quel point des segments se chevauchent.
seo-title: Présentation de l'IQ Segment
solution: Analytics
title: Présentation de l'IQ Segment
topic: Reports and Analytics
uuid: 80 b 8343 a -8 e 09-4234-9510-1 eecce 18567 f
translation-type: tm+mt
source-git-commit: f5f5b294f503911108e1693b7c6cd128bee659c6

---


# Présentation de l'IQ Segment

L’outil de comparaison des segments (Segment IQ) détecte les différences les plus importantes sur le plan statistique parmi un nombre illimité de segments par l’intermédiaire d’une analyse automatisée de chaque mesure et dimension auxquelles vous avez accès. Les principales caractéristiques des segments d’audience qui stimulent les indicateurs clés de performances de votre entreprise sont ainsi détectées et vous pouvez savoir de cette façon à quel point des segments se chevauchent.

Il arrive que les analystes passent des heures, voire des jours, à rechercher des différences significatives entre des segments à l’échelle de vastes portions de mesures et de dimensions de l’entreprise. Cette analyse est fastidieuse et chronophage. En outre, il n’est pas impossible qu’une différence clé pour un segment soit omise, ce qui pourrait avoir de fortes répercussions sur vos efforts de marketing ciblé.

[Comparaison des segments sur YouTube](https://www.youtube.com/watch?v=fO3PNB93U_w&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&index=38) (4:46)

Voici quelques-uns des principaux nouveaux concepts, visualisations et tableaux introduits avec l’outil Comparaison des segments :

## “Everyone else” segment {#section_30AEE8181E5D46D9AB27F7CA3815D0CD}

Pour plus de commodité, nous avons ajouté le segment « tous les autres » afin que vous n'ayez pas à le créer manuellement. Par exemple, prenez l'audience Acheteurs. Il n'est pas nécessaire de créer un segment Non-acheteurs, puisqu'il est déjà inclus dans le segment « tous les autres » et qu'il peut être rapidement supprimé si vous préférez ajouter un autre segment à comparer.

## Size and overlap {#section_885A71EE458C43189A77B8F552CA346A}

La visualisation Taille et chevauchement illustre les tailles comparatives de chaque segment sélectionné et la façon dont ils se chevauchent les uns les autres. Pointez sur le visuel pour savoir combien de visiteurs se trouvent dans chaque section en intersection ou non. Cliquez avec le bouton droit de la souris sur l’intersection afin de créer un nouveau segment pour une analyse plus approfondie. Si deux segments ne se chevauchent pas (par exemple si vous utilisez le segment « tous les autres »), cela s'affiche également dans ce visuel.

![](assets/size-overlap.png)

## Population summaries {#section_21F2B66C60184A71B89E2982A6FB945D}

À droite du visuel Taille et croisement, l’outil Comparaison des segments présente le nombre total de visiteurs uniques dans chaque segment et la population dans l’intersection.

![](assets/population_summaries.png)

## Top metrics {#section_E4A38516424949B79A559DC8793071F2}

>[!NOTE]
>
>Les éléments de ligne appliqués après la comparaison des segments ne reçoivent pas de note de différence ; le tableau chargera uniquement les données de mesure pour les deux segments comparés.

Le tableau des mesures principales répertorie les mesures qui présentent statistiquement le plus de différences entre les deux segments que vous avez sélectionnés. Chaque ligne de ce tableau représente une mesure de différenciation, classée selon le degré de différence entre chaque segment. Les mesures sont également présentées par visiteur, ce qui signifie que si les visites sont présentées dans le tableau, les chiffres correspondants dans le tableau représentent le nombre moyen de visites par visiteur dans chaque segment. Nous proposons également un score de différence indiquant le degré de différence entre ces deux segments pour cette mesure. Un score de 1 représente une différence statistique élevée ; un score de 0 indique qu’il n’y a aucune différence statistique.

Pour en savoir plus sur le calcul des scores de différence de chaque tableau, voir [Tests statistiques utilisés dans la comparaison de segments](../../../../analyze/analysis-workspace/c-panels/c-segment-comparison/statistical-test.md#concept_0B6AC754EAED460283D4626983F838F4).

Le tableau Mesures principales fonctionne comme les autres tableaux d’Analysis Workspace. Vous pouvez faire glisser les mesures de votre choix dans le tableau pour les comparer.

Vous pouvez personnaliser le tableau à votre gré. Nous avons également ajouté une nouvelle icône Créer un visuel à chaque ligne du tableau. Cliquez sur cette icône pour créer un nouveau tableau et visuel au-dessus de l’outil Comparaison des segments, de sorte que le tableau des mesures principales ne soit pas trop chargé et que vous puissiez approfondir l’analyse dans un nouveau tableau. Si cette mesure n’est pas pertinente, cliquez sur la croix (X) pour la supprimer du tableau. Enfin, de même que dans les tableaux à structure libre, vous pouvez paginer la liste des mesures affichées ou afficher les 10, 20, 50, etc. principales mesures pour voir davantage que les cinq lignes par défaut.

![](assets/top-metrics.png)

Une visualisation liée se trouve à droite du tableau de mesures. Par défaut, l’outil Comparaison des segments présente les mesures principales dans le tableau par tendances au cours des 30 derniers jours de chaque segment. Pour visualiser une autre mesure trouvée dans le tableau Mesures principales, cliquez dessus pour la sélectionner ; la visualisation à droite se met à jour pour présenter la mesure sélectionnée.

![](assets/linked-viz.png)

## Top dimension items {#section_439C1782B153427CB4FB85E177146EC0}

>[!NOTE]
>
>Les éléments de ligne appliqués après la comparaison des segments ne reçoivent pas de note de différence ; le tableau chargera uniquement les données de mesure pour les deux segments comparés.

De même que le tableau des mesures principales, l’outil Comparaison des segments propose un tableau des principaux éléments de dimension qui illustre les éléments de dimensions les plus notables dans la différenciation par rapport à toutes vos dimensions. Chaque ligne présente le pourcentage de chaque segment exposant cet élément de dimension.

Si, par exemple, vous comparez le segment A au segment B, le tableau Principaux éléments de dimension peut indiquer que 100 % des visiteurs du segment A ont l’élément de dimension Type de navigateur : Google, tandis que 19,6 % du segment B seulement ont cet élément de dimension.

![](assets/top-dimension-item1.png)

À droite du tableau Principaux éléments de dimension, l’outil Comparaison des segments surligne le principal élément de dimension sélectionné, ainsi que les autres principaux éléments de dimension à partir de cette dimension utilisée pour la comparaison :

![](assets/top-dimension-item.png)

## Top segments table {#section_6A0C39F930564240AF7A157005C7A80B}

>[!NOTE]
>
>Les éléments de ligne appliqués après la comparaison des segments ne reçoivent pas de note de différence ; le tableau chargera uniquement les données de mesure pour les deux segments comparés.

Le tableau Principaux segments indique quels segments (autres que les deux segments sélectionnés pour la comparaison) chevauchent très distinctement les deux segments sélectionnés. Si, par exemple, vous comparez le segment A au segment B, le tableau Principaux segments peut présenter un troisième segment, Visiteurs récurrents, qui chevauche nettement le segment A mais pas le segment B.

![](assets/top-segments.png)

En outre, le segment supplémentaire qui se différencie le plus s’affiche dans un visuel de l’intersection à droite du tableau :

![](assets/segment-overlap.png)

Le visuel de l’intersection indique de manière graphique la différence de l’intersection entre les trois segments. De même que les autres visuels liés, cliquez sur chaque segment supplémentaire du tableau pour mettre à jour le visuel afin qu’il corresponde au segment sélectionné.

Cliquez ici pour en savoir plus sur les [tests statistiques](../../../../analyze/analysis-workspace/c-panels/c-segment-comparison/statistical-test.md#concept_0B6AC754EAED460283D4626983F838F4) utilisés dans la comparaison des segments.
