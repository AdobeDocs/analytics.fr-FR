---
description: Répertorie quelques considérations que vous devez connaître avant de supprimer des segments.
title: Suppression des segments
topic: Segments
uuid: cb6db6ad-f400-4633-900a-8a02dcfccf2c
translation-type: ht
source-git-commit: 9e70cd51f8828cdcb698175a2b4c0150610d14d0
workflow-type: ht
source-wordcount: '259'
ht-degree: 100%

---


# Suppression des segments

Répertorie quelques considérations que vous devez connaître avant de supprimer des segments.

Lorsque vous supprimez un segment :

* Les rapports planifiés et les tableaux de bord pour lesquels ce segment est appliqué continuent de fonctionner normalement, c’est-à-dire que le segment ou le tableau de bord continue à utiliser le segment supprimé.
* Les rapports planifiés ne sont pas mis à jour lorsque vous modifiez un segment portant le même nom. Par exemple, supposons que 2 segments portant le même nom figurent dans différentes suites de rapports :

   ![](assets/duplicate_seg_names.png)

   Vous êtes doté d’un signet qui référence le segment pour la suite de rapports mainprod. Puis, vous supprimez ce segment, car il s’agit d’un doublon. Le signet continue à fonctionner, référençant la définition du segment supprimé. Si vous modifiez la définition de segment du segment restant pour inclure l’île Catalina et Tijuana au Mexique, le segment appliqué au signet ne change pas. Il utilise l’ancienne définition. Pour corriger ce problème, mettez à jour le signet qui référence la nouvelle définition. Si vous n’êtes pas certain qu’un signet, tableau de bord ou rapport planifié utilise un segment supprimé, vous pouvez modifier le nom du segment restant afin qu’il soit plus clair que le signet utilise le segment restant.

## Modifier des segments supprimés incorporés dans les Ad Hoc Analysis {#section_976D601DBD2244E38B0A0222E31D2610}

Ad Hoc Analysis vous permet désormais de modifier un segment supprimé incorporé dans le [Créateur de mesures calculées](https://docs.adobe.com/content/help/fr-FR/analytics/components/calculated-metrics/cm-overview.html) et d’effectuer une opération « Enregistrer sous » sur ce segment.

Cependant, tout autre segment supprimé faisant référence au segment supprimé restera inchangé.
