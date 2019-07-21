---
description: Options de calendrier autres que le modèle grégorien. Les options incluent les modèles de calendrier 4-4-5, 4-5-4 et 5-4-4, qui sont tous des normes du secteur de la vente au détail. En outre, la création de rapports offre une option de personnalisation complète du calendrier.
seo-description: Options de calendrier autres que le modèle grégorien. Les options incluent les modèles de calendrier 4-4-5, 4-5-4 et 5-4-4, qui sont tous des normes du secteur de la vente au détail. En outre, la création de rapports offre une option de personnalisation complète du calendrier.
seo-title: Personnalisation du calendrier
solution: Analytics
title: Personnalisation du calendrier
topic: Outils d’administration
uuid: 4 e 5 e 538 b -54 c 9-4 c 2 f -8 b 6 c -9 f 91 b 6 c 7 bcc 7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Personnalisation du calendrier

Options de calendrier autres que le modèle grégorien. Les options incluent les modèles de calendrier 4-4-5, 4-5-4 et 5-4-4, qui sont tous des normes du secteur de la vente au détail. En outre, la création de rapports offre une option de personnalisation complète du calendrier.

**[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[! UICONTROL[select report suite]]** &gt; **[!UICONTROL Modifier les paramètres]** &gt; **[!UICONTROL Général]** &gt; **[!UICONTROL Personnaliser le calendrier]**

>[!CAUTION]
>
>La modification du calendrier modifie la manière dont les données sont traitées (c.-à-d. la définition des visiteurs uniques par semaine et par mois). Les données historiques ne sont pas altérées quand la définition des semaines et des mois d’un calendrier est modifiée.

Vous pouvez utiliser le calendrier pour définir le premier jour de la semaine et de l’année, ou un style de calendrier de vente au détail différent. Chaque format a son utilité, notamment pour la comparaison des ventes et la normalisation des prévisions, l’analyse des coûts salariaux ou encore la régulation de l’inventaire matériel. Par exemple, dans le domaine de la vente au détail, on utilise un calendrier comptable de type 4-5-4 pour tenir compte des saisons de vente spécifiques à ce secteur d’activités. Vous trouverez, ci-dessous, la description de chacun des formats calendaires.

## Descriptions de la personnalisation des calendriers {#section_B0D224DACB914A378902A4E0E1234889}

<table id="table_E609632569EB499184E56618C2CEF742"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Calendrier </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Calendrier grégorien </p> </td> 
   <td colname="col2"> <p> Utilise le format de calendrier traditionnel (de janvier à décembre avec des mois de 30 et 31 jours et un nombre de semaines variable pour chaque mois). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calendrier grégorien modifié </p> </td> 
   <td colname="col2"> <p> Utilise le calendrier grégorien traditionnel, mais vous permet de choisir le premier mois de l’année et le premier jour de la semaine. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calendrier de vente au détail 4-5-4 </p> </td> 
   <td colname="col2"> <p> Décompose chaque mois selon le nombre de semaines qu’il comporte. En d’autres termes, janvier compte 4 semaines, etc. La National Retail Federation (États-Unis) utilise le format de calendrier en 4-5-4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calendrier personnalisé </p> </td> 
   <td colname="col2"> <p> Offre trois formats selon le nombre de semaines de chaque mois. Le nombre de semaines dans le mois dépend du premier jour de l’année choisi. </p> <p>Une année comporte 52 semaines. Divisez ce chiffre en 4 trimestres et vous obtenez 13 semaines par trimestre. Toutefois, un trimestre comprend 3 mois. 13 n’est pas divisible par trois. De ce fait, vous placez la semaine supplémentaire dans l’un des mois pour garantir la cohérence. 5-4-4 signifie que la semaine supplémentaire a été ajoutée au premier mois. 4-5-4 signifie que la semaine supplémentaire a été ajoutée au deuxième mois, etc. Dans le calendrier 5-4-4, la 53e semaine est ajoutée au dernier trimestre de l’année. </p> 
    <ul id="ul_1579FD106A47419486B03E248A5E6ED5"> 
     <li id="li_E9B9E8F03E324DBDA9139C2D0D599092"><b>4-5-4</b> : janvier comporte quatre semaines, février cinq, mars quatre, etc. </li> 
     <li id="li_D0675DBDEC4641D2A8645B5CDFC565AB"><b>4-4-5</b> : janvier comporte quatre semaines, février quatre, mars cinq, etc. </li> 
     <li id="li_6743BBB9AC9A4CFEAA0CBCE51052BC29"><b>5-4-4</b> : janvier comporte cinq semaines, février quatre, mars quatre, etc. </li> 
    </ul> <p>Remarque : Cette option de calendrier est prise en charge dans tous les outils Adobe Analytics (Analysis Workspace, Reports &amp; Analytics, Report Builder, Activity Map, Ad Hoc Analysis) à l’exception de Data Warehouse qui ne prend pas en charge les calendriers personnalisés. </p> </td> 
  </tr> 
 </tbody> 
</table>

