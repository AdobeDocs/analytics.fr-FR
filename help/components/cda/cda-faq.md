---
title: FAQ sur les analyses entre appareils
description: Questions fréquentes sur Analytics sur plusieurs périphériques
translation-type: tm+mt
source-git-commit: e7a78c2ac21042f57487c1c230e1c96318810429

---


# Questions fréquentes

> [!NOTE] La documentation d’Analytics sur plusieurs périphériques peut être modifiée au fur et à mesure que la fonctionnalité est développée. Consultez régulièrement les mises à jour.

**Comment puis-je utiliser l'ADC pour voir comment les gens passent d'un type d'appareil à un autre?**

Vous pouvez utiliser une visualisation Flux avec la dimension Type de périphérique mobile.

1. Connectez-vous à Adobe Analytics et créez un projet Workspace vide.
2. Cliquez sur l’onglet Visualisations sur la gauche, puis faites glisser une visualisation Flux vers le canevas sur la droite.
3. Cliquez sur l'onglet Composants sur la gauche, puis faites glisser la dimension "Type de périphérique mobile" vers l'emplacement central intitulé "Dimension ou élément".
4. Ce rapport de flux est interactif. Cliquez sur l’une des valeurs pour étendre les flux aux pages suivantes ou précédentes. Utilisez le menu contextuel pour développer ou réduire les colonnes. Différentes dimensions peuvent également être utilisées dans le même rapport de flux.

**Puis-je voir comment les utilisateurs passent d’une expérience utilisateur à l’autre (par exemple, navigateur de bureau ou navigateur mobile ou application mobile) ?**

L'utilisation du type de périphérique mobile comme illustré ci-dessus vous permet de voir comment les utilisateurs passent d'un type de périphérique mobile à un type de périphérique de bureau. Cependant, vous pouvez vouloir distinguer les navigateurs de bureau des navigateurs mobiles. Pour ce faire, vous pouvez créer une eVar qui enregistre si l’expérience s’est produite sur un navigateur de bureau, un navigateur mobile ou une application mobile. Créez ensuite un diagramme de flux comme décrit ci-dessus, en utilisant votre eVar "expérience" plutôt que la dimension Type de périphérique mobile. Ceci offre une vue légèrement différente du comportement sur plusieurs périphériques.

**Jusqu'où est-ce que CDA rassemble les visiteurs ?**

* Adobe conserve les données d’assemblage de périphériques pendant environ 30 jours. Si un appareil n'est pas initialement identifié par le graphique coopératif ou privé, mais qu'il est identifié plus tard dans les 30 jours, l'ADC revient en arrière et le répète comme appartenant à une personne identifiée jusqu'à 30 jours par le passé. Si le comportement non identifié d’un utilisateur dépasse la fenêtre de recherche de 30 jours, cette partie du parcours de l’utilisateur n’est pas couchée.
* Adobe conserve les mappages de périphériques dans les graphiques Co-op et Private Graph pendant environ 6 mois. Un ECID sans activité depuis plus de six mois est supprimé du graphique. Les données déjà recoupées dans l’ADC ne sont pas affectées, mais les accès ultérieurs pour cet ECID sont traités comme une nouvelle personne.

**Comment l’ADC gère-t-elle les accès horodatés ?**

Adobe traite les accès horodatés comme s’ils avaient été reçus au moment de l’horodatage et non lorsqu’Adobe a reçu l’accès. Les accès horodatés de plus d’un mois ne peuvent pas être assemblés, car ils sont considérés en dehors de la plage d’Adobe conserve les données utilisées pour l’assemblage.

**En quoi l’ACD se compare-t-il à l’identifiant visiteur personnalisé ?**

[L’identifiant](../../implement/js-implementation/c-unique-visitors/visid-custom.md) visiteur personnalisé est une méthode héritée qui permet de [connecter des utilisateurs entre des périphériques](../../implement/js-implementation/xdevice-visid/xdevice-connecting.md). Avec un identifiant visiteur personnalisé, vous utilisez la `s.visitorID` variable pour définir explicitement l’identifiant utilisé pour la logique du visiteur. La `s.visitorID` variable remplace les identifiants basés sur les cookies qui sont présents. Voir [Identification des visiteurs](../../implement/js-implementation/c-unique-visitors/visid-overview.md) uniques dans le guide de l’utilisateur Mise en oeuvre pour plus d’informations.

Les identifiants visiteur personnalisés ont un certain nombre d’effets secondaires indésirables que l’ADC est conçue pour surmonter ou minimiser. Par exemple, la méthodologie d’identification des visiteurs personnalisée ne comporte aucune fonctionnalité de recherche. Si un utilisateur s’authentifie au milieu d’une visite, la première partie de la visite est associée à un ID de visiteur différent de la seconde partie de la visite. Les identifiants de visiteur distincts génèrent un gonflement des visites et des visiteurs. La fenêtre de recherche de 30 jours de CDA lui permet de revenir en arrière dans le temps pour retraiter le comportement antérieur comme appartenant à la même personne, en associant le comportement non authentifié des périphériques et le comportement authentifié des périphériques multiples avec une inflation nulle ou minimale.

**Puis-je passer de l’identifiant visiteur personnalisé à l’identifiant de visiteur CDA ?**

Les clients qui utilisent déjà l’identifiant visiteur personnalisé peuvent effectuer une mise à niveau vers CDA. Le `s.visitorID` code remplace toujours les identifiants sous-jacents de cookie dans la suite de rapports de base. Toutefois, dans la suite de rapports virtuelle, CDA ignore `s.visitorID` les périphériques identifiés par le graphique de périphériques.

**Comment le graphique du périphérique gère-t-il les périphériques partagés ?**

Dans certains cas, il est possible que plusieurs personnes se connectent à partir du même périphérique. Par exemple, un périphérique partagé à la maison, des ordinateurs partagés dans une bibliothèque ou un kiosque dans un magasin de vente au détail. Dans ce cas, l’ID se synchronise avec le graphique de l’appareil à partir de ces périphériques partagés indique que plusieurs utilisateurs l’associent au fil du temps. Le graphique du périphérique (que ce soit Co-op ou Private Graph) ne lie pas l’ECID sur ce périphérique à l’un de ces utilisateurs. Le graphique associe l’ECID à une "grappe" qui comprend tous les utilisateurs associés. Le graphique tente de maintenir cette grappe aussi stable que possible, plutôt que de changer continuellement l'ECID entre les clusters au fil du temps. Par conséquent, CDA ne peut pas faire la distinction entre des utilisateurs individuels sur un périphérique partagé. Tous les utilisateurs de l’appareil partagé sont considérés comme une "personne" unique au sein de l’ADC.

**Comment le graphique de l'appareil gère-t-il les situations où une seule personne a BEAUCOUP d'appareils/d'ECID?**

Dans certains cas, un utilisateur individuel peut s’associer à un grand nombre d’ECID. Cela peut se produire si l’utilisateur utilise un grand nombre de navigateurs ou d’applications et peut être exacerbé s’il efface fréquemment les cookies ou utilise le mode de navigation privé ou incognito du navigateur. Le graphique du périphérique limite à 200 le nombre d’ECID liés à un ID utilisateur donné. Si un ID utilisateur est associé à un trop grand nombre d’ECID, le graphique du périphérique suppose que l’ID utilisateur n’est pas valide et supprime la grappe associée à cet ID utilisateur. L’ID utilisateur est alors mis sur liste noire pour ne plus être recluster à l’avenir. En conséquence, le comportement de l’ID utilisateur n’est pas assemblé sur plusieurs périphériques.
