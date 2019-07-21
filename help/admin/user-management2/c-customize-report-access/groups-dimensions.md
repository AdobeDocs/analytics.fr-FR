---
description: Personnalisez l’accès des utilisateurs à un niveau plus détaillé, y compris les eVars, les rapports de trafic, les rapports de solution et les rapports de cheminement.
keywords: groupes ; autorisations
seo-description: Personnalisez l’accès des utilisateurs à un niveau plus détaillé, y compris les eVars, les rapports de trafic, les rapports de solution et les rapports de cheminement.
seo-title: Personnalisation des autorisations de dimension
solution: Analytics
subtopic: Utilisateurs et groupes
title: Personnalisation des autorisations de dimension
topic: Outils d’administration
uuid: aaf 164 ad -3863-4129-864 e -39 ec 71 c 6 a 8 eb
translation-type: tm+mt
source-git-commit: e3b1ac3139f26ca3a97f3d2228276e690ec4cb79

---


# Personnalisation des autorisations de dimension

>[!IMPORTANT]
>
>User and product management is moving to the [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Adobe vous avertira lorsqu’il sera temps de migrer les utilisateurs. After all customers have migrated, help content for **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin Tools]** &gt; **[!UICONTROL User Management]** will be retired.

Personnalisez l’accès des utilisateurs à un niveau plus détaillé, y compris les eVars, les rapports de trafic, les rapports de solution et les rapports de cheminement.

**[!UICONTROL Gestion utilisateur]** &gt; **[!UICONTROL Groupes]** &gt; **[!UICONTROL Accès aux rapports]** &gt; **[!UICONTROL Dimensions]** &gt; **[!UICONTROL Personnaliser]**

>[!IMPORTANT]
>
>Actuellement, certaines dimensions ne peuvent pas faire l'objet d'autorisations. Il s’agit des dimensions suivantes : Longueur du signet mobile ; Numéro d’appareil mobile ; DRM mobile ; Services d’informations mobiles ; Java VM de mobile ; Mobile – Décoration de courrier ; Protocoles Net mobile ; SE Mobile ; Mobile – Presser pour parler.
>
>Ces dimensions sont disponibles pour tous les utilisateurs, quelles que soient les autres autorisations.

Les paramètres sur cette page se rapportent aux suites de rapports sélectionnées sur la page [!UICONTROL Définir un groupe d’utilisateurs].

![](assets/permissions-dimensions.png)

Consultez les informations suivantes au sujet de la catégorie Dimension en ce qui a trait aux autorisations.

* Les eVars 1 à 250 sont autorisées individuellement.
* Tous les rapports sur le trafic sont des dimensions.
* Les rapports Vidéo et Mobile sont des dimensions, ainsi que d'autres rapports de solutions Analytics (Experience Manager, Advertizing Cloud, Social, etc.).
* Les rapports de cheminement sont accessibles aux utilisateurs qui ont accès à la dimension parente.
* Toutes les dimensions et les mesures actuelles des groupes personnalisés ont été automatiquement transférées dans les nouvelles catégories. Si un groupe comprend des mesures actives, il obtiendra par défaut toutes les dimensions (eVars et reconnaissance du contenu) et mesures nouvellement autorisables.
* Droits d’accès de l’importateur de classifications (anciennement SAINT) : l’accès aux classifications est déterminé par l’accès à la [variable](https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html) sur laquelle repose la classification.

Pour en savoir plus, voir [Questions fréquentes sur les modifications de droits d’accès](https://marketing.adobe.com/resources/help/en_US/reference/permissions_faq.html).

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
   <td colname="col1"> <p> <a href="../../../admin/admin/conversion-var-admin/conversion-var-admin.md#concept_C02F7AA01DE242F1AA1A4E74022BE9DE" format="dita" scope="local"> eVars </a> </p> </td> 
   <td colname="col2"> <p>Les eVars 1 à 250 sont autorisées individuellement. Les eVars sont des variables de conversion personnalisées que vous utilisez pour segmenter les mesures de succès de conversion des segments dans les rapports personnalisés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/props_eVars.html" format="html" scope="external"> Props </a> </p> </td> 
   <td colname="col2"> <p>Les props sont des variables de trafic personnalisées. </p> <p>Voir <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/props_eVars.html" format="html" scope="external">Props de trafic et eVars de conversion</a> dans la mise en œuvre Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/hierN.html" format="html" scope="external"> Hiérarchie </a> </p> </td> 
   <td colname="col2"> <p> La variable de hiérarchie (hierN) détermine l’emplacement d’une page dans la hiérarchie de votre site ou la structure d’une page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/listN.html" format="html" scope="external"> Listvar </a> </p> </td> 
   <td colname="col2"> <p> À l’instar de la fonction Propriétés de liste, les variables de liste permettent la définition de plusieurs valeurs dans une même demande d’image. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard </p> </td> 
   <td colname="col2"> <p>Se rapporte aux Dimensions prêtes à l'emploi dans Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/em/" format="https" scope="external"> AEM </a> </p> </td> 
   <td colname="col2"> <p>Adobe Experience Manager    </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/media-optimizer/" format="https" scope="external"> AMO </a> </p> </td> 
   <td colname="col2"> <p>Adobe Advertising Cloud </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/" format="https" scope="external"> Activity Map </a> </p> </td> 
   <td colname="col2"> <p> Dimensions des rapports Activity Map : page d’Activity Map ; lien d’Activity Map ; région d’Activity Map ; lien d’Activity Map par région ; Activity Map XY </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/" format="https" scope="external"> Mobile </a> </p> </td> 
   <td colname="col2"> <p>Adobe Mobile Services </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Comscore </p> </td> 
   <td colname="col2"> <p>Cette intégration de partenaire n’est plus active. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/nielsen-partnership.html" format="html" scope="external"> Nielsen </a> </p> </td> 
   <td colname="col2"> <p>Intégrations partenaires. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Social </p> </td> 
   <td colname="col2"> <p>Inutilisé. </p> </td> 
  </tr> 
 </tbody> 
</table>

