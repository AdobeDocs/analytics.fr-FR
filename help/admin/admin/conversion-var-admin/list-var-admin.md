---
title: Variables de liste
description: Créez et configurez des variables de liste à utiliser dans les rapports.
translation-type: tm+mt
source-git-commit: 751d19227d74d66f3ce57888132514cf8bd6f7fc

---


# Variables de liste

Créez et configurez des variables de liste à utiliser dans les rapports. Définissez ici leurs valeurs de délimiteur, d’expiration, d’attribution et de plafond.

Vous pouvez accéder à la configuration dans la console d’administration :

1. Sélectionnez **[!UICONTROL Analytics]** >**[!UICONTROL  Administration]** > **[!UICONTROL Report Suites]**.
2. Sélectionnez la suite de rapports.
3. Cliquez sur **[!UICONTROL Modifier les paramètres]** >**[!UICONTROL  Conversion]** > **[!UICONTROL Variables de liste]**.

* **Nom** : chaque valeur délimitée peut contenir, au maximum, 255 caractères (ou moins en cas d’utilisation de caractères codés sur plusieurs octets). Il s’agit de la longueur maximale de chaque élément.
* **Délimiteur de valeurs** : caractère utilisé pour séparer les valeurs dans la variable de liste. Il s’agit généralement de caractères tels que des virgules, deux-points, barres verticales, etc.

   > [!NOTE] Les caractères à plusieurs octets ne peuvent pas servir de délimiteurs dans les variables de liste. Le délimiteur doit être un caractère à un seul octet.

* **Expiration** : à l’instar d’une expiration d’eVar, cette valeur détermine la période qui peut s’écouler entre la variable de liste et l’événement de conversion à relier.
   * **Au niveau d’une page vue ou d’une visite** : les événements de succès au-delà de la page vue ou de la visite ne sont reliés à aucune des valeurs dans la variable de liste.
   * **Sur la base d’une période, telle qu’un jour, une semaine, un mois, etc.** : les événements de succès au-delà de la période spécifiée ne sont reliés à aucune des valeurs dans la variable de liste. Un nombre personnalisé de jours peut être également défini.
   * **Evénements de conversion spécifiques** : tout autre événement de succès qui se déclenche après l’événement désigné n’est relié à aucune des valeurs dans la variable de liste.
   * **Jamais** : une période indéfinie peut s’écouler entre la variable de liste et l’événement de succès.

* **Affectation** : ce paramètre détermine comment les événements de succès répartissent le crédit entre les valeurs :
   * **Complète** : toutes les valeurs de la variable définies avant l’expiration de celle-ci obtiennent un crédit complet pour les événements de succès.
   * **Linéaire** : toutes les valeurs de la variable définies avant l’expiration de celle-ci obtiennent un crédit divisé pour les événements de conversion.
   * Les valeurs de la variable ne sont jamais remplacées. Elles sont ajoutées aux valeurs qui obtiennent le crédit pour les événements de succès.

* **Valeurs max.** : désigne le nombre de valeurs actives autorisées pour cette variable de liste. Par exemple, si ce paramètre est défini sur 3, seules les 3 dernières valeurs capturées sont enregistrées et toute valeur capturée précédemment est ignorée. Notez que si plusieurs valeurs pour la même variable de liste sont envoyées sur le même accès, alors que vous avez limité l’utilisation des valeurs maximales, chaque valeur aura le même horodatage et vous n’aurez aucune garantie quant à la valeur enregistrée.

250 valeurs au maximum sont stockées à la fois par visiteur. Si cette limite de 250 valeurs par visiteur est dépassée, seules les 250 dernières valeurs sont utilisées. L’expiration de ces valeurs dépend de l’expiration configurée pour la variable.

Le paramètre Valeurs max. se révèle particulièrement utile pour limiter l’attribution à un nombre spécifique de valeurs. Par exemple, si une variable de liste est définie sur « A,B,C » sur la première page d’une liste, puis sur « X,Y,Z » sur la page suivante, l’attribution est distribuée à ces six valeurs sur la base de l’allocation. Si vous souhaitez limiter l’attribution aux seules valeurs « X,Y,Z », vous pouvez définir ce paramètre sur 3.
