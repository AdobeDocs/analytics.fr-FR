---
description: Pour activer l’intégration, vous devez exécuter l’assistant de configuration dans l’interface des connecteurs de données.
seo-description: Pour activer l’intégration, vous devez exécuter l’assistant de configuration dans l’interface des connecteurs de données.
seo-title: Fin de l’assistant d’intégration Adobe
title: Fin de l’assistant d’intégration Adobe
uuid: 75260b92-a6f5-44b6-b3ea-d5945fdd1ecb
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Fin de l’assistant d’intégration Adobe{#completing-the-adobe-integration-wizard}

Pour activer l’intégration, vous devez exécuter l’assistant de configuration dans l’interface des connecteurs de données.

1. Accédez à la zone Connecteurs de données (anciennement Genesis) dans Adobe Experience Cloud.
1. Lancez l’assistant d’intégration Demandbase 2.0.
1. Choisissez une suite de rapports et nommez l’intégration.
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
   <td colname="col2"> (Facultatif) Description de cette configuration d’intégration. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clé d'API Demandbase </td> 
   <td colname="col2"> Vous pouvez obtenir cette information auprès de votre représentant Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimension de base de demande personnalisée #N </td> 
   <td colname="col2"> Il s’agit des ID des 8 dimensions facultatives. Pour plus d’informations, voir Demandbase Custom Dimensions. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Envoyer à Adobe Target </td> 
   <td colname="col2">Si la valeur est "true", les dimensions Demandbase sont également envoyées à Adobe Target à l’aide d’une mbox masquée. <p>Remarque :  Un fichier mbox.js configuré doit être implémenté sur la page Web pour que les dimensions soient collectées. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Configurez les éléments suivants de mappage des variables :

   | Élément | Description |
   |---|---|
   | Dimensions Demandbase | Choisissez une variable eVar disponible dans votre suite de rapports. |
   | Demandbase Custom Dimensions (facultatif) | Choisissez une variable eVar disponible dans votre suite de rapports. |

1. Configurez les noms de la dimension personnalisée (le cas échéant).

   1. Si vous avez choisi d’inclure des dimensions personnalisées à l’étape 4 et d’associer l’eVar facultative à l’étape 5, vous devez fournir des noms conviviaux pour ces dimensions. Par exemple, si vous avez choisi de saisir "stock_ticker" comme dimension personnalisée 1, vous devez modifier la zone contenant "Dimension 1" en "Stock Ticker".
   1. Ne modifiez **PAS** les noms des dimensions standard 8 (SID de base de la demande, nom de la société, industrie, etc.).

1. Cochez la case pour que le tableau de bord d’intégration Demandbase soit automatiquement créé (recommandé).
1. Vérifiez tous les éléments de configuration et cliquez sur **[!UICONTROL Activer maintenant]**.

