---
description: Les suites de rapports virtuelles peuvent être utilisées pour remplacer le balisage multisite. Par exemple, au lieu d’envoyer des données à deux suites de rapports distinctes, vous pouvez les envoyer à une suite de rapports et utiliser des suites de rapports virtuelles pour limiter l’accès aux données des utilisateurs. Toutefois, l’accès aux données est l’une des raisons pour lesquelles il est intéressant d’utiliser des suites de rapports distinctes. Examinez attentivement les cas d’utilisation suivants avant d’apporter des modifications d’implémentation en ce qui concerne les suites de rapports virtuelles.
keywords: Suite de rapports virtuelle
seo-description: Les suites de rapports virtuelles peuvent être utilisées pour remplacer le balisage multisite. Par exemple, au lieu d’envoyer des données à deux suites de rapports distinctes, vous pouvez les envoyer à une suite de rapports et utiliser des suites de rapports virtuelles pour limiter l’accès aux données des utilisateurs. Toutefois, l’accès aux données est l’une des raisons pour lesquelles il est intéressant d’utiliser des suites de rapports distinctes. Examinez attentivement les cas d’utilisation suivants avant d’apporter des modifications d’implémentation en ce qui concerne les suites de rapports virtuelles.
seo-title: Considérations sur le balisage global des suites de rapports virtuelles et de balisage global/multi-suite
solution: Analytics
title: Considérations sur le balisage global des suites de rapports virtuelles et de balisage global/multi-suite
topic: Reports and Analytics
uuid: f 17 d 3659-a 5 b 1-4807-a 01 d-a 1 b 422009 a 64
translation-type: tm+mt
source-git-commit: 800d4ed34a816bd331b339295dc3acd2a03a2cd5

---


# Considérations sur le balisage global des suites de rapports virtuelles et de balisage global/multi-suite

Les suites de rapports virtuelles vous permettent d’afficher les données d’une suite de rapports qui collecte les données de vos propriétés numériques, mais avec un segment appliqué de façon permanente.

Parce qu’elles fonctionnent comme des suites de rapports et peuvent être affectées à des groupes d’utilisateurs de la même manière que les suites de rapports, les suites de rapports virtuelles peuvent, dans certains cas, être utilisées pour remplacer le balisage multisuite et ainsi supprimer les [appels du serveur secondaire](/help/admin/c-server-call-usage/overage-overview.md). (Le balisage multi-suite est défini comme la capacité d'envoyer des données à plusieurs suites de rapports à l'aide d'une seule demande d'image.) Par exemple, au lieu d’envoyer des données pour deux de vos marques en deux suites de rapports « enfants » séparées, plus une suite de rapports « globale » où les données entre les marques sont rassemblées, vous pouvez envoyer les données des deux marques uniquement à la suite de rapports globale. Vous pouvez ensuite utiliser les suites de rapports virtuelles pour limiter l’accès des utilisateurs aux données (par marque) en répliquant les suites de rapports enfants.

Le remplacement d’un balisage multisuite par une suite de rapports globale et une suite de rapports virtuelle vous permet de simplifier votre implémentation Adobe Analytics et de réduire la consommation d’appel du serveur. Cela est généralement recommandé comme une meilleure pratique. Toutefois, il existe des limitations importantes des suites de rapports virtuelles que vous devez envisager si vous décidez d’utiliser le balisage multisuite ou une suite de rapports globale et une suite de rapports virtuelle. Les conseils suivants vous aideront à décider si l’implémentation des suites de rapports virtuelles créées sur une suite de rapports globale est la bonne approche pour vous.

## Instructions

>[!NOTE]
>
> Les considérations suivantes s'appliquent UNIQUEMENT à ces cas :
>
>* Vous envisagez de modifier votre implémentation pour supprimer les suites de rapports enfants et de vous reposer uniquement sur virtual &gt; Report Suites pour contrôler les vues des données pour la fin - Utilisateurs ou
>* Les utilisateurs d’Adobe Analytics au sein de votre entreprise font appel à des suites de rapports virtuelles comme leur principal affichage de données.


