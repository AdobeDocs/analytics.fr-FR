---
description: valeur nulle
seo-description: valeur nulle
seo-title: Présentation de l'IQ d'attribution
title: Présentation de l'IQ d'attribution
uuid: bb 345642-4 f 45-4 fb 8-82 d 0-803248 dd 52 ea
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Présentation de l'IQ d'attribution

>[!IMPORTANT]
>
>Attribution IQ est disponible pour tous les clients sur les SKU Adobe Analytics Ultimate, Prime, Select et Foundation.

## Valeur ajoutée de l’Attribution IQ {#section_E82B97114E1641A8AE911F57AEB3240A}

Le « parcours client » n’est pas linéaire et n’est que partiellement prévisible. Il est plus organique, plus flexible et souvent imprévisible. Chaque client avance à son propre rythme, souvent en revenant en arrière, en ralentissant, en redémarrant, etc. Il est donc difficile de connaître l’impact des efforts de marketing tout au long du parcours client. Il entrave également les efforts visant à relier plusieurs canaux de données pour répondre à des questions commerciales et mène à une connaissance incomplète du client.

L’Attribution IQ d’Adobe Analytics permet aux équipes de renseignement modernes de comprendre comment un engagement significatif se manifeste tout au long du parcours client, en identifiant intelligemment les points d’inflexion qui amènent les clients à cibler les résultats et en optimisant efficacement les initiatives de marketing.

![](assets/attribution_iq_problem.png)

Adobe Analytics améliore l’attribution en vous permettant de :

* définir l’attribution à des médias autres que ceux achetés : tout canal, dimension, mesure ou événement peut être appliqué aux modèles (par exemple, recherche interne) et pas seulement aux campagnes marketing ;
* utiliser la comparaison illimitée de modèles d’attribution : comparez dynamiquement autant de modèles que vous le souhaitez ;
* éviter les changements de mise en œuvre : avec le traitement de la période de rapport et les sessions contextuelles, le contexte du parcours client peut être intégré et appliqué lors de l’exécution ;
* construire la session qui correspond le mieux à votre scénario d’attribution ;
* ventiler l’attribution par segments : comparez facilement la performance de vos canaux marketing sur n’importe quel segment important (par exemple, les nouveaux clients par rapport aux clients réguliers, le produit X par rapport au produit Y, le niveau de fidélité ou la valeur vie client (CLV)) ;
* inspecter le croisement des canaux et l’analyse multi-touch : utilisation des histogrammes et diagrammes de Venn ainsi que des résultats de l’attribution des tendances ;
* analyser visuellement des séquences marketing importantes : explorez les chemins d’accès qui ont mené à la conversion sur le plan visuel par le biais de visualisations à plusieurs nœuds de flux et d’abandons ;
* créer des mesures calculées : utilisez n’importe quel nombre de méthodes d’attribution.

## Que fait l’Attribution IQ ? {#section_63B421E9E75B4CCEBA96726CAA37D73E}

L’Attribution IQ dans Analysis Workspace vous permet d’ajouter de nombreux nouveaux types de modèles d’attribution aux tableaux à structure libre, aux visualisations et aux mesures calculées. Tous les modèles d’attribution ont deux composants :

* Un **modèle d’attribution** (c.-à-d., Première touche, Dernière touche, Linéaire, etc.). Le modèle décrit la distribution des conversions pour les accès dans un groupe.
* Un **intervalle de recherche en amont des attributions** (c.-à-d., des visites ou des visiteurs). L’intervalle de recherche en amont décrit les groupes d’accès pris en compte pour chaque modèle.

L’exemple de parcours client suivant représente les points de contact marketing d’un visiteur unique couvrant trois visites, trois conversions et quatre canaux marketing (recherche, display, social et courrier électronique) :

![](assets/attribution_example.png)

## Attribution fondée sur l’instance {#section_A81DBC3B19014CE3894131F1CF72736F}

L’attribution dans Analysis Workspace utilise « l’instance » de n’importe quelle dimension, ce qui signifie que les modèles d’attribution sont appliqués aux valeurs qui ont été transmises dans Analytics (après les règles de traitement, VISTA et les règles de traitement des canaux marketing). En réalité, cela signifie qu’il n’y a pas de différence entre une prop ou une eVar (ou toute autre dimension) pour la modélisation de l’attribution. Les props peuvent être définies pour être conservées en utilisant un des intervalles de recherche en amont ou modèles ci-dessous. Les paramètres d’attribution et d’expiration pour les eVars ne sont pas utilisés (comme spécifié dans les paramètres d’administration) lorsque les intervalles de recherche en amont ou modèles d’attribution sont appliqués.

