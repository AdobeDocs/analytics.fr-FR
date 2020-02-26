---
description: Personnalisez l’accès des utilisateurs à un niveau plus détaillé, y compris les eVars, les rapports de trafic, les rapports de solution et les rapports de cheminement.
keywords: groups;permissions
subtopic: Users and groups
title: Personnalisation des autorisations liées aux dimensions
topic: Admin tools
uuid: aaf164ad-3863-4129-864e-39ec71c6a8eb
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Personnalisation des autorisations liées aux dimensions

> [!IMPORTANT] La gestion des utilisateurs et des produits aura dorénavant lieu dans [Admin Console](https://helpx.adobe.com/fr/enterprise/using/admin-console.html). Adobe vous avertira lorsqu’il sera temps de migrer les utilisateurs. Une fois tous les utilisateurs migrés, le contenu d’aide **[!UICONTROL Analytics]** > **[!UICONTROL Outils d’administration]** > **[!UICONTROL Gestion des utilisateurs]** sera retiré.

Personnalisez l’accès des utilisateurs à un niveau plus détaillé, y compris les eVars, les rapports de trafic, les rapports de solution et les rapports de cheminement.

**[!UICONTROL Gestion des utilisateurs]** > **[!UICONTROL Groupes]** > **[!UICONTROL Accès aux rapports]** > **[!UICONTROL Dimensions]** > **[!UICONTROL Personnaliser]**

> [!IMPORTANT] Certaines dimensions ne requièrent pas d’autorisation à l’heure actuelle. Il s’agit des dimensions suivantes : Longueur du signet mobile ; Numéro d’appareil mobile ; DRM mobile ; Services d’informations mobiles ; Java VM de mobile ; Mobile – Décoration de courrier ; Protocoles Net mobile ; SE Mobile ; Mobile – Presser pour parler.
>
>Ces dimensions sont disponibles pour tous les utilisateurs, quelles que soient les autres autorisations.

Les paramètres sur cette page se rapportent aux suites de rapports sélectionnées sur la page [!UICONTROL Définir un groupe d’utilisateurs].

![](assets/permissions-dimensions.png)

Consultez les informations suivantes au sujet de la catégorie Dimension en ce qui a trait aux autorisations.

* Les eVars 1 à 250 sont autorisées individuellement.
* Tous les rapports sur le trafic sont des dimensions.
* Les rapports Vidéo et Mobile sont des dimensions, ainsi que d’autres rapports de solutions Analytics (Experience Manager, Advertising Cloud, Social, etc.).
* Les rapports de cheminement sont accessibles aux utilisateurs qui ont accès à la dimension parente.
* Toutes les dimensions et les mesures actuelles des groupes personnalisés ont été automatiquement transférées dans les nouvelles catégories. Si un groupe comprend des mesures actives, il obtiendra par défaut toutes les dimensions (eVars et reconnaissance du contenu) et mesures nouvellement autorisables.
* Droits d’accès de l’importateur de classifications (anciennement SAINT) : l’accès aux classifications est déterminé par l’accès à la [variable](https://marketing.adobe.com/resources/help/fr_FR/reference/c_classifications.html) sur laquelle repose la classification.

Pour en savoir plus, voir [Questions fréquentes sur les modifications de droits d’accès](https://marketing.adobe.com/resources/help/fr_FR/reference/permissions_faq.html).

**Personnalisation des dimensions**

Les éléments suivants sont des dimensions pour lesquelles vous pouvez accorder des autorisations.

<table id="table_F37D74A1619A4560A5F5651E855DAF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Descriptions </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/admin/admin/conversion-var-admin/conversion-var-admin.md"> eVars </a> </p> </td> 
   <td colname="col2"> <p>Les eVars 1 à 250 sont autorisées individuellement. Les eVars sont des variables de conversion personnalisées que vous utilisez pour segmenter les mesures de succès de conversion des segments dans les rapports personnalisés. </p> </td> 
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
   <td colname="col2"> <p> À l’instar de la fonction Propriétés de liste, les variables de liste permettent la définition de plusieurs valeurs dans une même demande d’image. </p> </td> 
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
