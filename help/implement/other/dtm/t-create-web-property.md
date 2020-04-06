---
description: Une propriété web peut être n’importe quel regroupement d’un ou de plusieurs domaines et sous-domaines avec une bibliothèque de règles, inclus dans un code intégré.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;web property;property
title: Création d’une propriété web
topic: Developer and implementation
uuid: f19d5504-eb44-4d93-a387-7470ab4b3a3a
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Création d’une propriété web

Une propriété web peut être n’importe quel regroupement d’un ou de plusieurs domaines et sous-domaines avec une bibliothèque de règles, inclus dans un code intégré.

>[!NOTE] Seul un utilisateur disposant des droits d’administrateur peut créer une propriété. Pour plus d’informations sur les rôles, voir [Création et gestion de groupes dans DTM](https://marketing.adobe.com/resources/help/fr_FR/dtm/groups.html) dans la documentation du produit Dynamic Tag Management.

Vous pouvez gérer ces ressources et en effectuer le suivi au moyen de la gestion dynamique des balises. Par exemple, supposons que vous disposez de plusieurs sites web reposant sur un modèle et que vous souhaitez effectuer le suivi des mêmes ressources sur tous les sites. Vous pouvez appliquer une propriété Web à plusieurs domaines.

Pour obtenir des informations générales sur les propriétés web et les bonnes pratiques, voir [Propriétés web](https://marketing.adobe.com/resources/help/fr_FR/dtm/web_property.html) dans la documentation du produit Dynamic Tag Management.

1. Navigate to your company page, then click **[!UICONTROL Add Property]**.

   ![](assets/dtm-create-web-property.png)

1. Renseignez les champs suivants :

   <table id="table_376D72251C4D4C4CA878D10C18D2532C"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Elément </th> 
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
    <td colname="col2"> <p>Vous pouvez ajouter et supprimer des domaines si vous souhaitez que les données de persistent entre les domaines. Si cette option est sélectionnée, les données de la visite persistent dans les sous-domaines. </p> <p>Ce paramètre vous permet de spécifier le mode de suivi du trafic entre les sous-domaines ou domaines associés. Les liens vers les sous-domaines sont traités comme des liens sortants. Le suivi des visites des sous-domaines s’effectue de manière séparée. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. (Facultatif) Configurez [!UICONTROL Advanced Settings].

   <table id="table_6E687FBE6ACC4301BCCD837F4DCBB9C9"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Elément </th> 
    <th colname="col2" class="entry"> Description </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Autoriser les approbations de plusieurs règles</span> </td> 
    <td colname="col2"> <p>Permet d’approuver simultanément plusieurs règles pour cette propriété. L’approbation par défaut autorise uniquement l’approbation d’une règle unique. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Activer la publication sélective</span> </td> 
    <td colname="col2"> <p>Spécifie si les utilisateurs sont autorisés à sélectionner les règles approuvées à publier. Il s’agit de l’option par défaut. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Nom du cookie de suivi</span> </td> 
    <td colname="col2"> <p>Permet de remplacer le nom par défaut du cookie de suivi. Vous pouvez personnaliser le nom utilisé par la gestion dynamique des balises pour effectuer le suivi de votre état d’exclusion pour la réception d’autres cookies. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Expiration de balise</span> </td> 
    <td colname="col2"> <p>Indique la durée pendant laquelle la gestion dynamique des balises attend qu’une balise se déclenche avant d’expirer et d’annuler la demande de balise. </p> <p> Compte tenu de la façon dont fonctionne Dynamic Tag Management, ne vous inquiétez pas si ce nombre est élevé. La gestion dynamique des balises propose des méthodes efficaces pour s’assurer que les balises lentes n’affectent pas l’expérience utilisateur. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Délai d’ancrage</span> </td> 
    <td colname="col2"> <p>Permet d’indiquer le délai d’attente du déclenchement d’une balise lorsque des liens font l’objet d’un clic avant de passer à la page suivante. La valeur par défaut est de 100 millisecondes. </p> <p>Des délais supérieurs améliorent la précision du suivi. Adobe recommande un délai de 500 millisecondes ou moins, qui ne sera pas ressenti par l’utilisateur. </p> <p>La gestion dynamique des balises patiente jusqu’à l’heure spécifiée, mais si la balise se déclenche plus tôt, le délai est réduit. (Cela signifie que l’utilisateur ne patientera pas toujours pendant toute la durée spécifiée.) </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Cliquez sur **[!UICONTROL Create Property]**.