Si vous ne savez pas si les cas d’utilisation décrits s’appliquent à vous et à votre organisation, consultez vos autres administrateurs Adobe Analytics ou votre équipe de compte Adobe. Ils peuvent évaluer vos besoins commerciaux et faire une recommandation.

L’utilisation des suites de rapports virtuelles pour remplacer le balisage multisuite est recommandée si :

## La publication de segments d’Adobe Analytics sur le reste d’Adobe Experience Cloud n’est nécessaire qu’au niveau de la suite de rapports globale et tous les utilisateurs qui publient des segments ont accès à la suite de rapports globale.

Résumé :

* Le partage de segments dans Adobe Experience Cloud n’est pas pris en charge pour les suites de rapports virtuelles.
* Les utilisateurs qui doivent pouvoir partager un segment dans Experience Cloud doivent avoir accès à la suite de rapports (parent ou enfant).

Actuellement, les segments ne peuvent pas être publiés dans Adobe Experience Cloud depuis une suite de rapports virtuelle pour la personnalisation et le ciblage. Tous les utilisateurs qui publient des segments doivent accéder à une vraie suite de rapports dans ce but. Une approche par balisage multisuite crée des suites de rapports enfants au niveau d’une marque, d’une propriété, d’une région, etc. Cela permet aux utilisateurs qui n’ont pas accès à la suite de rapports globale de publier des segments uniquement sur le jeu de données qui leur est accessible dans la suite de rapports enfant.

Par exemple, les utilisateurs ont accès seulement aux suites de rapports virtuelles, mais vous souhaitez qu’ils puissent créer et partager des segments d’Adobe Analytics dans Adobe Experience Cloud à des fins de ciblage dans Adobe Target. Dans ce cas, ces utilisateurs ne pourront pas publier des segments et vous devez envisager d’utiliser le balisage multisuite pour vous assurer que les utilisateurs peuvent publier des segments.

## Vous n’avez pas besoin de rapports en temps réel (ou « Données actives ») au niveau de la suite de rapports virtuelle.

Résumé :

* Les rapports en temps réel ne sont pas pris en charge dans les suites de rapports virtuelles, car les données sont segmentées.
* Les « données actives » ne sont pas prises en charge dans les suites de rapports virtuelles, car elles ne prennent pas en charge la segmentation.

[Les rapports en temps réel](/help/admin/admin/realtime/t-realtime-admin.md) et [les « Données actives »](../../technotes/latency.md) ne sont pas disponibles dans les suites de rapports virtuelles. Ces fonctions de Reports &amp; Analytics permettent d’accéder à des types de données limités, en quelques secondes ou minutes. L’une des restrictions de ces vues réside dans le fait qu’elles ne prennent pas en charge la segmentation. En d’autres termes, les données en temps réel dans Reports &amp; Analytics ne peuvent pas être segmentées. Étant donné qu’une suite de rapports virtuelle est générée à l’aide de la segmentation, elle est incompatible avec les rapports en temps réel. Cela affecte les utilisateurs qui réagissent aux tendances rencontrées dans Adobe Analytics en quelques secondes ou quelques minutes de collecte de données, comme le font les éditeurs dans une salle de presse en ajustant les titres selon la consommation de contenu en temps réel. Dans ce cas :

* Envisagez d’utiliser le balisage multisuite pour vous assurer que chaque utilisateur ne voit que les données en temps réel qu’il doit être autorisé à voir, ou
* Accordez à ces utilisateurs l’accès à une vraie suite de rapports (globale) s’ils doivent être autorisés à accéder à votre jeu de données complet.

