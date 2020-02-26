---
description: La page Méthodes de recherche identifie comment les divers rapports de méthodes de recherche reçoivent le crédit des événements de succès de conversion sur votre site. Si, par exemple, un moteur de recherche dirige vers votre site un visiteur qui effectue un achat, les méthodes de recherche définissent la manière dont le moteur de recherche reçoit du crédit pour ce renvoi
title: Méthodes de recherche
topic: Admin tools
uuid: 1053993e-7fc4-4874-84fa-367ecdcd7b45
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Méthodes de recherche

La page Méthodes de recherche identifie comment les divers rapports de méthodes de recherche reçoivent le crédit des événements de succès de conversion sur votre site. Si, par exemple, un moteur de recherche dirige vers votre site un visiteur qui effectue un achat, les méthodes de recherche définissent la manière dont le moteur de recherche reçoit du crédit pour ce renvoi

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Conversion]** > **[!UICONTROL Méthodes de recherche]**.

## Description des méthodes de recherche {#section_8B6278DB75224EAB9F49D89A86274E8A}

<table id="table_8ABC1C9BD63F419082E4C4C69E401526"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nom </td> 
   <td colname="col2"> Méthode de recherche que vous souhaitez modifier. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Attribution </td> 
   <td colname="col2"> Indique comment appliquer du crédit pour un renvoi. Les options d’affectation prises en charge sont les suivantes : <p> <span class="uicontrol"> Le plus récent (Dernier) :</span> accorde tout le crédit au dernier référent (par défaut). </p> <p> <span class="uicontrol"> Valeur d’origine :</span> attribue tout le crédit au premier référent. </p> <p> <span class="uicontrol"> Linéaire :</span> répartit le crédit uniformément entre tous les référents. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Expire après </td> 
   <td colname="col2"> 
    <ul id="ul_95EB224CAD164E9997B148E08AFA5F9B"> 
     <li id="li_C240460C21E14AA498D2EA62B9354710"> <span class="uicontrol"> Visite :</span> après une période d’inactivité spécifiée ; de 30 minutes, en général. </li> 
     <li id="li_A3AE5438919E44B68DF99BEEA60C44EE"> <span class="uicontrol"> Page vue :</span> dès qu’une page est ouverte sur votre site. </li> 
     <li id="li_D5E20FEF313E4C5B99E7097CA175761A"> <span class="uicontrol"> Minute :</span> après 1 minute d’inactivité. </li> 
     <li id="li_7315AA3EDDBB47A2BEA3C173881378A1"> <span class="uicontrol"> Achat :</span> au moment de l’achat. </li> 
     <li id="li_C0CF07581654472C9C9EC944E6F18164"> <span class="uicontrol"> Consultation produit :</span> lorsqu’un visiteur affiche la page web d’un produit. </li> 
     <li id="li_A1B04065150B407491D2EC78EC0DBDF5"> <span class="uicontrol"> Ouverture de panier :</span> lorsqu’un visiteur ouvre un nouveau panier en ligne. </li> 
     <li id="li_2AA50C6B9CB14500B67909CDF2AA700C"> <span class="uicontrol"> Achat de panier :</span> lorsqu’un visiteur passe en caisse pour payer son panier en ligne. </li> 
     <li id="li_F58CE6FB8DCE4BE4927FFCB35A6D8E31"> <span class="uicontrol"> Ajout de panier :</span> lorsqu’un visiteur ajoute un produit à un panier en ligne. </li> 
     <li id="li_AD7C846F46604FC48E0919ACB7515E14"> <span class="uicontrol"> Retrait du panier :</span> lorsqu’un visiteur supprime un produit de son panier en ligne. </li> 
     <li id="li_EB66E0563F564C9F985BE922DABD0A56"> <span class="uicontrol"> Ouverture de panier :</span> lorsqu’un visiteur affiche le contenu d’un panier en ligne. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

> [!NOTE] Toutes les méthodes de recherche expirent à la fin d’une visite. Si vous choisissez l’option d’expiration après un autre événement (le Passage en caisse, par exemple), la Méthode de recherche expire quand le Passage en caisse survient pendant la visite. Si le Passage en caisse ne se produit pas pendant la visite, la Méthode de recherche expire quand même à la fin de la visite.

