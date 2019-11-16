---
description: Plusieurs types de variables sont disponibles dans Experience Cloud. Les deux types les plus populaires, propriétés et eVars, permettent à votre entreprise de générer des rapports sur des dimensions personnalisées de votre site, une fonctionnalité que les rapports standard ne proposent pas.
keywords: Analytics Implementation;prop;evar;props vs evars;naming convention;traffic variables;persistence;success event;pathing
solution: Analytics
title: Comparaison des propriétés et des eVars
topic: Developer and implementation
uuid: 0f02760f-ff69-481c-a817-799f02dafe8e
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Comparaison des propriétés et des eVars

Plusieurs types de variables sont disponibles dans Experience Cloud. Les deux types les plus populaires, propriétés et eVars, permettent à votre entreprise de générer des rapports sur des dimensions personnalisées de votre site, une fonctionnalité que les rapports standard ne proposent pas.

Lorsque vous déterminez l’emplacement d’affectation des différentes variables, il importe de faire clairement la distinction entre les fonctionnalités Prop et eVar. Etre en mesure d’identifier ces différences permet à votre entreprise de déterminer le type de variable idéal à utiliser.

**Props / eVars**

Vous trouverez, ci-dessous, une description des principales différences entre les props et les eVars :

* **Convention d’attribution de noms** : les props sont considérées comme des variables de trafic, ce qui signifie qu’elles sont utilisées pour indiquer la popularité de diverses dimensions de votre site. Les eVars sont considérées comme des variables de conversion. Elles servent à identifier les dimensions de votre site qui contribuent le plus aux événements de succès.
* **Persistance** : les props ne persistent pas au-delà de la demande d’image sur laquelle elles ont été déclenchées. Elles ne peuvent pas être associées à d’autres variables qui ne figurent pas dans la même demande d’image. Les eVars, en revanche, sont persistantes. Une variable finale est utilisée pour conserver la valeur déclenchée initialement, de sorte qu’elle puisse s’associer ultérieurement à des événements de succès.
* **Evénements de succès** : les événements de succès, connus également sous le nom d’événements de conversion, mesurent le nombre de fois où un visiteur atteint un certain objectif. Il peut s’agir d’un achat réalisé sur un site ou encore de l’inscription à un bulletin d’information. Les eVars sont conçues pour générer des rapports sur les événements de conversion. Elles affichent ainsi les valeurs dont l’influence sur les visiteurs est la plus forte en vue de l’accomplissement d’un objectif. Les variables de trafic ne disposent pas des mêmes fonctionnalités. Vous pouvez toutefois consulter des mesures de participation si votre suite de rapports est correctement configurée.
* **Cheminement** : les props peuvent utiliser le cheminement, ce qui permet à votre entreprise de visualiser le chemin emprunté par un utilisateur dans le cadre de la variable en cours de consultation. Au besoin, un représentant Adobe peut activer le cheminement. Les eVars ne peuvent pas utiliser le cheminement.
* **Mesures potentiellement disponibles** : les mesures disponibles pour les props et les eVars varient sensiblement en fonction des paramètres de la variable et de la version/plate-forme des données. La liste ci-dessous illustre les éléments pouvant être activés, ainsi que ceux qui ne le sont pas par défaut. Si une mesure spécifique ne figure pas dans les rapports, demandez à l’un des utilisateurs de votre société ayant souscrit un contrat dédié de contacter le service d’assistance clientèle.

