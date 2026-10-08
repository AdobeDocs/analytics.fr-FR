---
description: Découvrez les erreurs et la résolution des problèmes pour Analysis Workspace.
title: Erreurs et résolution des problèmes
feature: Workspace Basics
role: User, Admin
exl-id: e5c6f710-a205-48db-aeee-ee5b83c42795
TQID: 'https://experienceleague.adobe.com/Kr34CyT7YxRqKRdwpaLN-DZwHhLbaT663Gj-pc5Wd8s'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
    internal-label: Alerts
  - id: c457b289-f974-4a67-a5b6-dec3ffa77675
    internal-label: Workspace basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
source-git-commit: 319f78bb5f8c2449a7263e3f1c378c49656889a7
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 94%
---
# Erreurs et résolution des problèmes

Vous pouvez rencontrer des erreurs lorsque vous interagissez avec Analysis Workspace. Celles-ci peuvent affecter son fonctionnement ou ses performances. Les types d’erreur les plus courants sont répertoriés ci-dessous, ainsi que les raisons pour lesquelles ils se produisent et les optimisations qui peuvent être effectuées.

## Messages d’erreur

Voici quelques messages d’erreur courants susceptibles de s’afficher lorsque vous utilisez Analysis Workspace :

| Message d’erreur | Pourquoi l’erreur se produit-elle ? | Optimisation |
| --- | --- | --- |
| [!UICONTROL La suite de rapports fait l’objet de rapports exceptionnellement lourds. Veuillez réessayer ultérieurement.] | Votre entreprise essaie d’exécuter trop de requêtes simultanées sur une suite de rapports spécifique. Les facteurs à l’origine de cette erreur sont les demandes d’API, les projets planifiés, les rapports planifiés, les alertes planifiées et les utilisateurs qui effectuent simultanément des demandes de création de rapports. | Diffusez vos requêtes et plannings pour la suite de rapports de manière plus uniforme tout au long de la journée.<p>Les administrateurs et les administratrices peuvent utiliser le [Gestionnaire des activités de rapport pour identifier et annuler des requêtes](/help/admin/tools/reporting-activity-manager/reporting-activity-overview.md) qui consomment de la capacité de création de rapports.</p> |
| [!UICONTROL Ce rapport est trop complexe. Veuillez consulter les bonnes pratiques pour créer des rapports Analysis Workspace.] | Votre requête de création de rapports est trop volumineuse et ne peut pas être exécutée. Les facteurs à l’origine de cette erreur sont les temporisations en raison de la complexité de la requête. | Simplifiez votre requête. Par exemple, raccourcissez la période, simplifiez les critères de segment ou supprimez certaines colonnes ou lignes de votre tableau. Vous pouvez également envisager de diviser le tableau en plusieurs requêtes distinctes. |
| [!UICONTROL La suite de rapports dépasse actuellement sa capacité de création de rapports. Simplifiez la demande ou réessayez ultérieurement.] | Votre entreprise essaie d’exécuter trop de requêtes simultanées sur une suite de rapports spécifique. Cette erreur peut notamment être due aux requêtes API, aux projets planifiés et aux demandes de reporting effectuées simultanément par plusieurs utilisateurs. | Répartissez plus uniformément vos requêtes et vos planifications pour la suite de rapports tout au long de la journée. |
| [!UICONTROL Une erreur système s’est produite. Veuillez soumettre un ticket à l’assistance clientèle sous **[!UICONTROL Aide > Envoyer le ticket d’assistance]** en incluant votre code d’erreur.] | Adobe rencontre un problème qui doit être résolu. | Envoyez le code d’erreur à l’Assistance clientèle. |
| [!UICONTROL Erreur 500 : Échec du chargement de la page] | Les problèmes liés à votre réseau local, tels que les [paramètres du pare-feu](/help/technotes/ip-addresses.md) de la société, sont un facteur contribuant à cette erreur. En outre, Adobe peut rencontrer un problème qui doit être résolu. | Essayez de vous reconnecter après quelques minutes. Si le problème persiste, envoyez le code d’ID d’instance EIM à l’assistance clientèle. |
| [!UICONTROL Votre requête a échoué en raison d’un trop grand nombre de colonnes ou de lignes préconfigurées.] | Votre tableau comporte trop de cellules à structure libre (ligne * colonnes). | Supprimez les colonnes ou les lignes du tableau ou envisagez de diviser le tableau en requêtes distinctes. |


## Résolution des problèmes

Lors de l’utilisation d’Analysis Workspace, vous pouvez utiliser les informations ci-dessous pour résoudre certains problèmes courants.

| Problème | Comment résoudre le problème |
|---|---|
| Lorsque je glisse et dépose une mesure, un message indique *Données non valides*. | Des données non valides signifient qu’Adobe ne peut pas renvoyer de données avec la combinaison de dimensions et de mesures utilisée dans le rapport. Par exemple, deux mesures empilées les unes sur les autres ne peuvent pas être renvoyées sous forme de données, car il n’est pas possible d’afficher deux mesures de cette manière. Placez plutôt les mesures côte à côte. |
| Lorsque je glisse et dépose une mesure, je ne vois aucune donnée, seulement des zéros. | Si vous avez réussi à créer un rapport Workspace, qui ne comporte cependant aucune donnée, vous pouvez effectuer quelques vérifications :<ul><li>Si vous avez appliqué un segment dans votre rapport, il se peut que les critères de segment ne correspondent à aucune donnée. Essayez de supprimer le segment ou d’ajuster la définition du segment.</li><li>Vérifiez la période dans le coin supérieur droit et pour vous assurer qu’elle est définie sur la valeur souhaitée.</li><li>Accédez à votre site web et utilisez [&#128279;](https://experienceleague.adobe.com/fr/docs/experience-platform/debugger/home) pour vérifier que les données sont collectées.</li></ul> |
