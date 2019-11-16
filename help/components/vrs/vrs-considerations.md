---
description: Les suites de rapports virtuelles et le balisage multi-suite présentent des avantages différents. Découvrez ce qui est le mieux pour votre entreprise.
keywords: Virtual Report Suite,VRS
solution: Analytics
title: Suites de rapports virtuelles et considérations sur le balisage multi-suite
topic: Adobe Analytics
uuid: f17d3659-a5b1-4807-a01d-a1b422009a64
translation-type: tm+mt
source-git-commit: 6c57780d0ecf65669c1a5306dde267f6e48f1cc4

---


# Suites de rapports virtuelles et considérations sur le balisage multi-suite

Les suites de rapports virtuelles vous permettent d’afficher les données d’une suite de rapports qui collecte les données de vos propriétés numériques, mais avec un segment appliqué de façon permanente.

Dans de nombreux cas, vous pouvez utiliser des suites de rapports virtuelles pour remplacer le balisage multi-suite. Le passage à des suites de rapports virtuelles peut effectivement supprimer la nécessité d’effectuer des appels [au serveur](/help/admin/c-server-call-usage/overage-overview.md)secondaire. Par exemple, votre entreprise dispose de 6 sites Web différents, chacun envoyant des données à sa propre suite de rapports, ainsi qu’une suite de rapports globale combinée. Chaque site déclenche un appel serveur secondaire ; l’une à la suite de rapports de marque individuelle, l’autre à la suite de rapports globale. Vous pouvez plutôt envoyer des données de tous les sites uniquement à la suite de rapports globale, puis utiliser plusieurs suites de rapports virtuelles pour séparer chaque marque.

Le remplacement du balisage multi-suite par une suite de rapports globale et une suite de rapports virtuelle vous permet de simplifier votre mise en oeuvre Adobe Analytics et de réduire la consommation d’appels du serveur. Il est recommandé. Toutefois, il y a d'importantes limites à prendre en considération dans la SRV. Les conseils suivants vous aideront à décider si l’implémentation des suites de rapports virtuelles créées sur une suite de rapports globale est la bonne approche pour vous.

## Instructions

Si vous ne savez pas si les cas d’utilisation décrits s’appliquent à vous et à votre organisation, consultez vos autres administrateurs Adobe Analytics ou votre gestionnaire de compte Adobe. Ils peuvent évaluer vos besoins commerciaux et faire une recommandation.

Tenez compte des points suivants lorsque vous déterminez si vous devez utiliser le balisage multi-suite ou des suites de rapports virtuelles :

### Publication de segments dans Adobe Experience Cloud

Le partage de segments dans Adobe Experience Cloud n’est pas pris en charge pour les suites de rapports virtuelles. Les utilisateurs qui souhaitent partager un segment dans Experience Cloud doivent avoir accès à la suite de rapports source.

Les segments ne peuvent pas encore être publiés dans Adobe Experience Cloud à partir d’une suite de rapports virtuelle à des fins de personnalisation et de ciblage. Pour ce faire, tous les utilisateurs qui publient des segments doivent accéder à la suite de rapports source. Par exemple, vous souhaitez que les utilisateurs n’aient accès qu’aux données de leur région géographique, mais vous souhaitez qu’ils puissent créer et partager des segments d’Adobe Analytics vers Adobe Experience Cloud pour le ciblage dans Adobe Target. Dans ce cas, Adobe recommande d’utiliser le balisage multi-suite. Si vous n’avez pas peur que les utilisateurs aient accès à la suite de rapports globale ou que vous n’ayez pas besoin de publier des segments pour les utiliser dans d’autres solutions, vous pouvez utiliser des suites de rapports virtuelles.

### Données en temps réel et actuelles

Les rapports en temps réel ne sont pas pris en charge dans les suites de rapports virtuelles, car les données sont segmentées. Les données actives ne sont pas non plus prises en charge dans les suites de rapports virtuelles, car elles ne prennent pas en charge la segmentation. Ces deux fonctionnalités sont spécifiques aux rapports et analyses.

[Les rapports](/help/admin/admin/realtime/t-realtime-admin.md) en temps réel et les données [](/help/technotes/latency.md) actives ne sont pas disponibles dans les suites de rapports virtuelles. Cela affecte les utilisateurs qui répondent aux tendances affichées dans les rapports et analyses en quelques secondes ou quelques minutes après la collecte des données. Par exemple, il peut s’agir de rédacteurs dans une rédaction qui ajustent les titres en fonction de la consommation de contenu en temps réel. Pensez à utiliser le balisage multi-suite si vous avez des besoins importants en données en temps réel spécifiques à des suites de rapports individuelles. Les données en temps réel et actuelles peuvent toujours être utilisées dans la suite de rapports globale.

