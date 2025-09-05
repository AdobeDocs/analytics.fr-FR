---
title: Variables de liste
description: Créez et configurez des variables de liste à utiliser dans les rapports.
feature: Admin Tools
role: Admin
exl-id: 6d9a52d4-e7f3-4bbc-bad4-55c79f30b9f7
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '489'
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
