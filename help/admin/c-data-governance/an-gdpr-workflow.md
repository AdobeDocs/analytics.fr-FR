---
description: valeur nulle
seo-description: valeur nulle
seo-title: Flux de travaux sur la confidentialité des données Adobe Analytics
title: Flux de travaux sur la confidentialité des données Adobe Analytics
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
translation-type: tm+mt
source-git-commit: 21fe6a0ee434e430d77a24d060acd2ffce08e219

---


# Flux de travaux sur la confidentialité des données Adobe Analytics

Bienvenue dans Adobe Analytics et la préparation à la confidentialité des données ! Ce flux de travaux décrit les étapes à suivre pour rendre votre implémentation Adobe Analytics prête à prendre en charge l’accès à la confidentialité des données de vos personnes et les droits de suppression.

<table id="table_0E561F62247A4D01B6E7180560082DC9"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Description de tâche </th> 
   <th colname="col3" class="entry"> Liens vers les instructions et informations supplémentaires </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step1_icon.png" id="image_15849358972A4846A54FCB51997576D5" /> Assurez-vous que toutes vos suites de rapports pouvant contenir des données relatives à la confidentialité des données sont mises en correspondance avec votre organisation Experience Cloud (ou IMS). </p> <p>Les demandes de confidentialité des données sont envoyées à l’aide d’une organisation Experience Cloud et seront appliquées à toutes les suites de rapports demandées par cette organisation. Les demandes ne s’appliqueront pas aux suites de rapports non mappées à cette organisation, même si elles font partie de votre société de connexion. </p> </td> 
   <td colname="col3"> <p>Reportez-vous à <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html" format="html" scope="external">Mapper les suites de rapports à une organisation</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step2_icon.png" id="image_372B2C65DFAD46E39AE4D715313ABD0E"/> Définissez votre politique de conservation des données. </p> </td> 
   <td colname="col3"> <p>Une politique de rétention des données doit être en place pour qu’Adobe puisse traiter les demandes d’accès aux données de confidentialité/suppression des données. </p> <p>Pour plus d’informations, voir la <a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html" format="html" scope="external">FAQ sur la conservation des données Analytics</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step3_icon.png" id="image_30DB956290CC4E64A7085B46364BE059" /> Familiarisez-vous avec les libellés de confidentialité DULE/Data, les ID Adobe Analytics, les espaces de noms et l’extension des identifiants. </p> </td> 
   <td colname="col3"> <p> Lisez ces rubriques contenues dans ces documents : 
     <ul id="ul_F6E94B9281D446DB8F1F859F6056543B"> 
      <li id="li_6389D094B4B04CA181E5F077BF8C0F8E"><!--<a href="../../admin/c-data-governance/gdpr-labels.md#concept_F4061E29353446B5B0A7CF248D54E6F2" format="dita" scope="local"> Data Privacy Labels for Analytics Variables</a>--> </li> 
      <li id="li_CEEF2106E37845A49E0EA1225D5CFF14">Elément de liste </li> 
      <li id="li_0B79CEBD074A4C68923EE9C9766D4B9D"><!--<a href="../../admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local"> Labeling Best Practices</a>--> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img  src="assets/step4_icon.png" id="image_FE2039B8345248BCA303B44C10B68EA1" placement="break" /> Attribuez des étiquettes d’identité, de sensibilité et de gouvernance des données à chaque variable dans une suite de rapports. </p> <p>Remarque : Souvenez-vous que l’étiquetage doit être vérifié chaque fois qu’une nouvelle suite de rapports est créée ou qu’une nouvelle variable est activée dans une suite de rapports existante. Il peut également être nécessaire de vérifier l’étiquetage lors de l’activation de nouvelles intégrations à des solutions puisque celles-ci peuvent exposer de nouvelles variables nécessitant un étiquetage. Une nouvelle implémentation de vos applications mobiles ou sites web peut modifier la manière dont les variables existantes sont utilisées, rendant nécessaire la mise à jour des étiquettes. </p> </td> 
   <td colname="col3"> <p> Suivez les instructions de la section <!--<a href="../../admin/c-data-governance/gdpr-setup-reportsuite.md#concept_FAA948AD8CEA4BC38CB482EAF3648731" format="dita" scope="local"> Label Report Suite Data</a>-->. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step5_icon.png" id="image_E9BEF83BF30F4528A030F23F71E5E5D8" /> Connectez-vous à l’API de confidentialité des données Adobe et envoyez des demandes d’accès et de suppression. </p> </td> 
   <td colname="col3"> <p>As an Adobe Analytics customer, you can submit individual Data Privacy requests to access and delete customer data, by calling the <a href="https://www.adobe.io/apis/cloudplatform/gdpr.html" format="html" scope="external"> Adobe Experience Cloud Data Privacy API</a>. </p> <p>You can submit any Analytics identifiers (as described in the section <!--<a href="../../admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local"> Labeling Best Practices</a>-->) in the requests along with their respective namespace IDs (data source IDs). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step6_icon.png" id="image_5CF03706FECD4F8BBAE0D0C19F98B8BB" /> Affichez et gérez les paramètres de confidentialité des données de votre suite de rapports. </p> </td> 
   <td colname="col3"> <p>Suivez les instructions de la section <!--<a href="../../admin/c-data-governance/gdpr-view-settings.md#concept_7759BAD6F3174901A94116D189AEF80E" format="dita" scope="local"> View Report Suite's Data Governance Settings</a>-->. </p> </td> 
  </tr> 
 </tbody> 