<table id="table_FB963F60857A4AD79562324FB6F4B6A9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Mesure </p> </th> 
   <th colname="col2" class="entry"> <p>Propriétés </p> <p>(Variables de trafic) </p> </th> 
   <th colname="col3" class="entry"> <p>eVars </p> <p>(Variables de conversion) </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Profondeur moyenne de page </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_165C1BF1574247CEA9190ADCABF79D69" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Durée moyenne de la visite </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_9F0F396E11B442959EC3E5D4D508496D" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Taux de rebond </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_A268EAF747EA45F8A6A93A1B66667A06" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_09D486144CEA4293A505DCA3F90B82EC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Retours </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_471A02B78FD842BB97ED3FF4A5908B03" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_D2F11B5687484D9EBF6D1DEB3F303A20" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mesures calculées </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_7FAB1CF2ACC44D9198C648D3FC9E52D9" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_8BCC2EE92CC04778809D1BD48D2623D7" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Événements de conversion personnalisés </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_D75C764B83AE4491A7E68C459FED1300" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Entrées </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_E9A1FCDFCB924D75ABFAEBD5570D4EE0" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_F5E57974B5A64F3FA3A145428420EB23" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sorties </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_BE343F94EAD74D54B6ABC80E8A76A9BD" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_3183B2BB62C24B048EDED3295F2BEC85" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Instances </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_8733F5AC189E43DAA8D1847416EA68C8" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_B10AB2898F3D4EBA947FADB27B118143" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pages vues </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_8BD2B23FBDA64A648BED40A2993F7C1C" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_CBDFD74340FA4973847033C1F956F0AC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mesures de participation </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_E63F978830FB46809E62654F37C4C182" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_6AB756A4598F4452887D29AD4971985A" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mesures d’achat </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_8F8AB7CD02764245BA73CA1E6B69BAE1" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Actualisations </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_FBE0C84E01004937B7B408198A33A9E7" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mesures de panier </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_123993465D734EABB311730ED03263F6" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Accès unique </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_038C6991E3F341B18E7A355D17C88895" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Durée totale de la visite </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_090587D29F1649319033D5A15B34B138" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_841DF09FD32A44B1B1B876F4E0CE29AC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visiteurs uniques </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_38556E6A43B04E2E8A01855452D30A83" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_F5D4BDE1AA9C4C58A6402418390EEC52" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visites </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_017BB279C5824028870360A5D4D27556" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_2832E346D220429DA643B908EC10260D" /> </p> </td> 
  </tr> 
 </tbody> 
</table>

* **Ventilations** : les props utilisent des corrélations, lesquelles affichent les pages vues pour les autres variables de trafic déclenchées dans la même demande d’image. Les eVars utilisent des sous-relations, lesquelles fournissent une ventilation sur d’autres variables de conversion en rapport avec des événements de succès.

## Avantages exclusifs aux props et aux eVars {#section_B384031AB8674065BA5187B0A3A3DAB9}

Les différences propres aux props ou aux eVars sont beaucoup plus ténues dans la version 15. Les eVars ont récemment été mises à jour afin d’inclure certaines fonctionnalités du type visites/visiteurs uniques avec une charge de traitement minimale, ainsi que des mesures de cheminement.

Les props présentent certains avantages par rapport aux eVars, dont quelques-uns peuvent être contournés :

* Les données de prop sont collectées et disponibles presque instantanément lors de la création de rapports. Il peut falloir jusqu’à 30 minutes avant que les eVars n’apparaissent dans les données de la suite de rapports.
* Des rapports du type organigramme peuvent être activés pour toutes les props, ce qui permet de vérifier quel chemin ont emprunté les visiteurs pour accéder à votre site. [!UICONTROL Dans les analyses ad hoc], ces rapports de flux de cheminement sont disponibles pour les props comme pour les eVars.
* Les props peuvent être corrélées à plusieurs niveaux, tandis que les eVars peuvent être sous-liées une seule fois. Vous pouvez contourner cette restriction à l’aide d’une segmentation, qui génère des données identiques aux corrélations.
* Les mesures de participation permettent de déterminer quelles valeurs de prop ont contribué à un événement de succès.

D’un autre côté, les eVars présentent plusieurs avantages par rapport à la nature limitée des props :

* Les eVars peuvent utiliser les événements de succès comme des mesures, contrairement aux props.
* Il est possible de personnaliser l’expiration des eVars, notamment en définissant une péremption pour chaque accès (aucune valeur persistante). Les props ne persistent pas.

Les mesures de cheminement, du type Durée totale, Entrées et Sorties, n’étaient à l’origine pas proposées pour les eVars. Cependant, des mises à jour récentes ont rendu ces mesures accessibles, valorisant ainsi davantage les eVars.

## Quelle variable utiliser {#section_022D016A4EEB45179A15BFF044A261A4}

**Propriétés :** si la latence est votre principal sujet de préoccupation et que vous prévoyez de mesurer uniquement le trafic (et non les événements de succès) avec cette dimension, il est préférable d’utiliser des propriétés.

**eVars :** si la ventilation des données et leurs relations constituent les principales préoccupations.

>[!TIP]
>
>Si vous ne souhaitez pas utiliser de variables persistantes, vous pouvez définir l’expiration de la variable sur « accès » afin qu’elle ne conserve aucune donnée en aval de l’accès.

