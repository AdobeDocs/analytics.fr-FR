---
description: Le traitement du temps de rapport est un paramètre de suite de rapports virtuelle qui permet le traitement des données d'une manière non destructive et rétroactive.
seo-description: Le traitement du temps de rapport est un paramètre de suite de rapports virtuelle qui permet le traitement des données d'une manière non destructive et rétroactive.
seo-title: Traitement du temps passé sur le rapport
title: Traitement du temps passé sur le rapport
uuid: 1 a 1 d 82 ea -8 c 93-43 cc -8689-cdcf 59 c 309 b 1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Traitement du temps passé sur le rapport

Le traitement du temps de rapport est un paramètre de suite de rapports virtuelle qui permet le traitement des données d'une manière non destructive et rétroactive.

>[!NOTE]
>
>Le Traitement du temps de rapport est disponible uniquement pour Analysis Workspace.

Le traitement de la période de rapport affecte uniquement les données de la suite de rapports virtuelle et n’a aucune incidence sur les données ou la collecte de données dans la suite de rapports de base (parente). La différence entre le traitement de la période de rapport et le traitement Analytics classique est plus facile à comprendre à l’aide du diagramme suivant :

![](assets/google1.jpg)

Lors du traitement des données Analytics, les données circulent dans le pipeline de collecte de données et dans une étape de prétraitement qui prépare les données pour la création de rapports. Cette étape de prétraitement applique une logique d’expiration de visite et une logique de persistance des eVars (entre autres) aux données lors de leur collecte. Le principal inconvénient de ce modèle de prétraitement est qu’il nécessite une configuration préalable, avant la collecte des données. Cela signifie, qu’à partir de ce moment-là, les modifications apportées aux paramètres de prétraitement s’appliquent uniquement aux nouvelles données. Cela pose problème si les données n’arrivent pas dans l’ordre ou si les paramètres ont été mal configurés.

Le traitement de la période de rapport est une manière fondamentalement différente de traiter les données Analytics pour la création de rapports. Au lieu de prédéterminer la logique de traitement avant la collecte des données, Analytics ignore le jeu de données pendant l’étape de prétraitement et applique cette logique chaque fois qu’un rapport est exécuté :

![](assets/google2.jpg)

Cette architecture de traitement offre des options de création de rapports beaucoup plus flexibles. Par exemple, vous pouvez modifier le délai de visite de manière non destructive et ces modifications sont répercutées rétroactivement dans la persistance des eVars et les conteneurs de segments, comme si vous aviez appliqué ces paramètres avant la collecte des données. En outre, vous pouvez créer un nombre illimité de suites de rapports virtuelles, chacune avec des options de traitement de la période de rapport différentes, basées sur la même suite de rapports de base (parente), sans modifier les données de cette dernière.

Le traitement de la période de rapport permet également à Analytics d’empêcher les accès en arrière-plan de démarrer de nouvelles visites et permet au [SDK Mobile](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) d’indiquer à la création de rapports de démarrer une nouvelle visite chaque fois qu’un événement de lancement d’application est déclenché.

Les options de configuration suivantes sont actuellement disponibles pour les suites de rapports virtuelles pour lesquelles le traitement de la période de rapport est activé :

<table id="table_C086C5FD10A84A1ABC081F5DE28F802D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Délai de visite </p> </td> 
   <td colname="col2"> <p> Le paramètre Délai de visite définit le délai d’inactivité d’un visiteur unique avant qu’une nouvelle visite ne soit lancée automatiquement. Par défaut, cela prend 30 minutes. Par exemple, si vous définissez le délai de visite sur 15 minutes, un nouveau groupe de visites est créé pour chaque séquence d’accès collectés, séparé par 15 minutes d’inactivité. Ce paramètre impacte non seulement le nombre de visites, mais également la manière dont les conteneurs de segments de visite sont évalués, ainsi que la logique d’expiration de la visite pour les eVars expirant lors de la visite. La réduction du délai de visite augmentera probablement le nombre total de visites dans les rapports, tandis que l’augmentation du délai de visite réduira probablement le nombre total de visites dans les rapports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Paramètres de visite pour les applications mobiles </p> </td> 
   <td colname="col2"> <p> Pour les suites de rapports contenant des données générées par des applications mobiles via les <a href="https://www.adobe.io/apis/cloudplatform/mobile.html" format="html" scope="external">SDK Adobe Mobile</a>, des paramètres de visite supplémentaires sont disponibles. Ces paramètres sont non destructifs et affectent uniquement les accès collectés via les SDK Mobile. Ces paramètres n’ont aucun impact sur les données collectées en dehors du SDK Mobile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Empêcher les accès en arrière-plan de commencer une nouvelle visite </p> </td> 
   <td colname="col2"> <p> Les accès en arrière-plan sont collectés par les SDK Mobile lorsque l’application est dans un état d’arrière-plan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Démarrer une nouvelle visite à chaque lancement d’application </p> </td> 
   <td colname="col2"> <p> En plus du délai de visite, vous pouvez forcer une visite à démarrer chaque fois qu’un événement de lancement d’application est enregistré depuis les SDK Mobile, quelle que soit la fenêtre d’inactivité. Ce paramètre affecte la mesure des visites et le conteneur de segments de visite, ainsi que la logique d’expiration de visite des eVars. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Démarrer une nouvelle visite avec un événement </p> </td> 
   <td colname="col2"> <p>Une nouvelle session démarre lorsqu’un événement est déclenché, qu’une session ait expiré ou non. La session nouvellement créée inclut l’événement à l’origine de son démarrage. De plus, vous pouvez utiliser plusieurs événements pour démarrer une session. Une nouvelle session se déclenche alors si l’un de ces événements est observé dans les données. Ce paramètre aura un impact sur le nombre de visites, sur le conteneur de segmentation des visites et sur la logique d’expiration de visite des eVars. </p> </td> 
  </tr> 
 </tbody> 
