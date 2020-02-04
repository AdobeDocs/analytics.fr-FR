---
description: La variable de conversion Aperçu personnalisé (ou eVar) est placée dans le code Adobe sur les pages web sélectionnées de votre site. Son principal objectif est de segmenter les mesures de succès de conversion dans les rapports marketing personnalisés. Une eVar peut être basée sur les visites et fonctionner comme un cookie. Les valeurs transmises dans des variables eVar suivent l’utilisateur pendant une période prédéfinie.
keywords: eVar
title: Variables de conversion (eVar)
topic: Admin tools
uuid: 1eed0cb1-0735-4142-be21-43f264216b50
translation-type: tm+mt
source-git-commit: 751d19227d74d66f3ce57888132514cf8bd6f7fc

---


# Variables de conversion (eVars)

La variable de conversion Aperçu personnalisé (ou eVar) est placée dans le code Adobe sur les pages web sélectionnées de votre site. Son principal objectif est de segmenter les mesures de succès de conversion dans les rapports marketing personnalisés. Une eVar peut être basée sur les visites et fonctionner comme un cookie. Les valeurs transmises dans des variables eVar suivent l’utilisateur pendant une période prédéfinie.

Lorsqu’une eVar est définie sur une valeur pour un visiteur, Adobe la mémorise automatiquement jusqu’à ce qu’elle arrive à expiration. Tout événement de succès auquel est associé un visiteur alors que la valeur eVar est active est comptabilisé dans cette dernière.

Les eVars sont parfaitement adaptées à la mesure des causes et des effets, comme par exemple :

* Quelles sont les campagnes internes qui ont eu une incidence sur les recettes ?
* Quelles bannières publicitaires ont, au final, donné lieu à une inscription ?
* Combien de fois une recherche interne a-t-elle été utilisée avant de passer une commande ?

Il est conseillé d’utiliser des variables de trafic si vous souhaitez procéder à une mesure du trafic ou utiliser le cheminement.