</table>

| Description de tâche | Liens vers les instructions et informations supplémentaires |
|--- |--- |
| **Étape 1**: Assurez-vous que toutes vos suites de rapports pouvant contenir des données relatives à la confidentialité des données sont mises en correspondance avec votre organisation Experience Cloud (ou IMS).  Les demandes de confidentialité des données sont envoyées à l’aide d’une organisation Experience Cloud et seront appliquées à toutes les suites de rapports demandées par cette organisation. Les demandes ne s’appliqueront pas aux suites de rapports non mappées à cette organisation, même si elles font partie de votre société de connexion. | Reportez-vous à [Mapper les suites de rapports à une organisation.](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html) |
| **Étape 2** Définissez votre stratégie de rétention des données. | Une politique de rétention des données doit être en place pour qu’Adobe puisse traiter les demandes d’accès aux données de confidentialité/suppression des données.  Pour plus d’informations, voir la [FAQ sur la conservation des données Analytics.](/help/technotes/data-retention.md) |
| **Étape 3**: Familiarisez-vous avec les libellés de confidentialité DULE/Data, les ID Adobe Analytics, les espaces de noms et l’extension des identifiants. | Lisez ces rubriques contenues dans ces documents :<ul><li>[Étiquettes de confidentialité des données pour les variables Analytics](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[Bonnes pratiques en matière d’étiquetage](/help//admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E)</li></ul> |
| **Étape 4**: Affectez des étiquettes d’identité, de sensibilité et de gouvernance des données à chaque variable d’une suite de rapports.  Remarque : Souvenez-vous que l’étiquetage doit être vérifié chaque fois qu’une nouvelle suite de rapports est créée ou qu’une nouvelle variable est activée dans une suite de rapports existante. Il peut également être nécessaire de vérifier l’étiquetage lors de l’activation de nouvelles intégrations à des solutions puisque celles-ci peuvent exposer de nouvelles variables nécessitant un étiquetage. Une nouvelle implémentation de vos applications mobiles ou sites web peut modifier la manière dont les variables existantes sont utilisées, rendant nécessaire la mise à jour des étiquettes. | Suivez les instructions de la section [Étiquetage des données de suite de rapports.](/help//admin/c-data-governance/gdpr-setup-reportsuite.md#concept_FAA948AD8CEA4BC38CB482EAF3648731) |
| **Étape 5**: Connectez-vous à l’API de confidentialité des données Adobe et envoyez des demandes d’accès et de suppression. | As an Adobe Analytics customer, you can submit individual Data Privacy requests to access and delete customer data, by calling the [Adobe Experience Cloud Data Privacy API.](https://www.adobe.io/apis/experienceplatform/gdpr.html) Vous pouvez soumettre tous les identifiants Analytics (comme décrit dans la section [Bonnes pratiques en matière d’étiquetage](/help//admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E)) dans les demandes, ainsi que leurs ID d’espace de noms respectifs (ID de source de données). |
| **Étape 6**: Affichez et gérez les paramètres de confidentialité des données de votre suite de rapports. | Suivez les instructions de la section [Affichage des paramètres de gouvernance des données de la Report Suite.](/help/admin/c-data-governance/gdpr-view-settings.md) |