## Vous ne dépassez pas les limites de valeur uniques pour les dimensions de votre ou vos suites de rapports globales, ou vous ne savez pas si vos utilisateurs verront « Faible trafic » dans leurs suites de rapports virtuelles.

Résumé :

* Les suites de rapports virtuelles n’ont pas leur propre valeur unique pour les dimensions et les héritent de leur suite de rapports parente.
* Si vos utilisateurs d’Adobe Analytics ont besoin d’accéder à toutes les valeurs d’une dimension qui reçoit fréquemment plus de 500 000 valeurs uniques par mois, envisagez de continuer à utiliser la balise multisuite.

Dans les cas de cardinalité élevée (nombre de valeurs uniques d’une dimension donnée, comme les SKU de produits ou les Pages), les éléments Adobe Analytics se voient rarement attribuer des valeurs chaque mois dans une ligne collective « Faible trafic » au sein d’une dimension dans une suite de rapports. Les valeurs comprises dans le segment « Faible trafic » ne peuvent pas être segmentées. Cela permet aux requêtes Adobe Analytics de renvoyer une valeur rapidement, tout en se concentrant sur les 500 000 premiers éléments de ligne qui sont affichés le plus souvent pour la dimension sur vos propriétés numériques. (Par exemple, il peut s’agir de vos 500 000 premiers noms de page.) Vous pouvez en savoir plus sur les limites de valeur uniques [ici](../../technotes/low-traffic.md).

Les suites de rapports virtuelles n’ont pas leur propre ensemble de 500 000 valeurs uniques par dimension et par mois. Si la suite de rapports sur laquelle est basée une suite de rapports virtuelle a dépassé 500 000 valeurs uniques pour une dimension donnée et a commencé à combiner des valeurs de fréquence inférieure dans la ligne « Faible trafic » pour cette dimension, vous pouvez voir « Faible trafic » dans la suite de rapports virtuelle également.

**Exemple**: un conglomérat de médias détient 100 propriétés web. Chaque propriété publie quelques milliers d’articles d’actualités par mois, en plus de l’hébergement de tous les articles des mois précédents. Toutes les propriétés sont combinées dans une suite de rapports globale. Dans la dimension « Nom de l’article » dans la suite de rapports globale, supposons qu’il existe 4 millions de noms d’article uniques chaque mois, issus des différentes propriétés. Les 500 000 premières valeurs qui constituent la majeure partie du trafic sont affichées et peuvent être segmentées, mais les 3,5 millions restantes sont réparties dans l’élément de ligne « Faible trafic ».

Dans ce cas, vous pouvez créer 100 suites de rapports virtuelles pour les équipes qui travaillent sur les propriétés individuelles. Bien que cela soit acceptable, considérez que dans la dimension « Nom de l’article » de chaque suite de rapports virtuelle, les valeurs affichées en tant qu’éléments de ligne distincts ne sont que celles des 500 000 premiers de la suite de rapports globale pour la propriété donnée. Les suites de rapports virtuelles n’atteignent pas leur propre allocation de 500 000 valeurs uniques par dimension. Les valeurs qui s’affichent dans l’élément « Faible trafic » de la suite de rapports globale ne s’affichent pas individuellement dans la suite de rapports virtuelle. Ceci peut entraîner une confusion entre les utilisateurs qui préfèrent voir un ensemble entier de valeurs de dimension dans une suite de rapports virtuelle et ne pas afficher uniquement les valeurs de trafic élevées.

Si vous savez que vous dépassez régulièrement des limites de valeur uniques dans votre suite de rapports globale ou dans vos suites de rapports enfants existantes, pensez à déterminer si les utilisateurs ont besoin d’accéder à ces valeurs rares avant de migrer vers les suites de rapports virtuelles. Si vos utilisateurs ont besoin d’accéder à une valeur unique dans une dimension qui dépasse des limites de valeur uniques dans votre suite de rapports globale, pensez à continuer à utiliser le balisage multisuite pour fournir cet accès.

