---
title: FAQ sur les analyses entre appareils
description: Questions fréquentes sur les analyses entre appareils
exl-id: 7f5529f6-eee7-4bb9-9894-b47ca6c4e9be
translation-type: tm+mt
source-git-commit: 50ffeac17a07478e98e8d83bd3a87db0d9a1145d
workflow-type: tm+mt
source-wordcount: '1674'
ht-degree: 79%

---

# Questions fréquentes

## Comment puis-je utiliser les analyses entre appareils pour voir comment les gens passent d’un type d’appareil à un autre ?

Vous pouvez utiliser une visualisation [!UICONTROL Flux] avec la dimension Type de périphérique mobile.

1. Connectez-vous à Adobe Analytics et créez un projet Workspace vide.
2. Cliquez sur l’onglet Visualisations sur la gauche, puis faites glisser une visualisation de flux vers la zone de travail sur la droite.
3. Cliquez sur l’onglet Composants sur la gauche, puis faites glisser la dimension « Type de périphérique mobile » vers l’emplacement central intitulé « Dimension ou élément ».
4. Ce rapport de flux est interactif. Cliquez sur l’une des valeurs pour étendre les flux aux pages suivantes ou précédentes. Utilisez le menu contextuel pour développer ou réduire des colonnes. Il est également possible d’utiliser différentes dimensions dans le même rapport de flux.

## Puis-je voir comment les personnes passent d’une expérience utilisateur à l’autre (par exemple, navigateur de bureau ou navigateur mobile ou application mobile) ?

L’utilisation du type de périphérique mobile comme illustré ci-dessus vous permet de voir comment les utilisateurs passent d’un type de périphérique mobile à un type de périphérique de bureau. Cependant, il se peut que vous souhaitiez distinguer les navigateurs de bureau des navigateurs mobiles. Pour ce faire, vous pouvez créer une eVar qui enregistre si l’expérience s’est produite sur un navigateur de bureau, un navigateur mobile ou une application mobile. Créez ensuite un diagramme de flux comme décrit ci-dessus, en utilisant votre eVar « expérience » plutôt que la dimension Type de périphérique mobile. Cela permet de disposer d’une vue légèrement différente du comportement sur plusieurs périphériques.

## Quelle est la durée de regroupement des visiteurs par les analyses entre appareils ?

Lʼassemblage entre appareils des analyses entre appareils (CDA) se produit dans deux processus simultanés.

* Le premier processus, nommé « assemblage dynamique », se produit quand les données arrivent en flux continu dans Adobe Analytics. Pendant lʼassemblage dynamique, les CDA sʼefforcent de retraiter les données au niveau de la personne. Cependant, si la personne est inconnue lors de lʼassemblage dynamique, les CDA reviennent à lʼidentifiant visiteur pour représenter la personne.

* Le second processus est nommé « relecture ». Au cours de la relecture, les CDA remontent dans le temps et retraitent les données historiques, si possible, au cours dʼun intervalle de recherche en amont spécifié. Cet intervalle de recherche en amont est soit de 1 jour, soit de 7 jours, selon la configuration choisie pour les CDA. Au cours de la relecture, les CDA tentent de retraiter les accès où la personne était précédemment inconnue.

* **Si vous utilisez un graphique d’appareil**, Adobe conserve les mappages de l’appareil dans le graphique Co-op et le graphique Privé pendant environ 6 mois. Un ECID sans activité depuis plus de six mois est supprimé du graphique. Les données déjà recoupées dans les analyses entre appareils ne sont pas affectées, mais les accès ultérieurs pour cet ECID sont considérés comme une nouvelle personne.

## De quelle manière les analyses entre appareils gèrent-elles les accès horodatés ?

Adobe traite les accès horodatés comme s’ils avaient été reçus au moment de l’horodatage et non lorsqu’Adobe a reçu l’accès. Les accès horodatés de plus d’un mois ne sont jamais regroupés, car ils ne sont pas compris dans la plage utilisée par Adobe pour le groupement.

## Comment les Analyses entre appareils se comparent-elles à l’identifiant visiteur personnalisé ?

L’utilisation d’un identifiant visiteur personnalisé est une méthode héritée qui permet de [connecter des utilisateurs sur plusieurs appareils](/help/implement/js/xdevice-visid/xdevice-connecting.md). Avec un identifiant visiteur personnalisé, vous utilisez la variable [`visitorID`](/help/implement/vars/config-vars/visitorid.md) pour définir explicitement l’identifiant utilisé pour la logique du visiteur. La variable `visitorID` remplace les éventuels identifiants basés sur les cookies en présence.

