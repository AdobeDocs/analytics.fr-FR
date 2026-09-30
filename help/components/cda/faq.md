---
title: FAQ sur les analyses entre appareils
description: Questions fréquentes sur l’analytics sur plusieurs appareils
exl-id: 7f5529f6-eee7-4bb9-9894-b47ca6c4e9be
feature: CDA
role: Admin
TQID: 'https://experienceleague.adobe.com/tdOmNG-s2F-KOq9fCMILkovykm3gknjnS-8JdxiGnm4'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
    internal-label: Attribution
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
    internal-label: VRS
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
    internal-label: Visualizations
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
    internal-label: Report suites
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: f99536a1-75c7-4151-a2c8-073630632526
    internal-label: CDA
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '1728'
ht-degree: 96%
---
# Questions fréquentes

{{available-existing-customers}}

+++ Comment utiliser l’analytics sur plusieurs appareils (CDA) pour voir comment les personnes passent d’un type d’appareil à un autre ?

Vous pouvez utiliser une visualisation de [!UICONTROL flux] avec la dimension Type d’appareil mobile.

1. Connectez-vous à Adobe Analytics et créez un projet Workspace vide.
2. Cliquez sur l’onglet Visualisations sur la gauche, puis faites glisser une visualisation de flux vers la zone de travail sur la droite.
3. Cliquez sur l’onglet Composants sur la gauche, puis faites glisser la dimension « Type d’appareil mobile » vers l’emplacement central intitulé « Dimension ou élément ».
4. Ce rapport de flux est interactif. Cliquez sur l’une des valeurs pour développer les flux vers les pages suivantes ou précédentes. Utilisez le menu contextuel pour développer ou réduire des colonnes. Il est également possible d’utiliser différentes dimensions dans le même rapport de flux.

+++

+++ Puis-je voir comment les utilisateurs passent d’une expérience client à une autre (par exemple, d’un navigateur sur ordinateur à un navigateur sur appareil mobile ou à une application mobile) ?

L’utilisation du type d’appareil mobile comme illustré ci-dessus vous permet de voir comment les utilisateurs passent d’un type d’appareil mobile à un type d’appareil de bureau. Toutefois, il ne vous permet pas de distinguer les navigateurs de bureau des navigateurs mobiles. Si vous souhaitez obtenir ces informations, vous pouvez créer une variable personnalisée (une prop ou une eVar, par exemple) qui enregistre si l’expérience s’est produite sur un navigateur de bureau, un navigateur mobile ou une application mobile. Vous pouvez ensuite créer un diagramme Flux comme décrit ci-dessus, à l’aide de la variable personnalisée au lieu de la dimension Type d’appareil mobile. Cela permet de disposer d’une vue légèrement différente du comportement sur plusieurs appareils.

+++

+++ Jusqu’à quelle date dans le passé CDA peut-il rapprocher les visiteurs ?

Le rapprochement entre appareils de CDA s’effectue selon deux processus simultanés.

* Le premier processus, nommé « assemblage dynamique », se produit quand les données arrivent en flux continu dans Adobe Analytics. Pendant le rapprochement dynamique, CDA s’efforce de retraiter les données au niveau de la personne. Cependant, si la personne est inconnue lors du rapprochement en direct, CDA revient à l’identifiant visiteur pour la représenter.

* Le second processus est nommé « relecture ». Au cours de la relecture, les CDA remontent dans le temps et retraitent les données historiques, si possible, au cours dʼun intervalle de recherche en amont spécifié. Cet intervalle de recherche en amont est soit de 1 jour, soit de 7 jours, selon la configuration choisie pour les CDA. Lors de la relecture, CDA tente de retraiter les hits pour lesquels la personne était auparavant inconnue.


+++

+++ Comment CDA gère-t-il les hits avec date et heure ?

Adobe traite les hits avec date et heure comme s’ils avaient été reçus au moment de l’horodatage et non lorsqu’Adobe a reçu le hit. Les hits avec date et heure datant de plus d’un mois ne sont jamais rapprochés, car ils se situent en dehors de la période utilisée par Adobe pour le rapprochement.

+++

+++ Quelle est la différence entre CDA et les identifiants visiteur personnalisés ?

L’utilisation d’un identifiant visiteur personnalisé est une méthode héritée pour connecter les utilisateurs sur plusieurs appareils. Avec un identifiant visiteur personnalisé, vous utilisez la variable [`visitorID`](/help/implement/vars/config-vars/visitorid.md) pour définir explicitement l’identifiant utilisé pour la logique du visiteur. La variable `visitorID` remplace les éventuels identifiants basés sur les cookies en présence.

Les identifiants visiteur personnalisés ont plusieurs effets indésirables que CDA élimine ou réduit au minimum. Par exemple, la méthodologie d’identifiant visiteur personnalisé ne comporte aucune fonctionnalité de [relecture](replay.md). Si un utilisateur s’authentifie au milieu d’une visite, la première partie de la visite s’associe à un autre identifiant visiteur que celui de la seconde partie de la visite. Les identifiants visiteur séparés génèrent un gonflement des visites et des visiteurs. CDA retraite les données historiques afin que les hits non authentifiés soient attribués à la bonne personne.