Sachez également que le service clientèle d’Adobe peut augmenter les limites de valeur uniques d’une suite de rapports globale pour un petit nombre de dimensions, ce qui peut éliminer complètement ce problème. Pour plus d’informations, consultez votre équipe de compte et l’assistance clientèle.

## Vous pouvez utiliser votre jeu de dimensions personnalisées (eVars et props) et des mesures (events) dans votre suite de rapports globale pour suivre tous les points de données essentiels dans toutes les propriétés.

Résumé :

* Les suites de rapports virtuelles n’ont pas leur propre jeu de dimensions et de mesures, elles héritent de celles de leur suite de rapports parente.
* Par conséquent, la suite de rapports parente doit pouvoir capturer toutes les dimensions et mesures pertinentes pour chaque propriété combinée à l’aide uniquement des dimensions personnalisées et des mesures disponibles pour la suite de rapports globale (respectivement 325 et 1 000).

L’un des avantages actuels du balisage multisuite est que vous pouvez autoriser différentes propriétés, marques, régions, etc. pour capturer différents types de données. Par exemple, une unité d’entreprise peut utiliser eVar76 pour capturer des « mots-clés de recherche interne » alors qu’une autre unité d’entreprise peut utiliser cette même classe eVar pour capturer un « Nom de vidéo ». Les groupes sont libres d’implémenter Adobe Analytics selon leurs besoins spécifiques.

Avec une suite de rapports globale, toutes les propriétés doivent transmettre les mêmes points de données dans les mêmes dimensions et mesures. Dans l’exemple précédent, ces deux marques doivent s’aligner sur eVar76 en cours d’utilisation pour les « Mots-clés de recherche interne » ou « Nom de vidéo », puis placer l’autre point de données dans une autre dimension dans leurs implémentations respectives. Cette opération risque d’entraîner la corruption des dimensions et/ou des mesures dans la suite de rapports globale. Cela tend à poser problème dans les situations où diverses propriétés, marques, régions, etc. que vous pouvez prendre en charge (avec des suites de rapports individuelles) utilisent l’intégralité de leur contingent de dimensions ou de mesures personnalisées disponibles. Par conséquent, elles ne pourront pas réserver certaines de leurs dimensions ou métriques aux besoins de suivi d’autres propriétés, marques, régions, etc.

Le nombre maximum de dimensions personnalisées d’Adobe Analytics par suite de rapports est de 325 et le nombre maximum d’événements personnalisés par suites de rapports est égal à 1 000. Le déplacement vers une suite de rapports globale nécessite que tous les points de données critiques de toutes les propriétés numériques soient suivis à l’aide des mêmes 325 dimensions et de 1 000 événements personnalisés.

Si vous rencontrez ce problème et que vous envisagez de passer à une suite de rapports globale avec une suite de rapports virtuelle, consultez les différentes implémentations d’Adobe Analytics dans votre entreprise pour évaluer la quantité de chevauchement/dissonance dans ces implémentations et pour identifier les dimensions ou les mesures qui ne sont pas essentielles à la réussite de l’entreprise. Pensez aussi à utiliser [des classifications](/help/components/c-classifications2/c-classifications.md) dans votre suite globale pour générer des rapports sur les valeurs qui utilisent actuellement leur propre dimension. Les classifications sont automatiquement disponibles pour tous les suites de rapports virtuelles en fonction de cette suite globale. Par exemple, au lieu de capturer « Nom du produit » dans eVar5, créez une classification « Nom du produit » en fonction de la dimension du « Produit ».

Si l’assemblage de ces dimensions et événements personnalisés n’est pas possible, Adobe recommande d’utiliser le balisage multisuite.

