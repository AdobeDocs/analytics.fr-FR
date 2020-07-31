---
description: FAQ sur Workspace
title: Questions fréquentes et résolution des problèmes dans Workspace
translation-type: ht
source-git-commit: 7fbeac0488fbe9b3d10d7c1242f31250f1c7dc16
workflow-type: ht
source-wordcount: '541'
ht-degree: 100%

---


# Questions fréquentes

| Question | Réponse |
|--- |--- |
| Quelles sont les conditions préalables à l’utilisation d’Analysis Workspace ? | [Envoyer des données à Adobe Analytics à l’aide d’Adobe Experience Platform Launch](/help/implement/launch/validate-publish-prod.md) : l’utilisation d’Analysis Workspace nécessite une implémentation efficace. Assurez-vous que votre entreprise envoie les données à Adobe avant d’utiliser l’outil. D’autres implémentations, telles que la gestion dynamique des balises ou les implémentations manuelles héritées, peuvent également fonctionner. |
| Quelles sont les exigences en matière d’administration et d’accès concernant Analysis Workspace ? | Voir [Configuration requise pour l’administration](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| L’utilisation d’Analysis Workspace aura-t-elle une incidence sur la collecte des données ? | Analysis Workspace étant un outil de reporting, il n’a aucun impact sur la collecte de données. Il n’y a aucune répercussion si vous faites glisser sans distinction des composants dans un projet pour voir ce qui fonctionne. Faites glisser différentes combinaisons de dimensions et de mesures dans votre projet Workspace pour voir ce qui est mis à votre disposition. Si vous faites glisser accidentellement un composant non valide vers votre projet Workspace ou souhaitez revenir en arrière d’une étape, appuyez sur ctrl+Z (Windows) ou sur cmd+Z (Mac) pour annuler la dernière action effectuée. Vous pouvez également commencer à zéro en cliquant sur *[!UICONTROL Projet] > [!UICONTROL Nouveau]* dans le menu supérieur gauche. |
| Combien peut-on afficher de suites de rapports dans un projet Analysis Workspace ? | Vous pouvez désormais créer des projets dans Analysis Workspace à l’aide de données provenant de [plusieurs suites de rapports](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html). |
| Comment mettre en œuvre Analysis Workspace ? | Aucune mise en œuvre spéciale n’est requise. Analysis Workspace est mis à la disposition de toutes les entreprises possédant Analytics Standard ou Premium. Néanmoins, des autorisations standard d’accès au contenu (par exemple aux suites de rapports et aux composants des projets) s’appliquent ainsi qu’au traitement et au partage des projets. Voir [Administration et exigences d’accès](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| Analysis Workspace change-t-il les rapports préconfigurés dans Adobe Analytics ? | Non. Puisqu’il s’agit d’un environnement distinct, vos rapports existants ou préconfigurés dans Adobe Analytics ne seront pas modifiés. Vous pouvez continuer à utiliser les rapports générés avec les fonctionnalités Reports &amp; Analytics et Report Builder à l’aide d’Analysis Workspace. |
| Puis-je utiliser Analysis Workspace pour le Data Warehouse ? | Analysis Workspace n’est pas recommandé pour l’exportation en masse de données. Il s’agit d’un espace de travail de visualisation destiné à la création de projets d’analyse du style tableau de bord. |
| Comment optimiser les performances d’Analysis Workspace ? | Voir [Optimisation des performances](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md). |
| Comparaison des fonctionnalités d’Analysis Workspace et Ad Hoc Analysis | Voir [Comparaison entre Analysis Workspace et Ad Hoc Analysis](/help/analyze/analysis-workspace/workspace-faq/adhocanalysis-vs-analysisworkspace.md). |

## Résolution des problèmes

**Lorsque je fais glisser une mesure sur l’écran, un message indique « Données incorrectes ».**

Le message Données incorrectes signifie qu’Adobe ne peut pas renvoyer de données à l’aide de la combinaison de dimensions et de mesures utilisée dans le rapport. Par exemple, deux mesures empilées les unes sur les autres ne peuvent pas être renvoyées sous forme de données, car il n’est pas possible d’afficher deux mesures de cette manière. Placez plutôt les mesures côte à côte.

**Lorsque je fais glisser une mesure sur l’écran, je ne vois aucune donnée à proprement dit, seulement des zéros.**

Si vous êtes parvenu à créer un rapport Workspace, qui ne comporte cependant aucune donnée, vous pouvez effectuer quelques vérifications :

* Vérifiez deux fois la suite de rapports et assurez-vous qu’elle contient des données.
* Si vous avez appliqué un segment dans votre rapport, il se peut que les critères de segment ne correspondent à aucune donnée. Essayez de supprimer le segment ou d’ajuster la définition du segment.
* Vérifiez la période dans le coin supérieur droit et assurez-vous qu’elle est définie sur la valeur attendue.
* Accédez à votre site Web et utilisez [Debugger](https://docs.adobe.com/content/help/fr-FR/debugger/using/experience-cloud-debugger.html) pour vérifier que la collecte des données s’effectue.