> [!NOTE] Une seule valeur peut être stockée dans une eVar dans une demande d’image. Pour stocker plusieurs valeurs dans une eVar, il est recommandé d’utiliser des [variables de liste](https://marketing.adobe.com/resources/help/en_US/sc/implement/listN.html).

## Variables de conversion - Descriptions {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

Description des champs utilisés lors de la [modification des variables de conversion](/help/admin/admin/conversion-var-admin/t-conversion-variables-admin.md).

<table id="table_E48D50926E6B492183300CA58A886927"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Élément </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Nom </span> </p> </td> 
   <td colname="col2"> <p>Nom convivial de la variable de conversion. Il s’agit du nom sous lequel il est fait référence à l’eVar dans les rapports généraux. Il s’agira également du nom du rapport dans le menu de gauche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Type</span> </p> <p>(eVar uniquement) </p> </td> 
   <td colname="col2"> <p>Type de valeur de la variable : </p> <p> <b>Chaîne de texte</b> :</span> capture les valeurs textuelles utilisées sur votre site. Il s’agit du type d’eVar le plus courant et du paramètre par défaut. Cette chaîne se comporte comme les autres variables, la valeur qu’elle contient étant une chaîne de texte statique. Si vous effectuez le suivi d’éléments tels que des campagnes internes ou des mots-clés de recherche interne, ce paramètre est recommandé. </p> <p> <b>Compteur</b> :</span> compte le nombre d’occurrences d’une action avant l’événement de succès. Si, par exemple, vous utilisez une eVar pour suivre les recherches internes sur votre site, définissez cette valeur sur <span class="uicontrol">Chaîne de texte</span> pour suivre l’utilisation des termes de recherche. Définissez cette valeur sur <span class="uicontrol">Compteur</span> pour compter le nombre de recherches effectuées, quels que soient les termes recherchés. Vous pouvez, par exemple, utiliser une eVar de compteur pour suivre le nombre de fois où une personne a utilisé votre recherche interne avant d’effectuer un achat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol">Affectation</span> </p> </td> 
   <td colname="col2"> <p>Détermine la manière dont Analytics attribue le crédit d’un événement de succès si une variable reçoit plusieurs valeurs avant l’événement. Les valeurs acceptables sont : </p> <p> <b>Le plus récent</b> : la dernière valeur eVar reçoit le crédit des événements de succès jusqu’à l’expiration de l’eVar. </p> <p> <b>Valeur d’origine</b> : la première valeur eVar reçoit le crédit des événements de succès jusqu’à l’expiration de l’eVar. </p> <p> <b> Linéaire</b> : attribue uniformément les événements de succès sur toutes les valeurs eVar. Puisque l’attribution linéaire ne répartit précisément les valeurs que dans une visite, utilisez-la avec une expiration d’eVar de visite. </p> <p>Remarque : l’activation ou la désactivation d’une attribution de type Linéaire empêche l’affichage des données historiques. Mélanger divers types d’attribution dans l’interface de création de rapports peut se traduire par des données erronées dans les rapports. Il se peut, par exemple, qu’une attribution linéaire divise les recettes entre plusieurs valeurs eVar différentes. Après avoir rétabli le type d’attribution sur « Le plus récent », 100 % des recettes seront associées à la valeur unique la plus récente. Cette association peut mener à des conclusions incorrectes de la part des utilisateurs. </p> <p>Pour éviter tout risque de confusion dans les rapports, les données historiques ne sont pas mises à la disposition des utilisateurs dans l’interface. Elles peuvent être visualisées si vous décidez de redéfinir l’eVar sur le paramètre d’attribution initial, même s’il est déconseillé de modifier les paramètres d’attribution de l’eVar aux seules fins d’accéder aux données historiques. Adobe recommande d’utiliser une nouvelle eVar lorsque de nouveaux paramètres d’attribution sont souhaités pour des données déjà en cours d’enregistrement, plutôt que de modifier les paramètres d’attribution sur une eVar qui a déjà accumulé une certaine quantité de données historiques. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Expire après</span> </p> </td> 
   <td colname="col2"> <p>Indique une période, ou un événement, à l’issue de laquelle (ou duquel) la valeur eVar arrive à expiration (elle le reçoit plus de crédit pour les événements de succès). Si un événement de succès se produit après l’expiration de l’eVar, la valeur Aucun reçoit le crédit pour l’événement (aucune valeur eVar n’était active). </p> <p>Si vous sélectionnez un événement comme valeur d’expiration, la variable arrive uniquement à expiration si l’événement a lieu. Dans le cas contraire, la variable n’expire jamais. </p> <p>Les options d’expiration disponibles peuvent être classées dans quatre catégories principales : </p> 
    <ul id="ul_810A37C9B6624F429F2FB45C18F7B43F"> 
     <li id="li_654D9D9044EC4E61AA7ABA372DBF8A93"><b> Au niveau de la page vue ou de la visite.</b> Les événements de conversion situés au-delà de la page vue ou de la visite ne sont pas associés à l’eVar. </li> 
     <li id="li_689FBC8B4DAC41B3B0166E6586DD1990"><b> Sur la base d’une période, telle qu’un jour, une semaine, un mois ou un an.</b> Les événements de conversion situés au-delà de la période spécifiée ne sont pas associés à l’eVar. La période d’expiration débute lorsque la variable est définie. Les eVar expirent selon la date définie exprimée en secondes (minute, heure, jour, mois, etc) : 
      <ul id="ul_80C7E3182B6B4356B8A3CA920B81C6D5"> 
       <li id="li_F16F60319CCE406D9EDEFEC0A200BC4D">MINUTE=60 secondes </li> 
       <li id="li_45F47F3F5691415B84052B235DF3BB54">HEURE=3 600 secondes (60 minutes) </li> 
       <li id="li_5288CE7D168E4C85B3D9BB67A44D32EC">JOUR=86 400 secondes (24 heures) </li> 
       <li id="li_60FC8BCD657745EE87B4E458CBA69583">SEMAINE=604 800 secondes (7 jours) </li> 
       <li id="li_7A05A66613C84F929F030310B9567CF5">MOIS=2 678 400 secondes (31 jour) </li> 
       <li id="li_DCD3CABF59E34D5999B03E606B08AD85">TRIMESTRE=8 035 200 secondes (93 jours - 3 mois de 31 jours) </li> 
       <li id="li_54351D2899454D39A8BA205910D2CCB1">AN=31 536 000 secondes (365 jours) </li> 
      </ul> <p> </p> <p>Si une visite débute à 7:00 un lundi et si une eVar est définie dans cette visite à 7:15, l’expiration est la suivante : </p> 
      <ul id="ul_72B311006BE6428698313D251C0940DB"> 
       <li id="li_50925D4A40AD4ACA88704A523138C5B9">Expiration - jour : l’eVar expire à 7:15 le mardi. </li> 
       <li id="li_25846328766D4B4BAF407236C65C956C">Expiration - semaine : l’eVar expire le lundi suivant à 7:15. </li> 
       <li id="li_82DB2D7F53304623A5E1241D75C7DF94">Expiration - mois : l’eVar expire 31 jours à compter du lundi à 7:15. </li> 
      </ul> </li> 
     <li id="li_C132C5C5A5344B91BDF5EB6A1C717C37"><b>Evénements de conversion spécifiques.</b> Tout autre événement de conversion qui est déclenché après l’événement spécifique désigné est associé à l’eVar. </li> 
     <li id="li_5A782D743FB940649E6CB3E4BEA9B8B6"><b>Jamais.</b> Tant que le cookie <span class="varname"> visitorID</span> est intact, un laps de temps indéfini peut s’écouler entre l’eVar et l’événement. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> État</span> </p> <p>(eVar uniquement) </p> </td> 
   <td colname="col2"> <p>Définit l’état de la variable eVar : </p> <p><b>Désactivé</b> :</span> désactive la variable eVar. Supprime l’eVar de la liste des variables de conversion. </p> <p> <b>Sans sous-relations</b> :</span> empêche de ventiler l’eVar avec une sous-relation. </p> <p> <b>Sous-relations de base</b> :</span> permet de ventiler une variable eVar en fonction de n’importe quel rapport avec des sous-relations complètes (Produits ou Campagnes, par exemple). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol">Réinitialiser</span> </p> </td> 
   <td colname="col2"> <p>Réinitialise toute valeur dans la variable eVar. </p> <p>Utilisez ce paramètre lorsque vous redéfinissez l’objectif d’une eVar, afin d’éviter d’utiliser une ancienne valeur dans un nouveau rapport. La réinitialisation n’efface pas les données historiques. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Marchandisage</span> </p> <p>(eVar uniquement) </p> </td> 
   <td colname="col2"> <p>Les variables de marchandisage peuvent se conformer à l’une des deux syntaxes suivantes : </p> <p> <b>Syntaxe Produits</b> :</span> associe la valeur eVar à un produit. Remarque : si Syntaxe Produits est sélectionné, la section Événement de liaison de marchandisage est désactivée et ne peut pas être sélectionnée pour modification. Pour cette syntaxe, les événements de liaison ne sont pas applicables. </p> </p> <p> <b>Syntaxe de la variable de conversion</b> :</span> associe uniquement la valeur eVar à un produit si un événement de liaison survient. Dans ce cas, sélectionnez les événements qui se comportent comme des événements de liaison. </p> <p>Si vous modifiez ce paramètre sans mettre à jour votre code JavaScript, vous perdrez des données. Voir <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/var_merchandising.html"> Variables de marchandisage</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Événement de liaison de marchandisage</span> </p> <p>(eVar uniquement) </p> </td> 
   <td colname="col2"> <p>Si le marchandisage est défini sur <span class="uicontrol"> Syntaxe de la variable de conversion</span>, les événements sélectionnés lieront la valeur de l’eVar active à un produit. </p> <p>Pour utiliser un événement de liaison, définissez l’attribution sur <span class="uicontrol"> Le plus récent</span>. Si <span class="uicontrol">l’attribution est définie sur Valeur d’origine</span>, la première liaison de produit eVar demeure jusqu’à l’expiration de l’eVar. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Expiration**

Les `eVars` arrivent à expiration après une période que vous avez spécifiée. Une fois arrivées à expiration, elles ne reçoivent plus de crédit pour les événements de succès. Vous pouvez également configurer les eVars pour qu’elles arrivent à expiration lors d’un événement de succès. Ainsi, dans le cas d’une promotion interne qui arrive à expiration à la fin de la visite, celle-ci ne reçoit du crédit que pour les achats ou inscriptions qui ont lieu au cours de la visite pendant laquelle ils ont été activés.

Il existe deux méthodes pour faire expirer une eVar :

* Vous pouvez la configurer de manière à ce qu’elle arrive à expiration après une période ou un événement spécifique.
* Vous pouvez forcer l’expiration d’une eVar, ce qui se révèle utile pour redéfinir son objectif.

Prenons l’exemple d’une eVar, d’une durée de validité de 21 jours, qui est utilisée en mai pour faire état de promotions internes, et qui, en juin, est utilisée pour capturer des mots-clés de recherche interne. Dans ce cas, le 1er juin, vous devez forcer l’expiration de cette variable ou la réinitialiser. De cette manière, les valeurs de promotion interne ne figureront pas dans les rapports du mois de juin.

**Respect de la casse**

Les eVars ne sont pas sensibles à la casse, mais elles respectent la mise en majuscules de la première occurrence. Ainsi, si la première instance de la variable eVar1 est définie sur « Connecté », mais que toutes les instances suivantes sont transmises sous la forme « connecté », les rapports affichent toujours « Connecté » comme valeur de l’eVar.

**Compteurs**

Bien que les eVars soient généralement utilisées pour contenir des valeurs de chaîne, elles peuvent également être configurées pour faire office de compteurs. Elles s’avèrent particulièrement utiles sous cette forme lorsque vous essayez de comptabiliser le nombre d’actions qu’un utilisateur effectue avant un événement. Vous pouvez, par exemple, utiliser une eVar pour capturer le nombre de recherches internes avant un achat. Chaque fois qu’un visiteur effectue une recherche, l’eVar doit contenir une valeur « +1 ». Si un utilisateur effectue quatre recherches avant un achat, une instance est affichée pour chaque compte total : 1.00, 2.00, 3.00 et 4.00. Cependant, seule la valeur 4.00 reçoit du crédit pour l’événement d’achat (mesures Commandes et Recettes). Seuls les nombres positifs sont autorisés comme valeurs d’un compteur eVar.