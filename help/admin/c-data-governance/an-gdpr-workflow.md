---
description: valeur nulle
seo-description: valeur nulle
seo-title: Processus relatif à la confidentialité des données Adobe Analytics
title: Processus relatif à la confidentialité des données Adobe Analytics
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Processus relatif à la confidentialité des données Adobe Analytics

Bienvenue dans Adobe Analytics et la préparation à la Confidentialité des données ! Ce processus décrit les étapes à suivre pour que votre mise en œuvre d’Adobe Analytics soit en mesure de prendre en charge les droits d’accès et de suppression relatifs à la Confidentialité des données pour vos sujets des données.

<!--
<table id="table_0E561F62247A4D01B6E7180560082DC9"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Task Description </th> 
   <th colname="col3" class="entry"> Links to Instructions and More Information </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step1_icon.png" id="image_15849358972A4846A54FCB51997576D5" /> Ensure that any of your report suites that might contain Data Privacy-relevant data are mapped to your Experience Cloud (or IMS) organization. </p> <p>Data Privacy requests are submitted using an Experience Cloud Organization and will be applied to all report suites claimed by that Organization. Requests will not apply to report suites not mapped to that Organization, even if they are part of your login company. </p> </td> 
   <td colname="col3"> <p>Refer to <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html"> Map report suites to an organization</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step2_icon.png" id="image_372B2C65DFAD46E39AE4D715313ABD0E"/> Set your data retention policy. </p> </td> 
   <td colname="col3"> <p>A data retention policy needs to be in place in order for Adobe to service Data Privacy data access/delete requests. </p> <p>For more information, see this <a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html"> Analytics Data Retention FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step3_icon.png" id="image_30DB956290CC4E64A7085B46364BE059" /> Familiarize yourself with DULE/Data Privacy labels, Adobe Analytics IDs, namespaces, and ID expansion. </p> </td> 
   <td colname="col3"> <p> Read these topics in this documentation set: 
     <ul> 
      <li><a href="/help/admin/c-data-governance/gdpr-labels.md"> Data Privacy Labels for Analytics Variables</a> </li> 
      <li><a href="/help/admin/c-data-governance/gdpr-analytics-ids.md"> Labeling Best Practices</a>--> </li>
    &lt;/ul&gt; &lt;/p&gt; &lt;/td&gt;
</tr> 
  <tr> 
   <td colname="col2"> <p><img  src="assets/step4_icon.png" id="image_FE2039B8345248BCA303B44C10B68EA1" placement="break" /> Attribuez des étiquettes d’identité, de sensibilité et de gouvernance des données à chaque variable dans une suite de rapports. </p> <p>Remarque : souvenez-vous que l’étiquetage doit être vérifié chaque fois qu’une nouvelle suite de rapports est créée ou qu’une nouvelle variable est activée dans une suite de rapports existante. Il peut également être nécessaire de vérifier l’étiquetage lors de l’activation de nouvelles intégrations à des solutions puisque celles-ci peuvent exposer de nouvelles variables nécessitant un étiquetage. Une nouvelle implémentation de vos applications mobiles ou sites web peut modifier la manière dont les variables existantes sont utilisées, rendant nécessaire la mise à jour des étiquettes. </p> </td> 
   <td colname="col3"> <p> Suivez les instructions de la section <a href="/help/admin/c-data-governance/gdpr-setup-reportsuite.md"> Étiqueter les données d’une suite de rapports</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step5_icon.png" id="image_E9BEF83BF30F4528A030F23F71E5E5D8" /> Connectez-vous à l’API relative à la Confidentialité des données d’Adobe et soumettez les demandes d’accès et de suppression. </p> </td> 
   <td colname="col3"> <p>En tant que client Adobe Analytics, vous pouvez soumettre des demandes individuelles pour accéder et supprimer des données clients en vertu de la Confidentialité des données, en appelant l’<a href="https://www.adobe.io/apis/cloudplatform/gdpr.html">API relative à la Confidentialité des données d’Adobe Experience Cloud</a>. </p> <p>Vous pouvez soumettre tous les identifiants Analytics (comme décrit dans la section <a href="/help/admin/c-data-governance/gdpr-analytics-ids.md">Bonnes pratiques en matière d’étiquetage</a>) dans les demandes, ainsi que leurs ID d’espace de noms respectifs (ID de source de données). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step6_icon.png" id="image_5CF03706FECD4F8BBAE0D0C19F98B8BB" /> Afficher et gérer les paramètres relatifs à la Confidentialité des données pour votre suite de rapports. </p> </td> 
   <td colname="col3"> <p>Suivez les instructions de la section <a href="/help/admin/c-data-governance/gdpr-view-settings.md"> Afficher les paramètres de gouvernance des données de la suite de rapports</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
