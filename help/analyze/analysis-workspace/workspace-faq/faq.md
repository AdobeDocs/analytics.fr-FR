---
description: Obtenez des réponses à des questions courantes sur Analysis Workspace.
title: Questions fréquentes
feature: Workspace Basics
role: User, Admin
exl-id: cf7a9a73-bcbe-4bf5-b5dc-913199ab229c
TQID: https://experienceleague.adobe.com/Cp7KvN1Y7Mxr4iGWNF08TYBzJWqhVWVSHApX0989lZ4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 598
ht-degree: 93%

---

# Questions fréquentes

+++Quelles sont les conditions préalables à l’utilisation d’Analysis Workspace ?
[Envoyer des données à Adobe Analytics à l’aide de l’extension Adobe Analytics](/help/implement/launch/validate-publish-prod.md) : l’utilisation d’Analysis Workspace nécessite une implémentation fonctionnelle. Assurez-vous que votre entreprise envoie les données à Adobe avant d’utiliser l’outil. D’autres implémentations, telles que les implémentations manuelles héritées, peuvent également fonctionner.
+++

+++Quelles sont les exigences en matière d’administration et d’accès concernant Analysis Workspace ?
Consultez la page [Exigences en matière d’administration](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md).
+++

+++L’utilisation d’Analysis Workspace aura-t-elle une incidence sur la collecte des données ?
Analysis Workspace étant un outil de reporting, il n’a aucun impact sur la collecte de données. Il n’y a aucune répercussion si vous faites glisser sans distinction des composants dans un projet pour voir ce qui fonctionne. Faites glisser différentes combinaisons de dimensions et de mesures dans votre projet Workspace pour voir ce qui est mis à votre disposition. Si vous faites glisser accidentellement un composant non valide vers votre projet Workspace ou souhaitez revenir en arrière d’une étape, appuyez sur ctrl + Z (Windows) ou sur cmd + Z (Mac) pour annuler la dernière action effectuée. Vous pouvez également commencer à zéro en cliquant sur **[!UICONTROL Projet]** > **[!UICONTROL Nouveau]** dans le menu supérieur gauche.
+++

+++Combien peut-on afficher de suites de rapports dans un projet Analysis Workspace ?
Vous pouvez désormais créer des projets dans Analysis Workspace à l’aide de données provenant de [plusieurs suites de rapports](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md).
+++

+++Comment mettre en œuvre Analysis Workspace ?
Aucune mise en œuvre spéciale n’est requise. Analysis Workspace est mis à la disposition de toutes les entreprises possédant Analytics Standard ou Premium. Néanmoins, des autorisations standard d’accès au contenu (par exemple aux suites de rapports et aux composants des projets) s’appliquent ainsi qu’au traitement et au partage des projets. Voir [Administration et exigences d’accès](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md).
+++

+++Puis-je utiliser Analysis Workspace pour Data Warehouse ?
Analysis Workspace n’est pas recommandé pour l’exportation en masse de données. Il s’agit d’un espace de travail de visualisation destiné à la création de projets d’analyse du style tableau de bord.
+++

+++Comment optimiser les performances d’Analysis Workspace ?

Voir [Optimisation des performances](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md).

+++

+++Comment les données sont-elles intégrées à votre projet Analysis Workspace ?

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Données dans Analysis Workspace](https://experienceleague.adobe.com/fr/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/understanding-how-data-gets-into-your-analysis-workspace-project){target="_blank"} pour une vidéo de démonstration.

+++

+++Comment puis-je effectuer le suivi de l’utilisation de Workspace ?

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Suivi des journaux](https://experienceleague.adobe.com/fr/docs/analytics-learn/tutorials/administration/logs/usage-log-tracking-for-analysis-workspace){target="_blank"} pour une vidéo de démonstration.

+++

+++Lorsque je fais dépose une mesure, un message indique « Données non valides ». Comment résoudre ce problème ?

Le message Données incorrectes signifie qu’Adobe ne peut pas renvoyer de données à l’aide de la combinaison de dimensions et de mesures utilisée dans le rapport. Par exemple, deux mesures empilées les unes sur les autres ne peuvent pas être renvoyées sous forme de données, car il n’est pas possible d’afficher deux mesures de cette manière. Placez plutôt les mesures côte à côte.

+++

+++Lorsque je glisse et dépose une mesure, je ne vois aucune donnée, seulement des zéros. Comment résoudre ce problème ?

Si vous êtes parvenu à créer un rapport Workspace, qui ne comporte cependant aucune donnée, vous pouvez effectuer quelques vérifications :

* Vérifiez deux fois la suite de rapports et assurez-vous qu’elle contient des données.
* Si vous avez appliqué un segment dans votre rapport, il se peut que les critères de segment ne correspondent à aucune donnée. Essayez de supprimer le segment ou d’ajuster la définition du segment.
* Vérifiez la période dans le coin supérieur droit et assurez-vous qu’elle est définie sur la valeur attendue.
* Accédez à votre site Web et utilisez [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=fr) pour vérifier que la collecte des données s’effectue.


+++

+++En tant qu’utilisateur ou utilisatrice en lecture seule, quelles actions puis-je effectuer dans Analysis Workspace ?
Lorsqu’un projet est partagé en lecture seule, toutes les fonctions et fonctionnalités d’édition sont complètement désactivées et les destinataires peuvent uniquement modifier le menu déroulant pour appliquer un filtre au panneau d’une manière prédéfinie.
+++
