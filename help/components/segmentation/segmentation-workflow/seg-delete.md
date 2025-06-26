---
description: Répertorie quelques considérations que vous devez connaître avant de supprimer des segments.
title: Suppression des segments
feature: Segmentation
exl-id: 434b6fec-1dfa-4375-a9de-d47fad2c64bc
source-git-commit: 80e4a3ba4a5985563fcf02acf06997b4592261e4
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 39%

---

# Suppression des segments

Cet article répertorie quelques points à prendre en compte avant de supprimer des segments.

Lorsque vous supprimez un segment :

* Les rapports planifiés et les tableaux de bord auxquels ce segment est appliqué continuent à fonctionner normalement. Par exemple, le segment ou le tableau de bord continue à utiliser le segment supprimé.
* Les rapports planifiés ne sont pas mis à jour lorsque vous modifiez un segment portant le même nom. Voici un exemple : supposons que vous ayez 2 segments portant le même nom dans différentes suites de rapports :

  | Nom de segment | Suite de rapports |
  |---|---|
  | Visites depuis la Californie | mainprod |
  | Visites depuis la Californie | maindev |

  Vous disposez d’un signet qui fait référence au segment de la suite de rapports [!UICONTROL mainprod]. Supprimez ensuite ce segment, car il s’agit d’un doublon. Le signet continue à fonctionner, référençant la définition du segment supprimé. Si vous modifiez la définition de segment du segment restant pour inclure l’île Catalina et Tijuana au Mexique, le segment appliqué au signet ne change pas. Le segment utilise l’ancienne définition. Pour corriger ce problème, mettez à jour le signet pour référencer la nouvelle définition. Si vous ne savez pas si un signet, un tableau de bord ou un rapport planifié utilise un segment supprimé, vous pouvez modifier le nom du segment restant pour indiquer si le signet utilise le segment restant.
