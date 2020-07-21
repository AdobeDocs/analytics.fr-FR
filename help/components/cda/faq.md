---
title: FAQ sur les analyses entre appareils
description: Questions fréquentes sur les analyses entre appareils
translation-type: tm+mt
source-git-commit: f8b70ada0a2003e43a841b6721aaa474aa9699f0
workflow-type: tm+mt
source-wordcount: '1301'
ht-degree: 52%

---


# Questions fréquentes

## Comment puis-je utiliser les analyses entre appareils pour voir comment les gens passent d’un type d’appareil à un autre ?

Vous pouvez utiliser une visualisation de flux avec la dimension Type de périphérique mobile.

1. Connectez-vous à Adobe Analytics et créez un projet Workspace vide.
2. Cliquez sur l’onglet Visualisations sur la gauche, puis faites glisser une visualisation de flux vers la zone de travail sur la droite.
3. Cliquez sur l’onglet Composants sur la gauche, puis faites glisser la dimension « Type de périphérique mobile » vers l’emplacement central intitulé « Dimension ou élément ».
4. Ce rapport de flux est interactif. Cliquez sur l’une des valeurs pour étendre les flux aux pages suivantes ou précédentes. Utilisez le menu contextuel pour développer ou réduire des colonnes. Il est également possible d’utiliser différentes dimensions dans le même rapport de flux.

## Puis-je voir comment les personnes passent d’une expérience utilisateur à l’autre (par exemple, navigateur de bureau ou navigateur mobile ou application mobile) ?

L’utilisation du type de périphérique mobile comme illustré ci-dessus vous permet de voir comment les utilisateurs passent d’un type de périphérique mobile à un type de périphérique de bureau. Cependant, il se peut que vous souhaitiez distinguer les navigateurs de bureau des navigateurs mobiles. Pour ce faire, vous pouvez créer une eVar qui enregistre si l’expérience s’est produite sur un navigateur de bureau, un navigateur mobile ou une application mobile. Créez ensuite un diagramme de flux comme décrit ci-dessus, en utilisant votre eVar « expérience » plutôt que la dimension Type de périphérique mobile. Cela permet de disposer d’une vue légèrement différente du comportement sur plusieurs périphériques.

## Quelle est la durée de regroupement des visiteurs par les analyses entre appareils ?

Adobe conserve les données de regroupement de périphériques pendant environ 30 jours. Si un appareil n&#39;est pas identifié initialement mais est identifié plus tard dans les 30 jours, l&#39;ADC revient en arrière et le répète comme appartenant à une personne identifiée jusqu&#39;à 30 jours dans le passé. Si le comportement non identifié d’un utilisateur dépasse l’intervalle de recherche en amont de 30 jours, cette partie du parcours de l’utilisateur n’est pas regroupée.

* **Si vous utilisez un graphique** de périphérique, Adobe conserve les mappages de périphérique dans les graphiques Co-op et Private Graph pendant environ 6 mois. Un ECID sans activité depuis plus de six mois est supprimé du graphique. Les données déjà recoupées dans l&#39;ADC ne sont pas affectées, mais les accès ultérieurs pour cet ECID sont traités comme une nouvelle personne.

## De quelle manière les analyses entre appareils gèrent-elles les accès horodatés ?

Adobe traite les accès horodatés comme s’ils avaient été reçus au moment de l’horodatage et non lorsqu’Adobe a reçu l’accès. Les accès horodatés de plus d’un mois ne sont jamais assemblés, car ils ne sont pas compris dans la plage utilisée par Adobe pour l’assemblage.

## Comment les Analyses entre appareils se comparent-t-elles à l’identifiant visiteur personnalisé ?

Using a custom visitor ID is a legacy method to [connect users across devices](/help/implement/js/xdevice-visid/xdevice-connecting.md). Avec un identifiant visiteur personnalisé, vous utilisez la variable [`visitorID`](/help/implement/vars/config-vars/visitorid.md) pour définir explicitement l’identifiant utilisé pour la logique du visiteur. La variable `visitorID` remplace les éventuels identifiants basés sur les cookies en présence.

Les identifiants visiteur personnalisés ont plusieurs effets secondaires indésirables que les Analyses entre appareils surmontent ou minimisent. For example, the custom visitor ID methodology has no [replay](replay.md) capabilities. Si un utilisateur s’authentifie au milieu d’une visite, la première partie de la visite s’associe à un autre identifiant visiteur que celui de la seconde partie de la visite. Les identifiants visiteur séparés génèrent un gonflement des visites et des visiteurs. L’ADC redéfinit les données historiques de sorte que les accès non lantés appartiennent à la bonne personne.

## Puis-je effectuer une mise à niveau depuis un identifiant visiteur personnalisé vers les analyses entre appareils ?

Les clients qui utilisent déjà un ID de Visiteur personnalisé peuvent effectuer la mise à niveau vers CDA sans changement d’implémentation. La `visitorID` variable est toujours utilisée dans la suite de rapports source. Cependant, CDA ignore la `visitorID` variable dans la suite de rapports virtuelle si un utilisateur s’authentifie.

## De quelle manière le Device Graph gère-t-il les appareils partagés ?

Dans certains cas, il est possible que plusieurs personnes se connectent à partir du même appareil. Par exemple, un appareil partagé à la maison, des ordinateurs partagés dans une bibliothèque ou un kiosque dans un magasin de vente au détail.

