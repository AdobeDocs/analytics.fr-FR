---
description: valeur nulle
seo-description: valeur nulle
seo-title: Processus relatif à la confidentialité des données Adobe Analytics
title: Processus relatif à la confidentialité des données Adobe Analytics
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Processus relatif à la confidentialité des données Adobe Analytics

Bienvenue dans Adobe Analytics et la préparation à la Confidentialité des données ! Ce processus décrit les étapes à suivre pour que votre mise en œuvre d’Adobe Analytics soit en mesure de prendre en charge les droits d’accès et de suppression relatifs à la Confidentialité des données pour vos sujets des données.

<table id="table_0E561F62247A4D01B6E7180560082DC9"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Description de tâche </th> 
   <th colname="col3" class="entry"> Liens vers les instructions et informations supplémentaires </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step1_icon.png" id="image_15849358972A4846A54FCB51997576D5" /> Assurez-vous que toutes vos suites de rapports susceptibles de contenir des données relatives à la Confidentialité des données sont mappées à votre organisation Experience Cloud (ou IMS). </p> <p>Les demandes relatives à la Confidentialité des données sont soumises à l’aide d’une organisation Experience Cloud et seront appliquées à toutes les suites de rapports revendiquées par cette organisation. Les demandes ne s’appliqueront pas aux suites de rapports non mappées à cette organisation, même si elles font partie de votre société de connexion. </p> </td> 
   <td colname="col3"> <p>Reportez-vous à <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html" format="html" scope="external">Mapper les suites de rapports à une organisation.</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step2_icon.png" id="image_372B2C65DFAD46E39AE4D715313ABD0E"/> Définissez votre politique de conservation des données. </p> </td> 
   <td colname="col3"> <p>Une politique de conservation des données doit être mise en place afin qu’Adobe puisse traiter les demandes d’accès/de suppression de données relatives à la Confidentialité des données. </p> <p>Pour plus d’informations, voir la <a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html" format="html" scope="external">FAQ sur la conservation des données Analytics.</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step3_icon.png" id="image_30DB956290CC4E64A7085B46364BE059" /> Familiarisez-vous avec les étiquettes DULE/Confidentialité des données, les identifiants Adobe Analytics, les espaces de noms et l’extension d’ID. </p> </td> 
   <td colname="col3"> <p> Lisez ces rubriques contenues dans ces documents : 
     <ul id="ul_F6E94B9281D446DB8F1F859F6056543B"> 
      <li id="li_6389D094B4B04CA181E5F077BF8C0F8E"><!--<a href="/help/admin/c-data-governance/gdpr-labels.md#concept_F4061E29353446B5B0A7CF248D54E6F2" format="dita" scope="local"> Data Privacy Labels for Analytics Variables</a>--> </li> 
      <li id="li_CEEF2106E37845A49E0EA1225D5CFF14">Élément de liste </li> 
      <li id="li_0B79CEBD074A4C68923EE9C9766D4B9D"><!--<a href="/help/admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local"> Labeling Best Practices</a>--> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img  src="assets/step4_icon.png" id="image_FE2039B8345248BCA303B44C10B68EA1" placement="break" /> Attribuez des étiquettes d’identité, de sensibilité et de gouvernance des données à chaque variable dans une suite de rapports. </p> <p>Remarque : souvenez-vous que l’étiquetage doit être vérifié chaque fois qu’une nouvelle suite de rapports est créée ou qu’une nouvelle variable est activée dans une suite de rapports existante. Il peut également être nécessaire de vérifier l’étiquetage lors de l’activation de nouvelles intégrations à des solutions puisque celles-ci peuvent exposer de nouvelles variables nécessitant un étiquetage. Une nouvelle implémentation de vos applications mobiles ou sites web peut modifier la manière dont les variables existantes sont utilisées, rendant nécessaire la mise à jour des étiquettes. </p> </td> 
   <td colname="col3"> <p> Suivez les instructions de la section <!--<a href="/help/admin/c-data-governance/gdpr-setup-reportsuite.md#concept_FAA948AD8CEA4BC38CB482EAF3648731" format="dita" scope="local"> Label Report Suite Data</a>-->. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step5_icon.png" id="image_E9BEF83BF30F4528A030F23F71E5E5D8" /> Connectez-vous à l’API relative à la Confidentialité des données d’Adobe et soumettez les demandes d’accès et de suppression. </p> </td> 
   <td colname="col3"> <p>En tant que client Adobe Analytics, vous pouvez soumettre des demandes individuelles pour accéder et supprimer des données clients en vertu de la Confidentialité des données, en appelant l’<a href="https://www.adobe.io/apis/cloudplatform/gdpr.html" format="html" scope="external">API relative à la Confidentialité des données d’Adobe Experience Cloud.</a> </p> <p>Vous pouvez soumettre tous les identifiants Analytics (comme décrit dans la section <!--<a href="/help/admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local"> Labeling Best Practices</a>-->) dans les demandes, ainsi que leurs ID d’espace de noms respectifs (ID de source de données). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step6_icon.png" id="image_5CF03706FECD4F8BBAE0D0C19F98B8BB" /> Afficher et gérer les paramètres relatifs à la Confidentialité des données pour votre suite de rapports. </p> </td> 
   <td colname="col3"> <p>Suivez les instructions de la section <!--<a href="/help/admin/c-data-governance/gdpr-view-settings.md#concept_7759BAD6F3174901A94116D189AEF80E" format="dita" scope="local"> View Report Suite's Data Governance Settings</a>-->. </p> </td> 
  </tr> 
 </tbody> 
