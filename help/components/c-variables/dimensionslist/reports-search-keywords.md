---
description: Affiche une ventilation des mots-clés de recherche.
title: Mots-clés de recherche
topic: Reports
uuid: db9d477b-b711-4b93-9c25-3aebe5f2ace6
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Mots-clés de recherche

Affiche une ventilation des mots-clés de recherche.

**Mots-clés de recherche – Tous** : ce rapport répertorie chaque mot-clé de recherche qui a été utilisé pour trouver votre site. Vous pouvez trier cette liste par pages vues ou mots-clés de recherche en cliquant sur le titre de la colonne. Cliquez sur la loupe en regard d’un mot-clé de recherche afin d’afficher les écrans de résultats pour votre site.

**Mots-clés de recherche – Payée** : répertorie les mots-clés de recherche payante qui ont été utilisés pour trouver votre site. Vous pouvez trier cette liste par pages vues ou mots-clés de recherche en cliquant sur le titre de la colonne. Cliquez sur la loupe en regard d’un mot-clé de recherche afin d’afficher les écrans de résultats pour votre site.

**Mots-clés de recherche – Naturelle** : répertorie les mots-clés de recherche naturelle qui ont été utilisés pour trouver votre site. Vous pouvez trier cette liste par pages vues ou mots-clés de recherche en cliquant sur le titre de la colonne. Cliquez sur la loupe en regard d’un mot-clé de recherche afin d’afficher les écrans de résultats pour votre site.

>[!IMPORTANT]
>
>Pour les recherches payantes et naturelles, les moteurs de recherche ont cessé de fournir (dans la plupart des cas) les mots-clés de recherche dans le cadre du référent. Par conséquent, Adobe classe toujours le domaine Google (ou Bing ou Yahoo) comme recherche. En fonction du format et du contenu du référent (même sans les mots-clés), Adobe peut souvent déterminer qu’il s’agit du résultat d’une recherche. La recherche est donc comptabilisée avec les mots-clés non disponibles. [Plus...](https://helpx.adobe.com/fr/analytics/kb/keyword-unavailable.html)

## Attribution, expiration et valeurs spéciales {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> </th> 
   <th colname="col3" class="entry"> Ad Hoc Analysis </th> 
   <th colname="col4" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Attribution des mesures </td> 
   <td colname="col2"> <p>Valeur d’origine (par défaut) </p> <p> Peut être remplacée par Linéaire. </p> </td> 
   <td colname="col3"> Le plus récent (ce paramètre peut être remplacé par sa version linéaire) </td> 
   <td colname="col4"> <p>Valeur d’origine (par défaut) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valeurs Expire après </td> 
   <td colname="col2"> Visite - Peut être abrégée mais pas prolongée. </td> 
   <td colname="col3"> Visite </td> 
   <td colname="col4"> Visite </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valeur Limites </td> 
   <td colname="col2"> Aucune limite (peut changer dans les versions ultérieures) </td> 
   <td colname="col3"> Aucune limite (peut changer dans les versions ultérieures) </td> 
   <td colname="col4"> Aucune </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valeurs spéciales </td> 
   <td colname="col2"> <p>« Aucun » : totaux à l’échelle du site qui n’avaient aucun mot-clé durant la visite. </p> Les recherches « Mot-clé indisponible » sont les recherches d’où le mot-clé a été supprimé et n’est pas envoyé à la collecte de données. Ceci survient généralement lorsqu’un client a ouvert une session dans un compte Google. S’applique aux recherches payantes et naturelles. </td> 
   <td colname="col3"> (Faible trafic) Représente les valeurs au-delà des 500 000 premières visites qui n’ont pas encore suffisamment de trafic pour être reportées. </td> 
   <td colname="col4"> <p> Vide : équivalent à « Aucun », totaux à l’échelle du site qui n’avaient aucun mot-clé durant la visite. </p> <p>Les recherches « Mot-clé indisponible » sont les recherches d’où le mot-clé a été supprimé et n’est pas envoyé à la collecte de données. Ceci survient généralement lorsqu’un client a ouvert une session dans un compte Google. S’applique aux recherches payantes et naturelles. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Historique des rapports  {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

| Date | Changement |
|---|---|
| 16/1/2014 | Data Warehouse a été mis à jour pour correspondre à la logique utilisée par les Reports &amp; Analytics marketing. Auparavant, les mots-clés de recherche ne persistaient pas pendant la visite. |