</table>

Le traitement de la période de rapport ne prend pas en charge toutes les mesures et dimensions disponibles dans la création de rapports Analytics traditionnelle. Virtual report suites utilizing Report Time Processing are only accessible in Analysis Workspace and will not be accessible in [!UICONTROL Reports &amp; Analytics], Ad Hoc Analysis, Data Warehouse, Report Builder, Data Feeds, or the reporting API.

En outre, le traitement de la période de rapport traite uniquement les données comprises dans la plage de dates de création de rapports (appelée « fenêtrage de dates » ci-dessous). Cela signifie que les valeurs eVar définies sur « ne jamais expirer » pour un visiteur antérieurement à la plage de dates de création de rapports ne sont pas conservées dans les fenêtres de création de rapports et n’apparaissent pas dans les rapports. Cela signifie également que les mesures de fidélisation des clients sont basées exclusivement sur les données présentes dans la plage de dates de création de rapports et non sur l’ensemble de l’historique antérieurement à la plage de dates de création de rapports.

Vous trouverez ci-dessous une liste de mesures et de dimensions qui ne sont actuellement pas prises en charge lors de l’utilisation du traitement de la période de rapport :

<table id="table_127AFE8FA1BE4F2BAB3975CA12A2FA47"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nom de la mesure/dimension </th> 
   <th colname="col2" class="entry"> Remarques relatives au traitement de la période de rapport </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Analytics pour Target </p> </td> 
   <td colname="col2"> <p> Non prise en charge actuellement. Une prise en charge est prévue à l’avenir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Mesures/dimensions réservées à AMO </p> </td> 
   <td colname="col2"> <p> Non prise en charge actuellement. Une prise en charge est prévue à l’avenir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Mesure à accès unique </p> </td> 
   <td colname="col2"> <p> Non prise en charge à l’heure actuelle et à l’avenir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> eVars de liste </p> </td> 
   <td colname="col2"> <p> Non prise en charge actuellement. Une prise en charge est prévue à l’avenir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> eVars de compteur </p> </td> 
   <td colname="col2"> <p> Non prise en charge à l’heure actuelle et à l’avenir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Variables des canaux marketing </p> </td> 
   <td colname="col2"> <p> Non prise en charge actuellement. Une prise en charge est prévue à l’avenir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dimension Jours depuis le dernier achat </p> </td> 
   <td colname="col2"> <p> En raison de la nature du fenêtrage de dates de l’option Reporter le traitement du temps, cette dimension n’est pas prise en charge. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dimension Jours avant le premier achat </p> </td> 
   <td colname="col2"> <p> En raison de la nature du fenêtrage de dates de l’option Reporter le traitement du temps, cette dimension n’est pas prise en charge. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dimension Fréquence des retours </p> </td> 
   <td colname="col2"> <p> En raison de la nature du fenêtrage de dates de l’option Reporter le traitement du temps, cette dimension n’est pas prise en charge. </p> <p> Une autre approche utilisant une mesure du nombre de visites dans un segment est possible, ou en utilisant la mesure des visites dans un rapport sous forme d’histogramme. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dimension Jours depuis la dernière visite </p> </td> 
   <td colname="col2"> <p> En raison de la nature du fenêtrage de dates de l’option Reporter le traitement du temps, cette dimension n’est pas prise en charge. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dimension Page d’accès d’origine </p> </td> 
   <td colname="col2"> <p> En raison de la nature du fenêtrage de dates de l’option Reporter le traitement du temps, cette dimension n’est pas prise en charge. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> eVars d’affectation linéaire </p> </td> 
   <td colname="col2"> <p> Non prise en charge actuellement. Une prise en charge est prévue à l’avenir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dimension Domaine référent initial </p> </td> 
   <td colname="col2"> <p> Non prise en charge actuellement. Une prise en charge est prévue à l’avenir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Nombre de visites </p> </td> 
   <td colname="col2"> <p> En raison de la nature du fenêtrage de dates de l’option Reporter le traitement du temps, cette mesure n’est pas prise en charge. </p> <p> Pour créer un rapport sur le nombre de nouveaux visiteurs par rapport aux visiteurs récurrents dans les applications mobiles, vous pouvez utiliser une mesure calculée incluant les visiteurs/visites avec la mesure d’installation d’une application afin d’identifier les nouveaux visiteurs ou visites. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Sources de données des ID de transaction </p> </td> 
   <td colname="col2"> <p> Non prise en charge actuellement. Une prise en charge est prévue à l’avenir. </p> </td> 
  </tr> 
 </tbody> 