</table>

| Description de tâche | Liens vers les instructions et informations supplémentaires |
|--- |--- |
| **Étape 1** : assurez-vous que toutes vos suites de rapports susceptibles de contenir des données relatives à la Confidentialité des données sont mappées à votre organisation Experience Cloud (ou IMS).  Les demandes relatives à la Confidentialité des données sont soumises à l’aide d’une organisation Experience Cloud et seront appliquées à toutes les suites de rapports revendiquées par cette organisation. Les demandes ne s’appliqueront pas aux suites de rapports non mappées à cette organisation, même si elles font partie de votre société de connexion. | Reportez-vous à [Mapper les suites de rapports à une organisation.](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html) |
| **Étape 2** : définissez votre politique de conservation des données. | Une politique de conservation des données doit être mise en place afin qu’Adobe puisse traiter les demandes d’accès/de suppression de données relatives à la Confidentialité des données.  Pour plus d’informations, voir la [FAQ sur la conservation des données Analytics.](/help/technotes/data-retention.md) |
| **Étape 3** : familiarisez-vous avec les étiquettes DULE/Confidentialité des données, les identifiants Adobe Analytics, les espaces de noms et l’extension d’ID. | Lisez ces rubriques contenues dans ces documents :<ul><li>[Étiquettes relatives à la Confidentialité des données pour les variables Analytics](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[Bonnes pratiques en matière d’étiquetage](/help/admin/c-data-governance/gdpr-analytics-ids.md)</li></ul> |
| **Étape 4** : attribuez des étiquettes d’identité, de sensibilité et de gouvernance des données à chaque variable dans une suite de rapports.  Remarque : souvenez-vous que l’étiquetage doit être vérifié chaque fois qu’une nouvelle suite de rapports est créée ou qu’une nouvelle variable est activée dans une suite de rapports existante. Il peut également être nécessaire de vérifier l’étiquetage lors de l’activation de nouvelles intégrations à des solutions puisque celles-ci peuvent exposer de nouvelles variables nécessitant un étiquetage. Une nouvelle implémentation de vos applications mobiles ou sites web peut modifier la manière dont les variables existantes sont utilisées, rendant nécessaire la mise à jour des étiquettes. | Suivez les instructions de la section [ Étiqueter les données d’une suite de rapports.](/help/admin/c-data-governance/gdpr-setup-reportsuite.md) |
| **Étape 5**: Connectez-vous à l’API relative à la Confidentialité des données d’Adobe et soumettez les demandes d’accès et de suppression. | En tant que client Adobe Analytics, vous pouvez soumettre des demandes individuelles pour accéder et supprimer des données clients en vertu de la Confidentialité des données, en appelant l’[API relative à la Confidentialité des données d’Adobe Experience Cloud.](https://www.adobe.io/apis/experienceplatform/gdpr.html) Vous pouvez soumettre tous les identifiants Analytics (comme décrit dans la section [Bonnes pratiques en matière d’étiquetage](/help/admin/c-data-governance/gdpr-analytics-ids.md)) dans les demandes, ainsi que leurs ID d’espace de noms respectifs (ID de source de données). |
| **Étape 6**: Afficher et gérer les paramètres relatifs à la Confidentialité des données pour votre suite de rapports. | Suivez les instructions de la section [ Afficher les paramètres de gouvernance des données de la suite de rapports.](/help/admin/c-data-governance/gdpr-view-settings.md) |