--&gt;

| Description de tâche | Liens vers les instructions et informations supplémentaires |
|--- |--- |
| **Étape 1** : assurez-vous que toutes vos suites de rapports susceptibles de contenir des données relatives à la Confidentialité des données sont mappées à votre organisation Experience Cloud (ou IMS).  Les demandes relatives à la Confidentialité des données sont soumises à l’aide d’une organisation Experience Cloud et seront appliquées à toutes les suites de rapports revendiquées par cette organisation. Les demandes ne s’appliqueront pas aux suites de rapports non mappées à cette organisation, même si elles font partie de votre société de connexion. | Reportez-vous à [Mapper les suites de rapports à une organisation.](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html) |
| **Étape 2**: Définissez votre stratégie de rétention des données. | Une politique de conservation des données doit être mise en place afin qu’Adobe puisse traiter les demandes d’accès/de suppression de données relatives à la Confidentialité des données.  Pour plus d’informations, voir la [FAQ sur la conservation des données Analytics.](/help/technotes/data-retention.md) |
| **Étape 3** : familiarisez-vous avec les étiquettes DULE/Confidentialité des données, les identifiants Adobe Analytics, les espaces de noms et l’extension d’ID. | Lisez ces rubriques contenues dans ces documents :<ul><li>[Étiquettes relatives à la Confidentialité des données pour les variables Analytics](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[Bonnes pratiques en matière d’étiquetage](/help/admin/c-data-governance/gdpr-analytics-ids.md)</li></ul> |
| **Étape 4** : attribuez des étiquettes d’identité, de sensibilité et de gouvernance des données à chaque variable dans une suite de rapports.  Remarque : souvenez-vous que l’étiquetage doit être vérifié chaque fois qu’une nouvelle suite de rapports est créée ou qu’une nouvelle variable est activée dans une suite de rapports existante. Il peut également être nécessaire de vérifier l’étiquetage lors de l’activation de nouvelles intégrations à des solutions puisque celles-ci peuvent exposer de nouvelles variables nécessitant un étiquetage. Une nouvelle implémentation de vos applications mobiles ou sites web peut modifier la manière dont les variables existantes sont utilisées, rendant nécessaire la mise à jour des étiquettes. | Suivez les instructions de la section [Étiqueter les données d’une suite de rapports.](/help/admin/c-data-governance/gdpr-setup-reportsuite.md) |
| **Étape 5**: Connectez-vous à l’API relative à la Confidentialité des données d’Adobe et soumettez les demandes d’accès et de suppression. | En tant que client Adobe Analytics, vous pouvez soumettre des demandes individuelles pour accéder et supprimer des données clients en vertu de la Confidentialité des données, en appelant l’[API relative à la Confidentialité des données d’Adobe Experience Cloud.](https://www.adobe.io/apis/experienceplatform/gdpr.html) Vous pouvez soumettre tous les identifiants Analytics (comme décrit dans la section [Bonnes pratiques en matière d’étiquetage](/help/admin/c-data-governance/gdpr-analytics-ids.md)) dans les demandes, ainsi que leurs ID d’espace de noms respectifs (ID de source de données). |
| **Étape 6**: Afficher et gérer les paramètres relatifs à la Confidentialité des données pour votre suite de rapports. | Suivez les instructions de la section [Afficher les paramètres de gouvernance des données de la suite de rapports.](/help/admin/c-data-governance/gdpr-view-settings.md) |
