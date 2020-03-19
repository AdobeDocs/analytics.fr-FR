---
title: Collisions de hachage
description: Décrit ce qu’est une collision de hachage et de quelle façon elle se manifeste.
translation-type: ht
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# Collisions de hachage

Adobe traite les valeurs prop et eVar comme des chaînes, même si la valeur est un nombre. Parfois, ces chaînes sont constituées de centaines de caractères ; d’autres fois elles sont très courtes. Pour économiser de l’espace, améliorer les performances et uniformiser leur taille, les chaînes ne sont pas utilisées directement dans le traitement. À la place, un hachage de 32 bits ou 64 bits est calculé pour chaque valeur. Tous les rapports s’exécutent sur ces valeurs de hachage, où chaque hachage est remplacé par le texte d’origine. Les hachages augmentent considérablement les performances des rapports Analytics.

Pour la plupart des champs, la chaîne est convertie au préalable en minuscules (ce qui réduit le nombre de valeurs uniques). Les valeurs sont hachées chaque mois (la première fois qu’elles sont vues chaque mois). Au fil des mois, il peut arriver que deux valeurs de variable uniques soient hachées avec la même valeur de hachage. On parle alors de *collision de hachage*.

Les collisions de hachage peuvent se manifester dans les rapports comme suit :

* Si vous exécutez un rapport de tendance d’une valeur et que vous constatez un pic pour un mois donné, il est probable que d’autres valeurs pour cette variable soient hachées à la même valeur que la valeur que vous observez.
* Le même comportement se produit pour les segments pour une valeur spécifique.

## Exemple de collision de hachage

La probabilité des collisions de hachage augmente avec le nombre de valeurs uniques dans une dimension. Par exemple, l’une des valeurs transmises en fin de mois pourrait avoir la même valeur de hachage qu’une valeur plus tôt dans le mois. L’exemple suivant peut aider à comprendre de quelle façon ce comportement peut provoquer le changement des résultats des segments. Supposons que l’eVar62 reçoive la « valeur 100 » le 18 février. Analytics tient à jour un tableau qui peut ressembler à ceci :

<table id="table_6A49D1D5932E485DB2083154897E5074"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Valeur de chaîne eVar62 </th> 
   <th colname="col2" class="entry"> Hachage </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Valeur 99 </p> </td> 
   <td colname="col2"> <p> 111 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Valeur 100</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Valeur 101 </p> </td> 
   <td colname="col2"> <p> 222 </p> </td> 
  </tr> 
 </tbody> 
</table>

Si vous créez un segment qui recherche les visites où eVar62=&quot;valeur 500&quot;, Analytics détermine si la « valeur 500 » contient un hachage. Puisque la « valeur 500 » n’existe pas, Analytics renvoie zéro visite. Puis, le 23 février, l’eVar62 reçoit la « valeur 500 », pour laquelle le hachage est également 123. Le tableau ressemblera à ce qui suit :

<table id="table_5FCF0BCDA5E740CCA266A822D9084C49"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Valeur de chaîne eVar62 </th> 
   <th colname="col2" class="entry"> Hachage </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Valeur 99 </p> </td> 
   <td colname="col2"> <p> 111 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Valeur 100</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Valeur 101 </p> </td> 
   <td colname="col2"> <p> 222 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Valeur 500</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

Quand le même segment s’exécute à nouveau, il recherche le hachage de la « valeur 500 », trouve 123, et le rapport renvoie toutes les visites qui contiennent le hachage 123. Désormais, les visites survenues le 18 février seront incluses dans les résultats.

Cette situation est susceptible d’engendrer des problèmes lors de l’utilisation d’Analytics. Adobe continue à chercher des façons de réduire la probabilité de ces collisions de hachage à l’avenir. Pour éviter cette situation, essayez d’étaler les valeurs uniques entre les variables, supprimez les valeurs superflues avec les règles de traitement ou encore réduisez le nombre de valeurs par variable.
