---
description: Affiche le stade auquel chaque valeur a été déclenchée, en moyenne, au sein d’une visite. Cette mesure se révèle particulièrement utile pour déterminer le niveau auquel votre audience a atteint une page ou une valeur de propriété donnée au cours d’une visite. Profondeur moyenne de page est disponible sur toute variable dans laquelle le cheminement est activé.
title: Profondeur moyenne de page
topic: Metrics
uuid: 4d8a3a3c-c698-4210-8dd8-a02a1638483c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Profondeur moyenne de page

Affiche le stade auquel chaque valeur a été déclenchée, en moyenne, au sein d’une visite. Cette mesure se révèle particulièrement utile pour déterminer le niveau auquel votre audience a atteint une page ou une valeur de propriété donnée au cours d’une visite. Profondeur moyenne de page est disponible sur toute variable dans laquelle le cheminement est activé.

Si, par exemple, une visite comprend le chemin suivant : Page A &gt; Page B &gt; Page C &gt; Page D &gt; Page E &gt; Page F, la profondeur est un indice de là où se situe la page. Par exemple, la page A a une profondeur de 0, tandis que la page F a une profondeur de 5. La moyenne est fondée sur une combinaison de toutes les visites. Une profondeur de page avec une valeur inférieure à 1 (0,9, par exemple) est la valeur moyenne de toutes les pages consultées avant la page en question.

La [!UICONTROL profondeur de page] vous permet de comprendre où aboutit généralement une page donnée dans le cheminement d’un utilisateur, quelles que soient les pages précédentes ou suivantes dans ce cheminement. En l’occurrence, elle fournit des renseignements sur la manière dont la page se situe dans l’expérience globale de l’utilisateur sur votre site. L’affichage de ces renseignements est optimal dans un rapport [!UICONTROL Pages].

<table id="table_E92B185A487C40E28C70EA30EDF73A40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Utilisations </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Trafic </td> 
   <td colname="col2"> <p>Calcul des événements de page et des pages vues divisés par le nombre de visites, indiquant le nombre moyen de clics d’une page. Reprenons le même chemin de visite : </p> <p>A &gt; B &gt; B &gt; C &gt; D &gt; B </p> <p>Le nombre de clics est calculé pour chaque page et chaque événement de page, y compris les actualisations lorsque l’option Compter les répétitions est activée (elle est activée par défaut dans les Ad Hoc Analysis et est toujours activée dans les Marketing Reports and Analytics). Dans cette visite, la page A reçoit 0 clic. Pour la page B, les nombres de clics seront de 1, 2 et 5. Le calcul de la moyenne sera de [(1+2+5) / 3] pour une Profondeur moyenne de page de 2,67 pour la page B. </p> <p>Si l’option Compter les répétitions est désactivée, les nombres de clics de la page B seront 1 et 4. Le deuxième nombre n’est pas compté. Le calcul sera [(1+4) / 2 = 2,5]. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Conversion </td> 
   <td colname="col2"> S.O. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Rapport Profondeur de page](/help/components/c-variables/dimensionslist/reports-page-depth.md)

