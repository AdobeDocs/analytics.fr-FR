---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Analytics Implementation
subtopic: Variables
title: Variables dynamiques
topic: Developer and implementation
uuid: 1c6db083-570e-4bc4-858d-84cf46e7bec8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Variables dynamiques

Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.

Les variables dynamiques sont utilisées lors de la capture simultanée des mêmes données (des codes de suivi de campagne, par exemple) dans plusieurs variables. Il s’agit d’une pratique courante lorsque différents rapports proposent des mesures importantes. Par exemple, la capture de mots-clés de recherche interne dans une variable [!UICONTROL Conversion personnalisée] et dans une variable [!UICONTROL Trafic personnalisé] vous permet de consulter, respectivement, les mesures [!UICONTROL Recettes] et [!UICONTROL Visiteurs uniques par semaine] associées à ces mots-clés..

Les variables dynamiques se révèlent également utiles pour visualiser les données selon différentes conditions de génération de rapports. Un code de suivi de campagne peut être capturé dans plusieurs eVars avec différents paramètres d’attribution et d’expiration de cookies. Les utilisateurs ont ainsi la possibilité de choisir la méthode à appliquer pour attribuer des mesures de conversion à ces campagnes.

> [!NOTE] Les variables dynamiques ne sont pas prises en charge conjointement avec les cookies (s_cc, s_sq, s_fid, s_vi et les cookies définis par un module externe). Vous ne pouvez pas utiliser `D=<cookie value>`.

La capture de longues chaînes de données dans plusieurs variables, sans les transmettre à plusieurs reprises, constitue un avantage considérable des variables dynamiques. Certains navigateurs limitent la longueur maximale des demandes GET HTTP (y compris la demande d’image Adobe). L’utilisation de variables dynamiques garantit la capture de toutes les données en réduisant la longueur de la demande faite aux serveurs Adobe lorsque les données sont dupliquées dans plusieurs variables..

Dans la demande d’image Adobe qui survient sur la page vue, si vous utilisez des variables dynamiques pour copier la valeur de [!UICONTROL Trafic personnalisé ] dans [!UICONTROL Conversion personnalisée ], `v1=D=c1`1=1 sera affiché. Si eVar1 a reçu une valeur qui figurait précédemment dans la demande, les serveurs d’Adobe copient dynamiquement la valeur de [!UICONTROL Trafic personnalisé 1] dans [!UICONTROL Conversion personnalisée 1] au cours du traitement des données. En conséquence, la valeur transmise initialement à l’aide de [!UICONTROL Trafic personnalisé 1] apparaît également dans les rapports [!UICONTROL Conversion personnalisée 1].

Les variables dynamiques sont transmises en définissant une variable sur la valeur souhaitée et en définissant ensuite d’autres sur `D=[variable abbreviation]`. Pour consulter les abréviations pour chaque variable, voir la section [Paramètres de requête de la collecte de données](/help/implement/js-implementation/data-collection/query-parameters.md). Les variables dynamiques peuvent extraire des données des emplacements suivants :

* Autres variables de chaîne de requête
* En-tête HTTP (à l’exception de l’en-tête HTTP Cookie)

Pour créer une variable dynamique, ajoutez un préfixe spécial au début de la valeur. Le préfixe par défaut est « D= ». Pour baliser des variables dynamiques, deux méthodes sont possibles :

* Utilisation d’un préfixe par défaut D= (par exemple : s.prop1="D=User-Agent")
* Pour les implémentations non JavaScript, vous pouvez définir un préfixe personnalisé à l’aide du paramètre de chaîne de requête « D ». Par exemple, si le paramètre de chaîne de requête est `"&D=$"`, vous pouvez créer une variable dynamique avec la commande suivante : `s.prop1="$User-Agent"`.

L’abréviation de variable utilisée doit correspondre au nom du paramètre de variable transmis dans la demande d’image. Pour certaines variables, plusieurs paramètres sont acceptés dans différents cas de figure. Ainsi, `pageName=` et `gn=` transmettent toutes deux le nom de page, mais la seconde est généralement utilisée dans les implémentations mobiles et codées en dur. Si la demande d’image utilise `pageName=` pour transmettre le nom de la page, `D=pageName` est acceptable, mais pas `D=gn`. Si la demande d’image utilise l’abréviation `gn=`, `D=gn` est acceptable, mais pas `D=pageName`.

Les informations suivantes s’appliquent aux variables dynamiques :

* Les variables dynamiques fonctionnent avec toutes les versions du code AppMeasurement.
* Les variables dynamiques sont sensibles à la casse.
* Les variables dynamiques prennent en charge les chaînes littérales entre guillemets.
* Le remplacement des variables dynamiques s’opère avant les règles de traitement, VISTA et autres.
* Le préfixe de variable dynamique « D= » doit se trouver au début de la valeur, et non au milieu. Par exemple, utilisez `c2='D="test7"+User-Agent'` plutôt que `c2='"test7"+D=User-Agent'` .

