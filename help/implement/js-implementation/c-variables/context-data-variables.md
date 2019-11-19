---
description: Les variables de données contextuelles permettent de définir, sur chaque page, des variables personnalisées lisibles par les règles de traitement.
keywords: Analytics Implementation;contextdata;s.contextdata
solution: Analytics
subtopic: Variables
title: Variables de données contextuelles
topic: Developer and implementation
uuid: 4b215803-99d4-46f2-b3c1-e78558987764
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Variables de données contextuelles

Les variables de données contextuelles permettent de définir, sur chaque page, des variables personnalisées lisibles par les règles de traitement.

Au lieu d’affecter de façon explicite des valeurs aux props et eVars dans votre code, vous pouvez envoyer des données dans des variables de données contextuelles mises en correspondance à l’aide de règles de traitement. Les règles de traitement offrent une interface graphique puissante pour apporter des modifications aux données reçues. Selon les valeurs envoyées dans les données contextuelles, vous pouvez définir des événements, copier les valeurs dans des eVars et des props et exécuter des instructions conditionnelles supplémentaires.

> [!NOTE] Les variables de données contextuelles ne sont pas sensibles à la casse. Par exemple, les deux variables suivantes sont effectivement identiques :
>```
>s.contextData['article_title'] = 'Weekend Concert Controversy'; 
>```
>et
>```
>s.contextData['ARTICLE_TITLE'] = 'Weekend Concert Controversy';
>```

L’utilisation de données contextuelles vous évite de mettre à jour le code pour prendre en charge différentes configurations de suite de rapports.

Vous pouvez par exemple définir la variable Variable *`s.contextData`* :

```
s.contextData['myco.rsid'] = 'value'
```

Les règles de traitement vous permettent d’ajouter une condition qui recherche une variable de données contextuelles `myco.rsid`. Une fois cette variable trouvée, vous pouvez ajouter une action afin de la copier dans une variable prop ou eVar.

Les variables de données contextuelles peuvent également être définies directement dans l’interface des règles de traitement afin de stocker temporairement une valeur ou de collecter les valeurs d’une variable de données contextuelles qui sera utilisée dans la suite de rapports. Par exemple, si vous devez permuter deux valeurs, vous pouvez créer une variable Données contextuelles pour stocker l’une d’elles pendant l’opération.

Etant donné que les règles de traitement ne sont appliquées qu’au moment de la collecte des données, il est important de les configurer avant de commencer l’envoi des données contextuelles. Les valeurs de données contextuelles qui ne sont pas lues par des règles de traitement lors du traitement d’un accès sont ignorées.

## Règles {#section_2229739F6B1A4C1CAD7140BDF4687523}

<table id="table_4433A32A952340699B189CAEAF158B06"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Règle </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Noms et caractères pris en charge </p> </td> 
   <td colname="col2"> <p>Les noms de variable de données contextuelles peuvent comporter uniquement des caractères alphanumériques, des traits de soulignement et des points. Les autres caractères sont supprimés. Les variables de données contextuelles n’ont pas de désignation numérique, mais un nom. </p> <p>For example, the context data variable <code> login_page-home </code> automatically becomes <code> login_pagehome </code>. All data sent to the <code> login_page-home </code> variable is allocated under <code> login_pagehome </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Espace de noms </p> </td> 
   <td colname="col2"> <p>Il est conseillé de faire précéder vos variables du nom de la société, du nom du site ou d’une valeur semblable afin de vous assurer que le nom est unique dans toute la suite de rapports. </p> <p>Les variables de données contextuelles peuvent être nommées de la même manière que d’autres variables JavaScript. Be aware that the namespace <code> a.* </code> is reserved for use by Adobe products in context variable names. Par exemple, la bibliothèque AppMeasurement pour iOS utilise <code> a.InstallEvent </code> pour mesurer les installations d’application. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limites d’URL pour Internet Explorer </p> </td> 
   <td colname="col2"> <p>Dans Internet Explorer 6 et 7, les URL sont tronquées à 2 000 octets. Vous pouvez utiliser le débogueur <span class="keyword">DigitalPulse</span> pour déterminer la taille d’une chaîne d’URL. </p> <p>Suite aux mises à jour récentes apportées à AppMeasurement (septembre 2014), HTTP POST est utilisé avec Internet Explorer 8+, ce qui permet d’éliminer les problèmes de troncation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Version d’AppMeasurement prise en charge </p> </td> 
   <td colname="col2"> <p>Les variables de données contextuelles nécessitent le code H23 ou une version ultérieure. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Envoi de données contextuelles sur un appel de lien de suivi {#section_35EBE5D1CF29427598BD4B2165CE64FC}

Indiquez `ContextData` + le nom de la variable que vous souhaitez inclure dans `s.linkTrackVars` :

```
s.contextData['myco.value'] = "some value"; 
s.linkTrackVars = "contextData.myco.value"; 
s.tl(true,"o","Link Name"); 
```

## Exemples {#section_A16AD9E6E0E84F6A85CA4F08512480B3}

Méthodes possibles pour remplacer l’implémentation de la variable *`s.pageName`*, en supposant que les règles de traitement sont correctement configurées pour chacune d’elles :

```
s.contextData['page'] = "Home Page" 
s.contextData['pagename'] = document.title // Takes the web page's title and passes it into the pageName context data variable 
s.contextData['pagevar'] = s.pageName // This example would be considered redundant, as both the pageName and contextData variable are available in Processing rules
```

Autres exemples d’implémentation des variables de données contextuelles :

```
s.contextData['owner'] = "Jesse" 
s.contextData['campaign'] = "Campaign A" 
s.contextData['author'] = "Sheridan Andrius"
```

Pour obtenir un exemple, reportez-vous à la section [Copier une variable de données contextuelles dans une variable eVar](https://marketing.adobe.com/resources/help/en_US/reference/processing_rules_copy_context_data.html) de la Référence Analytics.