## Intervalle de recherche en amont des attributions {#section_A2782BB64171431EB370CDCD4AD8030D}

L’intervalle de recherche en amont des attributions est un groupe d’accès auquel un modèle d’attribution sera appliqué. Il y a deux paramètres d’intervalle de recherche en amont des attributions dans Analysis Workspace : les visites et les visiteurs.

**Intervalle de recherche en amont des visites**

L’intervalle de recherche en amont des visites correspond à toute séquence d’activité séparée par 30 minutes d’inactivité par défaut. Toutefois, les [sessions contextuelles](https://marketing.adobe.com/resources/help/en_US/reference/vrs-mobile-visit-processing.html) sont également prises en charge via le [traitement de la période de rapport](https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html) si vous préférez modifier ce paramètre par défaut. Si vous utilisez l’intervalle de recherche en amont des attributions des visites dans une suite de rapports virtuelle à l’aide d’une session personnalisée, l’intervalle de recherche en amont des attributions utilisera la définition de visite personnalisée comme base de calcul. Dans l’exemple ci-dessus, chaque visite serait considérée comme une recherche en amont indépendante des attributions.

**Intervalle de recherche en amont des visiteurs**

L’intervalle de recherche en amont des visiteurs prendra en compte la totalité des accès d’un visiteur dans le créneau de rapport de votre panneau Espace de travail, plus les mois complets qui englobent le créneau du rapport. Par exemple, si la période du créneau de rapport s’étend du 15 au 30 septembre, la période de recherche en amont des visiteurs serait du 1er au 30 septembre. Pour plus d’informations concernant l’intervalle de recherche en amont des visiteurs, veuillez vous référer à la section [Données apparaissant hors du créneau de rapport](https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html).

**Exemple d’intervalle de recherche en amont des attributions**

Pour illustrer l’impact des intervalles de recherche en amont de l’attribution, nous appliquerons un modèle linéaire (qui accorde le même crédit à tous les points de contact) à notre exemple ci-dessus :

Lorsque vous utilisez **l’intervalle de recherche en amont des attributions des visites**, la conversion de chaque visite est distribuée indépendamment :

* Le/$ 10 de la première visite serait fractionné uniformément entre Search, Display, Social et Email, chacun recevant/$ 2,50.
* Lors de la deuxième visite, la recherche et le courrier électronique reçoivent chacune la moitié de la conversion/$ 5. Par conséquent, Courriel et Recherche reçoivent chacun un autre/2,50 $.
* Enfin, lors de la dernière visite, Email recevra tout le crédit pour la conversion/$ 2.

Dans **l’intervalle de recherche en amont des visiteurs**, toutes les conversions sont traitées ensemble, mais le calcul est légèrement plus complexe en raison du fait qu’il y a plusieurs conversions.

* La conversion initiale/$ 10 serait divisée uniformément entre Search, Display, Social et Email.
* La conversion deuxième/$ 5 serait ensuite divisée entre les canaux présents dans cette visite ainsi que les canaux précédents de la visite précédente : Search = (2/6) */$ 5 =/$ 1.67, Display = (1/6) */$ 5 =/$ 0.83, Social = (1/6) */$ 5 =/$ 0.83, Email = (2/6) */$ 5 =/$ 1.67.
* Enfin, la dernière conversion serait fractionnée sur tous les canaux du visiteur : Search = (2/2/) */$ 2 =/$ 0.57, Display = (1/7) */$ 2 =/$ 0.29, Social = (1/7) */$ 2 =/$ 0.29, Email = (3/7) */$ 2 =/$ 0.86.

Voici un résumé des résultats sous forme de tableau :

| Canal | Recettes (linéaire/visite) | Recettes (Linéaire/Visiteur) |
|---|---|---|
| Outils | /$5.00 | /$4.74 |
| Display | /$2.50 | /$3.62 |
| Social | /$2.50 | /$3.62 |
| Courrier électronique | /$7.00 | /$5.02 |
| Total | /$17.00 | /$17.00 |

Cette différence dans l’intervalle de recherche en amont des attributions fonctionne de la même manière avec tous les modèles d’attribution décrits ci-dessous.

## Modèles d’attribution {#section_4B9E7F83AE0B451A992397E55C3F5871}

Analysis Workspace prend en charge dix modèles d’attribution différents : Première touche, Dernière touche, Même touche, Linéaire, En forme de U, En forme de J, En forme de J inversé, Décroissance temporelle, Participation et Personnalisé. Les détails de chaque modèle, accompagnés d’exemples, sont présentés ci-dessous :

<table id="table_A3EB34CD52314F0393FF0D12E5F9779D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Icône de l’interface utilisateur </th> 
   <th colname="col2" class="entry"> Modèle d’attribution </th> 
   <th colname="col3" class="entry"> Définition </th> 
   <th colname="col4" class="entry"> Conditions d’utilisation </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/last_touch.PNG" id="image_7D574182B1564109B0F1C3DD4FD9E8E9" /> </p> </td> 
   <td colname="col2"> <p>Dernière touche </p> </td> 
   <td colname="col3"> <p>Le modèle Dernière touche attribue 100 % du crédit au point de contact survenant immédiatement avant la conversion. Dans le cas ci-dessus, le canal Courrier électronique obtiendrait le crédit pour l’intégralité des 17 $ dans une visite ou une recherche en amont des visiteurs car le canal Courrier électronique est survenu juste avant les trois conversions. </p> </td> 
   <td colname="col4"> <p>Il s’agit du modèle d’attribution le plus élémentaire et le plus courant et il est fréquemment utilisé pour les conversions dont le cycle de traitement est court. </p> <p>Le modèle Dernière touche est couramment utilisé par les équipes qui gèrent le marketing de moteur de recherche ou qui analysent les mots-clés de recherche interne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/first_touch.png" id="image_D8CD48CB39D64A0386CBA38397BB69B0" /> </p> </td> 
   <td colname="col2"> <p>Première touche </p> </td> 
   <td colname="col3"> <p>Le modèle Première touche accorde 100 % du crédit au point de contact survenant en premier dans l’intervalle de recherche en amont des attributions. </p> <p>Dans l’exemple ci-dessus, avec la recherche en amont des visites, les 10 $ + 5 $ = 15 $ seraient attribués au canal Recherche et les 2 $ seraient attribués au canal Courrier électronique. Dans le cas d’une recherche en amont des visites, les 17 $ seraient attribués au canal Recherche car il survient en premier dans tous les accès du créneau de rapport. </p> </td> 
   <td colname="col4"> <p>Il s’agit d’un autre modèle d’attribution commun utile pour l’analyse des canaux marketing destinés à accroître la notoriété de la marque ou à favoriser l’acquisition client. </p> <p>Le modèle Première touche est fréquemment utilisé par les équipes Display ou Marketing social, mais est également utile pour évaluer l’efficacité des recommandations de produits sur site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/same_touch.png" id="image_7E093A65BA4048F0B46E1110D9569C84" /> </p> </td> 
   <td colname="col2"> <p>Même touche </p> </td> 
   <td colname="col3"> <p>Le modèle Même touche accorde 100 % du crédit à l’accès où la conversion a eu lieu. </p> <p>Dans notre exemple ci-dessus, chaque conversion est survenue lors d’un accès ultérieur à partir du point de contact marketing précédent. Ainsi, les 17 $ seraient attribués à l’élément de ligne « Aucun » dans le rapport. </p> </td> 
   <td colname="col4"> <p>Il s’agit d’un modèle utile pour évaluer le contenu ou l’expérience client qui a été présenté immédiatement au moment de la conversion. Les équipes produit ou de conception l’utiliseront souvent pour évaluer l’efficacité d’une page où la conversion a lieu. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/linear.png" id="image_FB96E57837EE47B5B6AE0066CC6DCF45" /> </p> </td> 
   <td colname="col2"> <p>Linéaire </p> </td> 
   <td colname="col3"> <p>Le modèle Linéaire est un modèle multi-touch qui accorde le même crédit à chaque accès précédant une conversion. </p> <p>Dans les scénarios où des commandes multiples surviennent au cours de la même recherche en amont des visites ou des visiteurs, le même crédit est réparti entre tous les canaux qui sont survenus avant la conversion. </p> </td> 
   <td colname="col4"> <p>Ce modèle est utile pour les conversions avec des cycles de traitement plus longs ou des expériences client qui nécessitent un engagement plus fréquent et plus constant de la part des clients. </p> <p>L’attribution linéaire est souvent utilisée par des équipes qui mesurent l’efficacité des notifications d’applications mobiles ou avec des produits sur abonnement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/u_shaped.png" id="image_625BB199056D453E8DA8FA283A990DDD" /> </p> </td> 
   <td colname="col2"> <p>En forme de U </p> </td> 
   <td colname="col3"> <p>Le modèle En forme de U accorde 40 % de crédit à la première interaction, 40 % de crédit à la dernière interaction et partage les 20 % restants entre toutes les interactions intermédiaires. </p> <p>Dans le cas de recherches en amont des attributions avec un seul point de contact, 100 % du crédit est accordé au point de contact unique. Dans les cas où il n’y en a que deux, 50 % du crédit est accordé à chacun. </p> </td> 
   <td colname="col4"> <p>C’est un excellent modèle pour ceux privilégiant les interactions qui sont survenues en premier ou en dernier (introduites ou terminées) dans une conversion, mais qui souhaitent quand même reconnaître les interactions d’assistance. </p> <p>L’attribution En forme de U est souvent utilisée par des équipes qui adoptent une approche plus équilibrée, mais qui veulent accorder plus de crédit aux canaux ayant trouvé ou mis fin à une conversion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/j_shaped.png" id="image_D062FD7277A947BC9802F8BDFC139427" /> </p> </td> 
   <td colname="col2"> <p>En forme de J </p> </td> 
   <td colname="col3"> <p>Le modèle En forme de J accorde 60 % de crédit à la dernière interaction, 20 % de crédit à la première interaction et partage les 20 % restants entre toutes les interactions intermédiaires. </p> <p>Dans le cas de recherches en amont des attributions avec un seul point de contact, 100 % du crédit est accordé au point de contact unique. Dans les cas où il n’y en a que deux, 75 % est accordé au dernier point de contact et 25 % au premier. </p> </td> 
   <td colname="col4"> <p>Semblable au modèle En forme de U, c’est un excellent modèle pour ceux privilégiant les interactions qui sont survenues en premier ou en dernier (introduites ou terminées) dans une conversion, mais qui mettent l’accent sur l’interaction qui s’est terminée lors de la conversion. </p> <p>L’attribution En forme de J est souvent utilisée par des équipes qui adoptent une approche plus équilibrée et qui veulent accorder plus de crédit aux canaux ayant mis fin à une conversion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/inverse_j.png" id="image_20FFD4C9C9714901B3F54C049D129BC6" /> </p> </td> 
   <td colname="col2"> <p>En forme de J inversé </p> </td> 
   <td colname="col3"> <p>Le modèle En forme de J inversé accorde 60 % de crédit à la première interaction, 20 % de crédit à la dernière interaction et partage les 20 % restants entre toutes les interactions intermédiaires. </p> <p>Dans le cas de recherches en amont des attributions avec un seul point de contact, 100 % du crédit est accordé au point de contact unique. Dans les cas où il n’y en a que deux, 75 % est accordé au premier point de contact et 25 % au dernier. </p> </td> 
   <td colname="col4"> <p>Semblable au modèle En forme de U, c’est un excellent modèle pour ceux privilégiant les interactions qui sont survenues en premier ou en dernier (introduites ou terminées) dans une conversion, mais qui souhaitent mettre l’accent sur l’interaction qui a déclenché la conversion. </p> <p>L’attribution En forme de J inversé est souvent utilisée par des équipes qui adoptent une approche plus équilibrée et qui veulent accorder plus de crédit aux canaux ayant déclenché une conversion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/custom.png" id="image_D46A787AC72248C7B28C402F5515B099" /> </p> </td> 
   <td colname="col2"> <p>Personnalisé </p> </td> 
   <td colname="col3"> <p>Le modèle Personnalisé est un modèle basé sur la position qui vous permet de spécifier les coefficients de pondération que vous souhaitez donner à la première interaction (starter), à la dernière (closer) et à celle du milieu (player). </p> <p>Les valeurs spécifiées sont normalisées à 100 % même si les chiffres saisis ne totalisent pas 100. Dans le cas de recherches en amont des attributions avec un seul point de contact, 100 % du crédit est accordé au point de contact unique. Dans les cas où il n’y en a que deux, le paramètre « Player » est ignoré et les première et dernière interactions sont pondérées par les coefficients de pondération des paramètres des modèles « starter » et « closer », normalisés à 100 %. </p> </td> 
   <td colname="col4"> <p>Si votre organisation n’est pas convaincue par les valeurs par défaut fournies par Adobe Analytics, un modèle personnalisé vous permet de spécifier les coefficients de pondération qui conviennent le mieux à votre organisation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/time_decay.png" id="image_7976721B60454944BF516FCF8484D3A2" /> </p> </td> 
   <td colname="col2"> <p>Décroissance temporelle </p> </td> 
   <td colname="col3"> <p>Le modèle Décroissance temporelle suit une décroissance exponentielle avec un paramètre de demi-vie personnalisé (sept jours par défaut). </p> <p>Le coefficient de pondération de chaque canal dépend du temps qui s’est écoulé entre le point de contact et la conversion éventuelle et est déterminé par la formule 2^(-t/demi-vie) où t est le temps entre un point de contact et la conversion. Pour les recherches en amont avec un seul point de contact, 100 % du crédit est accordé au point de contact unique. Pour celles avec deux points de contact, le crédit est proportionnel au temps écoulé depuis la conversion. </p> </td> 
   <td colname="col4"> <p>Il s’agit d’un bon modèle pour les équipes qui exécutent des promotions sur un nombre prédéterminé de jours et qui souhaitent mettre l’accent sur les canaux qui sont survenus plus récemment. </p> <p>L’attribution Décroissance temporelle est souvent utilisée par les équipes qui diffusent de la publicité vidéo ou qui planifient leur stratégie marketing autour d’un événement important dont la date est prédéterminée (comme une conférence ou un événement sportif). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/participation.png" id="image_19DD3CA5C0F24F05835D8522C6708DE4" /> </p> </td> 
   <td colname="col2"> <p>Participation </p> </td> 
   <td colname="col3"> <p>Le modèle Participation accorde 100 % du crédit à tous les points de contact ou canaux uniques dans un intervalle de recherche en amont des attributions. Avec Participation, le nombre total de conversions sera artificiellement élevé dans votre rapport par rapport à d’autres modèles d’attribution. Notez que Participation déduplique les canaux qui surviennent plusieurs fois dans un seul intervalle de recherche en amont des attributions avant d’accorder du crédit. </p> <p>À partir de notre exemple ci-dessus et en fournissant un intervalle de recherche en amont des visiteurs, les canaux Recherche, Display, Social et Courrier électronique recevraient chacun 17 $. En utilisant le même exemple avec un intervalle de recherche en amont des visites, le canal Recherche recevrait 15 $, le Display recevrait 10 $, le Social recevrait 10 $ et le Courrier électronique recevrait 17 $. </p> </td> 
   <td colname="col4"> <p>Ce modèle est excellent pour l’analyse et la découverte afin de comprendre à quelle fréquence vos utilisateurs finaux ou clients sont exposés à une page, à une interaction ou à un canal particulier. </p> <p>Les équipes des médias utiliseront souvent ce modèle pour calculer la vitesse du contenu. Les organisations de vente au détail l’utiliseront souvent pour comprendre quelles parties de leur application ou de leur site web sont dans une phase critique de la conversion. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Canaux marketing et Règles de traitement des canaux marketing {#section_FCBF08A9D7C94B67B7AD76E8633E7916}

Les canaux Première touche et Dernière touche, ainsi que les Détails du canal Première touche et les Détails du canal Dernière touche, peuvent être utilisés avec les nouveaux modèles d’attribution. Afin d’éviter toute confusion pour votre équipe à l’avenir, nous vous recommandons d’utiliser plutôt deux nouvelles dimensions : **Canaux marketing** et **Détails des canaux marketing**. Elles agissent exactement de la même manière, mais ne portent pas dans le nom les distinctions « Première touche » et « Dernière touche » qui peuvent prêter à confusion. Si aucun modèle d’attribution n’est appliqué, les Canaux marketing et les Détails des canaux marketing donneront respectivement les mêmes résultats que le Canal Dernière touche et les Détails du canal Dernière touche.

Lorsque vous appliquez des modèles d’attribution au Canal Première touche ou au Canal Dernière touche, tous les paramètres d’attribution seront remplacés par le modèle d’attribution que vous avez sélectionné. Par conséquent, même si le nom de la dimension peut être « Canal Première touche », si vous avez sélectionné le modèle Linéaire (par exemple), les résultats reflètent l’attribution linéaire et non le canal « Première touche ».

De plus, puisque les variables des canaux marketing dépendent de la visite traditionnelle (telle que définie par les règles de traitement des canaux marketing qui sont appliquées pendant le processus de collecte de données), elles ne peuvent pas être utilisées avec les sessions contextuelles.

## Attribution sur les ventilations de classification {#section_F9DE21758C4643879BE05EEAE9A34E5A}

Les modèles d’attribution peuvent être appliqués à n’importe quelle valeur et à sa classification. Dans les cas où une valeur classée est ventilée par clé, Analytics n’inclura que les clés associées à cette valeur classée particulière. Par exemple, pour un modèle d’attribution linéaire appliqué à une eVar donnée avec les valeurs « pomme », « banane » et « carotte » classées selon les valeurs « Fruits » et « Légumes », où la valeur « Légumes » est ventilée par l’eVar de base, seule la « carotte » apparaît au niveau de la ventilation. De même, les « Fruits » ventilés par l’eVar de base n’indiqueraient que « pomme » et « banane » dans les résultats de la ventilation, même si le crédit d’attribution était réparti sur les trois valeurs eVar de base.

Ce comportement s’applique également aux rapports où les dimensions des canaux marketing sont ventilées selon les dimensions des détails des canaux marketing.

## Attribution des ventilations {#section_B2E87C768B6B4DBFA8EB7DB5E2DF881E}

Analysis Workspace vous permet de ventiler n’importe quelle valeur par toute autre dimension et de spécifier des paramètres d’attribution identiques ou différents lors de la ventilation. Par exemple, l’attribution linéaire peut être appliquée à une dimension de canal, mais la ventilation du canal par campagne vous permet de spécifier un modèle d’attribution différent au niveau de la campagne.

Cela est utile pour les équipes ayant un modèle d’attribution au niveau du canal (pour répartir équitablement entre les canaux), mais qui ont des équipes individuelles souhaitant utiliser un modèle d’attribution distinct pour leurs campagnes individuelles et ayant besoin des totaux de leurs campagnes pour correspondre à ce qui a été attribué au niveau du canal.

## « Aucun » dans Attribution {#section_BC71DA030E45487AA3C3F6ED247A3C4A}

L’attribut « aucun » est un attribut universel représentant toutes les conversions survenues là où il n’existait aucune valeur de dimension. À l’origine, l’attribut « aucun » existait uniquement dans les rapports eVar ou dans d’autres dimensions ayant une persistance. Lors de l’application de modèles d’attribution, un attribut « aucun » peut apparaître là où il n’existait pas auparavant. Cela se produit généralement lors de l’application de modèles d’attribution à des props qui introduisent un attribut « aucun » qui n’était pas présent auparavant.

## Attribution des variables à valeurs multiples

Certaines dimensions dans Analytics peuvent contenir plusieurs valeurs pour un seul accès, telles que les variables de liste (listVars), la variable product, les propriétés de liste (list props) ou l’eVar de marchandisage. Analysis Workspace vous permet d’appliquer l’Attribution IQ à n’importe quel type de ces variables au niveau de l’accès. Exemple de l’utilisation de l’attribution En forme de U (40/20/40) pour une visite unique :

| Nombre d’accès | Variable à plusieurs valeurs | Événement de conversion | Pourcentage de crédit pour l’accès (en forme de U) |
|--- |--- |---|---|
| 1 | A,B,C | - | 40 % |
| 2 | D | - | 20 % |
| 3 | E,F | 1 | 40 % |

Dans ce cas, A, B et C étaient tous définis au même moment sur l’accès 1, D était défini seul sur l’accès 2, tandis que E et F étaient définis sur l’accès 3.

L’Attribution IQ donne l’intégralité du crédit de pourcentage pour l’accès à toute valeur présente sur cet accès. Dans notre exemple précédent, A, B et C recevront 40 % ou 0,4 conversion, D recevra 20 % ou 0,2 conversion, alors que E et F recevront chacun 40 % des conversions ou 0,4. Un rapport utilisant l’attribution En forme de U sur les accès ci-dessus ressemblerait à celui ci-dessous :

| Variable à plusieurs valeurs | Conversions (forme U/Visite) |
|--- |---|
| A | .4 |
| B | .4 |
| C | .4 |
| D | .2 |
| E | .4 |
| F | .4 |
| Total | 1 |

>[!NOTE]
>En raison de l'allocation au niveau de l'accès des modèles d'attribution, la somme de chaque élément de ligne de votre rapport peut ne pas être égale au total dû à chaque valeur recevant le crédit total du crédit appartenant à l'accès dans lequel il était contenu.