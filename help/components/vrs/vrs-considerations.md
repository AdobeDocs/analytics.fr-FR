---
description: Les suites de rapports virtuelles et le balisage multisuite présentent des avantages différents. Découvrez ce qui est le mieux pour votre entreprise.
keywords: Suite de rapports virtuelle
title: Points à prendre en compte concernant le balisage multisuite et les suites de rapports virtuelles
feature: VRS
exl-id: 7e0a1f5b-26ac-438c-b481-33669039efe5
source-git-commit: 6e9ea48df286b2bde6a071ab3d0f29a764382c6d
workflow-type: tm+mt
source-wordcount: '1636'
ht-degree: 79%

---

# Points à prendre en compte concernant le balisage multisuite et les suites de rapports virtuelles

Les suites de rapports virtuelles vous permettent d’afficher les données d’une suite de rapports qui collecte les données de vos propriétés numériques, mais avec un segment appliqué de manière permanente.

Dans de nombreux cas, vous pouvez utiliser des suites de rapports virtuelles pour remplacer le balisage multisuite. Le passage à des suites de rapports virtuelles peut effectivement supprimer la nécessité d’effectuer des [appels au serveur secondaire](/help/admin/admin/c-server-call-usage/overage-overview.md). Par exemple, votre entreprise dispose de 6 sites Web différents, chacun envoyant des données à sa propre suite de rapports, ainsi qu’une suite de rapports globale combinée. Chaque site déclenche un appel au serveur secondaire ; l’un à la suite de rapports de marque individuelle, l’autre à la suite de rapports globale. Au lieu de cela, vous pouvez envoyer des données de tous les sites uniquement à la suite de rapports globale, puis utiliser plusieurs suites de rapports virtuelles pour séparer chaque marque.

Le remplacement du balisage multisuite par une suite de rapports globale et une suite de rapports virtuelle vous permet de simplifier votre mise en oeuvre Adobe Analytics et de réduire la consommation d’appels au serveur. Cette méthode est recommandée comme une bonne pratique. Toutefois, il existe d’importantes limites à prendre en compte pour les suites de rapports virtuelles. Les conseils suivants vous aideront à décider si l’implémentation des suites de rapports virtuelles créées sur une suite de rapports globale est la bonne approche pour vous.

## Instructions

Si vous ne savez pas si les cas d’utilisation décrits s’appliquent à vous et à votre organisation, consultez vos autres administrateurs Adobe Analytics ou votre équipe de compte d’Adobe. Ils peuvent évaluer vos besoins commerciaux et faire une recommandation.

Tenez compte des points suivants lorsque vous déterminez si vous devez utiliser le balisage multisuite ou des suites de rapports virtuelles :

### Publication de segments dans Adobe Experience Cloud

Le partage de segments dans Adobe Experience Cloud n’est pas pris en charge pour les suites de rapports virtuelles. Les utilisateurs qui souhaitent partager un segment dans Experience Cloud doivent avoir accès à la suite de rapports source.

Les segments ne peuvent pas encore être publiés dans Adobe Experience Cloud depuis une suite de rapports virtuelle pour la personnalisation et le ciblage. Tous les utilisateurs qui publient des segments doivent accéder à une suite de rapports source dans ce but. Par exemple, vous souhaitez que les utilisateurs aient uniquement accès aux données de leur région géographique, mais vous souhaitez qu’ils puissent créer et partager des segments d’Adobe Analytics dans Adobe Experience Cloud à des fins de ciblage dans Adobe Target. Dans ce cas, Adobe recommande d’utiliser le balisage multisuite. Si vous n’avez pas peur que les utilisateurs aient accès à la suite de rapports globale ou que vous n’avez pas besoin de publier des segments pour les utiliser dans d’autres solutions, vous pouvez utiliser des suites de rapports virtuelles.

### Limites uniques (faible trafic)

Si vous disposez d’une suite de rapports globale qui regroupe un grand nombre de sites, il est possible que vous rencontriez fréquemment l’élément de ligne [faible trafic](/help/technotes/low-traffic.md). Si vous utilisez le balisage multisuite, le problème se pose uniquement pour la suite de rapports globale (les suites de rapports individuelles risquent moins de voir un faible trafic). Si vous utilisez des suites de rapports virtuelles, des limites uniques sont partagées, ce qui entraîne également un faible trafic pour les suites de rapports individuelles. Pensez à utiliser le balisage multisuite si vous souhaitez éviter de placer des données en faible trafic.

