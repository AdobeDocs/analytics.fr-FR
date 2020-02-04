---
title: FAQ sur les analyses entre appareils
description: Questions fréquentes sur les analyses entre appareils
translation-type: tm+mt
source-git-commit: 984d6034d14cc4256d93bd4f7d1a7f01b63b71e9

---


# Questions fréquentes

> [!NOTE] La documentation des analyses entre appareils peut être modifiée au fur et à mesure que la fonctionnalité est développée. Consultez régulièrement les mises à jour.

**Comment puis-je utiliser les analyses entre appareils pour voir comment les gens passent d’un type d’appareil à un autre ?**

Vous pouvez utiliser une visualisation de flux avec la dimension Type de périphérique mobile.

1. Connectez-vous à Adobe Analytics et créez un projet Workspace vide.
2. Cliquez sur l’onglet Visualisations sur la gauche, puis faites glisser une visualisation de flux vers la zone de travail sur la droite.
3. Cliquez sur l’onglet Composants sur la gauche, puis faites glisser la dimension « Type de périphérique mobile » vers l’emplacement central intitulé « Dimension ou élément ».
4. Ce rapport de flux est interactif. Cliquez sur l’une des valeurs pour étendre les flux aux pages suivantes ou précédentes. Utilisez le menu contextuel pour développer ou réduire des colonnes. Il est également possible d’utiliser différentes dimensions dans le même rapport de flux.

**Puis-je voir comment les personnes passent d’une expérience utilisateur à l’autre (par exemple, navigateur de bureau ou navigateur mobile ou application mobile) ?**

L’utilisation du type de périphérique mobile comme illustré ci-dessus vous permet de voir comment les utilisateurs passent d’un type de périphérique mobile à un type de périphérique de bureau. Cependant, il se peut que vous souhaitiez distinguer les navigateurs de bureau des navigateurs mobiles. Pour ce faire, vous pouvez créer une eVar qui enregistre si l’expérience s’est produite sur un navigateur de bureau, un navigateur mobile ou une application mobile. Créez ensuite un diagramme de flux comme décrit ci-dessus, en utilisant votre eVar « expérience » plutôt que la dimension Type de périphérique mobile. Cela permet de disposer d’une vue légèrement différente du comportement sur plusieurs périphériques.

**Quelle est la durée de regroupement des visiteurs par les analyses entre appareils ?**

* Adobe conserve les données de regroupement de périphériques pendant environ 30 jours. Si un périphérique n’est pas initialement identifié par le graphique Co-op ou Privé, mais qu’il est identifié plus tard dans les 30 jours, les analyses entre appareils reviennent en arrière et indiquent à nouveau que ce périphérique appartient à une personne identifiée jusqu’à 30 jours dans le passé. Si le comportement non identifié d’un utilisateur dépasse l’intervalle de recherche en amont de 30 jours, cette partie du parcours de l’utilisateur n’est pas regroupée.
* Adobe conserve les mappages de périphériques dans les graphiques Co-op et Privé pendant environ 6 mois. Un ECID sans activité depuis plus de six mois est supprimé du graphique. Les données déjà recoupées dans les analyses entre appareils ne sont pas affectées, mais les accès ultérieurs pour cet ECID sont considérés comme une nouvelle personne.

**De quelle manière les analyses entre appareils gèrent-elles les accès horodatés ?**

Adobe traite les accès horodatés comme s’ils avaient été reçus au moment de l’horodatage et non lorsqu’Adobe a reçu l’accès. Les accès horodatés de plus d’un mois ne peuvent pas être regroupés, car ils sont considérés comme étant hors de la période de conservation des données utilisées pour le regroupement par Adobe.

**De quelle manière les analyses entre appareils se comparent-elles à l’identifiant visiteur personnalisé ?**

[L’identifiant visiteur personnalisé](/help/implement/vars/config-vars/visitorid.md) est une méthode héritée qui permet de [connecter des utilisateurs sur plusieurs périphériques](/help/implement/js/xdevice-visid/xdevice-connecting.md). Avec un identifiant visiteur personnalisé, vous utilisez la variable `s.visitorID` pour définir explicitement l’identifiant utilisé pour la logique du visiteur. La variable `s.visitorID` remplace les éventuels identifiants basés sur les cookies en présence.

Les identifiants visiteur personnalisés ont un certain nombre d’effets secondaires indésirables que les analyses entre appareils est en mesure de surmonter ou de minimiser. Par exemple, la méthodologie d’identifiant visiteur personnalisé ne comporte aucune fonctionnalité de recherche en amont. Si un utilisateur s’authentifie au milieu d’une visite, la première partie de la visite s’associe à un autre identifiant visiteur que celui de la seconde partie de la visite. Les identifiants visiteur séparés génèrent un gonflement des visites et des visiteurs. L’intervalle de recherche en amont de 30 jours des analyses entre appareils lui permet de revenir dans le temps pour indiquer à nouveau que le comportement antérieur appartient à la même personne, en associant le comportement non authentifié entre appareils à un comportement authentifié entre périphériques avec une inflation nulle ou minimale.

**Puis-je effectuer une mise à niveau depuis un identifiant visiteur personnalisé vers les analyses entre appareils ?**

Les clients qui utilisent déjà un identifiant visiteur personnalisé peuvent effectuer une mise à niveau vers les analyses entre appareils. L’`s.visitorID` remplace toujours les identifiants basés sur des cookies sous-jacents dans la suite de rapports de base. Toutefois, dans la suite de rapports virtuelle, les analyses entre appareils ignorent l’`s.visitorID` pour les appareils identifiés par le Device Graph.

**De quelle manière le Device Graph gère-t-il les appareils partagés ?**

Dans certains cas, il est possible que plusieurs personnes se connectent à partir du même appareil. Par exemple, un appareil partagé à la maison, des ordinateurs partagés dans une bibliothèque ou un kiosque dans un magasin de vente au détail. Dans ces cas de figure, la synchronisation des identifiants avec le Device Graph à partir de ces appareils partagés indique que plusieurs utilisateurs sont associés à cet appareil au fil du temps. Le Device Graph (que ce soit le graphique Co-op ou Privé) ne lie pas l’ECID sur cet appareil à l’un de ces utilisateurs. Le graphique associe l’ECID à une « grappe » qui comprend tous les utilisateurs associés. Le graphique tente de maintenir cette grappe aussi stable que possible, plutôt que de changer continuellement d’ECID entre les grappes au fil du temps. Par conséquent, les analyses entre appareils ne peuvent pas faire la distinction entre des utilisateurs individuels sur un appareil partagé. Tous les utilisateurs de l’appareil partagé sont considérés comme une « personne » unique au sein des analyses entre appareils.

**Comment le graphique de l’appareil gère-t-il les situations où une seule personne a BEAUCOUP d’appareils/d’ECID ?**

Dans certains cas, un utilisateur individuel peut s’associer à un grand nombre d’ECID. Cela peut se produire s’il utilise un grand nombre de navigateurs ou d’applications et peut être exacerbé s’il lui arrive régulièrement de supprimer les cookies ou d’utiliser le mode de navigation privé ou incognito du navigateur. Le Device Graph limite à 200 le nombre d’ECID liés à un ID utilisateur donné. Si un ID utilisateur est associé à un trop grand nombre d’ECID, le Device Graph suppose que l’ID utilisateur n’est pas valide et supprime la grappe qui lui est associée. L’ID utilisateur est alors mis sur liste noire afin de ne plus être mis en grappe à l’avenir. Par conséquent, le comportement de l’ID utilisateur n’est pas regroupé sur plusieurs appareils.
