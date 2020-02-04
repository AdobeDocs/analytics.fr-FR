---
description: Description des champs et options des paramètres Gestion des bibliothèques dans Dynamic Tag Management.
keywords: library management;page code;load library at;managed by adobe;custom;code hosted;s_code hosted
solution: Experience Cloud,Dynamic Tag Management
title: Gestion des bibliothèques
uuid: 4cfa47f9-ae98-4feb-a58d-a3a6e45f8d5b
translation-type: tm+mt
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# Gestion des bibliothèques

Description des champs et options des paramètres Gestion des bibliothèques dans Dynamic Tag Management.

**[!UICONTROL *`Property`*]**>![](assets/settings_gear.png)**[!UICONTROL Modifier l’outil]**>**[!UICONTROL Gestion des bibliothèques]**

> [!NOTE] Si plusieurs outils Adobe Analytics sont utilisés dans une seule propriété web, chaque outil doit disposer d’un nom de variable d’outil de suivi unique. Dans une propriété web, les noms de variable d’objet en double dans les outils Adobe Analytics entraînent des conflits.

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Le code de page existe déjà </p> </td> 
   <td colname="col2"> <p> Permet d’empêcher Dynamic Tag Management d’installer le code de page <span class="keyword">Adobe Analytics</span> s’il existe déjà sur votre site. </p> <p>Cette fonctionnalité vous permet d’utiliser Dynamic Tag Management à ajouter à votre mise en œuvre existante au lieu de commencer de rien. Assurez-vous de définir correctement le nom de variable de votre outil de suivi lorsque vous cochez cette case. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Charger la bibliothèque en &lt;<span class="term"> Haut de la page</span> ou <span class="term"> Bas de la page</span>&gt; </p> </td> 
   <td colname="col2"> <p>Permet d’indiquer où et à quel moment charger le code de page. Quelle que soit votre sélection, les règles utilisant l’outil Analytics doivent avoir le même paramètre. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Géré par Adobe (recommandé) </p> </td> 
   <td colname="col2"> <p>Permet d’activer Dynamic Tag Management pour gérer votre bibliothèque. </p> <p>Lorsque vous sélectionnez cette option, l’option suivante devient disponible : </p> <p> <b>Version de la bibliothèque :</b> sélectionnez la dernière version dans le menu <span class="wintitle">Version de la bibliothèque</span>. Dynamic Tag Management vous avertit lorsque de nouvelles versions sont disponibles. Vous pouvez revenir à une version antérieure, le cas échéant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Personnalisé </p> </td> 
   <td colname="col2"> <p>Vous pouvez configurer le code de la bibliothèque. </p> <p>Lorsque vous sélectionnez cette option, les options suivantes deviennent disponibles : </p> <p> <b>Définir les suites de rapports avec le code personnalisé ci-dessous :</b> lorsque cette case est cochée, Dynamic Tag Management recherche dans le code personnalisé une variable appelée <span class="varname"> s_account</span>. Cette variable doit contenir une liste séparée par des virgules des suites de rapports auxquelles vous souhaitez envoyer des données. </p> <p> <b>Code hébergé :</b> sélectionnez une option pour héberger le fichier <span class="filepath">s_code</span> : </p> 
    <ul id="ul_FC395283365A4BBAA8A5FE5871D16EC6"> 
     <li id="li_36D733C533CE40F1868309130551D4DE"> <b>Dans Dynamic Tag Management</b> : vous pouvez héberger le fichier <span class="filepath">s_code</span> dans Dynamic Tag Management. Cliquez sur <span class="uicontrol">Modifier le code</span> pour couper le fichier et le coller directement dans l’éditeur. </li> 
     <li id="li_A64734C66D254079A5E16DC8DBEDA3F6"> <b>URL</b> : si vous disposez déjà d’un fichier <span class="filepath">s_code</span> et que vous souhaitez le mettre à jour, indiquez l’URL vers le fichier ici. Dynamic Tag Management utilise ensuite ce fichier <span class="filepath">s_code</span> pour l’implémentation d’<span class="keyword">Adobe Analytics</span>. </li> 
    </ul> <p> <b>Ouvrir l’éditeur : </b>vous permet <a href="/help/implement/other/dtm/c-aa-tool/t-appmeasurement-code.md"  > d’insérer du code AppMeasurement de base</a>. Ce code est renseigné automatiquement lors de l’utilisation de la méthode de configuration automatique décrite dans <a href="/help/implement/other/dtm/c-aa-tool/analytics-dtm.md"  > Adobe Analytics Settings</a>. </p> <p> <b>Nom de variable de l’outil de suivi :</b> si vous souhaitez exécuter en parallèle deux instances d’<span class="keyword">Adobe Analytics</span> (une instance dans Dynamic Tag Management et l’autre de manière native), vous pouvez renommer l’objet <span class="term">s</span>. Attribuer un nouveau nom à cet objet permet d’éviter toute collision. </p> </td> 
  </tr> 
 </tbody> 
</table>