Par exemple, une grande entreprise médiatique possède 100 propriétés web. Chaque propriété publie quelques milliers d’articles par mois, en plus d’héberger tous les articles des mois précédents. Cette organisation utilise une suite de rapports globale dans laquelle eVar1 est le « Nom de l’article ». Supposons que ce rapport contienne environ 5 millions de noms d’article uniques par mois issus des différentes propriétés combinées. Si vous utilisez une suite de rapports virtuelle, seule une partie des 5 millions de valeurs sera incluse dans la suite de rapports virtuelle. Les autres sont inclus sous faible trafic. Si le balisage multisuite est utilisé, chaque suite de rapports individuelle peut voir son propre jeu de valeurs uniques.

L’assistance clientèle d’Adobe peut parfois augmenter les limites de valeur uniques pour un petit nombre de dimensions, ce qui peut éliminer entièrement ce problème. Pour plus d’informations, consultez votre équipe de compte et l’assistance clientèle.

### Variables partagées dans l’ensemble des suites de rapports.

Les suites de rapports virtuelles n’ont pas leur propre jeu de dimensions et de mesures, elles héritent de celles de leur suite de rapports sources. La suite de rapports globale doit capturer toutes les dimensions et mesures de tous les sites Web. Les suites de rapports disposent actuellement d’un maximum de 250 eVars et de 1 000 événements personnalisés.

Des sites différents ont des besoins d’implémentation différents. Certains événements et dimensions peuvent être partagés entre deux sites. Par exemple, une inscription par courrier électronique peut utiliser le même événement sur plusieurs sites Web, déclenchant le même événement personnalisé. D’autres dimensions peuvent être spécifiques à un site. Par exemple, seul l’un de vos sites permet à l’utilisateur de modifier sa photo de profil. Cet événement personnalisé ne serait implémenté que sur le site Web qui le prend en charge.

Assurez-vous que le nombre de dimensions et de mesures uniques peut tenir dans une seule suite de rapports globale. Si vous constatez qu’il existe trop de dimensions ou de mesures uniques, passez en revue chaque dimension dans chaque implémentation. Il y a probablement des chevauchements et des dimensions qui ne sont pas essentiels à la réussite de l’entreprise. Pensez également à utiliser [des classifications](/help/components/classifications/c-classifications.md). Par exemple, au lieu de capturer « Nom du produit » dans eVar5, créez une classification « Nom du produit » en fonction de la dimension du « Produit ». Les classifications d’une suite de rapports source sont automatiquement disponibles pour toutes les suites de rapports virtuelles dépendantes.

>[!TIP]
>
>Avec l’introduction de [traitement](/help/analyze/analysis-workspace/curate-share/curate.md), vous pouvez modifier le nom d’une dimension ou d’une mesure donnée par suite de rapports virtuelle.

### Nuances de segmentation

Une suite de rapports virtuelle à un niveau fondamental est simplement un segment appliqué à une suite de rapports. Les dimensions basées sur les visites et les visiteurs peuvent fournir des résultats de rapport non intuitifs.

Par exemple, vous avez deux sites Web, A et B, qui envoient tous deux des données dans une suite de rapports globale. Certains visiteurs passent inévitablement du site A au site B et ce mouvement de l’un à l’autre est visible dans le cheminement de la suite de rapports globale. Si vous créez des suites de rapports virtuelles pour les sites A et B, une visite qui a commencé sur le site A et s’est terminée sur le site B n’afficherait pas de page d’entrée dans la suite de rapports virtuelle B. La page d’accès de cette visite a commencé sur le site A, qui est segmenté en dehors de la suite de rapports virtuelle.

### Conversion des devises

Les suites de rapports virtuelles ne génèrent pas de rapports dans une devise différente de celle de la suite de rapports sur laquelle elles sont basées. Adobe Analytics ne permet pas de convertir une devise lors de l’exécution des rapports. Le taux de change repose toutefois sur le jour actuel (et ce, même pour les données historiques).

Si votre organisation effectue son analyse dans une seule devise, cela ne pose aucun problème. Cependant, si vous avez un besoin commercial important pour différentes équipes régionales qui doivent consulter les recettes dans leur propre devise locale, envisagez d’utiliser le balisage multisuite.

