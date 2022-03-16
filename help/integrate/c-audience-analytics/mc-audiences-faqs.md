---
description: Réponses aux questions pouvant survenir lors de la mise en œuvre d’Audience Analytics.
solution: Experience Cloud
title: Questions fréquentes pour l’Audience Analytics
feature: Audience Analytics
exl-id: 86e7967c-030c-44d6-8294-e7e6d41f6fc3
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '1094'
ht-degree: 98%

---

# Questions fréquentes

Réponses aux questions pouvant survenir lors de la mise en œuvre d’Audience Analytics.

## Questions fréquentes d’ordre juridique {#section_B51CFC961C0B45A2BE5F4A4404620764}

<table id="table_22037CCB516C4231BF5820004FBB351A"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Q : Comment savoir si des informations d’identification personnelle sont contenues dans mes données Analytics ? Si tel est le cas, que dois-je faire ?</b> </td> 
   <td colname="col2"> 
    <ul id="ul_71E0ECD5981D4B65BCDA065BE07A43AA"> 
     <li id="li_F8FF61A4D7B54BA39DAA6F28DB51D749">Si des adresses postales ou électroniques sont contenues dans une entité prop ou eVar, envisagez d’effectuer un hachage des données lors de la collecte. </li> 
     <li id="li_57A8B4C7BB784FFCBC1DC363B35D9FF7">Si votre pays considère l’adresse IP comme une information personnelle, <a href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/exclude-ip.html?lang=fr"  >activez la dissimulation d’adresses IP </a>. </li> 
     <li id="li_C7AA02B831AE47A59E783623126A7789">Pour voir les données recueillies, adressez-vous à votre administrateur Analytics. </li> 
     <li id="li_F6AAE868141E486AB8CAB291BD8EDB71">Contactez votre service juridique pour savoir ce qu’il considère comme des informations d’identification personnelle. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q : Comment savoir si mes suites de rapports effectuent une personnalisation sur site ou un ciblage sur site/hors site ?</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F0984CEF80DB4B589716BC55549E32B8"> 
     <li id="li_9BC3819784A9408F846D60FF0F20AAF9">Ces activités ne s’appliquent pas à l’envoi de données d’Adobe Analytics vers Adobe Audience Manager. </li> 
     <li id="li_050A1BF9978E436895B5C7E33A82527D">Posez-vous la question suivante : allez-vous repartager un segment Analytics partagé avec une dimension MCA vers Experience Cloud ? </li> 
     <li id="li_C52D969681B94F4AAA18FDEB21EC5B49">Effectuez-vous une exportation (par exemple via le flux de données) vers un système Business Intelligence (BI) exploité dans ce but ? </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Questions fréquentes spécifiques à AAM  {#section_6BDF746BA6464359A6A89A64EB025D12}

<table id="table_15B44592161240BDA79F3B020EA9CC9D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q : Comment créer une destination Analytics dans Audience Manager ?</b> </p> </td> 
   <td colname="col2"> Reportez-vous à la section <a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/experience-cloud-destinations/create-analytics-destination.html?lang=fr"  >Configuration d’une destination Analytics dans AAM</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q : Une fois une destination Analytics créée et enregistrée, combien de temps faut-il pour que les données apparaissent dans mes suites de rapports sélectionnées ?</b> </p> </td> 
   <td colname="col2"> <p>Plusieurs heures peuvent s’écouler avant que les nouvelles données n’apparaissent dans vos suites de rapports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q : J’ai créé une nouvelle destination Analytics mais je ne la vois pas dans la section Mises en correspondance de destinations de mes segments disponibles. Où cette destination est-elle passée et comment la trouver ?</b> </p> </td> 
   <td colname="col2"> <p>Une destination Analytics disparaît de la section Mises en correspondance de destinations d’un segment lorsque vous sélectionnez l’option <span class="uicontrol">Mapper automatiquement tous les segments actuels et futurs</span> dans <span class="uicontrol">Mappages des segments</span>. </p> <p><img placement="break" align="left"  src="assets/auto-mapping.png" id="image_670ED5A306784FCBA8A0B336AC1F0FC6" width="300px" /> </p> <p>Pour éviter ceci, sélectionnez <span class="uicontrol">Mapper les segments manuellement</span> au lieu de l’option de mappage automatique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Q : Toutes les informations d’AAM seront-elles disponibles dans Analytics ?</b> </p> </td> 
   <td colname="col2"> <p>Non, seules les données relatives aux personnes qui consultent votre site pendant ou après l’activation d’audiences Audience Manager et pendant/après la qualification des segments sont incluses. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Q : Ces données me procurent-elles une audience adressable totale par segment ?</b> </p> </td> 
   <td colname="col2"> <p>Pas exactement. Elles vous indiquent le nombre de visiteurs de ce segment qui ont visité votre site pendant ou après la qualification du segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Q : En quoi cette fonctionnalité diffère-t-elle de la destination des cookies hérités dans Analytics ?</b> </p> </td> 
   <td colname="col2"> <p>Les segments sont qualifiés et renvoyés en temps réel au cours d’un même accès. </p> <p>Les noms conviviaux sont affichés automatiquement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q : Que se passe-t-il si certaines de mes suites de rapports contiennent des données personnelles et d’autres pas ?</b> </p> </td> 
   <td colname="col2"> <p>Conseil : créez deux destinations. Ajoutez les suites de rapports contenant des données personnelles à l’une des destinations et celles n’en contenant pas à l’autre destination. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Questions fréquentes spécifiques à Analytics  {#section_67BFB1B1E48D4113A38B075C020931BA}

<table id="table_19AEAE0A3575423CB4F5F164DB5626D5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q : Cette intégration apparaîtra-t-elle en tant que dimension ou segment dans Analytics ?</b> </p> </td> 
   <td colname="col2"> <p>En tant que dimensions : ID d’audience et Nom d’audience. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q : Où utiliser ces dimensions dans Analytics ?</b> </p> </td> 
   <td colname="col2"> <p>Presque partout ; elles sont traitées comme toutes les autres dimensions collectées dans Analytics. Il y a une exception : pour l’instant, les données ne seront pas dans Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q : Pourquoi les données ne sont-elles pas visibles dans Analytics ?</b> </p> </td> 
   <td colname="col2"> <p>Il existe probablement un conflit entre les contrôles de la confidentialité AAM pour la source et la destination des données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q : Pourquoi certains de mes segments sont-ils manquants dans Analytics, alors que j’ai choisi d’envoyer tous les segments ?</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_B8938FD08C6F4F2387EDADDEF8089319"> 
     <li id="li_50A9BDF612304062913370F16BC882EF">Il existe peut-être un conflit entre vos contrôles des exportations de données AAM pour la destination et les sources de données des segments, bloquant ainsi l’envoi de certains segments. </li> 
     <li id="li_AF5D6F883D6F4D3192E0BF23CF12ADEA">Si vous utilisez des caractéristiques de données tierces dans vos segments, ces segments ne peuvent pas être partagés avec des destinations (un jeu de suites de rapports) contenant des données personnelles. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q : Pourquoi est-il indiqué « Limite d’audience atteinte » dans mon rapport Analytics ? (Remarque : il sera également représenté sous la forme ID d’audience = -1 et "::max_audiences_exceeded::" en Data Warehouse)</b> </p> </td> 
   <td colname="col2"> <p>Par défaut, l’intégration Audience Analytics pour AAM envoie à Analytics tous les segments pour lesquels un visiteur est admissible, accès par accès. Si un visiteur appartient à plus de 150 segments AAM au cours d’un même accès, les <b>150 segments les plus récemment qualifiés</b> sont envoyés à Analytics, tandis que la liste des segments restants est tronquée. </p> <p>Un indicateur supplémentaire signifiant que la liste de segments a été tronquée est envoyé à Analytics. Celui-ci s’affiche sous la forme de la mention « Limite d’audience atteinte » dans la dimension Nom d’audience et de « -1 » dans la dimension ID d’audience. </p> <p>Il est peu probable qu’un visiteur soit admissible pour plus de 150 segments au cours d’un accès particulier, mais cela peut se produire dans un nombre réduit de cas. Si la mention « Limite d’audience atteinte » apparaît dans vos rapports, vous avez deux possibilités : </p> 
    <ul id="ul_8E290B2E32DC49738F6FD00CB0CE2BBB"> 
     <li id="li_12F498981EA949B5BCBD40ECC954C339"><b>Option 1</b> : Continuez de laisser l’intégration fonctionner dans sa version prête à l’emploi, qui envoie les 150 segments les plus récemment qualifiés pour un visiteur particulier. </li> 
     <li id="li_CA4D5747AA4A4452929097807B604959"><b>Option 2</b> : Dans AAM, sélectionnez les 150 segments les plus importants pour votre entreprise pour l’intégration. AAM vérifie alors uniquement les visiteurs par rapport à ces 150 segments. Cette approche présente l’inconvénient que vous recevez uniquement ces 150 segments pour tous les visiteurs. En revanche, l’approche de l’option 1 peut fournir un nombre illimité de segments du fait que l’intégration repose sur les accès. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q : Des appels au serveur supplémentaires vers Analytics seront-ils facturés pour cette intégration ?</b> </p> </td> 
   <td colname="col2"> <p>Non. Les audiences AAM sont intégrées dans l’accès Analytics côté serveur. Cela ne génère aucun appel (primaire ou secondaire) au serveur supplémentaire vers Analytics. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Questions fréquentes sur la redirection côté serveur  {#section_ADDE84ABCA0D4906B6235E92D185E0C6}

<table id="table_B7067B70FF85498896801F58D716202F"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q : Si la redirection côté serveur héritée est mise en œuvre, dois-je également accéder aux paramètres d’administration d’Analytics et activer la redirection côté serveur pour les suites de rapports ?</b> </p> </td> 
   <td colname="col2"> <p>Oui. Dans la configuration des destinations AAM, seules les suites de rapports pour lesquelles la redirection côté serveur est activée sont visibles. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q : Pourquoi ne puis-je pas activer la redirection côté serveur pour certaines suites de rapports dans les paramètres d’administration d’Analytics ?</b> </p> </td> 
   <td colname="col2"> <p>La redirection côté serveur peut être activée uniquement pour les suites de rapports qui sont mappées sur votre organisation Experience Cloud. </p> </td> 
  </tr> 
 </tbody> 
</table>

Pour plus de questions fréquentes sur ce sujet, consultez la [FAQ sur la redirection côté serveur](/help/admin/admin/c-server-side-forwarding/ssf-faq.md).

## Questions fréquentes d’ordre général {#section_E55410BBFB624AAFB87ADCF7F036DDA3}

<table id="table_1F7C0C785F9C472286A96F8C25E8440B"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Q : Pourquoi les nombres de visiteurs de segments diffèrent-ils entre Audience Manager et Analytics ?</b> </p> </td> 
   <td colname="col2"> <p>Voir  <a href="/help/integrate/c-audience-analytics/visitor-count-reconciliation.md"  > Différences entre les nombres de visiteurs </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q : Quelle est la différence entre « audiences » dans AAM et « segments » dans Analytics ?</b> </p> </td> 
   <td colname="col2"> <p>Voir  <a href="/help/integrate/c-audience-analytics/aam-analytics-segments.md"  > Présentation des segments dans Analytics et Audience Manager </a>. </p> <p>Les audiences AAM sont envoyées et partagées en tant que composants « Dimension » pour une utilisation dans Analytics. Elles n’apparaîtront pas en tant que segments dans le Créateur de segments, mais en tant que dimensions que vous pouvez utiliser pour créer des segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q : Quelle est la différence entre les attributs du client et les données de clients intégrées à partir d’AAM ?</b> </p> </td> 
   <td colname="col2"> <p>Les attributs du client ne dépendent pas du temps ; ils s’appliquent de façon rétroactive et par la suite. Les données intégrées à partir d’AAM dépendent du temps et s’appliquent uniquement par la suite. Par ailleurs, les attributs du client offrent un tableau de recherche pour les identifiants visiteurs d’Experience Cloud, tandis que l’intégration AAM fournit des données assemblées dans chaque accès pour un visiteur donné. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q : Qu’en est-il des approches héritées en la matière, par exemple, les anciennes destinations bêta ou la consultation des destinations dans les cookies de module externe ?</b> </p> </td> 
   <td colname="col2"> <p>Il est recommandé de mettre en œuvre la nouvelle intégration et de supprimer les autres destinations. </p> </td> 
  </tr> 
 </tbody> 
</table>
