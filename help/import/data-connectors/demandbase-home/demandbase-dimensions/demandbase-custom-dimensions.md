---
description: Répertorie les identifiants de dimension facultatifs qui peuvent être donnés à l'étape 4 de l'assistant d'intégration Adobe.
seo-description: Répertorie les identifiants de dimension facultatifs qui peuvent être donnés à l'étape 4 de l'assistant d'intégration Adobe.
seo-title: Demandbase Custom Dimensions
title: Demandbase Custom Dimensions
uuid: d 1621046-3 aa 2-46 b 9-a 536-4 a 8 fb 792 b 69 f
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Demandbase Custom Dimensions{#demandbase-custom-dimensions}

Répertorie les identifiants de dimension facultatifs qui peuvent être donnés à l'étape 4 de l'assistant d'intégration Adobe.

Si vous ne connaissez pas l'ID exact de l'API à entrer dans l'assistant, contactez votre représentant Demandbase.

>[!IMPORTANT]
>
>Il est vivement recommandé de NE PAS inclure l'adresse IP en tant que dimension personnalisée. Le nombre extrêmement élevé de valeurs uniques peut entraîner des problèmes de performances avec la création de rapports. En outre, l'adresse IP est déjà proposée comme option de création de rapports par le biais de la création de rapports d'entrepôt de données Adobe.

<table id="table_3B44A18BE5FE45BC83389F89B48D9B97"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimension </th> 
   <th colname="col2" class="entry"> Identifiants API </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Fournisseur de services Internet </td> 
   <td colname="col2"> isp </td> 
   <td colname="col3"> Indique si l'organisation identifiée est classée comme fournisseur de services Internet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alias marketing </td> 
   <td colname="col2"> marketing_ alias </td> 
   <td colname="col3"> Nom de l'organisation nettoyé et/ou réduit (32 caractères ou moins) pour être utilisé dans les publicités, les messages ou la copie marketing. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Balises de contrôle de compte </td> 
   <td colname="col2"> watch_ list (personnalisé) </td> 
   <td colname="col3">Jeu illimité de balises définies par le client pouvant être ajoutées à leurs données de réponse API par organisation. <p><b>Exemple</b>: si vous avez une balise de contrôle nommée Q 4 Target, le champ API est </p> <code> watch_ list_ q 4_ target</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fortune 1000 </td> 
   <td colname="col2"> fortune_ 1000 </td> 
   <td colname="col3"> Indique si l'organisation figure dans la liste Fortune 1000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Forbes 2000 </td> 
   <td colname="col2"> forbes_ 2000 </td> 
   <td colname="col3"> Indique si l'organisation figure dans la liste Forbes 2000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre d'employés </td> 
   <td colname="col2"> employee_ count </td> 
   <td colname="col3"> Nombre de personnes employées dans l'organisation. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ventes annuelles </td> 
   <td colname="col2"> annual_ sales </td> 
   <td colname="col3"> Pour les entités publiques, les recettes annuelles sont basées sur les enregistrements publics signalés par l'entreprise pour le HQ global sur tous les emplacements. Pour les entreprises privées, il est basé sur l'estimation consensuelle du chiffre d'affaires des ventes annuelles. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numéro de téléphone </td> 
   <td colname="col2"> téléphone </td> 
   <td colname="col3"> Numéro de téléphone de l'organisation identifiée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse postale </td> 
   <td colname="col2"> street_ address </td> 
   <td colname="col3"> Adresse postale de l'organisation identifiée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ville </td> 
   <td colname="col2"> ville </td> 
   <td colname="col3"> Ville de l'organisation identifiée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> État </td> 
   <td colname="col2"> state </td> 
   <td colname="col3"> Etat de l'organisation identifié. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Code de pays </td> 
   <td colname="col2"> country_ code </td> 
   <td colname="col3"> Code pays ISO à deux caractères de l'organisation identifiée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nom du pays </td> 
   <td colname="col2"> country_ name </td> 
   <td colname="col3"> Nom de pays de la valeur de chaîne du pays pour l'organisation identifiée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Postal </td> 
   <td colname="col2"> zip </td> 
   <td colname="col3"> Code postal du pays/état de l'organisation identifiée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Site Web </td> 
   <td colname="col2"> web_ site </td> 
   <td colname="col3"> URL utilisée par l'organisation identifiée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Symbole Stock </td> 
   <td colname="col2"> stock_ ticker </td> 
   <td colname="col3"> Symbole de stock si l'organisation identifiée est échangée publiquement. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Code SIC principal </td> 
   <td colname="col2"> primary_ sic </td> 
   <td colname="col3"> Code SIC consensuel affecté pour l'organisation identifiée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Latitude </td> 
   <td colname="col2"> latitude </td> 
   <td colname="col3"> Latitude de l'emplacement de l'organisation identifiée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Longitude </td> 
   <td colname="col2"> longitude </td> 
   <td colname="col3"> Longitude de l'emplacement de l'organisation identifiée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trafic </td> 
   <td colname="col2"> trafic </td> 
   <td colname="col3"> Quantité de trafic Web, estimée à faible, moyen ou élevé ou très élevé. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2B </td> 
   <td colname="col2"> b2b </td> 
   <td colname="col3"> Indique que la société identifiée vend principalement à d'autres entreprises. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2C </td> 
   <td colname="col2"> b2c </td> 
   <td colname="col3"> Indique que la société identifiée vend principalement aux consommateurs ou aux individus. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Technologie Insight </td> 
   <td colname="col2"> ??? </td> 
   <td colname="col3"> Jusqu'à 75 catégories de technologie définies par des clients par catégorie, fournisseur et produits pour l'utilisation de ciblage et/ou de personnalisation de publicités, de messages ou de copies marketing. </td> 
  </tr> 
 </tbody> 
</table>