>[!IMPORTANT]
>
>With the introduction of [virtual report suite curation](/help/analyze/analysis-workspace/curate-share/curate-projects-vrs.md), you can now change the name of a given dimension or &gt;metric on a per-VRS basis. Si vous segmentez correctement votre suite de rapports virtuelle, cela signifie que vous pouvez maintenant utiliser la même evar, la même variable evar ou l'événement evénement pour capturer différents éléments dans différentes suites de rapports virtuelles. Cependant, la transmission de deux types &gt; différents types de données dans la même dimension ou mesure rend ce point de données pratiquement inutilisable dans la suite de rapports globale. Cela peut également entraîner des problèmes d'attribution, comme dans l'exemple suivant : si un utilisateur reçoit deux valeurs pour evar 10, c'est-à-dire une « Campagne interne » sur la propriété A et l'autre qui est un « Nom de page » sur la propriété B, cela signifie que la réussite est désormais divisée entre les « Campagnes internes » et « Nom de page », qui doit &gt; fonctionner sur différents niveaux. Par conséquent, Adobe ne conseille généralement pas d'utiliser la fonction de traitement de la suite de rapports virtuelle comme solution de contournement &gt; pour ce problème particulier.

## Les segments que vous allez utiliser avec les suites de rapports virtuelles ne divisent pas les données d’une manière susceptible de dérouter les utilisateurs.

Résumé :

* La segmentation de données d’une suite de rapports globale en suites de rapports virtuelles peut créer des résultats nuancés qui risquent de dérouter certains utilisateurs.
* Déterminez l’impact de vos segments dans les suites de rapports virtuelles sur les dimensions et les fonctionnalités, telles que la page d’accès, le domaine de référence, le chemin d’accès, etc.

N’oubliez pas qu’une suite de rapports virtuelle n’est qu’un segment appliqué à une suite de rapports. Toutes les nuances des données segmentées sont prises en compte. Les segments (et par conséquent les suites de rapports virtuelles) peuvent être utilisés pour découper les données de manière non intuitive pour vos utilisateurs Adobe Analytics.

Par exemple, supposons que vous ayez deux marques, A et B, dont les propriétés numériques envoient des données dans une suite de rapports globale. Certains utilisateurs passeront du site web A au site web B, et inversement, et ce mouvement de l’un à l’autre est visible dans le chemin d’accès à la suite de rapports globale. Toutefois, si vous créez des suites de rapports virtuelles pour les marques A et B, les utilisateurs qui accèdent à la suite de rapports virtuelle B peuvent voir des résultats non intuitifs pour certaines dimensions et métriques. Une visite commençant sur la marque A et se terminant sur la marque B n’affiche aucune page d’entrée dans la suite de rapports virtuelle B, car la page d’accès de la visite intersite a commencé sur la marque A, qui est segmentée à partir de cette suite de rapports virtuelle.

Un exemple similaire porte sur le « nombre de visites ». Dans la suite de rapports virtuelle pour la marque B, les utilisateurs peuvent voir des visiteurs qui semblent avoir une deuxième, troisième et quatrième visites, mais aucune première visite. Cela se produit lorsque la première visite du client est pour la marque A et toutes les visites suivantes sont pour la marque B. Les données de la marque A n’étant pas incluses dans la suite de rapports virtuelle, toutes les informations relatives à la première visite, y compris le fait qu’elles se soient produites, ne sont pas incluses dans cette suite de rapports virtuelle.

Adobe recommande d’utiliser le balisage multisuite dans ces scénarios ou dans d’autres situations dans lesquelles une partie du parcours du client peut se produire en dehors d’une suite de rapports virtuelle d’une manière qui peut dérouter vos utilisateurs. Le balisage multisuite vous permet de suivre un parcours au niveau des propriétés dans une suite de rapports globale, mais offre également aux équipes individuelles une vue complète du parcours au niveau des propriétés.

## Vous et vos utilisateurs n’avez pas besoin d’afficher les transactions dans diverses devises nationales.

Résumé :