+++

+++ Puis-je passer des identifiants visiteur personnalisés à CDA ?

Les clients qui utilisent déjà un identifiant visiteur personnalisé peuvent effectuer une mise à niveau vers les analyses entre appareils sans aucune modification de l’implémentation. La variable `visitorID` est toujours utilisée dans la suite de rapports source. Cependant, les analyses entre appareils ignorent la variable `visitorID` dans la suite de rapports virtuelle si un utilisateur s’authentifie.

+++



+++ Comment les analyses entre appareils gèrent-ils les situations où une seule personne a BEAUCOUP d’appareils/d’ECID ?

Dans certains cas, un utilisateur individuel peut s’associer à un grand nombre d’ECID. Cela peut se produire s’il utilise un grand nombre de navigateurs ou d’applications et peut être exacerbé s’il lui arrive régulièrement de supprimer les cookies ou d’utiliser le mode de navigation privé ou incognito du navigateur.

* **Si vous utilisez le groupement basé sur les champs**, le nombre d’appareils est sans importance par rapport à la prop/l’eVar que vous choisissez pour identifier les utilisateurs connectés. Un même utilisateur peut être associé à un nombre indéfini d’appareils sans que cela n’affecte la capacité de CDA à établir des liens entre les appareils.

+++

+++ Quelle est la différence entre la mesure Personnes dans CDA et la mesure Visiteurs uniques en dehors de CDA ?

Les mesures [Personnes](/help/components/metrics/people.md) et [Visiteurs uniques](/help/components/metrics/unique-visitors.md) visent toutes deux à comptabiliser des visiteurs distincts (individus). Toutefois, envisagez la possibilité que 2 appareils différents peuvent appartenir à la même personne. CDA associe les deux appareils à la même personne, tandis que ces deux appareils sont enregistrés en tant que deux « visiteurs uniques » distincts en dehors de CDA.

+++

+++ Quelle est la différence entre la mesure « Appareils uniques » dans CDA et la mesure « Visiteurs uniques » en dehors de CDA ?

Ces deux mesures sont à peu près équivalentes. Des différences entre les 2 mesures se produisent lorsque :

* Un appareil partagé est mappé à plusieurs personnes. Dans ce scénario, un visiteur unique et plusieurs appareils uniques sont comptabilisés.
* Un appareil reçoit du trafic groupé et non groupé provenant du même visiteur. Par exemple, un navigateur génère du trafic groupé identifié + du trafic anonyme historique qui n’a pas été groupé. Dans ce cas, 1 visiteur unique est comptabilisé, tandis que 2 appareils uniques sont comptabilisés.

Voir la rubrique [Appareils uniques](/help/components/metrics/unique-devices.md) pour plus d’exemples et de détails sur son fonctionnement.

+++

+++ Puis-je inclure des mesures Analytics sur l’ensemble des appareils à l’aide de l’API Adobe Analytics 2.0 ?

Oui. Analysis Workspace utilise l’API 2.0 pour demander des données aux serveurs Adobe et vous pouvez afficher les appels d’API qu’Adobe utilise pour créer vos propres rapports :

1. Lors de la connexion à Analysis Workspace, accédez à [!UICONTROL Aide] > [!UICONTROL Activer le débogueur].
2. Cliquez sur l’icône de débogage dans le panneau de votre choix, puis sélectionnez la visualisation souhaitée et l’heure de la requête.
3. Recherchez la demande JSON, que vous pouvez utiliser dans votre appel d’API à Adobe.

+++

+++ Les Analyses entre appareils peuvent regrouper des visiteurs uniques. Peut-il regrouper des visites ?

Oui. Si une personne envoie des hits à partir de deux appareils distincts dans le délai d’expiration de visite de votre suite de rapports virtuelle (30 minutes par défaut), ils sont regroupés au sein de la même visite.

+++

+++ Quel est l’identifiant visiteur ultime utilisé par les Analyses entre appareils ? Puis-je l’exporter à partir d’Adobe Analytics ?

* **Si vous utilisez un graphique d’appareil**, un identifiant personnalisé basé sur la grappe est l’identifiant principal.
* **Si vous utilisez le groupement basé sur les champs**, un identifiant personnalisé basé sur la prop/l’eVar que vous choisissez est l’identifiant principal.

Ces deux identifiants sont calculés par Adobe au moment de l’exécution du rapport, également appelé [Traitement de la période de rapport](../vrs/vrs-report-time-processing.md). La nature du traitement lors de l’exécution du rapport signifie qu’il n’est pas compatible avec Data Warehouse, les flux de données ou les autres fonctionnalités d’export proposées par Adobe.

+++

+++ Comment puis-je passer du graphique d’appareils au groupement basé sur les champs, ou vice versa ?