### Limites uniques

Si vous disposez d’une suite de rapports globale qui combine un grand nombre de sites, il est possible que vous rencontriez fréquemment l’élément de ligne à [faible trafic](/help/technotes/low-traffic.md) . Si vous utilisez le balisage multi-suite, il s’agit uniquement d’un problème pour la suite de rapports globale (les suites de rapports individuelles risquent moins de voir le trafic faible). Si vous utilisez des suites de rapports virtuelles, des limites uniques sont partagées, ce qui entraîne également un faible trafic pour les suites de rapports individuelles. Pensez à utiliser le balisage multi-suite si vous souhaitez éviter de placer des données dans un environnement à faible trafic.

Par exemple, une grande entreprise de médias possède 100 propriétés web. Chaque propriété publie quelques milliers d'articles mensuels, en plus d'héberger tous les articles des mois précédents. Cette organisation utilise une suite de rapports globale dans laquelle eVar1 est "Nom de l’article". Dans ce rapport, il existe environ 4 millions de noms d’article uniques par mois à partir des différentes propriétés combinées. Si vous utilisez une suite de rapports virtuelle, les 500 000 premières valeurs qui constituent la majeure partie du trafic sont incluses dans les suites de rapports virtuelles ; les 3,5 millions restants sont inclus dans les rubriques à faible trafic. Si le balisage multi-suite est utilisé, chaque suite de rapports individuelle peut voir ses propres valeurs supérieures de 500 000. Les limites uniques des suites de rapports globales sont les mêmes entre l’utilisation du balisage multi-suite et les suites de rapports virtuelles.

Le service à la clientèle d’Adobe peut augmenter les limites de valeurs uniques pour un petit nombre de dimensions, ce qui peut éliminer complètement ce problème. Pour plus d’informations, consultez votre équipe de compte et l’assistance clientèle.

### Variables partagées entre les suites de rapports

Les suites de rapports virtuelles ne possèdent pas leurs propres ensembles de dimensions et de mesures ; ils héritent de ces éléments de leur suite de rapports source. La suite de rapports globale doit capturer toutes les dimensions et mesures de tous les sites Web. Les suites de rapports disposent actuellement d’un maximum de 250 eVars et de 1 000 événements personnalisés.

Différents sites ont des besoins d’implémentation différents. Certains événements et dimensions peuvent être partagés entre deux sites. Par exemple, une inscription par courrier électronique peut utiliser le même événement sur plusieurs sites Web, déclenchant le même événement personnalisé. D’autres dimensions peuvent être spécifiques à un site. Par exemple, seul l’un de vos sites permet à l’utilisateur de modifier sa photo de profil. Cet événement personnalisé ne serait implémenté que sur le site Web qui le prend en charge.

Assurez-vous que le nombre de dimensions et de mesures uniques peut tenir dans une seule suite de rapports globale. Si vous constatez qu’il existe trop de dimensions ou de mesures uniques, passez en revue chaque dimension dans chaque implémentation. Il y a probablement des chevauchements et des dimensions qui ne sont pas essentiels à la réussite de l’entreprise. Pensez également à utiliser [des classifications](/help/components/c-classifications2/c-classifications.md) . Par exemple, au lieu de capturer « Nom du produit » dans eVar5, créez une classification « Nom du produit » en fonction de la dimension du « Produit ». Les classifications d’une suite de rapports source sont automatiquement disponibles pour toutes les suites de rapports virtuelles dépendantes.

> [!TIP] Avec l’introduction du [traitement](/help/analyze/analysis-workspace/curate-share/curate-projects-vrs.md), vous pouvez modifier le nom d’une dimension ou d’une mesure donnée par suite de rapports virtuelle.

### Nuances de segmentation

Une suite de rapports virtuelle à un niveau fondamental est simplement un segment appliqué à une suite de rapports. Les dimensions basées sur les visites et les visiteurs peuvent fournir des résultats de rapport non intuitifs.

Par exemple, vous avez deux sites Web, A et B, qui envoient tous deux des données dans une suite de rapports globale. Certains visiteurs passent inévitablement du site A au site B et ce mouvement de l’un à l’autre est visible dans le cheminement de la suite de rapports globale. Si vous créez des suites de rapports virtuelles pour les sites A et B, une visite qui a commencé sur le site A et s’est terminée sur le site B n’afficherait pas de page d’entrée dans la suite de rapports virtuelle B. La page d’entrée de cette visite a commencé sur le site A, qui est segmenté hors de la suite de rapports virtuelle.

### Conversion des devises