* Les suites de rapports virtuelles ne peuvent pas actuellement générer de rapports dans une devise différente de celle de la suite de rapports sur laquelle elles sont basées.
* Adobe Analytics ne permet pas de convertir une devise lors de l’exécution des rapports. Le taux de change repose toutefois sur le jour actuel et ce, même pour les données historiques.

Les suites de rapports virtuelles ne peuvent pas actuellement générer de rapports dans une devise différente de celle de la suite de rapports sur laquelle elles sont basées. Si votre société et vos utilisateurs d’Adobe Analytics effectuent leurs analyses dans une seule devise, cela ne pose aucun problème. Toutefois, si vous avez un besoin commercial important pour différentes équipes régionales qui doivent pouvoir visualiser les revenus et les indicateurs similaires dans leur propre devise locale (qui est convertie en fonction du taux de change au moment de la collecte des données), vous devez utiliser le balisage multisuite.

Vous pouvez ainsi envoyer des données dans Adobe Analytics sous différentes devises simultanément. Avec le balisage multisuite, une transaction qui se produit dans la version japonaise de l’application peut être enregistrée dans la suite globale en dollars américains. Elle peut être convertie à partir du yen au taux de change du jour indiqué, mais continue de figurer dans votre suite de rapports sur le Japon en yen.

>[!NOTE]
>
>Bien que les suites de rapports virtuelles ne vous permettent pas de convertir les données de recettes dans une autre devise à un taux d'historique, vous pouvez toujours convertir la devise dans une suite de rapports virtuelle de manière ponctuelle. Vous pouvez appliquer le taux de change &gt; le taux de change à des données historiques en accédant à Composants &gt; Paramètres de rapport.

## Vous pouvez utiliser un seul flux de données pour recevoir toutes les données à partir d’une suite de rapports globale.

Résumé :

* Les flux de données peuvent uniquement être créés en fonction de véritables suites de rapports, et non de suites de rapports virtuelles.
* Vous pouvez toutefois recevoir un flux de données à partir d’une suite de rapports globale puis le diviser par marque, propriété, région, etc.

Les flux de données vous permettent de recevoir une exportation quotidienne ou horaire de toutes vos données Adobe Analytics à un niveau « événement » ou « accès ». Comme les flux de données ne peuvent pas être présegmentés avant de vous être livrés, l’utilisation d’une suite de rapports globale avec des suites de rapports virtuelles signifie que vous ne pouvez recevoir qu’un flux de données pour votre suite de rapports globale. Les flux de données ne sont pas pris en charge par les suites de rapports virtuelles.

Toutefois, vous pouvez configurer autant de flux de données que vous le souhaitez en vous basant sur les vraies suites de rapports. Une fois ces flux de données reçus, vous pouvez les segmenter et les fractionner dans toute configuration utile. Par exemple, après avoir reçu un flux de données pour une suite de rapports globale, vous pouvez charger la partie de ce flux de données relative à votre site web dans un seul entrepôt de données. Vous pouvez charger simultanément la partie appartenant à votre application mobile dans un entrepôt de données différent.

Notez cependant que certains champs précalculés dans le flux de données doivent éventuellement être recalculés après réception. Voir l’article 5 (ci-dessus) pour des exemples de champs susceptibles d’avoir besoin d’être recalculés lors du filtrage d’un flux de données en fonction de certains critères.

Si votre organisation a un fort besoin de flux de données individuels au niveau d’une marque, propriété, région, etc., vous pouvez envisager d’utiliser le balisage multisuite.

## Vous n’utilisez pas une intégration Exchange (connecteurs de données) qui n’autorise qu’un seul compte partenaire par suite de rapports et vous ne souhaitez pas intégrer plusieurs comptes partenaires.

Résumé :

* Certaines intégrations de partenaire Adobe dans Adobe Analytics sont limitées à un compte de partenaire par suite de rapports.
* Certaines sociétés peuvent utiliser plusieurs comptes de partenaire dans Adobe Analytics, ce qui nécessite un balisage multisuite.

