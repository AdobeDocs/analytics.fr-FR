---
title: Variables de liste
description: Créez et configurez des variables de liste à utiliser dans les rapports.
feature: Admin Tools
role: Admin
exl-id: 6d9a52d4-e7f3-4bbc-bad4-55c79f30b9f7
TQID: https://experienceleague.adobe.com/22yU-AEfp08-BPNwwC6LrJO7iX7n44mZzP9799l6fmQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 490
ht-degree: 25%

---

# Variables de liste

Créez et configurez des variables de liste à utiliser dans les rapports. Définissez leurs valeurs de délimiteur, d’expiration, d’attribution et de max. Collectez des données pour les variables de liste à l’aide de [`list1` - `list3`](/help/implement/vars/page-vars/list.md).

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Conversion]** > **[!UICONTROL List Variables]**

* **[!UICONTROL Name]** : nom de la variable de liste. Ce nom est le libellé de dimension dans Analysis Workspace.

* **[!UICONTROL Statut]** : activez ou désactivez la collecte de données pour cette variable. Si une variable est désactivée, aucune donnée n’est collectée, même si votre implémentation envoie des données à cette variable.

* **[!UICONTROL Délimiteur de valeur]** : caractère utilisé pour séparer les valeurs dans la variable de liste. Il s’agit le plus souvent de caractères tels que des virgules, deux-points, barres verticales ou similaires. Les caractères multi-octet ne sont pas pris en charge comme délimiteurs dans les variables de liste.

* **[!UICONTROL Expire après]** : comme pour l’expiration eVar, ce champ détermine le délai pouvant s’écouler entre la variable de liste et l’événement de conversion pour qu’ils soient associés.
   * **Au niveau d’une page vue ou d’une visite** : les événements de succès au-delà de la page vue ou de la visite ne sont pas liés à des valeurs dans la variable de liste.
   * **Basé sur une période de temps, telle que jour, semaine, mois, etc** : les événements de succès au-delà de la période spécifiée ne sont liés à aucune valeur de la variable de liste. Un nombre personnalisé de jours peut être également défini.
   * **Événements de conversion spécifiques** : tous les autres événements de succès qui se déclenchent après l’événement spécifique désigné ne sont pas liés à des valeurs de la variable de liste.
   * **Jamais** : un laps de temps indéfini peut s’écouler entre la variable de liste et l’événement de succès.

* **[!UICONTROL Affectation]** : ce paramètre détermine comment les événements de succès répartissent le crédit entre les valeurs :
   * **Complète** : toutes les valeurs de la variable définies avant l’expiration de celle-ci obtiennent un crédit complet pour les événements de succès.
   * **Linéaire** : toutes les valeurs de la variable définies avant l’expiration de celle-ci obtiennent un crédit divisé pour les événements de conversion.
   * Les valeurs de la variable ne sont jamais remplacées. Elles sont ajoutées aux valeurs qui obtiennent le crédit pour les événements de succès.

* **[!UICONTROL Description]** : description de la manière dont votre entreprise utilise la variable de liste.

* **[!UICONTROL Valeurs max.]** : désigne le nombre de valeurs actives autorisées pour cette variable de liste. Par exemple, si ce paramètre est défini sur 3, seules les 3 dernières valeurs capturées sont enregistrées et toute valeur capturée précédemment est ignorée. Notez que si plusieurs valeurs pour la même variable de liste sont envoyées sur le même accès et que vous avez restreint l’utilisation de valeurs maximales , chaque valeur aura le même horodatage et il n’est pas garanti quelle valeur est enregistrée. Si un visiteur persiste plus de valeurs que le nombre maximal autorisé, les valeurs les plus récentes sont utilisées. Jusqu’à 250 valeurs max sont autorisées.

  Ce paramètre est utile pour limiter l’attribution à un nombre spécifique de valeurs. Par exemple, si une variable de liste est définie sur `"A,B,C"` sur la première page d’une visite, puis sur `"X,Y,Z"` sur la page suivante, l’attribution est distribuée à ces six valeurs en fonction de son affectation. Si vous souhaitez limiter l’attribution à `"X,Y,Z"` uniquement, vous pouvez définir des valeurs maximales à trois.