Les identifiants visiteur personnalisés ont plusieurs effets secondaires indésirables que les Analyses entre appareils surmontent ou minimisent. Par exemple, la méthodologie d’identifiant visiteur personnalisé ne comporte aucune fonctionnalité de [relecture](replay.md). Si un utilisateur s’authentifie au milieu d’une visite, la première partie de la visite s’associe à un autre identifiant visiteur que celui de la seconde partie de la visite. Les identifiants visiteur séparés génèrent un gonflement des visites et des visiteurs. Les analyses entre appareils indiquent à nouveau les données historiques de sorte que les accès non authentifiés appartiennent à la bonne personne.

## Puis-je effectuer une mise à niveau depuis un identifiant visiteur personnalisé vers les analyses entre appareils ?

Les clients qui utilisent déjà un identifiant visiteur personnalisé peuvent effectuer une mise à niveau vers les analyses entre appareils sans aucune modification de l’implémentation. La variable `visitorID` est toujours utilisée dans la suite de rapports source. Cependant, les analyses entre appareils ignorent la variable `visitorID` dans la suite de rapports virtuelle si un utilisateur s’authentifie.

## De quelle manière le graphique d’appareil gère-t-il les appareils partagés ?

Dans certains cas, il est possible que plusieurs personnes se connectent à partir du même appareil. Par exemple, un appareil partagé à la maison, des ordinateurs partagés dans une bibliothèque ou un kiosque dans un magasin de vente au détail.

* **Si vous utilisez un graphique d’appareil**, votre capacité à gérer les appareils partagés est limitée. Le graphique d’appareil utilise un algorithme pour déterminer la propriété d’une « grappe » et peut changer chaque fois que cette grappe est publiée. Les utilisateurs de l’appareil partagé dépendent de la grappe à laquelle ils appartiennent.
* **Si vous utilisez le groupement basé sur les champs**, la prop ou l’eVar que vous choisissez pour identifier les utilisateurs connectés remplace d’autres identifiants. Les appareils partagés sont considérés comme des personnes distinctes, même s’ils proviennent du même appareil.

## Comment les analyses entre appareils gèrent-ils les situations où une seule personne a BEAUCOUP d’appareils/d’ECID ?

Dans certains cas, un utilisateur individuel peut s’associer à un grand nombre d’ECID. Cela peut se produire s’il utilise un grand nombre de navigateurs ou d’applications et peut être exacerbé s’il lui arrive régulièrement de supprimer les cookies ou d’utiliser le mode de navigation privé ou incognito du navigateur.

* **Si vous utilisez un graphique d’appareil**, les analyses entre appareils limitent à 50 le nombre d’ECID liés à un identifiant utilisateur donné. Si un identifiant utilisateur est associé à un trop grand nombre d’ECID, le graphique d’appareil suppose que l’identifiant utilisateur n’est pas valide et supprime la grappe qui lui est associée. L’identifiant utilisateur est ensuite ajouté à une liste bloquée afin d’éviter qu’il ne soit ajouté à d’autres grappes à l’avenir. Par conséquent, l’identifiant utilisateur n’est pas regroupé sur plusieurs appareils.
* **Si vous utilisez le groupement basé sur les champs**, le nombre d’appareils est sans importance par rapport à la prop/l’eVar que vous choisissez pour identifier les utilisateurs connectés. Un utilisateur unique peut appartenir à un nombre indéfini d’appareils sans que cela ait d’incidence sur la capacité de groupement sur plusieurs appareils des analyses entre appareils.

## Quelle est la différence entre la mesure Personnes des analyses entre appareils et la mesure Visiteurs uniques en dehors des analyses entre appareils ?

La mesure [Personnes](/help/components/metrics/people.md) est similaire à la mesure [Visiteurs uniques](/help/components/metrics/unique-visitors.md) en ce sens qu’elle indique le nombre d’individus uniques. Toutefois, lors de l’utilisation d’Analyses entre appareils, les visiteurs uniques sont combinés lorsqu’ils sont enregistrés en tant que deux visiteurs uniques distincts en dehors des Analyses entre appareils. La mesure « Personnes » remplace la mesure « Visiteurs uniques » lorsque la fonctionnalité Analytics sur l’ensemble des appareils est activée. Une nouvelle mesure, [Appareils uniques](/help/components/metrics/unique-devices.md), est disponible et est à peu près similaire à Visiteurs uniques en dehors d’Analytics sur l’ensemble des appareils.

## Quelle est la différence entre la mesure « Appareils uniques » des Analyses entre appareils et la mesure « Visiteurs uniques » hors Analyses entre appareils ?

Ces deux mesures sont à peu près équivalentes.

## Puis-je inclure des mesures des Analyses entre appareils à l’aide de l’API 2.0 ?

Oui. Analysis Workspace utilise l’API 2.0 pour demander des données aux serveurs Adobe et vous pouvez afficher les appels d’API qu’Adobe utilise pour créer vos propres rapports :