* Comme c’est le cas pour toutes les techniques d’implémentation, Adobe conseille vivement de tester les implémentations de variables dynamiques dans un environnement de développement avant leur déploiement en production. Les chaînes complètes qui sont copiées ne sont pas visibles dans les outils de débogage côté client. Vous devez donc consulter les rapports Analytics concernés pour confirmer que l’implémentation s’est déroulée avec succès.
* Lors de la copie de valeurs entre des variables dont la longueur maximale est différente, notez que la copie d’une valeur qui dépasse la longueur maximale de la variable de destination entraînera une troncature. Par exemple, la limite est de 100 caractères pour les variables [!UICONTROL Trafic personnalisé] et de 255 caractères pour les variables [!UICONTROL Conversion personnalisée]. Lorsque vous copiez une valeur de 150 caractères depuis s.eVar1 vers s.prop1 à l’aide de variables dynamiques, celle-ci est tronquée à 100 caractères dans le rapport [!UICONTROL Trafic personnalisé].

## Exemples de variables dynamiques {#section_5CE4468D978540FBA384B9D6477C92EC}

<!-- 

dynvars_examples.xml

 -->

Exemples de variables dynamiques utilisables dans Analytics.

Dans la demande d’image Adobe qui survient sur la page vue, si vous utilisez des variables dynamiques pour copier la valeur de [!UICONTROL Trafic personnalisé ] dans [!UICONTROL Conversion personnalisée ], `v1=D=c1`1=1 sera affiché. Si eVar1 a reçu une valeur qui figurait précédemment dans la demande, les serveurs d’Adobe copient dynamiquement la valeur de [!UICONTROL Trafic personnalisé 1] dans [!UICONTROL Conversion personnalisée 1] au cours du traitement des données. En conséquence, la valeur transmise initialement à l’aide de [!UICONTROL Trafic personnalisé 1] apparaît également dans les rapports [!UICONTROL Conversion personnalisée 1].

Notez que la valeur de `D=[variable]` doit se trouver entre guillemets. Le code Analytics la considère alors comme une chaîne. La chaîne sera codée au format URL lors de sa transmission à Analytics (comme vous pourrez le voir en affichant la demande dans le DigitalPulse Debugger ou un utilitaire du même type). Cela est tout à fait normal. Les serveurs d’Adobe reconnaissent la construction `D=[variable]` et copient la valeur appropriée lorsqu’ils trouvent cette chaîne.

> [!NOTE] Lorsque vous utilisez la demande d’image pour effectuer le suivi des liens, le type de lien (téléchargement=lnk_d, sortie=lnk_e ou lien personnalisé=lnk_o) doit être défini, comme l’URL ou le nom du lien (pev2). Pour les liens, une implémentation manuelle s’avère nécessaire en insérant du code dans la balise `<a href>`.

> [!NOTE] Les variables dynamiques ne sont pas prises en charge conjointement avec les cookies (s_cc, s_sq, s_fid, s_vi et les cookies définis par un module externe). Vous ne pouvez pas utiliser `D=<cookie value>`.

<table id="table_A25D5EA2A8C446F5A55AB32955B9848C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exemple JavaScript </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      s.eVar1="D=pageName" 
    </code> </td> 
   <td colname="col2"> <p>Capture la valeur pageName dans eVar1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      s.prop1='D=v2+":"+c2'&amp;nbsp; 
    </code> </td> 
   <td colname="col2"> <p>Concatène eVar2:prop2 dans prop1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      s.prop1=s.eVar1="D=g"&amp;nbsp; 
    </code> </td> 
   <td colname="col2"> <p>Transmet l’URL de page à prop1 et eVar1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      s.eVar1="D=v0" 
    </code> </td> 
   <td colname="col2"> <p>Capture la campagne dans eVar 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      s.prop1='D=User-Agent+" ;- "+Accept-Language' 
    </code> </td> 
   <td colname="col2"> <p>Concatène l’agent utilisateur et les en-têtes de langue d’acceptation dans prop1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>
      s.prop1="D=User-Agent" 
    </code> </td> 
   <td colname="col2"> <p>Capture l’agent utilisateur dans prop1. </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_DD0B7F0648054E01A5F98CDF18D745E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exemple de demande d’image </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      /b/ss/rsid/?gn=Home&amp;D=~~&amp;c1=~~v0 /b/ss/rsid/?gn=Home&amp;D=~~&amp;c1=~~campaign /b/ss/rsid/?gn=Home&amp;c1=D%3dv0%3d&nbsp;is /b/ss/rsid/?gn=Home&amp;c1=%5b%5bv0%5d%5d%5b
    </code> </td> 
   <td colname="col2"> <p>Quatre façons de définir prop1 sur une campagne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>
      /b/ss/rsid/?gn=Home&amp;D=~~&amp;c2=~~x-up-subno 
    </code> </td> 
   <td colname="col2"> <p> Récupère l’en-tête x-up-subno dans prop2. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>
      c1=D%3DUser-Agent 
    </code> </td> 
   <td colname="col2"> <p> Transforme prop1 en une variable dynamique remplie avec l’en-tête HTTP User-Agent. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      &amp;c1=D%3D%22test%22 
    </code> </td> 
   <td colname="col2"> <p> Transforme prop1 en une variable dynamique remplie avec la chaîne « test ». Cela se révèle particulièrement utile en combinaison avec la concaténation qui utilise l’opérateur « + ». </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      &amp;c1=D%3D%22US%3A%20%22%2BUser-Agent 
    </code> </td> 
   <td colname="col2"> <p> Transforme prop1 en une variable dynamique remplie avec l’en-tête User-Agent accompagné du préfixe « UA: ». </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      &amp;vid=D%3DX-TM-ANTID 
    </code> </td> 
   <td colname="col2"> <p> Cet exemple recherche un en-tête unique qui, dans le cas présent, est X-TM-ANTID. </p> </td> 
  </tr> 
 </tbody> 
</table>
