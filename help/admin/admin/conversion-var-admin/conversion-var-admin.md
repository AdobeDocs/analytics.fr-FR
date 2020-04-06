---
description: La variable de conversion Custom Insight (ou eVar) est placée dans le code Adobe sur les pages Web sélectionnées de votre site. Son principal objectif est de segmenter les mesures de réussite de conversion dans les rapports marketing personnalisés. Une eVar peut être basée sur les visites et fonctionner de la même manière que les cookies. Les valeurs transmises aux variables eVar suivent l’utilisateur pendant une période prédéterminée.
keywords: eVar
title: Variables de conversion (eVar)
topic: Admin tools
uuid: 1eed0cb1-0735-4142-be21-43f264216b50
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Variables de conversion (eVars)

La variable de conversion Custom Insight (ou eVar) est placée dans le code Adobe sur les pages Web sélectionnées de votre site. Son principal objectif est de segmenter les mesures de réussite de conversion dans les rapports marketing personnalisés. Une eVar peut être basée sur les visites et fonctionner de la même manière que les cookies. Les valeurs transmises aux variables eVar suivent l’utilisateur pendant une période prédéterminée.

Lorsqu’une eVar est définie sur une valeur pour un, Adobe la mémorise automatiquement jusqu’à son expiration. Tout de réussite rencontré par un alors que la valeur eVar est active est comptabilisé dans la valeur eVar.

Les eVars sont mieux utilisées pour mesurer les causes et les effets, comme par exemple :

* Quelles sont les campagnes internes qui ont influencé les recettes ?
* Quelles bannières publicitaires ont abouti à un enregistrement ?
* Nombre de fois où une recherche interne a été utilisée avant de passer une commande

Si une mesure du trafic ou un cheminement est souhaité, il est recommandé d’utiliser des variables de trafic.

