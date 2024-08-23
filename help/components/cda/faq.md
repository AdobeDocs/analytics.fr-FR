---
title: FAQ sur les analyses entre appareils
description: Questions fréquentes sur les analyses entre appareils
exl-id: 7f5529f6-eee7-4bb9-9894-b47ca6c4e9be
feature: CDA
role: Admin
source-git-commit: cfa5cc02ba3a7349b51a904f29bab533c0f1c603
workflow-type: tm+mt
source-wordcount: '1953'
ht-degree: 98%

---


# Questions fréquentes

{{available-existing-customers}}

+++ Comment puis-je utiliser les analyses entre appareils pour voir comment les gens passent d’un type d’appareil à un autre ?

Vous pouvez utiliser une visualisation de [!UICONTROL flux] avec la dimension Type d’appareil mobile.

1. Connectez-vous à Adobe Analytics et créez un projet Workspace vide.
2. Cliquez sur l’onglet Visualisations sur la gauche, puis faites glisser une visualisation de flux vers la zone de travail sur la droite.
3. Cliquez sur l’onglet Composants sur la gauche, puis faites glisser la dimension « Type d’appareil mobile » vers l’emplacement central intitulé « Dimension ou élément ».
4. Ce rapport de flux est interactif. Cliquez sur l’une des valeurs pour étendre les flux aux pages suivantes ou précédentes. Utilisez le menu contextuel pour développer ou réduire des colonnes. Il est également possible d’utiliser différentes dimensions dans le même rapport de flux.

+++

+++ Puis-je voir comment les personnes passent d’une expérience utilisateur à l’autre (par exemple, navigateur de bureau/navigateur mobile/application mobile) ?

L’utilisation du type d’appareil mobile comme illustré ci-dessus vous permet de voir comment les utilisateurs passent d’un type d’appareil mobile à un type d’appareil de bureau. Toutefois, il ne vous permet pas de distinguer les navigateurs de bureau des navigateurs mobiles. Si vous souhaitez obtenir ces informations, vous pouvez créer une variable personnalisée (une prop ou une eVar, par exemple) qui enregistre si l’expérience s’est produite sur un navigateur de bureau, un navigateur mobile ou une application mobile. Vous pouvez ensuite créer un diagramme Flux comme décrit ci-dessus, à l’aide de la variable personnalisée au lieu de la dimension Type d’appareil mobile. Cela permet de disposer d’une vue légèrement différente du comportement sur plusieurs appareils.

+++

+++ Quelle est la durée de regroupement des visiteurs par les analyses entre appareils ?

Lʼassemblage entre appareils des analyses entre appareils (CDA) se produit dans deux processus simultanés.

* Le premier processus, nommé « assemblage dynamique », se produit quand les données arrivent en flux continu dans Adobe Analytics. Pendant lʼassemblage dynamique, les CDA sʼefforcent de retraiter les données au niveau de la personne. Cependant, si la personne est inconnue lors de lʼassemblage dynamique, les CDA reviennent à lʼidentifiant visiteur pour représenter la personne.

* Le second processus est nommé « relecture ». Au cours de la relecture, les CDA remontent dans le temps et retraitent les données historiques, si possible, au cours dʼun intervalle de recherche en amont spécifié. Cet intervalle de recherche en amont est soit de 1 jour, soit de 7 jours, selon la configuration choisie pour les CDA. Au cours de la relecture, les CDA tentent de retraiter les accès où la personne était précédemment inconnue.

* **Si vous utilisez un graphique de l’appareil**, Adobe conserve les mappages du graphique de l’appareil pendant environ 6 mois. Un ECID sans activité depuis plus de six mois est supprimé du graphique. Les données déjà recoupées dans CDA ne sont pas affectées, mais les accès ultérieurs pour cet ECID sont considérés comme une nouvelle personne.

+++

+++ De quelle manière les analyses entre appareils gèrent-elles les accès horodatés ?

Adobe traite les accès horodatés comme s’ils avaient été reçus au moment de l’horodatage et non lorsqu’Adobe a reçu l’accès. Les accès horodatés de plus d’un mois ne sont jamais regroupés, car ils ne sont pas compris dans la plage utilisée par Adobe pour le groupement.

+++

+++ Comment les Analyses entre appareils se comparent-elles à l’identifiant visiteur personnalisé ?