Adobe Exchange vous permet d’intégrer d’autres solutions de marketing et de technologie publicitaire avec Adobe Analytics. Parmi les intégrations disponibles, citons la publicité d’affichage, le courrier électronique, le VOC et le centre d’appels. En raison des variations de la collecte, de la présentation et de l’intégration des données, certains partenaires d’Adobe que vous pouvez choisir d’utiliser avec Adobe Exchange ont une limitation d’une instance d’intégration par suite de rapports. Chaque instance est associée à un compte avec le partenaire.

Google DCM est un exemple de cette fonctionnalité. De nombreuses entreprises disposent de plusieurs comptes DCM, qui autorisent différentes marques, unités commerciales, régions, etc. à gérer leurs publicités séparément les unes des autres. Toutefois, lors de l’intégration de DCM avec Adobe Analytics, vous ne pouvez utiliser qu’un seul compte DCM par suite de rapports. Vous ne pouvez pas intégrer chacun de vos différents comptes DCM dans la même suite de rapports. Vous ne pouvez pas non plus configurer une intégration directement dans une suite de rapports virtuelle.

Par conséquent, le balisage multisuite est l’approche recommandée si des équipes différentes de votre entreprise doivent posséder leurs propres données de compte dans Adobe Analytics pour un partenaire Adobe Exchange. Si vous utilisez (ou comptez utiliser) les intégrations Adobe Exchange où différents groupes gèrent différents comptes, vérifiez auprès du partenaire Adobe si plusieurs comptes par suite de rapports sont autorisés.

>[!NOTE]
>
>Le terme « compte » peut signifier des éléments différents à différents fournisseurs. Dans le contexte de la technologie marketing, il n'est généralement pas fait référence à un compte utilisateur individuel mais à un ensemble de services mis à la disposition d'une équipe ou d'une organisation entière. Ainsi, alors que plusieurs noms d'utilisateur se connectent au service d'un partenaire Adobe, tous ces noms d'utilisateur peuvent appartenir au même compte.

>[!NOTE]
>
>Les mesures « pré-clic » (résumées/agrégées) importées à partir d'un partenaire Adobe Exchange ne sont pas disponibles pour la segmentation et peuvent donc ne pas être visibles dans une suite de rapports virtuelle. Voici quelques exemples de mesures de ce type : inclure les courriers électroniques envoyés ou afficher les impressions de publicité, tous deux ayant lieu hors site/hors application et importés dans Adobe &gt; Analytics dans un formulaire agrégé.

## Vous ne pouvez pas utiliser les sources de données récapitulatives au niveau d’une propriété, d’une marque, d’une région, etc. niveau.

Résumé :

* Les « sources de données récapitulatives » vous permettent d’importer des mesures fusionnées dans Adobe Analytics au niveau de la suite de rapports.
* Le déplacement vers une suite de rapports globale avec des suites de rapports virtuelles nécessite que tous les téléchargements de données récapitulatives se produisent dans la suite de rapports globale.

Les « sources de données récapitulatives » vous permettent d’importer des mesures pré-agrégées dans une vraie suite de rapports dans Adobe Analytics. Les exemples de « sources de données récapitulatives » incluent des mesures telles que « Recettes hors ligne » ou « Pages vues » qui ont eu lieu dans une autre solution avant l’implémentation d’Adobe Analytics. Étant donné que les sources de données récapitulatives contiennent des mesures fusionnées, elles ne peuvent pas être segmentées. Par conséquent, elles n’apparaissent pas segmentées dans les suites de rapports virtuelles.

Le balisage multisuite permet à votre entreprise d’importer des mesures agrégées au niveau de la suite de rapports individuelle. Si la marque A souhaite importer des recettes hors ligne, cela peut faire l’objet d’un rapport indépendant de la marque B et ces données s’afficheront dans la suite de rapports de la marque A. La marque B peut faire la même opération. Si votre entreprise utilise ou prévoit d’utiliser des sources de données récapitulatives au niveau d’une propriété, d’une marque, d’une région, etc., vous pouvez envisager d’utiliser le balisage multisuite plutôt que des suites de rapports virtuelles.