1. Lors de la connexion à Analysis Workspace, accédez à [!UICONTROL Aide] > [!UICONTROL Activer le débogueur].
2. Cliquez sur l’icône de débogage dans le panneau de votre choix, puis sélectionnez la visualisation souhaitée et l’heure de la requête.
3. Recherchez la demande JSON, que vous pouvez utiliser dans votre appel d’API à Adobe.

## Les Analyses entre appareils peuvent regrouper des visiteurs uniques. Peuvent-ils regrouper des visites ?

Oui. Si une personne envoie des accès à partir de deux appareils distincts dans le délai d’expiration de visite de votre suite de rapports virtuelle (30 minutes par défaut), ils sont regroupés au sein de la même visite.

## Quel est l’identifiant visiteur ultime utilisé par les Analyses entre appareils ? Puis-je l’exporter à partir d’Adobe Analytics ?

* **Si vous utilisez un graphique d’appareil**, un identifiant personnalisé basé sur la grappe est l’identifiant principal.
* **Si vous utilisez le groupement basé sur les champs**, un identifiant personnalisé basé sur la prop/l’eVar que vous choisissez est l’identifiant principal.

Ces deux identifiants sont calculés par Adobe au moment de l’exécution du rapport, également appelé [Traitement de la période de rapport](../vrs/vrs-report-time-processing.md). La nature du traitement de la période de rapport signifie qu’il n’est pas compatible avec Data Warehouse, les flux de données ou d’autres fonctionnalités d’exportation des offres Adobe.

## Comment puis-je passer du graphique d’appareils au groupement basé sur les champs, ou vice versa ?

Le service à la clientèle peut vous demander de passer du graphique du périphérique à l’assemblage sur le terrain ou vice versa. Cependant, la réalisation d&#39;un tel commutateur peut prendre quelques semaines ou plus et *les données assemblées historiques de la méthode précédente sont perdues.*

## Comment Adobe gère-t-il les limites uniques d’une eVar utilisée dans un groupement basé sur les champs ?

Les analyses entre appareils extraient les éléments de dimension eVar avant de les optimiser pour les rapports. Vous n’avez pas à vous inquiéter des limites uniques à des fins d’analyses entre appareils. Cependant, si vous avez essayé d’utiliser cette prop/eVar dans un projet Workspace, vous pouvez toujours voir l’élément de dimension [(Faible trafic)](/help/technotes/low-traffic.md).

## Combien de suites de rapports de ma société peuvent être activées pour l’ADC ?

Il est possible d’activer plusieurs suites de rapports. Toutefois, chaque suite de rapports supplémentaire augmentera le temps de mise en service général si plusieurs suites de rapports sont demandées à la fois. CDA ne fusionne pas les suites de rapports. Chaque suite de rapports activée pour CDA doit être de nature inter-périphériques (contenant des données provenant de plusieurs surfaces telles que le web pour ordinateur, le web mobile, les applications mobiles, etc.)

## Si mon organisation Experience Cloud (ou organisation IMS) a plusieurs sociétés dans différentes régions, puis-je activer l&#39;ACD pour toutes ?

Non. Pour la même organisation, seule une région peut avoir activé l&#39;ADC.

## Quels sont les avantages et les inconvénients d&#39;une relecture de 7 jours par rapport à une relecture de 1 jour ?

L&#39;avantage de la fenêtre de recherche de relecture de 7 jours est que l&#39;ADC peut revenir plus loin dans le temps pour essayer d&#39;associer des événements anonymes antérieurs à une personne qui s&#39;est connectée plus tard dans les 7 jours. Les inconvénients de la fenêtre de recherche de 7 jours sont 1) la relecture ne s&#39;exécute qu&#39;une fois par semaine, et 2) les 7 derniers jours sont sujets à changement.

Les avantages de l&#39;utilisation de la fenêtre de recherche de relecture de 1 jour sont 1) la relecture s&#39;exécute tous les jours et 2) seulement hier est sujet à changement. L&#39;inconvénient de la fenêtre de recherche en amont d&#39;un jour est que l&#39;ADC ne peut revenir qu&#39;en arrière d&#39;un jour pour essayer d&#39;associer des événements précédemment anonymes à une personne qui s&#39;est connectée hier.

## Qu’advient-il des données assemblées dans mes suites de rapports virtuelles CDA si ma société décide de réduire la mise à niveau d’Analytics Ultimate ?

Si un client effectue une mise à niveau depuis Ultimate, il n’aura plus accès aux données assemblées. Toutes les données précédemment assemblées seront supprimées. Cela signifie que les suites de rapports virtuelles de l’ADC ne refléteront plus aucun assemblage sur plusieurs périphériques. Les données ressembleront à la suite de rapports désassemblée d’origine.
