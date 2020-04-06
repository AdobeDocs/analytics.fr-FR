---
description: Personnalisez l’accès des utilisateurs à un niveau plus détaillé, y compris les eVars, les rapports de trafic, les rapports de solution et les rapports de cheminement.
keywords: groups;permissions
subtopic: Users and groups
title: Personnalisation des autorisations liées aux dimensions
topic: Admin tools
uuid: aaf164ad-3863-4129-864e-39ec71c6a8eb
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Personnalisation des autorisations liées aux dimensions

>[!IMPORTANT] La gestion des utilisateurs et des produits aura dorénavant lieu dans [Admin Console](https://helpx.adobe.com/fr/enterprise/using/admin-console.html). Adobe vous avertira lorsqu’il sera temps de migrer les utilisateurs. After all customers have migrated, help content for **[!UICONTROL Analytics]** > **[!UICONTROL Admin Tools]** > **[!UICONTROL User Management]** will be retired.

Personnalisez l’accès des utilisateurs à un niveau plus détaillé, y compris les eVars, les rapports de trafic, les rapports de solution et les rapports de cheminement.

**[!UICONTROL User Management]** > **[!UICONTROL Groups]** > **[!UICONTROL Report Access]** > **[!UICONTROL Dimensions]** > **[!UICONTROL Customize]**

>[!IMPORTANT] Certaines dimensions ne requièrent pas d’autorisation à l’heure actuelle. Ces dimensions sont les suivantes : Longueur des signets mobiles ; Numéro de dispositif portable; DRM mobile ;  mobiles ; Java VM mobile ; Mobile Mail Decoration ; Protocoles réseau mobile; SE mobile ; Pression mobile pour parler.
>
>Ces dimensions sont disponibles pour tous les utilisateurs, indépendamment des autres autorisations.

Les paramètres de cette page concernent les suites de rapports sélectionnées sur la [!UICONTROL Define User Groups] page.

![](assets/permissions-dimensions.png)

Découvrez les informations suivantes sur le de dimensions pour les autorisations.

* Les eVars 1 à 250 sont autorisées individuellement.
* Tous les rapports de trafic sont des dimensions.
* Les rapports Vidéo et Mobile sont des dimensions, ainsi que d’autres rapports de solutions Analytics (Experience Manager, Advertising Cloud, Social, etc.).
* Les rapports de cheminement sont disponibles si un utilisateur a accès à la dimension parent.
* Toutes les dimensions et mesures actuelles dans les groupes personnalisés ont été automatiquement migrées vers le nouveau  de. Si des mesures sont activées pour un groupe existant, toutes les nouvelles dimensions (eVars et reconnaissance du contenu) et mesures qui peuvent faire l’objet de droits d’accès sont attribuées par défaut.
* Droits d’accès de l’importateur de classifications (anciennement SAINT) : l’accès aux classifications est déterminé par l’accès à la [variable](https://marketing.adobe.com/resources/help/fr_FR/reference/c_classifications.html) sur laquelle repose la classification.

Pour plus d’informations, voir Questions [fréquentes sur les modifications](https://marketing.adobe.com/resources/help/fr_FR/reference/permissions_faq.html)des autorisations.

**Personnaliser les dimensions**

Les éléments suivants sont des dimensions que vous pouvez autoriser.

<table id="table_F37D74A1619A4560A5F5651E855DAF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elément </th> 
   <th colname="col2" class="entry"> Descriptions </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/admin/admin/conversion-var-admin/conversion-var-admin.md"> eVars </a> </p> </td> 
   <td colname="col2"> <p>Les eVars 1 à 250 sont autorisées individuellement. Les eVars sont des variables de conversion personnalisées que vous utilisez pour segmenter les mesures de réussite de conversion dans les rapports personnalisés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/fr_FR/sc/implement/props_eVars.html"> Propriétés </a> </p> </td> 
   <td colname="col2"> <p>Les props sont des variables de trafic personnalisées. </p> <p>Voir <a href="https://marketing.adobe.com/resources/help/fr_FR/sc/implement/props_eVars.html">Props de trafic et eVars de conversion</a> dans la mise en œuvre Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/fr_FR/sc/implement/hierN.html"> Hiérarchie </a> </p> </td> 
   <td colname="col2"> <p> La variable de hiérarchie (hierN) détermine l’emplacement d’une page dans la hiérarchie de votre site ou la structure d’une page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/fr_FR/sc/implement/listN.html"> Listvar </a> </p> </td> 
   <td colname="col2"> <p> Tout comme la fonction  Props, les variables  de autorisent plusieurs valeurs dans la même demande d’image. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard </p> </td> 
   <td colname="col2"> <p>Se rapporte aux Dimensions standard (prêtes à l’emploi) dans Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/fr_FR/em/"> AEM </a> </p> </td> 
   <td colname="col2"> <p>Adobe Experience Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/media-optimizer/"> AMO </a> </p> </td> 
   <td colname="col2"> <p>Adobe Advertising Cloud </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/fr_FR/analytics/activitymap/">Activity Map </a> </p> </td> 
   <td colname="col2"> <p> Dimensions des rapports Activity Map : page d’Activity Map ; lien d’Activity Map ; région d’Activity Map ; lien d’Activity Map par région ; Activity Map XY </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/fr_FR/mobile/"> Mobile </a> </p> </td> 
   <td colname="col2"> <p>Adobe Mobile Services </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Comscore </p> </td> 
   <td colname="col2"> <p>Cette intégration de partenaire n’est plus active. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/fr-FR/media-analytics/using/media-overview.html"> Nielsen </a> </p> </td> 
   <td colname="col2"> <p>Cette intégration de partenaire n’est plus active. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Social </p> </td> 
   <td colname="col2"> <p>Inutilisé. </p> </td> 
  </tr> 
 </tbody> 
</table>
