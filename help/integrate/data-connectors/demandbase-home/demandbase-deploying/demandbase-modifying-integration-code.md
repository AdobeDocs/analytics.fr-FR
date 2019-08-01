---
description: Dans la plupart des cas, il n'est pas nécessaire de modifier le code d'intégration généré par l'assistant Connecteur de données.
seo-description: Dans la plupart des cas, il n'est pas nécessaire de modifier le code d'intégration généré par l'assistant Connecteur de données.
seo-title: Modification du code d'intégration
title: Modification du code d'intégration
uuid: 3 f 49 a 29 b-ad 38-4967-894 a-ef 7 ecf 4 d 268 f
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Modifying the Integration Code{#modifying-the-integration-code}

Dans la plupart des cas, il n'est pas nécessaire de modifier le code d'intégration généré par l'assistant Connecteur de données.

Toutefois, si vous devez effectuer des ajustements, certains paramètres du code sont décrits ci-dessous.

<table id="table_5405A73CEFD44466B3C39559F4A037C9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre du code </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> s.maxDelay </td> 
   <td colname="col2">nombre maximal de millisecondes que la demande d'image Adobe Analytics attend pour les données Demandbase avant de déclencher le serveur de collecte Analytics. <p>Remarque : Ce paramètre s'applique à toutes les intégrations qui peuvent être exécutées via le module Integrate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._key </td> 
   <td colname="col2"> Votre clé d'API Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Apiurl </td> 
   <td colname="col2"> Modèle d'URL de l'API Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._delim </td> 
   <td colname="col2"> Délimiteur utilisé pour séparer les valeurs de dimension Demandbase lorsqu'elles sont envoyées à Adobe Analytics. La modification de ce paramètre peut entraîner le mauvais fonctionnement des règles de classification par défaut. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Settnt </td> 
   <td colname="col2">Si la valeur est true, le code d'intégration tentera d'utiliser une mbox masquée pour envoyer les dimensions Demandbase à Adobe Target en tant que paramètres de profil. <p>Remarque : Cela implique que le code mbox. js existe sur la page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Tntvarprefix </td> 
   <td colname="col2"> Cette chaîne est précédée de chaque nom de dimension Demandbase avant d'envoyer à Adobe Target. Par exemple, si ce paramètre possède la valeur « db_ », la dimension « industry » sera envoyée à Adobe Target sous la forme « db_ industry ». </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Dimensionsarray </td> 
   <td colname="col2"> Dimensions Demandbase standard envoyées à Adobe Analytics. Il est recommandé de ne pas modifier ce paramètre. La propriété max_ size est le nombre de caractères autorisés pour la dimension avant la troncature. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Dimensionsarraycustom </td> 
   <td colname="col2"> Dimensions Demandbase personnalisées envoyées à Adobe Analytics. La propriété max_ size est le nombre de caractères autorisés pour la dimension avant la troncature. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Cname </td> 
   <td colname="col2"> nom du cookie de session utilisé pour conserver l'état de la communication de l'API Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Contextname </td> 
   <td colname="col2"> nom de la variable contextdata utilisée pour envoyer les dimensions standard à Adobe Analytics. Il est recommandé de ne pas modifier ce paramètre. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Contextnamecustom </td> 
   <td colname="col2"> nom de la variable contextdata utilisée pour envoyer les dimensions personnalisées à Adobe Analytics. Il est recommandé de ne pas modifier ce paramètre. </td> 
  </tr> 
 </tbody> 
</table>