### Flux de données

Les flux de données ne peuvent pas utiliser de suites de rapports virtuelles. Vous pouvez toutefois recevoir un flux de données d’une suite de rapports globale, puis le séparer.

Les flux de données vous permettent de recevoir une exportation quotidienne ou horaire de toutes vos données Adobe Analytics à un niveau d’accès individuel. Les flux de données ne peuvent pas être présegmentés avant d’être livrés. Vous ne pouvez donc recevoir un flux de données que pour votre suite de rapports globale. Si votre entreprise a un grand besoin de flux de données individuels au niveau d’une marque, d’une propriété, d’une région ou à un autre niveau granulaire, pensez à utiliser le balisage multisuite.

### Connecteurs de données avec comptes partenaires

Certaines intégrations de partenaire Adobe dans Adobe Analytics sont limitées à un compte de partenaire par suite de rapports. Certaines organisations peuvent avoir besoin de plusieurs comptes partenaires pour la même intégration.

Par exemple, un seul DCM Google est autorisé par suite de rapports. De nombreuses entreprises disposent de plusieurs comptes DCM, ce qui permet à différentes marques, unités commerciales et régions de gérer leurs publicités affichées séparément. Les intégrations ne peuvent pas être configurées dans des suites de rapports virtuelles. Si vous disposez de connecteurs de données dépendants avec plusieurs comptes, pensez à utiliser le balisage multisuite.

### Sources de données récapitulatives

Les sources de données récapitulatives vous permettent d’importer des mesures fusionnées dans Adobe Analytics au niveau de la suite de rapports. Étant donné que les chargements de sources de données de résumé contiennent des mesures agrégées *sans identifiant visiteur*, ces sources ne peuvent pas être segmentées dans des conteneurs [!UICONTROL Visite] et [!UICONTROL Visiteur]. La suite de rapports virtuelle utilisant la segmentation, les données importées à l’aide de sources de données récapitulatives ne seront pas disponibles dans les suites de rapports virtuelles si le segment est créé à l’aide d’un conteneur Visite ou Visiteur.

Les sources de données de résumé s’affichent dans la suite de rapports virtuelle si un conteneur Accès est utilisé et si les règles de ce conteneur sont conditionnées pour inclure les informations de la source de données.

>[!TIP]
>
>Les sources de données entièrement traitées prennent en charge la segmentation et peuvent être utilisées dans des suites de rapports virtuelles.

## Procédure à suivre si vous avez décidé d’utiliser la suite de rapports virtuelle

Si vous optez pour la suppression des appels au serveur secondaire au profit des suites de rapports virtuelles :

1. Créez les suites de rapports virtuelles par rapport aux données de vos suites de rapports enfants. Segmenter selon une dimension personnalisée qui distingue vos sites les uns des autres.
   * Si vous effectuez une migration depuis une implémentation balisée multisuite existante, comparez les segments de la suite de rapports virtuelle à vos suites de rapports enfants existantes. Vous devez vous assurer que les données sont comparables avant de déplacer les utilisateurs vers la suite de rapports virtuelle.
   * Une bonne pratique consiste à utiliser [l’empilement des segments](/help/components/segmentation/segmentation-workflow/seg-build.md) afin de pouvoir modifier un segment à un emplacement et de l’appliquer à toutes les suites de rapports virtuelles dépendantes.
   * Utilisez des conteneurs d’accès si vous souhaitez que les suites de rapports virtuelles restent mutuellement exclusives.
2. Une fois que vous avez confirmé la configuration correcte des suites de rapports virtuelles, supprimez les identifiants des suites de rapports secondaires de votre implémentation. Pour supprimer les suites de rapports secondaires :
   * Dans l’extension Adobe Analytics de la collecte de données Adobe Experience Platform, cliquez sur le &quot;x&quot; en regard des suites de rapports que vous ne souhaitez plus utiliser.
   * Dans les implémentations JavaScript héritées, recherchez la variable `s.account` et supprimez les identifiants de suite de rapports que vous ne souhaitez plus utiliser.
   * Dans tous les cas, laissez uniquement l’identifiant de suite de rapports globale/parente pour collecter les données de vos sites et applications.
   * Accédez à Admin > Report Suites et masquez les suites de rapports secondaires qui ne sont plus utilisées.