* **Si vous utilisez un graphique** de périphérique, la capacité de gérer les périphériques partagés est limitée. Le graphique de périphériques utilise un algorithme pour déterminer la propriété d’une &quot;grappe&quot; et peut changer chaque fois que cette grappe est publiée. Les utilisateurs du périphérique partagé sont soumis à la grappe à laquelle ils appartiennent.
* **Si vous utilisez l’assemblage** basé sur des champs, la prop ou l’eVar que vous choisissez pour aider à identifier les utilisateurs connectés remplace d’autres identifiants. Les périphériques partagés sont considérés comme des personnes distinctes, même s’ils proviennent du même périphérique.

## Comment l&#39;ACD gère-t-elle les situations où une seule personne a BEAUCOUP d&#39;appareils/d&#39;ECID ?

Dans certains cas, un utilisateur individuel peut s’associer à un grand nombre d’ECID. Cela peut se produire s’il utilise un grand nombre de navigateurs ou d’applications et peut être exacerbé s’il lui arrive régulièrement de supprimer les cookies ou d’utiliser le mode de navigation privé ou incognito du navigateur.

* **Si vous utilisez un graphique** de périphérique, l’ADC limite à 50 le nombre d’ECID liés à un ID utilisateur donné. Si un ID utilisateur est associé à un trop grand nombre d’ECID, le graphique du périphérique suppose que l’ID utilisateur n’est pas valide et supprime la grappe associée à cet ID utilisateur. L’ID utilisateur est ensuite ajouté à une liste bloquée pour l’empêcher d’être ajouté à des grappes à l’avenir. En rapports, l’ID utilisateur n’est pas assemblé sur plusieurs périphériques.
* **Si vous utilisez l’assemblage** basé sur des champs, le nombre de périphériques n’est pas pertinent en faveur de la variable prop/eVar que vous choisissez pour aider à identifier les utilisateurs connectés. Un utilisateur unique peut appartenir à un nombre indéfini d&#39;appareils sans que cela n&#39;ait d&#39;incidence sur la capacité de l&#39;ADC de s&#39;accrocher à l&#39;ensemble des appareils.

## Quelle est la différence entre la mesure Personnes dans l&#39;ACD et la mesure Visiteuse unique en dehors de l&#39;ACD ?

The [People](/help/components/metrics/people.md) metric is similar to the [Unique Visitors](/help/components/metrics/unique-visitors.md) metric in that it reports on the number of unique individuals. Toutefois, lors de l’utilisation d’Analyses entre appareils, les visiteurs uniques sont combinés lorsqu’ils sont enregistrés en tant que deux visiteurs uniques distincts en dehors des Analyses entre appareils. La mesure « Personnes » remplace la mesure « Visiteurs uniques » lorsque les Analyses entre appareils sont activées.

## Quelle est la différence entre la mesure « Appareils uniques » des Analyses entre appareils et la mesure « Visiteurs uniques » hors Analyses entre appareils ?

Ces deux mesures sont à peu près équivalentes.

## Puis-je inclure des mesures des Analyses entre appareils à l’aide de l’API 2.0 ?

Oui. Analysis Workspace utilise l’API 2.0 pour demander des données aux serveurs Adobe et vous pouvez afficher les appels d’API qu’Adobe utilise pour créer vos propres rapports :

1. Lors de la connexion à l’Analysis Workspace, accédez à [!UICONTROL Aide] > [!UICONTROL Activer le débogueur].
2. Cliquez sur l’icône de débogage dans le panneau de votre choix, puis sélectionnez la visualisation souhaitée et l’heure de la requête.
3. Recherchez la demande JSON, que vous pouvez utiliser dans votre appel d’API à Adobe.

## Les Analyses entre appareils peuvent regrouper des visiteurs uniques. Peuvent-elles regroupes des visites ?

Oui. Si une personne envoie des accès à partir de deux appareils distincts dans le délai d’expiration de visite de votre suite de rapports virtuelle (30 minutes par défaut), ils sont regroupés au sein de la même visite.

## Quel est l’identifiant visiteur ultime utilisé par les Analyses entre appareils ? Puis-je l’exporter à partir d’Adobe Analytics ?

* **Si vous utilisez un graphique** de périphérique, un identifiant personnalisé basé sur leur grappe est l’identifiant principal.
* **Si vous utilisez l’assemblage** basé sur des champs, un identifiant personnalisé basé sur la variable prop/eVar que vous choisissez est l’identifiant principal.

Ces deux identifiants sont calculés par Adobe au moment de l’exécution du rapport, également appelé traitement [](../vrs/vrs-report-time-processing.md)des rapports. La nature du traitement des rapports signifie qu’il n’est pas compatible avec le Data warehouse, les flux de données ou d’autres fonctionnalités d’exportation que Adobe offre.

## Comment puis-je passer du graphique du périphérique à l’assemblage basé sur les champs, ou vice versa ?

Si vous souhaitez changer de méthode d&#39;identification de l&#39;ADC, contactez le gestionnaire de compte de votre organisation. Le gestionnaire de compte peut configurer votre suite de rapports selon la méthode souhaitée pour identifier les personnes. *Les données assemblées historiques issues de la méthode précédente sont perdues.*

## Comment Adobe gère-t-il les limites uniques pour une eVar utilisée dans l’assemblage sur le terrain ?

CDA extrait les valeurs de dimension eVar avant de les optimiser pour le rapports. Vous n&#39;avez pas à vous inquiéter des limites uniques pour les besoins de l&#39;ADC. Cependant, si vous avez essayé d’utiliser cette prop/eVar dans un projet Workspace, vous pouvez toujours voir la valeur de dimension [(Faible trafic)](/help/technotes/low-traffic.md) .