L’utilisation d’un identifiant visiteur personnalisé est une méthode héritée qui permet de [connecter des utilisateurs sur plusieurs appareils](/help/implement/js/xdevice-visid/xdevice-connecting.md). Avec un identifiant visiteur personnalisé, vous utilisez la variable [`visitorID`](/help/implement/vars/config-vars/visitorid.md) pour définir explicitement l’identifiant utilisé pour la logique du visiteur. La variable `visitorID` remplace les éventuels identifiants basés sur les cookies en présence.

Les identifiants visiteur personnalisés ont plusieurs effets secondaires indésirables que les Analyses entre appareils surmontent ou minimisent. Par exemple, la méthodologie d’identifiant visiteur personnalisé ne comporte aucune fonctionnalité de [relecture](replay.md). Si un utilisateur s’authentifie au milieu d’une visite, la première partie de la visite s’associe à un autre identifiant visiteur que celui de la seconde partie de la visite. Les identifiants visiteur séparés génèrent un gonflement des visites et des visiteurs. Les analyses entre appareils indiquent à nouveau les données historiques de sorte que les accès non authentifiés appartiennent à la bonne personne.

+++

+++ Puis-je effectuer une mise à niveau depuis un identifiant visiteur personnalisé vers les analyses entre appareils ?

Les clients qui utilisent déjà un identifiant visiteur personnalisé peuvent effectuer une mise à niveau vers les analyses entre appareils sans aucune modification de l’implémentation. La variable `visitorID` est toujours utilisée dans la suite de rapports source. Cependant, les analyses entre appareils ignorent la variable `visitorID` dans la suite de rapports virtuelle si un utilisateur s’authentifie.

+++

+++ De quelle manière le graphique d’appareil gère-t-il les appareils partagés ?

Dans certains cas, il est possible que plusieurs personnes se connectent à partir du même appareil. Par exemple, un appareil partagé à la maison, des ordinateurs partagés dans une bibliothèque ou un kiosque dans un magasin de vente au détail.

* **Si vous utilisez un graphique d’appareil**, votre capacité à gérer les appareils partagés est limitée. Le graphique d’appareil utilise un algorithme pour déterminer la propriété d’une « grappe » et peut changer chaque fois que cette grappe est publiée. Les utilisateurs de l’appareil partagé dépendent de la grappe à laquelle ils appartiennent.
* **Si vous utilisez le groupement basé sur les champs**, la prop ou l’eVar que vous choisissez pour identifier les utilisateurs connectés remplace d’autres identifiants. Les appareils partagés sont considérés comme des personnes distinctes, même s’ils proviennent du même appareil.

+++

+++ Comment les analyses entre appareils gèrent-ils les situations où une seule personne a BEAUCOUP d’appareils/d’ECID ?

Dans certains cas, un utilisateur individuel peut s’associer à un grand nombre d’ECID. Cela peut se produire s’il utilise un grand nombre de navigateurs ou d’applications et peut être exacerbé s’il lui arrive régulièrement de supprimer les cookies ou d’utiliser le mode de navigation privé ou incognito du navigateur.

* **Si vous utilisez un graphique d’appareil**, les analyses entre appareils limitent à 50 le nombre d’ECID liés à un identifiant utilisateur donné. Si un identifiant utilisateur est associé à un trop grand nombre d’ECID, le graphique d’appareil suppose que l’identifiant utilisateur n’est pas valide et supprime la grappe qui lui est associée. L’identifiant utilisateur est ensuite ajouté à une liste bloquée afin d’éviter qu’il ne soit ajouté à d’autres grappes à l’avenir. Par conséquent, l’identifiant utilisateur n’est pas regroupé sur plusieurs appareils.
* **Si vous utilisez le groupement basé sur les champs**, le nombre d’appareils est sans importance par rapport à la prop/l’eVar que vous choisissez pour identifier les utilisateurs connectés. Un utilisateur unique peut appartenir à un nombre indéfini d’appareils sans que cela ait d’incidence sur la capacité de groupement sur plusieurs appareils des analyses entre appareils.

+++

+++ Quelle est la différence entre la mesure Personnes des analyses entre appareils et la mesure Visiteurs uniques en dehors des analyses entre appareils ?