Passer du graphique d’appareil au groupement basé sur les champs et inversement peut être demandé via l’assistance clientèle. Cependant, la réalisation d’un tel changement peut prendre quelques semaines ou plus encore et *les données historiques regroupées de la méthode précédente sont perdues.*

+++

+++ Comment les limites uniques d’une prop ou eVar utilisée dans un groupement basé sur les champs sont-elles gérées par Adobe ?

Les analyses entre appareils extraient les éléments de dimension des variables avant de les optimiser pour le compte-rendu des performances. Dans le cadre de CDA, vous n’avez pas à vous soucier des limites de valeurs uniques. Cependant, si vous avez essayé d’utiliser cette prop/eVar dans un projet Workspace, vous pouvez toujours voir l’élément de dimension [(Faible trafic)](/help/technotes/low-traffic.md).

+++

+++ Combien de suites de rapports de mon entreprise peuvent être activées pour CDA ?

À compter du 1er mai 2022, toute nouvelle mise en œuvre de CDA sera limitée à un maximum de trois identifiants de suite de rapports (RSID) par client. CDA ne fusionne pas les suites de rapports. Chaque suite de rapports activée pour Analytics sur l’ensemble des appareils doit être entre appareils par nature (contenant des données provenant de plusieurs surfaces telles que le Web bureau, le Web mobile, l’application mobile, etc.).

+++

+++ Si l’ID d’organisation comporte plusieurs sociétés dans différentes zones géographiques, puis-je activer Analytics sur l’ensemble des appareils pour chacune d’entre elles ?

Non. Pour un même ID d’organisation, CDA ne peut être activé que dans une seule zone géographique.

+++

+++ Quels sont les avantages et les inconvénients d’une relecture de sept jours par rapport à une relecture d’un jour ?

L’avantage de la fenêtre de recherche en amont de 7 jours pour la relecture est que CDA peut remonter plus loin dans le temps pour essayer d’associer des événements qui étaient auparavant anonymes à une personne qui s’est connectée plus tard au cours de cette période de 7 jours. Les inconvénients de l’intervalle de recherche en amont de sept jours sont les suivants : 1) la relecture ne s’exécute qu’une fois par semaine et 2) les sept derniers jours peuvent faire l’objet de modifications.

Les avantages de l’utilisation d’une fenêtre de recherche en amont de 1 jour pour la relecture sont les suivants : 1) la relecture est exécutée quotidiennement et 2) seul le jour précédent peut faire l’objet de modifications. L’inconvénient de la fenêtre de recherche en amont de 1 jour est que CDA ne peut revenir que d’un jour en arrière pour essayer d’associer des événements qui étaient auparavant anonymes à une personne qui s’est connectée hier.

+++

+++ Qu’advient-il des données rapprochées dans mes suites de rapports virtuelles CDA si mon entreprise décide de passer d’Analytics Ultimate à une offre inférieure ?

Si un client passe à une version inférieure d’Ultimate, il n’aura plus accès aux données groupées. Toutes les données précédemment regroupées seront supprimées. Cela signifie que les suites de rapports virtuelles CDA ne refléteront désormais plus le rapprochement entre appareils. Les données ressembleront à la suite de rapports d’origine non rapprochée.

+++

+++ Pourquoi le nombre total de hits est-il différent entre ma suite de rapports source et la suite de rapports virtuelle CDA ?

CDA utilise un pipeline de traitement parallèle complexe, avec de multiples composants dépendants. Il faut s’attendre à un écart d’environ 1 % dans le nombre total de hits entre la suite de rapports d’origine et la suite de rapports virtuelle CDA.

+++

+++ Pourquoi la mesure « Personnes identifiées » est-elle surévaluée ?

Le nombre de la mesure « Personnes identifiées » peut être légèrement plus élevé si la valeur de l’identifiant prop/eVar s’exécute dans une [collision de hachage](/help/implement/validate/hash-collisions.md).

Pour le groupement basé sur les champs, la variable personnalisée de lʼidentifiant est sensible à la casse. La valeur de la mesure « Personnes identifiées » peut être considérablement plus élevée si les valeurs des identifiants ne correspondent pas à la casse. Par exemple, si `bob` et `Bob` sont envoyés par une seule et même personne, l’Analyse entre appareils interprète ces deux valeurs comme distinctes.

+++

+++ Lorsque je consulte la prop/eVar d’identifiant, pourquoi la mesure « Personnes non identifiées » affiche-t-elle des valeurs non nulles ?

Cette situation se produit généralement lorsquʼun visiteur génère des hits authentifiés et non authentifiés au cours de la période de reporting. Le visiteur appartient à la fois à « Non identifié » et à « Identifié » dans la dimension [État identifié](/help/components/dimensions/identified-state.md), ce qui entraîne lʼattribution de hits non identifiés à un identifiant. Ce scénario peut évoluer après lʼexécution de la [Relecture](replay.md), en fonction de la fréquence de relecture et du taux de réussite.

+++