</table>

Vous trouverez ci-dessous une liste des dimensions et des mesures affectées en fonction des paramètres de traitement de la période de rapport sélectionnés :

<table id="table_491E48C55BC84917B4A8EACBF04C939F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nom de la mesure/dimension </th> 
   <th colname="col2" class="entry"> Remarques relatives au traitement de la période de rapport </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Mesure Visiteurs uniques </p> </td> 
   <td colname="col2"> <p> Si l’option « Empêcher les accès en arrière-plan de commencer une nouvelle visite » est activée, la mesure Visiteurs uniques n’inclut pas les visiteurs qui n’ont disposé que d’accès en arrière-plan dans la plage de dates de création de rapports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Visites </p> </td> 
   <td colname="col2"> <p> Les visites reflètent les paramètres configurés par la suite de rapports virtuelle, qui peuvent différer de ceux de la suite de rapports de base (parente). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Événements sérialisés avec des ID d’événement </p> </td> 
   <td colname="col2"> <p> Les événements qui utilisent la sérialisation des événements avec un ID d’événement ne sont dédupliqués que pour les événements se produisant dans la plage de dates de création de rapports pour un visiteur plutôt que pour toutes les dates ou tous les visiteurs en raison du fenêtrage de dates de l’option Reporter le traitement du temps. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Achats/Recettes/Commandes/Unités </p> </td> 
   <td colname="col2"> <p> Lorsque l’identifiant d’achat est utilisé, ces mesures ne sont dédupliquées que pour les identifiants d’achat en double se produisant dans la plage de dates de création de rapports pour un visiteur plutôt que pour l’ensemble des dates ou visiteurs en raison du fenêtrage de dates de l’option Reporter le traitement du temps. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Rebonds/Taux de rebond </p> </td> 
   <td colname="col2"> <p> Si l’option « Empêcher les accès en arrière-plan de commencer une nouvelle visite » est activée, les accès en arrière-plan qui ne sont pas suivis par un accès de premier plan ne sont pas considérés comme un rebond et ne contribuent pas au taux de rebond. See <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> Context-Aware Sessionization</a> for more details. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Durée de la visite - Secondes par visite </p> </td> 
   <td colname="col2"> <p> Si l’option « Empêcher les accès en arrière-plan de commencer une nouvelle visite » est activée, seules les visites incluant des accès de premier plan contribuent à cette mesure. See <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> Context-Aware Sessionization</a> for more details. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Durée de la visite </p> </td> 
   <td colname="col2"> <p> Si l’option « Empêcher les accès en arrière-plan de commencer une nouvelle visite » est activée, seules les visites incluant des accès de premier plan contribuent à cette mesure. See <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> Context-Aware Sessionization</a> for more details. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Entrées </p> </td> 
   <td colname="col2"> <p> Si l’option « Empêcher les accès en arrière-plan de commencer une nouvelle visite » est activée, seules les entrées provenant de visites contenant un accès de premier plan sont prises en compte. See <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> Context-Aware Sessionization</a> for more details. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> eVars sans marchandisage/eVars réservées </p> </td> 
   <td colname="col2"> <p> Les valeurs définies dans une eVar ne sont conservées que si la valeur a été définie dans la plage de dates de création de rapports en raison du fenêtrage de dates de l’option Reporter le traitement du temps. </p> <p> En outre, les expirations basées sur le temps peuvent expirer une heure plus tôt ou une heure en retard si la persistance chevauche un passage à l’heure d’été/d’hiver. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> eVars de marchandisage/eVars réservées </p> </td> 
   <td colname="col2"> <p> Voir ci-dessus. </p> <p> De plus, pour la syntaxe de la conversion pour laquelle la liaison est définie sur « any event », « any hit » est utilisé à la place. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dimensions de l’entrée et de la sortie </p> </td> 
   <td colname="col2"> <p> Si l’option « Empêcher les accès en arrière-plan de commencer une nouvelle visite » est activée, seules les entrées et les sorties des visites avec des accès de premier plan apparaissent dans cette dimension. See <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> Context-Aware Sessionization</a> for more details. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Type d’accès </p> </td> 
   <td colname="col2"> <p> Cette dimension indique si un accès est de premier plan ou en arrière-plan. </p> </td> 
  </tr> 
 </tbody> 
</table>