Les mesures [Personnes](/help/components/metrics/people.md) et [Visiteurs uniques](/help/components/metrics/unique-visitors.md) visent toutes deux à comptabiliser des visiteurs distincts (individus). Toutefois, envisagez la possibilité que 2 appareils différents peuvent appartenir à la même personne. Les analyses entre appareils mappent les 2 appareils à la même personne, tandis que les 2 appareils sont enregistrés en tant que 2 « visiteurs uniques » distincts en dehors des analyses entre appareils.

+++

+++ Quelle est la différence entre la mesure « Appareils uniques » des Analyses entre appareils et la mesure « Visiteurs uniques » hors Analyses entre appareils ?

Ces deux mesures sont à peu près équivalentes. Des différences entre les 2 mesures se produisent lorsque :

* Un appareil partagé est mappé à plusieurs personnes. Dans ce scénario, un visiteur unique et plusieurs appareils uniques sont comptabilisés.
* Un appareil reçoit du trafic groupé et non groupé provenant du même visiteur. Par exemple, un navigateur génère du trafic groupé identifié + du trafic anonyme historique qui n’a pas été groupé. Dans ce cas, 1 visiteur unique est comptabilisé, tandis que 2 appareils uniques sont comptabilisés.

Voir la rubrique [Appareils uniques](/help/components/metrics/unique-devices.md) pour plus d’exemples et de détails sur son fonctionnement.

+++

+++ Puis-je inclure des mesures des Analyses entre appareils à l’aide de l’API Adobe Analytics 2.0 ?

Oui. Analysis Workspace utilise l’API 2.0 pour demander des données aux serveurs Adobe et vous pouvez afficher les appels d’API qu’Adobe utilise pour créer vos propres rapports :

1. Lors de la connexion à Analysis Workspace, accédez à [!UICONTROL Aide] > [!UICONTROL Activer le débogueur].
2. Cliquez sur l’icône de débogage dans le panneau de votre choix, puis sélectionnez la visualisation souhaitée et l’heure de la requête.
3. Recherchez la demande JSON, que vous pouvez utiliser dans votre appel d’API à Adobe.

+++

+++ Les Analyses entre appareils peuvent regrouper des visiteurs uniques. Peuvent-ils regrouper des visites ?

Oui. Si une personne envoie des accès à partir de deux appareils distincts dans le délai d’expiration de visite de votre suite de rapports virtuelle (30 minutes par défaut), ils sont regroupés au sein de la même visite.

+++

+++ Quel est l’identifiant visiteur ultime utilisé par les Analyses entre appareils ? Puis-je l’exporter à partir d’Adobe Analytics ?

* **Si vous utilisez un graphique d’appareil**, un identifiant personnalisé basé sur la grappe est l’identifiant principal.
* **Si vous utilisez le groupement basé sur les champs**, un identifiant personnalisé basé sur la prop/l’eVar que vous choisissez est l’identifiant principal.

Ces deux identifiants sont calculés par Adobe au moment de l’exécution du rapport, également appelé [Traitement de la période de rapport](../vrs/vrs-report-time-processing.md). La nature du traitement de la période de rapport signifie qu’il n’est pas compatible avec Data Warehouse, les flux de données ou d’autres fonctionnalités d’exportation des offres Adobe.

+++

+++ Comment puis-je passer du graphique d’appareils au groupement basé sur les champs, ou vice versa ?

Passer du graphique d’appareil au groupement basé sur les champs et inversement peut être demandé via l’assistance clientèle. Cependant, la réalisation d’un tel changement peut prendre quelques semaines ou plus encore et *les données historiques regroupées de la méthode précédente sont perdues.*

+++

+++ Comment les limites uniques d’une prop ou eVar utilisée dans un groupement basé sur les champs sont-elles gérées par Adobe ?

Les analyses entre appareils extraient les éléments de dimension des variables avant de les optimiser pour le compte-rendu des performances. Vous n’avez pas à vous inquiéter des limites uniques à des fins d’analyses entre appareils. Cependant, si vous avez essayé d’utiliser cette prop/eVar dans un projet Workspace, vous pouvez toujours voir l’élément de dimension [(Faible trafic)](/help/technotes/low-traffic.md).

+++

+++ Combien de suites de rapports de mon entreprise peuvent être activées pour Analytics sur l’ensemble des appareils ?