## Étapes à suivre si vous avez choisi d’utiliser des suites de rapports virtuelles

Après avoir pris connaissance des considérations ci-dessus, si vous avez décidé de supprimer les appels au serveur secondaire et d’utiliser des suites de rapports virtuelles à la place. Voici ce que vous devez faire :

**Créez d'abord** des suites de rapports virtuelles pour qu'elles correspondent aux données de vos suites de rapports secondaires/enfants. Segmentez sur une dimension personnalisée telle que « marque », « plate-forme », « domaine ». Choisissez une dimension qui facilite la distinction entre une propriété numérique et une autre et appliquez ces segments aux suites de rapports virtuelles.

* Si vous migrez depuis une implémentation de balisage multisuite Adobe Analytics existante, n’oubliez pas de comparer les segments des suites de rapports virtuelles à vos suites de rapports enfants existantes avant de migrer vos utilisateurs. Vous souhaitez vous assurer que les segments utilisés dans les suites de rapports virtuelles sont corrects.

* Si nécessaire, réglez les segments qui sont basés sur les suites de rapports virtuelles.

* Il est recommandé d’[empiler les segments](/help/components/c-segmentation/c-segmentation-workflow/seg-build.md) chaque fois que cela s’avère possible, de sorte que si vous modifiez un segment à un emplacement, ces modifications se répercutent dans toutes les suites de rapports virtuelles qui utilisent ce segment. Si, par exemple, vous souhaitez créer une suite de rapports virtuelle pour les « utilisateurs de mobile en Europe » et une autre pour les « utilisateurs de mobile en Asie », créez un segment pour les utilisateurs de mobile, puis divisez-le entre les utilisateurs européens et asiatiques. Ainsi, si vous mettez à jour la définition des « utilisateurs de mobile », il vous suffit de le faire dans un seul segment, sans avoir à mettre à jour individuellement chaque segment de suite de rapports virtuelle.

* Vous pouvez rechercher des jeux de données mutuellement exclusifs dans vos suites de rapports virtuelles. Par exemple, vous pouvez souhaiter voir « domaine A » et « domaine B » comme des suites de rapports distinctes, et vous ne souhaitez aucun trafic du domaine A dans la suite de rapports du domaine B. Dans ce cas, utilisez un conteneur « accès » pour vos segments.

**Ensuite,** après avoir confirmé que les suites de rapports virtuelles que vous avez créées sont correctement configurées et répondront aux besoins de votre équipe, supprimez les identifiants de suite de rapports secondaires de votre implémentation.

Pour supprimer les suites de rapports secondaires :

* Dans le lancement de la plate-forme Adobe Experience Platform, cliquez sur « x » en regard des suites de rapports que vous ne souhaitez plus utiliser.
* Dans DTM, recherchez la propriété et l’outil Adobe Analytics en question. Dans les champs Identifiant de compte de production et Identifiant de compte intermédiaire, supprimez tous les identifiants de suite de rapports que vous ne souhaitez plus utiliser.
* In legacy JavaScript implementations, locate the `s.account` variable and remove any report suites that you no longer wish to use.

Conservez uniquement les identifiants des suites de rapports globales/parentes afin de collecter les données de vos sites et applications. Dans l’interface Adobe Analytics, vous pouvez masquer les suites de rapports héritées de vos utilisateurs en accédant à Admin &gt; Paramètres de l’entreprise.

Si vous ne parvenez pas à modifier votre mise en œuvre, communiquez avec votre équipe de compte Adobe. Ils peuvent rechercher des moyens de bloquer le traitement par Adobe Analytics des appels au serveur secondaire.