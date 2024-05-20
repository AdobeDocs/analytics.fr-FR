---
title: Variables de liste
description: Créez et configurez des variables de liste à utiliser dans les rapports.
feature: Admin Tools
role: Admin
exl-id: 6d9a52d4-e7f3-4bbc-bad4-55c79f30b9f7
source-git-commit: cf924b337772764b33d750787a0d09b3f11203be
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 25%

---

# Variables de liste

Créez et configurez des variables de liste à utiliser dans les rapports. Définissez leur délimiteur, expiration, attribution et valeurs max. Collecte de données pour les variables de liste à l’aide de [`list1` - `list3`](/help/implement/vars/page-vars/list.md).

**[!UICONTROL Analytics]** > **[!UICONTROL Administration]** > **[!UICONTROL Suites de rapports]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Conversion]** > **[!UICONTROL Variables de liste]**

* **[!UICONTROL Nom]**: nom de la variable de liste. Ce nom est le libellé de la dimension dans Analysis Workspace.

* **[!UICONTROL État]**: activez ou désactivez la collecte de données pour cette variable. Si une variable est désactivée, aucune donnée n’est collectée, même si votre implémentation envoie des données à cette variable.

* **[!UICONTROL Délimiteur de valeurs]**: caractère utilisé pour séparer les valeurs dans la variable de liste. Il s’agit généralement de caractères tels que des virgules, deux-points, barres verticales ou autres. Les caractères à plusieurs octets ne sont pas pris en charge en tant que délimiteurs dans les variables de liste.

* **[!UICONTROL Expire après]**: tout comme pour l’expiration en eVar, ce champ détermine le temps qui peut s’écouler entre la variable de liste et l’événement de conversion à relier.
   * **Au niveau d’une page vue ou d’une visite**: les événements de succès au-delà de la page vue ou de la visite ne sont reliés à aucune des valeurs de la variable de liste.
   * **Sur la base d’une période comme un jour, une semaine, un mois, etc.**: les événements de succès au-delà de la période spécifiée ne sont reliés à aucune des valeurs de la variable de liste. Un nombre personnalisé de jours peut être également défini.
   * **Événements de conversion spécifiques**: tout autre événement de succès qui se déclenche après l’événement désigné n’est relié à aucune des valeurs de la variable de liste.
   * **Jamais**: un laps de temps indéfini peut s’écouler entre la variable de liste et l’événement de succès.

* **[!UICONTROL Affectation]** : ce paramètre détermine comment les événements de succès répartissent le crédit entre les valeurs :
   * **Complète** : toutes les valeurs de la variable définies avant l’expiration de celle-ci obtiennent un crédit complet pour les événements de succès.
   * **Linéaire** : toutes les valeurs de la variable définies avant l’expiration de celle-ci obtiennent un crédit divisé pour les événements de conversion.
   * Les valeurs de la variable ne sont jamais remplacées. Elles sont ajoutées aux valeurs qui obtiennent le crédit pour les événements de succès.

* **[!UICONTROL Description]**: description de la manière dont votre organisation utilise la variable de liste.

* **[!UICONTROL Valeurs max.]** : désigne le nombre de valeurs actives autorisées pour cette variable de liste. Par exemple, si ce paramètre est défini sur 3, seules les 3 dernières valeurs capturées sont enregistrées et toute valeur capturée précédemment est ignorée. Notez que si plusieurs valeurs pour la même variable de liste sont envoyées sur le même accès et que vous avez limité l’utilisation des valeurs maximales, chaque valeur aura le même horodatage et il n’est pas garanti que la valeur soit enregistrée. Si un visiteur conserve plus de valeurs que la valeur maximale autorisée, les valeurs les plus récentes sont utilisées. Jusqu’à 250 valeurs max. sont autorisées.

  Ce paramètre est utile pour limiter l’attribution à un nombre spécifique de valeurs. Par exemple, si une variable de liste est définie sur `"A,B,C"` sur la première page d’une visite, puis définissez sur `"X,Y,Z"` sur la page suivante, l’attribution est distribuée à ces six valeurs en fonction de son attribution. Si vous souhaitez limiter l’attribution à uniquement `"X,Y,Z"`, vous pouvez définir le nombre maximal de valeurs sur trois.