À compter du 1er mai 2022, toute nouvelle implémentation d’Analytics sur l’ensemble des appareils sera limitée à un maximum de trois identifiants de suite de rapports (RSID) par client. Les analyses entre appareils ne fusionnent pas les suites de rapports. Chaque suite de rapports activée pour les analyses entre appareils doit être de nature multi-appareils (contenant des données provenant de plusieurs surfaces telles que le web pour ordinateur, le web mobile, l’application mobile, etc.).

+++

+++ Si l’ID d’organisation comporte plusieurs sociétés dans différentes zones géographiques, puis-je activer Analytics sur l’ensemble des appareils pour chacune d’entre elles ?

Non. Pour le même ID d’organisation, une seule zone géographique peut avoir Analytics sur l’ensemble des appareils activé.

+++

+++ Quels sont les avantages et les inconvénients d’une relecture de sept jours par rapport à une relecture d’un jour ?

L’avantage de l’intervalle de recherche en amont de la relecture de sept jours est que les analyses entre appareils peuvent revenir plus loin dans le temps pour essayer d’associer des événements qui étaient alors anonymes à une personne qui s’est connectée plus tard au cours de ces sept jours. Les inconvénients de l’intervalle de recherche en amont de sept jours sont les suivants : 1) la relecture ne s’exécute qu’une fois par semaine et 2) les sept derniers jours peuvent faire l’objet de modifications.

Les avantages à utiliser l’intervalle de recherche en amont de la relecture en un jour sont les suivants : 1) la relecture s’exécute tous les jours et 2) seulement le jour d’avant peut faire l’objet de modifications. L’inconvénient de l’intervalle de recherche en amont d’un jour est que les analyses entre appareils ne peuvent revenir qu’un jour en arrière pour essayer d’associer des événements qui étaient alors anonymes à une personne qui s’est connectée hier.

+++

+++ Qu’advient-il des données regroupées dans mes suites de rapports virtuelles des analyses entre appareils si mon entreprise décide de passer à une version inférieure d’Analytics Ultimate ?

Si un client passe à une version inférieure d’Ultimate, il n’aura plus accès aux données groupées. Toutes les données précédemment regroupées seront supprimées. Cela signifie que les suites de rapports virtuelles des analyses entre appareils ne reflèteront plus aucun regroupement entre appareils. Les données ressembleront à la suite de rapports non regroupés originale.

+++

+++ Pourquoi le nombre total dʼaccès est-il différent entre ma suite de rapports source et la suite de rapports virtuelle CDA (Cross-Device Analytics, Analyses entre appareils) ?

Les analyses entre appareils utilisent un pipeline de traitement parallèle complexe, avec de multiples composants dépendants. Il faut sʼattendre à une discordance de données dʼenviron 1 % pour le nombre total dʼaccès entre la suite de rapports dʼorigine et la suite de rapports virtuelle dʼAnalytics sur lʼensemble des appareils.

+++

+++ Pourquoi la mesure « Personnes identifiées » est-elle surévaluée ?

Le nombre de la mesure « Personnes identifiées » peut être légèrement plus élevé si la valeur de l’identifiant prop/eVar s’exécute dans une [collision de hachage](/help/implement/validate/hash-collisions.md).

Pour le groupement basé sur les champs, la variable personnalisée de lʼidentifiant est sensible à la casse. La valeur de la mesure « Personnes identifiées » peut être considérablement plus élevée si les valeurs des identifiants ne correspondent pas à la casse. Par exemple, si `bob` et `Bob` sont envoyés par une seule et même personne, l’Analyse entre appareils interprète ces deux valeurs comme distinctes.

+++

+++ Lors de lʼaffichage de la variable prop/eVar de lʼidentifiant, pourquoi des valeurs non nulles pour la mesure « Personnes non identifiées » sont-elles présentes ?

Cette situation se produit généralement lorsquʼun visiteur génère des accès authentifiés et non authentifiés dans la fenêtre du compte rendu des performances. Le visiteur appartient à la fois à « Non identifié » et à « Identifié » dans la dimension [État identifié](/help/components/dimensions/identified-state.md), ce qui entraîne lʼattribution dʼaccès non identifiés à un identifiant. Ce scénario peut évoluer après lʼexécution de la [Relecture](replay.md), en fonction de la fréquence de relecture et du taux de réussite.

+++
