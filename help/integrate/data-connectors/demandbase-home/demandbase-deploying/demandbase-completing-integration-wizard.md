---
description: Pour activer l'intégration, vous devez terminer l'assistant de configuration dans l'interface des Connecteurs de données.
seo-description: Pour activer l'intégration, vous devez terminer l'assistant de configuration dans l'interface des Connecteurs de données.
seo-title: Exécution de l'assistant d'intégration Adobe
title: Exécution de l'assistant d'intégration Adobe
uuid: 75260 b 92-a 6 f 5-44 b 6-b 3 ea-d 5945 fdd 1 ecb
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

Pour activer l'intégration, vous devez terminer l'assistant de configuration dans l'interface des Connecteurs de données.

1. Accédez à la zone Connecteurs de données (anciennement Genesis) dans Adobe Marketing Cloud.
1. Lancez l'assistant d'intégration Demandbase 2.0.
1. Choisissez la suite de rapports souhaitée et attribuez un nom à l'intégration.
1. Configurez les éléments suivants :

<table id="table_8D60DC7C48C144DC9934749E7F9F65FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Adresse électronique </td> 
   <td colname="col2"> Adresse électronique du contact principal. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Description </td> 
   <td colname="col2"> (Facultatif) Description de cette configuration de l'intégration. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clé de l'API Demandbase </td> 
   <td colname="col2"> Vous pouvez obtenir ce résultat auprès de votre représentant Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimension Demandbase personnalisée N ° N </td> 
   <td colname="col2"> Il s'agit des ID des 8 dimensions facultatives. Pour plus d'informations, voir Demandbase Custom Dimensions. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Envoyer à Adobe Target </td> 
   <td colname="col2">Si « true », les dimensions Demandbase sont également envoyées à Adobe Target à l'aide d'une mbox masquée. <p>Remarque : Un fichier mbox. js configuré doit être implémenté sur la page Web pour que les dimensions soient collectées. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Configurez les éléments Mappages de variables suivants :

   | Élément | Description |
   |---|---|
   | Demandbase Dimensions | Choisissez une variable evar disponible dans votre suite de rapports. |
   | Demandbase Custom Dimensions (facultatif) | Choisissez une variable evar disponible dans votre suite de rapports. |

1. Configurez les noms de la dimension personnalisée (le cas échéant).

   1. Si vous avez choisi d'inclure des dimensions personnalisées à l'étape 4 et mappé l'evar facultative à l'étape 5, vous devez fournir des noms conviviaux pour ces dimensions. Par exemple, si vous choisissez de saisir « stock_ ticker » comme Dimension personnalisée 1, vous devez remplacer la case « Dimension 1 » par « Stock Ticker ».
   1. Do **NOT** modify the names of the standard 8 dimensions (i.e. Demandbase SID, Company Name, Industry, etc.).

1. Cochez la case pour que le tableau de bord Demandbase Integration soit automatiquement créé pour vous (recommandé).
1. Review all configuration items and click **[!UICONTROL Activate Now]**.

