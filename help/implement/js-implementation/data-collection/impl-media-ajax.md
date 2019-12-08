---
description: Dans la conception de sites Web, AJAX est un nouveau concept qui utilise plusieurs technologies pour créer et gérer du contenu dynamique sur les pages Web.
keywords: Analytics Implementation
title: Suivi AJAX des applications rich media
topic: Developer and implementation
uuid: ffe6a263-ae18-4875-badb-b3aea3efcb64
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Suivi AJAX des applications rich media

Dans la conception de sites Web, AJAX est un nouveau concept qui utilise plusieurs technologies pour créer et gérer du contenu dynamique sur les pages Web.

Le suivi des interactions utilisateur avec [!UICONTROL AJAX] et d’autres applications multimédias riches est crucial pour le succès des analyses et le retour sur investissement. Ce livre blanc a pour but de fournir des recommandations pour le suivi des applications Internet riches, notamment celles qui utilisent [!UICONTROL AJAX].

## Applications Internet riches (RIA) {#section_CDCAFC4E05B44985BCBF34DFCB35DCA6}

Les applications Internet riches (RIA) sont en train de transformer l’univers du Web. Elles comblent le fossé entre la promesse de technologies à la demande pour le plus grand nombre et les expériences utilisateur réalistes. Les RIA existent et sont développées depuis des années. Le plus grand bond en avant a eu lieu avec l’adoption à grande échelle des navigateurs qui prennent en charge les technologies sous-jacentes avec lesquelles fonctionnent ces applications. Bien que les RIA revêtent différentes formes et utilisent de nombres technologies de support, les plus courantes (et peut-être les plus adoptées) sont AJAX et Flash. Il est important de comprendre que ce qui définit une RIA, c’est son utilisation et son application, et non pas la technologie.

## Eléments pour lesquels effectuer un suivi {#section_E96EC5127E554B8384FD0A7A0B3118DF}

Une des questions les plus courantes concernant les RIA est comment séparer le suivi de l’activité de macroniveau de l’activité de microniveau et dans quels cas effectuer ces deux types de suivi. Imaginons par exemple que votre application permet aux clients de configurer de façon unique un produit. Cette application peut demander aux utilisateurs de suivre des étapes importantes. Ces étapes sont-elles considérées comme des pages vues ? De plus, chaque étape comprend des activités de microniveau. Ces activités doivent-elles être suivies en tant que pages vues ?

Que devez-vous faire si vous souhaitez déterminer le flux entre les activités ou les fonctionnalités qui font l’objet de la plus grande activité ? Le problème des applications Internet riches est qu’elles sont uniques. Elles sont conçues pour imiter des actions réalistes, et comme les actions dépendent de la situation, les possibilités sont infinies. La plupart des applications ont toutefois quelques composants majeurs : étapes majeures, fonctionnalités et actions de microniveau au sein des fonctionnalités. Bien que chaque application doit être étudiée pour déterminer quels éléments doivent être tout particulièrement mesurés, certaines généralisations peuvent être appliquées au suivi des RIA.
En règle générale, l’activité de microniveau représente le chargement de l’application, qui fournit des informations sur les visites, les visiteurs, les instances, la valeur des actions futures, etc. Elle peut, et doit également représenter les étapes majeures du processus. Si une action de RIA modifie l’application à plus de 50 % (ou tout pourcentage considéré comme modifiant de façon significative l’expérience utilisateur ou le contenu), il s’agit alors d’une activité de macroniveau et elle doit être suivie en tant que page vue. L’activité de microniveau comprend toute modification inférieure à 50 % (ou qui n’est pas considérée comme modifiant de façon significative l’expérience utilisateur ou le contenu). Modifier les sélections de couleur, par exemple, est considéré comme une activité de microniveau. Adobe conseille que le suivi de microniveau soit lié aux fonctionnalités. Dans le cas d’un changement de couleurs par exemple, est-il important de déterminer les couleurs qui ont été envisagées ou est-il plus important de savoir quelle fonctionnalité de sélection de couleur a été utilisée ? Ces deux éléments peuvent être importants. Si c’est le cas, capturez les deux. Lorsque vous mesurez l’efficacité d’une RIA, considérez l’activité de niveau fonctionnalité comme étant la plus précieuse.

L’activité de microniveau doit être suivie en tant que liens personnalisés avec des éléments spécifiques mesurés via des variables de trafic associées (props et eVars si l’utilisation doit être mesurée par rapport aux événements de succès). Ce suivi permet de s’assurer que les pages vues n’augmentent pas en raison de l’activité de microniveau. Il permet en outre d’analyser le chemin par le biais de la variable de trafic.

## Eléments à analyser {#section_56824EF675874BA99127A566F6B1383F}

Il est important de déterminer l’efficacité avec laquelle votre RIA concoure au succès. Le succès est généralement mesuré par le biais des conversions. Une analyse de macroniveau donne un aperçu de l’efficacité globale de la RIA. Une analyse de microniveau peut donner quant à elle un aperçu des fonctionnalités qui engendrent des conversions.

Vous devez mesurer l’efficacité de votre RIA. Il s’agit d’une analyse de l’activité de microniveau par rapport aux macromesures de la RIA. Les utilisateurs suivent-ils plus d’étapes que nécessaires pour atteindre le même objectif ? Les mesures de l’analyse peuvent inclure l’activité des visites/fonctionnalités, l’activité des pages vues/fonctionnalités, l’activité des visiteurs/fonctionnalités, etc.

Effectuez l’analyse sur le flux du chemin et les abandons. Les utilisateurs évitent-ils la RIA et trouvent-il un autre chemin pour atteindre l’objectif ? Exécutez des rapports sur les abandons conçus autour du site et du flux de la RIA. Effectuez une analyse du chemin à partir des pages d’entrées pour déterminer les vrais modèles de trafic. Examinez les obstacles et les facteurs incitatifs pour guider les utilisateurs vers l’objectif.

## Mesures proposées {#section_AB7047D6C74740C6B6E47ED93602DB07}

* Visites de la RIA
* Visiteurs de la RIA
* Pages vues de la RIA
* Activité des fonctionnalités de la RIA (liens personnalisés) : mesure l’activité des clics par fonctionnalité

## Analyses proposées {#section_5BE0FB9ECA3049E5965BEAD733DA5B6E}

* Activité des fonctionnalités de la RIA / Pages vues de la RIA
* Activité des fonctionnalités de la RIA / Visites de la RIA
* Pages vues de la RIA / Mesure de succès - Taux de conversion : mesure l’efficacité de l’application
* Activité totale de la RIA / Mesure de succès - Taux de conversion : mesure l’efficacité de l’application
* Activité des fonctionnalités de la RIA / Mesure de succès - Taux de conversion : mesure l’efficacité de l’application
* Flux du chemin vers et à partir de la RIA
* Taux d’abandon par le biais du processus de conversion de la RIA

