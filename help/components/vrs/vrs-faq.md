---
description: Cette section contient des conseils et des bonnes pratiques à l’intention des nouveaux utilisateurs de suites de rapports virtuelles.
keywords: Suite de rapports virtuelle
title: FAQ sur les suites de rapports virtuelles
feature: Concepts de base des rapports et analyses
uuid: 91225743-765a-4145-9ce5-4268e80ea7e8
exl-id: ab961bec-5719-4b90-bc10-c929b63dc923
translation-type: tm+mt
source-git-commit: cddf2a76ca36914f133379959b7cbb5246bdd695
workflow-type: tm+mt
source-wordcount: '904'
ht-degree: 99%

---

# FAQ sur les suites de rapports virtuelles

Cette section contient des conseils et des bonnes pratiques à l’intention des nouveaux utilisateurs de suites de rapports virtuelles.

<table id="table_4D9DE70984674B65AD7D40E3D1479CD2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Réponse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Dois-je regrouper plusieurs suites de rapports en une seule suite de rapports globale et utiliser ensuite des suites de rapports virtuelles afin d’afficher les différents segments de données pour les utilisateurs ?</b> </td> 
   <td colname="col2"> <p>Cela dépend. Voici quelques cas pour lesquels vous devez <b>continuer à utiliser des suites de rapports distinctes</b> : </p> 
    <ul> 
     <li>Si vous disposez de variables/dimensions avec un grand nombre de valeurs uniques, le regroupement de plusieurs suites de rapports en une seule suite peut entraîner le dépassement des limites mensuelles liées aux valeurs uniques dans cette suite globale et des troncatures (élément de ligne Faible trafic dans les rapports). </li> 
     <li>Si vous avez besoin de rapports en temps réel ou de données actives pour chaque segment (marques, unités opérationnelles, etc.) des données. </li> 
     <li>Si les différentes suites de rapports dont vous disposez possèdent des exigences uniques en ce qui concerne le suivi (si elles utilisent de manière très différente les variables et les événement d’Adobe Analytics, par exemple). Notez que le regroupement de ces suites de rapports en une seule suite ne vous donnera pas des variables ou des événements supplémentaires pour le suivi. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Quels paramètres des suites de rapports virtuelles sont hérités de la suite de rapports parente ?</b> </td> 
   <td colname="col2"> <p>Une suite de rapports virtuelle hérite de la plupart des niveaux de service de la suite de rapports parente, tels que les paramètres d’eVar, les règles de traitement, les classifications, etc. </p> <p>Les paramètres suivants <b>NE sont PAS</b> hérités : </p> 
    <ul> 
     <li>Identifiant de suite de rapports </li> 
     <li>Nom de la suite de rapports </li> 
     <li>Groupes d’autorisations (les suites de rapports virtuelles peuvent être affectées à leurs propres groupes d’autorisations) </li> 
    </ul> <p>Remarque : la plupart des entités créées par l’utilisateur ne sont pas incluses : signets, tableaux de bord, rapports planifiés, etc.Ces éléments ne sont pas hérités du parent et peuvent être créés et utilisés spécifiquement dans une suite de rapports virtuelle (des informations supplémentaires sont données dans la question suivante). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>En quoi diffère l’utilisation d’une suite de rapports virtuelle de celle d’une suite de rapports de base dans l’interface utilisateur d’Analytics ?</b> </td> 
   <td colname="col2"> <p>Une fois créée, une suite de rapports virtuelle est considérée comme une suite de rapports de base dans toute l’interface utilisateur. Elle est généralement prise en charge pour les fonctionnalités les plus étendues. Par exemple : </p> 
    <ul> 
     <li>À l’instar des suites de rapports de base, les suites de rapports virtuelles s’affichent dans le sélecteur de suites de rapports et peuvent être sélectionnées. </li> 
     <li>Il est possible de créer par exemple des rapports, des signets, des tableaux de bord, des cibles, des alertes, des segments et des mesures calculées dans une suite de rapports virtuelle. Le comportement de tous ces éléments ne dépend pas du parent. </li> 
     <li>Tout comme n’importe quelle suite de rapports, une suite de rapports virtuelle peut être ajoutée à des groupes d’autorisations. </li> 
     <li>Des segments peuvent toujours être appliqués lors de l’exécution des rapports dans le contexte d’une suite de rapports virtuelle. Ils sont automatiquement empilés avec le ou les segments de la suite de rapports virtuelle lors de la récupération des données du rapport. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Comment les suites de rapports virtuelles sont-elles traitées dans l’Admin Console et l’API Admin ? Puis-je y enregistrer des fonctionnalités à l’instar des suites de rapports de base ?</b> </td> 
   <td colname="col2"> <p>Non, les suites de rapports virtuelles <b>ne sont pas prises en charge pour la plupart des fonctionnalités d’administration</b>. Comme nous l’avons mentionné plus haut, une suite de rapports virtuelle hérite de la plupart des niveaux de service et des fonctionnalités (paramètres d’eVar, règles de traitement, classifications, par exemple). Pour modifier ces paramètres hérités dans une suite de rapports virtuelle, vous devez donc apporter les modifications à la suite de rapports parente. </p> <p>Par conséquent, les suites de rapports s’affichent <b>uniquement à cet emplacement</b> dans l’interface utilisateur : </p> 
    <ul> 
     <li>Gestionnaire de suites de rapports virtuelles où vous pouvez créer et modifier des suites de rapports virtuelles. <p>( <span class="ignoretag"> <span class="uicontrol"> Analytics</span> &gt; <span class="uicontrol">Composants</span> &gt; <span class="uicontrol">Suites de rapports virtuelles </span> </span>) </p> </li> 
     <li id="li_E2B3F61A3013402697DCF6E0D32A62DC"> Interface Gestion utilisateur où vous pouvez modifier les groupes d’autorisations personnalisés. Les comptes des suites de rapports virtuelles peuvent ainsi être ajoutés à un groupe d’autorisations et utilisés pour créer un groupe ayant uniquement accès aux suites de rapports virtuelles (si l’administrateur souhaitait refuser l’accès au parent et autoriser l’accès à des segments spécifiques uniquement). <p>( <span class="ignoretag"> <span class="uicontrol"> Admin</span> &gt; <span class="uicontrol">Gestion utilisateur </span> </span>) </p> </li> 
    </ul> <p>Remarque : Lorsque vous utilisez l’API des services web et que vous essayez d’enregistrer les paramètres des fonctionnalités sur une suite de rapports virtuelle, une exception est levée. Les fonctionnalités ne peuvent être définies que dans une suite de rapports de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> J’ai coché « démarrer une nouvelle visite au lancement ». Pourquoi les visites sont-elles toujours beaucoup plus élevées que les lancements ?</b> </td> 
   <td colname="col2"> <p> Lorsque « Démarrer une nouvelle visite au lancement » est cochée, le délai d’expiration s’applique toujours. Ainsi, si un utilisateur utilise l’application pendant dix minutes avec une pause d’une minute entre chaque action, une nouvelle visite commence au lancement, puis neuf visites supplémentaires sont créées lorsque la visite expire. Pour que les lancements et les visites soient aussi proches que possible lors de l’utilisation de l’option « Démarrer une nouvelle visite au lancement », vous devez utiliser un délai d’expiration supérieur au délai d’expiration de la session défini dans le SDK. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> J’ai défini « démarrer une nouvelle visite au lancement » et un délai d’expiration plus long que celui de mon SDK. Pourquoi mes lancements sont-ils toujours largement inférieurs aux visites ?</b> </td> 
   <td colname="col2"> <p> Si le délai d’expiration est supérieur à la valeur définie dans le SDK, il est très probable que votre application envoie des accès en arrière-plan et que ces accès soient enregistrés en tant que nouvelles visites. Vérifiez cela en utilisant la dimension de type accès de la suite de rapports parente pour voir s’il existe des accès en arrière-plan. </p> <p> <p>Remarque : Les accès en arrière-plan et de premier plan sont différenciés uniquement dans les versions 4.13.6 et supérieures du SDK. Si vous utilisez une version inférieure, tous les accès s’affichent en premier plan. Si vous utilisez la version correcte du SDK, vous devez activer le paramètre « Empêcher les accès en arrière-plan de commencer une nouvelle visite ». </p> </p> <p> <p>Remarque : Si vous avez désactivé le traitement hérité pour les accès en arrière-plan dans Admin Console, ils n’apparaîtront pas dans la suite de rapports parente mais apparaîtront dans la suite de rapports virtuelle. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> Quelle version du SDK dois-je avoir pour effectuer le suivi des accès en arrière-plan ?</b> </td> 
   <td colname="col2"> <p> Vous devez disposer de la version 4.13.6 ou supérieure du SDK. </p> </td> 
  </tr> 
 </tbody> 
</table>