>[!NOTE] Une seule valeur peut être stockée dans une eVar dans une demande d’image. Pour stocker plusieurs valeurs dans une eVar, il est recommandé d’utiliser des [variables de liste](https://marketing.adobe.com/resources/help/fr_FR/sc/implement/listN.html).

## Variables de conversion - Descriptions {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

Description des champs utilisés lors de la [modification des variables de conversion](/help/admin/admin/conversion-var-admin/t-conversion-variables-admin.md).

<table id="table_E48D50926E6B492183300CA58A886927"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Elément </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Nom </span> </p> </td> 
   <td colname="col2"> <p>Nom convivial de la variable de conversion. Il s’agit du nom auquel l’eVar est référencée dans le  général et du nom du rapport dans le menu de gauche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Type</span> </p> <p>(eVar uniquement) </p> </td> 
   <td colname="col2"> <p>Type de valeur de variable : </p> <p> <b>Chaîne de texte</b> :</span> capture les valeurs textuelles utilisées sur votre site. Il s’agit du type d’eVar le plus courant et du paramètre par défaut. Il agit de la même manière que les autres variables, où la valeur qu’il contient est une chaîne de texte statique. Si vous effectuez le suivi d’éléments tels que des campagnes internes ou des mots-clés de recherche interne, il s’agit du paramètre recommandé. </p> <p> <b>Compteur</b> :</span> compte le nombre d’occurrences d’une action avant l’événement de succès. Si, par exemple, vous utilisez une eVar pour suivre les recherches internes sur votre site, définissez cette valeur sur <span class="uicontrol">Chaîne de texte</span> pour suivre l’utilisation des termes de recherche. Définissez cette valeur sur <span class="uicontrol">Compteur</span> pour compter le nombre de recherches effectuées, quels que soient les termes recherchés. Par exemple, vous pouvez utiliser une eVar de compteur pour effectuer le suivi du nombre de fois où une personne a utilisé votre recherche interne avant d’effectuer un achat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol">Attribution</span> </p> </td> 
   <td colname="col2"> <p>Détermine la manière dont Analytics attribue le crédit d’un de réussite si une variable reçoit plusieurs valeurs avant le  du. Les valeurs prises en charge sont les suivantes : </p> <p> <b>Le plus récent</b> : la dernière valeur eVar reçoit le crédit des événements de succès jusqu’à l’expiration de l’eVar. </p> <p> <b>Valeur d’origine</b> : la première valeur eVar reçoit le crédit des événements de succès jusqu’à l’expiration de l’eVar. </p> <p> <b> Linéaire</b> : attribue uniformément les événements de succès sur toutes les valeurs eVar. Puisque l’attribution linéaire ne répartit précisément les valeurs que dans une visite, utilisez-la avec une expiration d’eVar de visite. </p> <p>Remarque : l’activation ou la désactivation d’une attribution de type Linéaire empêche l’affichage des données historiques. Le mélange des types d’allocation dans l’interface  du peut entraîner des données erronées dans les rapports. Par exemple, l’attribution linéaire peut diviser les recettes entre plusieurs valeurs d’eVar différentes. Après avoir rétabli l’affectation Le plus récent, 100 % de ces recettes seraient associées à la valeur unique la plus récente. Cette association peut conduire à des conclusions incorrectes de la part des utilisateurs. </p> <p>Pour éviter tout risque de confusion dans les , Analytics rend les données historiques indisponibles pour l’interface. Il peut être affiché si vous décidez de rétablir le paramètre d’attribution initial de l’eVar donnée, même si vous ne devez pas modifier les paramètres d’attribution d’eVar simplement pour accéder aux données historiques. Adobe recommande d’utiliser une nouvelle eVar lorsque de nouveaux paramètres d’attribution sont souhaités pour les données déjà enregistrées, plutôt que de modifier les paramètres d’attribution sur une eVar qui comporte déjà une quantité importante de données historiques. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Expire après</span> </p> </td> 
   <td colname="col2"> <p>Indique une période, ou , au terme de laquelle la valeur eVar expire (ne reçoit plus de crédit pour les  de réussite). Si un événement de succès se produit après l’expiration de l’eVar, la valeur Aucun reçoit le crédit pour l’événement (aucune valeur eVar n’était active). </p> <p>Si vous sélectionnez un  comme valeur d’expiration, la variable n’expire que si le se produit. Si le  ne se produit pas, la variable n’expire jamais. </p> <p>Les options d’expiration disponibles peuvent être classées sous quatre  principaux : </p> 
    <ul id="ul_810A37C9B6624F429F2FB45C18F7B43F"> 
     <li id="li_654D9D9044EC4E61AA7ABA372DBF8A93"><b>Au niveau d’un de page ou d’une visite.</b> Les de conversion  au-delà du de page ou de la visite ne sont pas associés à l’eVar. </li> 
     <li id="li_689FBC8B4DAC41B3B0166E6586DD1990"><b>Basé sur une période, telle qu’un jour, une semaine, un mois ou une année.</b> Les de conversion  au-delà de la période spécifiée ne sont pas associés à l’eVar. Période d’expiration lorsque la variable est définie. Les eVars expirent en fonction de l’heure à laquelle elles ont été définies, à la seconde (minute, heure, jour, mois, etc.) : 
      <ul id="ul_80C7E3182B6B4356B8A3CA920B81C6D5"> 
       <li id="li_F16F60319CCE406D9EDEFEC0A200BC4D">MINUTE=60 secondes </li> 
       <li id="li_45F47F3F5691415B84052B235DF3BB54">HEURE=3 600 secondes (60 minutes) </li> 
       <li id="li_5288CE7D168E4C85B3D9BB67A44D32EC">JOUR=86 400 secondes (24 heures) </li> 
       <li id="li_60FC8BCD657745EE87B4E458CBA69583">SEMAINE=604 800 secondes (7 jours) </li> 
       <li id="li_7A05A66613C84F929F030310B9567CF5">MOIS=2 67 8400 secondes (31 jours) </li> 
       <li id="li_DCD3CABF59E34D5999B03E606B08AD85">TRIMESTRE=8035200 secondes (93 jours - 3 mois sur 31 jours) </li> 
       <li id="li_54351D2899454D39A8BA205910D2CCB1">AN=31 536 000 secondes (365 jours) </li> 
      </ul> <p> </p> <p>Si une visite  à 7 h 00 le lundi et qu’une eVar est définie dans cette visite à 7 h 15, l’expiration est la suivante : </p> 
      <ul id="ul_72B311006BE6428698313D251C0940DB"> 
       <li id="li_50925D4A40AD4ACA88704A523138C5B9">Expiration du jour : L’eVar expire à 7:15 le mardi. </li> 
       <li id="li_25846328766D4B4BAF407236C65C956C">Expiration de la semaine : eVar expire le lundi suivant à 7:15. </li> 
       <li id="li_82DB2D7F53304623A5E1241D75C7DF94">Expiration du mois : L’eVar expire 31 jours à partir du lundi à 7:15. </li> 
      </ul> </li> 
     <li id="li_C132C5C5A5344B91BDF5EB6A1C717C37"><b>de conversion spécifique.</b> Tout autre de conversion qui se déclenche après le spécifique  désigné comme associé à l’eVar. </li> 
     <li id="li_5A782D743FB940649E6CB3E4BEA9B8B6"><b>Jamais.</b> Tant que le cookie <span class="varname"> visitorID</span> est intact, un laps de temps indéfini peut s’écouler entre l’eVar et l’événement. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> État</span> </p> <p>(eVar uniquement) </p> </td> 
   <td colname="col2"> <p>Définit l’état de l’eVar : </p> <p><b>Désactivé</b> :</span> désactive la variable eVar. Supprime l’eVar de la liste des variables de conversion. </p> <p> <b>Sans sous-relations</b> :</span> empêche de ventiler l’eVar avec une sous-relation. </p> <p> <b>Sous-relations de base</b> :</span> permet de ventiler une variable eVar en fonction de n’importe quel rapport avec des sous-relations complètes (Produits ou Campagnes, par exemple). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Réinitialiser le</span> </p> </td> 
   <td colname="col2"> <p>Réinitialise toute valeur existante dans l’eVar. </p> <p>Utilisez ce paramètre lorsque vous redéfinissez l’objectif d’une eVar afin de combiner une ancienne valeur dans un nouveau rapport. La réinitialisation n’efface pas les données historiques. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Marchandisage</span> </p> <p>(eVar uniquement) </p> </td> 
   <td colname="col2"> <p>Les variables de marchandisage peuvent suivre l’une des deux syntaxes suivantes : </p> <p> <b>Syntaxe Produits</b> :</span> associe la valeur eVar à un produit. Remarque : si Syntaxe Produits est sélectionné, la section Événement de liaison de marchandisage est désactivée et ne peut pas être sélectionnée pour modification. Pour cette syntaxe, les événements de liaison ne sont pas applicables. </p> </p> <p> <b>Syntaxe de la variable de conversion</b> :</span> associe uniquement la valeur eVar à un produit si un événement de liaison survient. Dans ce cas, sélectionnez les événements qui se comportent comme des événements de liaison. </p> <p>Si vous modifiez ce paramètre sans mettre à jour votre code JavaScript, vous perdrez des données. Voir <a href="https://marketing.adobe.com/resources/help/fr_FR/sc/implement/var_merchandising.html"> Variables de marchandisage</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Événement de liaison de marchandisage</span> </p> <p>(eVar uniquement) </p> </td> 
   <td colname="col2"> <p>Si le marchandisage est défini sur <span class="uicontrol"> Syntaxe de la variable de conversion</span>, les événements sélectionnés lieront la valeur de l’eVar active à un produit. </p> <p>Pour utiliser un événement de liaison, définissez l’attribution sur <span class="uicontrol"> Le plus récent</span>. Si <span class="uicontrol">l’attribution est définie sur Valeur d’origine</span>, la première liaison de produit eVar demeure jusqu’à l’expiration de l’eVar. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Expiration**

Les `eVars` arrivent à expiration après une période que vous avez spécifiée. Une fois l’eVar expirée, elle ne reçoit plus de crédit pour les  de réussite. Vous pouvez également configurer les eVars pour qu’elles arrivent à expiration lors d’un événement de succès. Si, par exemple, vous disposez d’une promotion interne qui expire à la fin d’une visite, la promotion interne reçoit le crédit uniquement pour les achats ou les inscriptions survenant pendant la visite au cours de laquelle ils ont été activés.

Une eVar peut expirer de deux manières :

* Vous pouvez définir l&#39;eVar pour qu&#39;elle arrive à expiration après une période ou un spécifique.
* Vous pouvez forcer l’expiration d’une eVar en la réinitialisant, ce qui s’avère utile lors de la réaffectation d’une variable.

Par exemple, si vous modifiez l’expiration d’une eVar de 30 à 90 jours, les valeurs d’eVar collectées continueront à persister pendant la durée du nouveau jeu d’expiration (dans ce cas, 90 jours). Le système examine simplement le paramètre d’expiration actuel et le dernier horodatage défini de la valeur eVar collectée pour déterminer l’expiration. Seule l’ **[!UICONTROL Reset]** option expire les valeurs et le fait immédiatement.

Autre exemple : Si une eVar est utilisée en mai pour refléter les promotions internes et expire après 21 jours, et qu’en juin elle est utilisée pour capturer les mots-clés de recherche interne, le 1er juin, vous devez forcer l’expiration de la variable ou la réinitialiser. De cette manière, les valeurs de promotion interne ne figureront pas dans les rapports du mois de juin.

**Respect de la casse**

Les eVars ne sont pas sensibles à la casse, mais elles respectent la mise en majuscules de la première occurrence. Par exemple, si la première instance d’eVar1 est définie sur &quot;Connecté&quot;, mais que toutes les instances suivantes sont transmises sous la forme &quot;connecté&quot;, les rapports affichent toujours &quot;Connecté&quot; comme valeur de l’eVar.

**Compteurs**

Bien que les eVars soient généralement utilisées pour contenir des valeurs de chaîne, elles peuvent également être configurées pour faire office de compteurs. Elles s’avèrent particulièrement utiles sous cette forme lorsque vous essayez de comptabiliser le nombre d’actions qu’un utilisateur effectue avant un événement. Vous pouvez, par exemple, utiliser une eVar pour capturer le nombre de recherches internes avant un achat. Chaque fois qu’un visiteur effectue une recherche, l’eVar doit contenir une valeur « +1 ». Si un utilisateur effectue quatre recherches avant un achat, une instance est affichée pour chaque compte total : 1.00, 2.00, 3.00 et 4.00. Cependant, seule la valeur 4.00 reçoit du crédit pour l’événement d’achat (mesures Commandes et Recettes). Seuls les nombres positifs sont autorisés comme valeurs d’un compteur d’eVar.