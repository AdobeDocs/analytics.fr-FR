---
description: Une propriété web peut être n’importe quel regroupement d’un ou de plusieurs domaines et sous-domaines avec une bibliothèque de règles, inclus dans un code intégré.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;web property;property
title: Création d’une propriété web
topic: Developer and implementation
uuid: f19d5504-eb44-4d93-a387-7470ab4b3a3a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Création d’une propriété web

Une propriété web peut être n’importe quel regroupement d’un ou de plusieurs domaines et sous-domaines avec une bibliothèque de règles, inclus dans un code intégré.

> [!NOTE] Seul un utilisateur disposant des droits d’administrateur peut créer une propriété. Pour plus d’informations sur les rôles, voir [Création et gestion de groupes dans la gestion dynamique des balises](https://marketing.adobe.com/resources/help/en_US/dtm/groups.html) dans la documentation du produit Gestion dynamique des balises.

Vous pouvez gérer ces ressources et en effectuer le suivi au moyen de la gestion dynamique des balises. Par exemple, supposons que vous disposez de plusieurs sites web reposant sur un modèle et que vous souhaitez effectuer le suivi des mêmes ressources sur tous les sites. Vous pouvez appliquer une propriété web à plusieurs domaines.

Pour obtenir des informations générales sur les propriétés web et les bonnes pratiques, voir [Propriétés web ](https://marketing.adobe.com/resources/help/en_US/dtm/web_property.html) dans la Documentation du produit Dynamic Tag Management.

1. Accédez à la page Entreprises, puis cliquez sur **[!UICONTROL Ajouter une propriété]**.

   ![](assets/dtm-create-web-property.png)

1. Renseignez les champs suivants :

   <table id="table_376D72251C4D4C4CA878D10C18D2532C"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Élément </th> 
    <th colname="col2" class="entry"> Description </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Nom</span> </td> 
    <td colname="col2"> <p>Nom de la propriété. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> URL</span> </td> 
    <td colname="col2"> <p>URL de base de la propriété. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Ce site englobe plusieurs domaines </span> </td> 
    <td colname="col2"> <p>Vous pouvez ajouter ou supprimer des domaines si vous voulez que les données de visiteur persistent entre les domaines. Si cette option est sélectionnée, les données associées à la visite persistent à travers les sous-domaines. </p> <p>Ce paramètre permet de spécifier le mode de suivi du trafic entre vos sous-domaines ou domaines associés. Les liens vers les sous-domaines sont traités comme des liens sortants. Le suivi des visites des sous-domaines s’effectue de manière séparée. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. (Facultatif) Configurez les [!UICONTROL Paramètres avancés].

   <table id="table_6E687FBE6ACC4301BCCD837F4DCBB9C9"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Élément </th> 
    <th colname="col2" class="entry"> Description </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Autoriser les approbations de plusieurs règles</span> </td> 
    <td colname="col2"> <p>Permet d’approuver simultanément plusieurs règles pour cette propriété. Le processus d’approbation n’autorise l’approbation que d’une seule règle. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Activer la publication sélective</span> </td> 
    <td colname="col2"> <p>Spécifie si les utilisateurs sont autorisés à sélectionner les règles approuvées à publier. Il s’agit de l’option par défaut. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Nom du cookie de suivi</span> </td> 
    <td colname="col2"> <p>Permet de remplacer le nom par défaut du cookie de suivi. Vous pouvez personnaliser le nom utilisé par Dynamic Tag Management pour effectuer le suivi de votre état d’exclusion pour la réception d’autres cookies. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Expiration de balise</span> </td> 
    <td colname="col2"> <p>Permet d’indiquer le délai d’attente du déclenchement d’une balise avant d’arriver à expiration et d’annuler la demande de balise. </p> <p> Compte tenu de la façon dont fonctionne Dynamic Tag Management, ne vous inquiétez pas si ce nombre est élevé. La gestion dynamique des balises dispose de méthodes efficaces pour s’assurer que les balises lentes n’aient aucune incidence sur l’expérience utilisateur. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Délai d’ancrage</span> </td> 
    <td colname="col2"> <p>Permet d’indiquer le délai d’attente du déclenchement d’une balise lorsque des liens font l’objet d’un clic avant de passer à la page suivante. La valeur par défaut est de 100 millisecondes. </p> <p>Des délais supérieurs améliorent la précision du suivi. Adobe recommande un délai de 500 millisecondes ou moins, qui ne sera pas ressenti par l’utilisateur. </p> <p>Dynamic Tag Management patiente pendant la durée spécifiée, mais si la balise se déclence plus tôt, le délai est raccourci. (Cela signifie que l’utilisateur ne patientera pas toujours pendant toute la durée spécifiée.) </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Cliquez sur **[!UICONTROL Créer une propriété]**.