Les suites de rapports virtuelles ne génèrent pas de rapport sur une devise différente de celle de la suite de rapports sur laquelle elles reposent. Adobe Analytics vous permet de convertir une devise lors de l’exécution des rapports, mais le taux de change est basé sur le jour en cours (même pour les données historiques).

Si votre organisation effectue son analyse dans une seule devise, cela ne pose aucun problème. Cependant, si vous avez un besoin commercial important pour différentes équipes régionales qui doivent consulter les recettes dans leur propre devise locale, envisagez d’utiliser le balisage multi-suite.

### Flux de données

Les flux de données ne peuvent pas utiliser de suites de rapports virtuelles. Vous pouvez toutefois recevoir un flux de données d’une suite de rapports globale, puis le séparer.

Les flux de données vous permettent de recevoir une exportation quotidienne ou horaire de toutes vos données Adobe Analytics au niveau d’un accès individuel. Les flux de données ne peuvent pas être présegmentés avant d’être livrés. Vous ne pouvez donc recevoir un flux de données que pour votre suite de rapports globale. Si votre entreprise a un grand besoin de flux de données individuels au niveau d’une marque, d’une propriété, d’une région ou d’un autre niveau granulaire, pensez à utiliser le balisage multi-suite.

### Connecteurs de données avec comptes partenaires

Certaines intégrations de partenaire Adobe dans Adobe Analytics sont limitées à un compte de partenaire par suite de rapports. Certaines organisations peuvent avoir besoin de plusieurs comptes partenaires pour la même intégration.

Par exemple, un seul DCM Google est autorisé par suite de rapports. De nombreuses entreprises disposent de plusieurs comptes DCM, ce qui permet à différentes marques, unités commerciales et régions de gérer leurs publicités affichées séparément. Les intégrations ne peuvent pas être configurées dans des suites de rapports virtuelles. Si vous disposez de connecteurs de données dépendants avec plusieurs comptes, pensez à utiliser le balisage multi-suite.

### Sources de données récapitulatives

Les sources de données récapitulatives vous permettent d’importer des mesures agrégées dans Adobe Analytics au niveau de la suite de rapports. Les transferts de source de données récapitulatives contenant des mesures agrégées, il n’est pas possible de les segmenter. Etant donné que VRS utilise la segmentation, toutes les données importées à l’aide de sources de données récapitulatives ne sont pas disponibles dans les suites de rapports virtuelles. Les sources de données récapitulatives ne sont visibles que dans la suite de rapports source.

> [!TIP] Les sources de données à traitement complet prennent en charge la segmentation et peuvent être utilisées dans des suites de rapports virtuelles.

## Étapes à suivre si vous avez choisi d’utiliser des suites de rapports virtuelles

Si vous optez pour la suppression des appels du serveur secondaire au profit des suites de rapports virtuelles :

1. Créez des suites de rapports virtuelles qui correspondent aux données de vos suites enfants. Segmenter selon une dimension personnalisée qui distingue vos sites les uns des autres.
   * Si vous effectuez une migration depuis une implémentation balisée multi-suite existante, comparez les segments de la suite de rapports virtuelle à vos suites de rapports enfants existantes. Vous devez vous assurer que les données sont comparables avant de déplacer les utilisateurs vers la suite de rapports virtuelle.
   * Il est recommandé d’utiliser l’empilement [des](/help/components/c-segmentation/c-segmentation-workflow/seg-build.md) segments afin de pouvoir modifier un segment à un emplacement et de l’appliquer à toutes les suites de rapports virtuelles dépendantes.
   * Utilisez des conteneurs d’accès si vous souhaitez que les suites de rapports virtuelles restent mutuellement exclusives.
2. Une fois que vous avez confirmé la configuration correcte des suites de rapports virtuelles, supprimez les identifiants des suites de rapports secondaires de votre implémentation. Pour supprimer les suites de rapports secondaires :
   * Dans le lancement d’Adobe Experience Platform, cliquez sur le X en regard des suites de rapports que vous ne souhaitez plus utiliser.
   * Dans la gestion dynamique des balises, recherchez la propriété et l’outil Analytics. Dans les champs ID du compte de production et ID du compte d’évaluation, supprimez les identifiants de suite de rapports que vous ne souhaitez plus utiliser.
   * Dans les implémentations JavaScript héritées, recherchez la `s.account` variable et supprimez les identifiants de suite de rapports que vous ne souhaitez plus utiliser.
   * Dans tous les cas, laissez uniquement l’identifiant de suite de rapports globale/parente pour collecter les données de vos sites et applications.
   * Accédez à Admin &gt; Report Suites et masquez les suites de rapports secondaires qui ne sont plus utilisées.
