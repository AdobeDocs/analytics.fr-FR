---
description: Répertorie les identifiants de dimension facultatifs pouvant être fournis à l’étape 4 de l’assistant d’intégration Adobe.
seo-description: Répertorie les identifiants de dimension facultatifs pouvant être fournis à l’étape 4 de l’assistant d’intégration Adobe.
seo-title: Demandbase Custom Dimensions
title: Demandbase Custom Dimensions
uuid: d1621046-3aa2-46b9-a536-4a8fb792b69f
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Demandbase Custom Dimensions{#demandbase-custom-dimensions}

Répertorie les identifiants de dimension facultatifs pouvant être fournis à l’étape 4 de l’assistant d’intégration Adobe.

If you are unsure of the exact API ID to enter into the wizard, please consult with your Demandbase representative.

>[!IMPORTANT]
>
>Il est vivement recommandé de NE PAS inclure l’adresse IP comme dimension personnalisée. Le nombre extrêmement élevé de valeurs uniques peut entraîner des problèmes de performances lors de la création de rapports. In addition, IP Address is already offered as a reporting option through Adobe data warehouse reporting.

<table id="table_3B44A18BE5FE45BC83389F89B48D9B97"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimension </th> 
   <th colname="col2" class="entry"> ID d’API </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Fournisseur de services Internet </td> 
   <td colname="col2"> isp </td> 
   <td colname="col3"> Indique si l’organisation identifiée est classée comme FAI. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alias marketing </td> 
   <td colname="col2"> marketing_alias </td> 
   <td colname="col3"> Nom d’organisation nettoyé et/ou raccourci (32 caractères ou moins) à utiliser dans les publicités, les messages ou la copie marketing. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Balises de surveillance de compte </td> 
   <td colname="col2"> watch_list (personnalisé) </td> 
   <td colname="col3">Ensemble illimité de balises définies par le client et pouvant être ajoutées à leurs données de réponse API, par organisation. <p><b>Exemple</b>: si vous disposez d’une balise de contrôle appelée Target Q4, le champ API sera </p> <code> watch_list_q4_target</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fortune 1000 </td> 
   <td colname="col2"> fortune_1000 </td> 
   <td colname="col3"> Indicates whether the organization is on the Fortune 1000 list. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Forbes 2000 </td> 
   <td colname="col2"> forbes_2000 </td> 
   <td colname="col3"> Indique si l’organisation figure dans la liste Forbes 2000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre d'employés </td> 
   <td colname="col2"> employee_count </td> 
   <td colname="col3"> Nombre de personnes employées dans l’organisation. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ventes annuelles </td> 
   <td colname="col2"> year_sales </td> 
   <td colname="col3"> Pour les entités publiques, les recettes annuelles sont basées sur les registres publics déclarés par l’entreprise pour le siège social mondial, sur tous les sites. For privately-held organizations, it is based on consensus estimate for the yearly sales revenue number. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numéro de téléphone </td> 
   <td colname="col2"> phone </td> 
   <td colname="col3"> The telephone number of the organization identified. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Street address </td> 
   <td colname="col2"> street_address </td> 
   <td colname="col3"> The street address of the organization identified. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ville </td> 
   <td colname="col2"> city </td> 
   <td colname="col3"> The city of the organization identified. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> État </td> 
   <td colname="col2"> state </td> 
   <td colname="col3"> The state of the organization identified. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Code de pays </td> 
   <td colname="col2"> country_code </td> 
   <td colname="col3"> The ISO two-character country code of the organization identified. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nom du pays </td> 
   <td colname="col2"> country_name </td> 
   <td colname="col3"> The string value country name of the country for the organization identified. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zip </td> 
   <td colname="col2"> zip </td> 
   <td colname="col3"> Code postal du pays/de l’État pour l’organisation identifiée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Site Web </td> 
   <td colname="col2"> web_site </td> 
   <td colname="col3"> URL utilisée par l’organisation identifiée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Billetterie </td> 
   <td colname="col2"> stock_ticker </td> 
   <td colname="col3"> The stock ticker if the organization identified is publicly traded. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Code SIC principal </td> 
   <td colname="col2"> primaire_sic </td> 
   <td colname="col3"> Code SIC consensuel attribué pour l'organisation identifiée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Latitude </td> 
   <td colname="col2"> latitude </td> 
   <td colname="col3"> Latitude pour l'emplacement de l'organisation identifiée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Longitude </td> 
   <td colname="col2"> longitude </td> 
   <td colname="col3"> Longitude de l'emplacement de l'organisation identifiée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trafic </td> 
   <td colname="col2"> traffic </td> 
   <td colname="col3"> The amount of website traffic, estimated to low, medium or high or very high. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2B </td> 
   <td colname="col2"> b2b </td> 
   <td colname="col3"> Indicates that the identified company primarily sells to other businesses. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2C </td> 
   <td colname="col2"> b2c </td> 
   <td colname="col3"> Indique que la société identifiée vend principalement aux consommateurs ou aux particuliers. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aperçu de la technologie </td> 
   <td colname="col2"> ??? </td> 
   <td colname="col3"> Jusqu'à 75 catégories de technologies définies par les clients par catégorie, fournisseur et produit pour l'utilisation du ciblage et/ou de la personnalisation des publicités, messages ou copies marketing. </td> 
  </tr> 
 </tbody> 
</table>

