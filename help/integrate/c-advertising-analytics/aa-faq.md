---
description: valeur nulle
title: Questions fréquentes
uuid: 05724f56-cf98-4ad8-ad0d-83a5a4b1944a
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Questions fréquentes

## Accès/Droits {#section_5F558C5981F747F0AF375A9E4B75C93C}

<table id="table_6713C3B0B6734F768370F974EB5AC5E8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Réponse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Q. : Dois-je être un <b>client Adobe Advertising Cloud ou Adobe Advertising Cloud (AMO)</b> pour accéder à cette fonctionnalité ? </p> </td> 
   <td colname="col2"> <p>R. : Non, cette fonctionnalité est disponible pour les clients ne bénéficiant pas d’Advertising Cloud et d’AMO. </p> <p>Les clients AMO peuvent utiliser l’intégration Analytics-AMO existante, mais ne seront pas en mesure d’utiliser Ad Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q. : Quels <b>SKU d’Adobe Analytics</b> permettent d’utiliser Advertising Analytics ? </p> </td> 
   <td colname="col2"> <p>R. : Advertising Analytics est disponible pour les SKU <a href="https://www.adobe.com/data-analytics-cloud/analytics/select.html"  >Select</a>, <a href="https://www.adobe.com/data-analytics-cloud/analytics/prime.html"  >Prime</a> ou <a href="https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html"  >Ultimate</a> d’Adobe Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q. : Dois-je <b>payer un supplément</b> pour utiliser Advertising Analytics ? </p> </td> 
   <td colname="col2"> <p>R. : Non, en dehors des prestations propres aux SKU, Advertising Analytics n’occasionne pas de coûts supplémentaires. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q. : Est-ce qu’Advertising Analytics sera décompté de mon <b>utilisation d’appels au serveur</b> ? </p> </td> 
   <td colname="col2"> <p>R. : Non, Advertising Analytics utilise un type spécifique de sources de données qui n’occasionne pas de coûts de serveur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q. : Si <b>j’utilise déjà Advertising Cloud/AMO</b>, puis-je quand même utiliser la fonctionnalité Advertising Analytics ? </p> </td> 
   <td colname="col2"> <p>R. : Tous les comptes de moteur de recherche compatibles seront transférés dans Advertising Analytics et seront affichés en lecture seule. Toutes les modifications et les mises à jour doivent être gérées dans Advertising Cloud/AMO. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q. : Je possède un SKU correct, mais je <b>ne peux pas accéder</b> à Advertising Analytics, pourquoi ? </p> </td> 
   <td colname="col2"> <p>R. : Advertising Analytics est disponible uniquement pour les administrateurs Adobe Analytics ; cependant, les administrateurs peuvent accorder l’accès à des non-administrateurs. Contactez votre administrateur au sujet des droits d’accès. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Utilisation d’Advertising Analytics  {#section_3A70C6C4D5A842B2981F0257A01F95FF}

<table id="table_4EC69262B7AB4DF49E736CF3B0362302"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Réponse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Q. : Quels <b>comptes de moteur de recherche</b> sont inclus dans Advertising Analytics ? </p> </td> 
   <td colname="col2"> <p>R : Les comptes de moteur de recherche incluent Google AdWords et Microsoft Bing. </p> <p>Remarque : Yahoo Gemini a été absorbé par Microsoft Bing le 31 mars 2019. Par conséquent, l’option de compte publicitaire Yahoo Gemini n’est plus disponible. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q. : Où dois-je me rendre pour <b>accéder</b> à Advertising Analytics ? </p> </td> 
   <td colname="col2"> <p>R. : Une fois connecté à Adobe Analytics, accédez au menu <span class="uicontrol">Admin</span>. Puis, sélectionnez l’option <span class="uicontrol">Advertising Analytics</span> du nouveau menu pour ajouter vos comptes de moteur de recherche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q. : Comment <b>les données sont-elles collectées et transférées vers Analytics</b> ? </p> </td> 
   <td colname="col2"> <p>R. : Advertising Analytics utilise une série d’API personnalisées pour transférer les données des moteurs de recherche via Adobe Advertising Cloud dans Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q. : Quelles <b>données de recherche</b> obtiendrai-je avec cette intégration ? </p> </td> 
   <td colname="col2"> <p>R. : Vous obtiendrez 1) les Impressions, 2) les Clics, 3) les Coûts, 4) la Note de qualité et 5) la Position moyenne directement à partir des moteurs de recherche ainsi que 6) les Instances AMO ID (cliquez sur Instances). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q. : Puis-je <b>ventiler mes données Advertising Analytics</b> selon d’autres données Analytics (mesures/dimensions) ? </p> </td> 
   <td colname="col2"> <p>R. : Non, les données de recherche brutes arriveront en tant qu’ensemble de données indépendant. Cependant, il existe une version des Instances des données de clic qui peut être ventilée selon d’autres données Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q. : Que signifient les diverses <b>indications d’état</b> de mes comptes (en attente, actif, en pause, etc.) ? </p> </td> 
   <td colname="col2"> <p>R. : Chacune de ces indications d’état identifie les étapes du cycle de vie de chaque compte de moteur de recherche. </p> 
    <ul id="ul_F68AD377B2F04A47B20355B2FF4CF345"> 
     <li id="li_05F8D7C6D00E4742A65373BE6FAA0448"><b>En attente</b> signifie que le compte a été configuré, mais que les données n’ont pas encore été extraites. </li> 
     <li id="li_42B1557A8AEC41008B85AF6E3F625CAB"><b>En pause</b> signifie que le compte a été initialement configuré, mais a été placé en mode inactif. </li> 
     <li id="li_30B72CC171874F308A2B8CE552EA6930"><b>Actif</b> signifie que le compte a été complètement configuré et extrait des données. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q. : J’essaie de <b>mapper mes comptes Advertising Analytics à une suite de rapports spécifique</b>, mais elle n’est pas disponible dans le mode Suite de rapports. Pourquoi ? </p> </td> 
   <td colname="col2"> <p>R. : Pour pouvoir assigner une suite de rapports à un compte Advertising Analytics, la suite de rapports souhaitée doit être <a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md"  >configurée pour la création de rapports Advertising Analytics </a>. </p> <p>Cette action se fait par le biais d’une page d’administration séparée accessible à partir de : <span class="ignoretag"> <span class="uicontrol"> Admin</span> &gt; <span class="uicontrol">Suites de rapports</span> &gt; <span class="uicontrol">[sélectionner la suite de rapports compatible avec Experience Cloud]</span> &gt; <span class="uicontrol">Modifier les paramètres</span> &gt; <span class="uicontrol">Configuration Advertising Analytics </span> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q. : Est-il possible d’assigner une <b>suite de rapports virtuelle</b> (SRV) à un compte Advertising Analytics ? </p> </td> 
   <td colname="col2"> <p>R. : Les suites de rapports virtuelles ne collectent pas de données, vous ne pouvez donc pas mapper directement un compte Advertising Analytics à une suite de rapports virtuelle. </p> <p>Cependant, vous pouvez mapper un compte Advertising Analytics à une suite de rapports parente de la suite de rapports virtuelle dans laquelle vous souhaitez afficher les données. </p> <p>Les mesures du moteur de recherche (clics/coûts/impressions) peuvent ne pas s’afficher dans la SRV à moins d’inclure une condition « ou » dans la logique des segments basés sur l’AMO ID (ou sa classification). Exemple : ajouter « tous les accès dans lesquels l’AMO ID existe » permet d’inclure les mesures du moteur de recherche dans le segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q. : Les mesures Advertising Analytics peuvent-elles être reportées dans un rapport de <b>canaux marketing</b> ? </p> </td> 
   <td colname="col2"> <p>R. : Non, elles ne sont pas incluses dans le rapport de canaux marketing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q. : <b>Quand</b> les données de recherche sont-elles transférées dans Analytics ? </p> </td> 
   <td colname="col2"> <p>R. : Les données de recherche sont extraites du moteur de recherche vers 6 heures de matin (06:00) selon le fuseau horaire de votre centre de données Analytics. C’est à ce moment que les données AMO sont collectées et insérées dans la suite de rapports. Les données sont alors converties selon le fuseau horaire de la suite de rapports au cours de l’insertion des données dans Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q. : Qu’est-ce qui peut être <b>capturé avant le clic</b> ? Est-ce que nous fournissons le nombre d’impressions, le coût, la position moyenne, etc. même sans clic ? </p> </td> 
   <td colname="col2"> <p>R. : L’AMO ID capture les mesures du moteur de recherche : Impressions, Coût, Clics, Position moyenne et Note de qualité moyenne. En l’absence de clics, mais s’il y a des impressions, les données de note d’impression/de position/de qualité continueront à être envoyées à Analytics. En règle générale, l’absence de clics ne génère également aucun coût. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q. : À quel niveau ces données sont-elles capturées ? <b>Visiteur ? Accès ?</b> </p> </td> 
   <td colname="col2"> <p>R. : Les mesures du moteur de recherche sont capturées au niveau de l’accès et liées à l’AMO ID (et à ses classifications). Ce sont des données de niveau résumé, non liées aux visites/visiteurs. En tant que telles, les mesures du moteur de recherche peuvent être utilisées uniquement dans des segments dont la portée est de niveau accès et qui sont basés sur l’AMO ID (ou ses classifications). </p> <p>L’AMO ID est également capturé sur la page d’entrée dans l’accès à cette page (qui le lie à la visite/au visiteur) et persistera en aval pour créditer d’autres mesures d’Analytics (jusqu’à expiration ou remplacement par un nouvel AMO ID). Il est entièrement intégré au jeu de données comme toute autre eVar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q. : Est-ce que nous capturons uniquement google.com ou également les <b>versions par pays</b> (comme google.co.uk, google.it, google.fr ou google.de) ? </p> </td> 
   <td colname="col2"> <p>R. : La classification de la plateforme d’annonces publicitaires capture les valeurs suivantes : « Google Adwords » et « Bing Ads ». </p> <p>Il est recommandé d’inclure le code de pays dans le nom des campagnes. Vous pouvez ensuite filtrer ou segmenter. Par exemple, si toutes les campagnes commencent par codepays_, la création d’un segment où Campagnes (AMO ID) commence par « FR_ » vous fournirait uniquement des données pour la France. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q. : La mesure « Coût AMO » correspond au coût payé pour chaque mot-clé/annonce publicitaire comme rapporté par le moteur de recherche. S’agit-il du coût net ou du coût brut ? </p> </td> 
   <td colname="col2"> <p>R. : Le « Coût AMO » représente uniquement le coût payé aux moteurs de recherche. Il n’inclut aucuns frais d’agence ou d’optimisation de recherche/de plateforme de gestion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q. : Existe-t-il un projet visant à inclure d’autres canaux publicitaires comme <b>Display</b> ou <b>Social</b> ? </p> </td> 
   <td colname="col2"> <p>R. : Non, nous n’avons actuellement aucun projet visant ces autres canaux publicitaires. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Suivi automatique vs. manuel  {#section_7437C4698A6D482EB7ED94A948390119}

<table id="table_9738FF8459574ED2937A860A665BE739"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Réponse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Q. : Lors du paramétrage de mon compte Advertising, il est stipulé que le <b>Suivi automatique</b> peut entraîner des conséquences imprévues. Quel genre de conséquences peuvent survenir ? </p> </td> 
   <td colname="col2"> <p>R. : 
     <ul id="ul_59EFF4A2ECE947EBBDB6A9FF6D072FE0"> 
      <li id="li_8731E4B7D6ED4F0996B3630A35D5BAC4">Le mode automatique tentera d’ajouter les paramètres d’URL à la fin du modèle de suivi ou de l’URL de destination dans un format correct. <b>Cependant, il vous appartient de vous assurer que les paramètres d’URL ajoutés demeurent correctement à la dernière page d’entrée. </b> </li> 
      <li id="li_1202FE1FC88342378A60E8FE65E5426B">Le mode automatique peut insérer des mot-clés dans l’URL d’entrée et votre serveur web peut ne pas prendre en charge les mots-clés contenant des caractères spéciaux. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q. : Si je configure d’abord un suivi manuel ou automatique, <b>puis-je changer</b> de mode de suivi plus tard ? Quelles sont les implications ? </p> </td> 
   <td colname="col2"> <p>R. : Oui, vous pouvez changer, mais vous devrez supprimer l’ancienne logique de suivi avant de passer à l’autre mode. Cela peut entraîner une interruption du suivi le jour du changement (en particulier si vous passez du mode manuel au mode automatique). Il est donc recommandé de ne pas changer de mode à moins que cela ne soit absolument nécessaire. </p> 
    <ul id="ul_3F3CADD1C97B4947A13837CEE63A599D"> 
     <li id="li_CB9265951FD040388AEAB9EAD790A36E"><b>Passer du mode manuel au mode automatique</b> : supprimez les ajouts manuels apportés aux modèles de suivi puis basculez le bouton de manuel à automatique dans l’interface utilisateur d’Advertising Analytics et enregistrez cette configuration. Notez que le système peut prendre x heures pour renseigner les codes de suivi automatique. </li> 
     <li id="li_2B6ED1342E2D443B8AF26D03532AB8E4"><b>Passer du mode automatique au mode manuel</b> : basculez le bouton de manuel à automatique dans l’interface de configuration d’Advertising Analytics puis déployez les codes de suivi manuel aussi vite que possible. Lorsque vous déployez les codes de suivi manuel, si vous détectez des codes de suivi automatique dans les modèles de suivi du moteur de recherche, supprimez-les. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

