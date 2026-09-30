---
description: Découvrez comment partager des segments avec l’ensemble de votre organisation, des groupes ou des utilisateurs individuels.
title: Partager des segments
feature: Segmentation
exl-id: f51a0d1b-d293-4b41-b1dd-a79da841d94a
TQID: 'https://experienceleague.adobe.com/6NHInvDefCx7jcszRiGERN2FadCAC3QIUqgCw9pnoII'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: c47a19a5-f47b-4e53-afe0-e230da195ebe
    internal-label: Segmentation
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 57%
---
# Partager des segments

Selon vos autorisations, vous pouvez partager des segments avec l’ensemble de l’entreprise, des groupes ou des individus.

| Administrateur | Peut partager des segments avec l’ensemble de l’entreprise, avec des groupes et avec des utilisateurs. Les groupes sont définis en tant que groupes d’autorisations dans Admin Console. |
|---|---|
| Non administrateur | Peut partager les segments uniquement avec des individus. |

À quel moment devriez-vous partager des segments avec l’ensemble de l’entreprise au lieu de vous limiter à un groupe d’utilisateurs et d’utilisatrices ou à des individus ? Vous trouverez ci-dessous quelques bonnes pratiques que vous pouvez suivre :

* En tant qu’administrateur, partagez un segment avec **[!UICONTROL Tous]** s’il est utile à l’ensemble de l’entreprise et si tout le monde sait l’utiliser correctement. Dans ce cas, vous devez également envisager d’en faire un segment [approuvé](/help/components/segmentation/segmentation-workflow/seg-approve.md).

* En tant qu’administrateur, partagez un segment avec un **[!UICONTROL Groupe]** spécifique si le segment offre une valeur ajoutée intéressante à l’équipe en question. N’approuvez pas officiellement ce type de segment.
* En tant qu’administrateur ou administratrice, ou en tant qu’utilisateur ou utilisatrice individuel, partagez un segment avec d’autres individus afin d’examiner et de valider ce segment. S’il ne s’avère pas utile, il peut être ignoré. N’approuvez pas officiellement ce type de segment.

1. Dans le gestionnaire de segments, cochez la case ![SelectBox](/help/assets/icons/SelectBox.svg) située en regard du segment à partager.
1. Sélectionnez ![Partager](/help/assets/icons/Share.svg) Partager.
1. Dans la boîte de dialogue **[!UICONTROL Partager des segments]** :

   ![Partage des segments](assets/share-segments-dialog.png)

   Si vous êtes administrateur, vous pouvez sélectionner **[!UICONTROL Tous]** ou effectuer une sélection dans les **[!UICONTROL Groupes]** et **[!UICONTROL Utilisateurs]** de votre entreprise. En tant que non administrateur, vous ne pouvez consulter que les utilisateurs individuels. Utilisez le champ **[!UICONTROL Rechercher]** pour rechercher des groupes ou des utilisateurs. 1.

   1. (Facultatif) utilisez ![Rechercher](/help/assets/icons/Search.svg) pour *Rechercher des individus ou des groupes* et limiter la liste des groupes ou des individus avec lesquels vous souhaitez partager le segment.

   1. Sélectionnez **[!UICONTROL Enregistrer]** pour partager les segments. Sélectionnez **[!UICONTROL Annuler]** pour annuler.




   L’icône Partagé s’affiche en regard du segment : ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg)

1. Vous pouvez filtrer par segments partagés avec vous en accédant à **[!UICONTROL Filtres]** > **[!UICONTROL Autres filtres]** > **[!UICONTROL Partagés avec moi]**.

## Bonnes pratiques

Vous trouverez ci-dessous quelques bonnes pratiques concernant le partage de segments et les personnes avec lesquelles vous devez les partager.

* En tant qu’administrateur ou administratrice, ne partagez un segment avec Tous que si vous êtes convaincu(e) que toute personne de votre organisation est à l’aise avec l’utilisation des segments. Vous pouvez également envisager de favoriser ces segments. Voir [Marquer un segment comme favori](t-seg-favorite.md) pour plus d’informations.

* En tant qu’administrateur ou administratrice, partagez un segment avec un groupe spécifique si ce segment apporte une valeur commerciale aux utilisateurs et utilisatrices de ce groupe.

* En tant qu’administrateur ou utilisatrice individuelle, partagez un segment avec une ou plusieurs personnes afin de valider un segment. Si les segments ne s’avèrent pas utiles, vous pouvez les supprimer.
