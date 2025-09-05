---
description: Interprétez les identifiants capturés dans vos données Analytics et décidez lesquels utiliser pour les demandes relatives à la confidentialité des données.
title: Bonnes pratiques en matière d’étiquetage
feature: Data Governance
role: Admin
exl-id: 00da58b0-d613-4caa-b9c1-421b1b541f47
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '2286'
ht-degree: 100%

---

# Bonnes pratiques en matière d’étiquetage

Lʼétiquetage doit être vérifié chaque fois quʼune nouvelle suite de rapports est créée ou quʼune nouvelle variable est activée dans une suite de rapports existante. Il peut également être nécessaire de vérifier l’étiquetage lors de l’activation de nouvelles intégrations à des solutions puisque celles-ci peuvent exposer de nouvelles variables nécessitant un étiquetage. Une nouvelle implémentation de vos applications mobiles ou sites web peut modifier la manière dont les variables existantes sont utilisées, rendant nécessaire la mise à jour des étiquettes.

Les étiquettes I1, I2, S1 et S2 ont la même signification que les étiquettes DULE correspondantes dans Adobe Experience Platform. Cependant, elles sont utilisées à des fins très différentes. Dans Adobe Analytics, ces étiquettes sont utilisées pour permettre d’identifier les champs qui doivent être rendus anonymes à la suite d’une requête Privacy Service. Dans Adobe Experience Platform, elles sont utilisées pour le contrôle d’accès, la gestion du consentement et l’application des restrictions marketing aux champs étiquetés. Adobe Experience Platform prend en charge de nombreuses étiquettes supplémentaires qui ne sont pas utilisées par Adobe Analytics. Si vous utilisez le connecteur de données Analytics pour importer vos données Adobe Analytics dans Adobe Experience Platform, assurez-vous que les étiquettes I1, I2, S1 et S2 que vous avez appliquées dans Adobe Analytics sont également appliquées aux schémas d’Adobe Experience Platform utilisées par les suites de rapports importées.

## ID directement ou indirectement identifiables {#direct-vs-indirect}

Avant de pouvoir déterminer quelles étiquettes doivent être appliquées à tel ou tel champ/variable, vous devez d’abord comprendre les ID que vous capturez dans vos données Analytics et définir ceux qui seront utilisés pour les demandes relatives à la Confidentialité des données. La Confidentialité des données donne une dimension plus large de ce qui peut être considéré comme un ID. Les ID se divisent en deux grandes catégories : directement identifiables (étiquette d’identité : I1) et indirectement identifiables (étiquette d’identité : I2).

* **Un ID directement identifiable (I1)** : nomme la personne ou fournit une méthode directe pour la contacter. Parmi les exemples on retrouve les noms (même un nom commun comme John Smith qui peut être celui de centaines de personnes), les numéros de téléphone ou adresses électroniques, etc. des individus. Une adresse postale sans nom peut être considérée comme directement identifiable, même si elle ne peut identifier qu’un ménage ou une entreprise plutôt qu’une personne spécifique au sein de ce ménage ou de cette entreprise.
* **Un ID indirectement identifiable (I2)** : ne permet pas l’identification d’un individu en soi, mais peut être combiné avec d’autres informations (qui peuvent être ou non en votre possession), pour identifier une personne. Les exemples d’ID indirectement identifiables incluent un numéro de fidélisation de la clientèle, ou des ID spécifiques à chaque client ou cliente utilisés par la gestion de la relation client (CRM) d’une entreprise. En vertu de la Confidentialité des données, les ID anonymes stockés dans les cookies de suivi utilisés par Analytics sont réputés pour être identifiables indirectement, même s’ils ne peuvent identifier qu’un appareil plutôt qu’un individu. Sur un appareil partagé, ces cookies ne peuvent pas distinguer les différents utilisateurs du système. Par exemple, bien que le cookie ne puisse pas être utilisé pour trouver un ordinateur contenant le cookie, si quelqu’un accède à l’ordinateur et localise le cookie, il peut alors ré-associer les données du cookie Analytics à l’ordinateur.

Une adresse IP est également considérée comme indirectement identifiable, car elle pourrait être uniquement attribuée à un seul appareil. Cependant, les FAI peuvent changer les adresses IP, ce qu’ils font d’ailleurs régulièrement pour la plupart de leurs abonnés, si bien que dans le temps, une même adresse IP peut avoir été utilisée par n’importe lequel de leurs utilisateurs. Il n’est pas rare non plus que de nombreux clients d’un FAI ou plusieurs employés d’une entreprise utilisant le même intranet partagent la même adresse IP externe. Pour cette raison, Adobe ne prend pas en charge l’utilisation d’une adresse IP en tant qu’ID pour une demande d’accès à des informations personnelles. Cependant, lorsqu’un ID que nous acceptons est utilisé dans le cadre d’une requête DELETE, les adresses IP y étant associées seront également supprimées. Vous devez décider s’il existe d’autres ID collectés qui peuvent appartenir à cette catégorie (I1 ou I2), mais qui ne peuvent pas être utilisés comme ID distinctif pour les demandes d’accès à des informations personnelles.

Même si votre entreprise collecte de nombreux ID différents dans vos données Analytics, vous pouvez choisir d’utiliser uniquement un sous-ensemble de ces ID pour les demandes relatives à la Confidentialité des données. Les raisons de ce choix pourraient être les suivantes :

* Au sein de vos propres systèmes, il se peut que vous mappiez l’un des ID (par exemple, l’adresse e-mail) à un ID différent (tel que l’ID de gestion de la relation client) ; puis, par souci de cohérence, que vous décidiez d’utiliser uniquement l’ID de gestion de la relation client pour les demandes relatives à la Confidentialité des données lors de votre traitement en vertu de la Confidentialité des données.
* Vous n’avez pas de méthode pour confirmer si la personne est réellement celle associée à l’ID. Par exemple, cela peut être très difficile de confirmer si une adresse IP n’a été utilisée que par une seule personne et si la personne qui soumet la demande est réellement cette personne.
* Certains ID peuvent correspondre à plusieurs personnes et vous ne voulez pas risquer de renvoyer des informations relatives à une personne à quelqu’un d’autre possédant le même ID. Par exemple, même si vous pouvez vérifier que le nom de la personne est John Smith, vous ne voulez peut-être pas renvoyer l’intégralité des données relatives à tous les John Smith de votre système.
* Un autre exemple concerne un ID d’appareil, tel que l’ID de cookie Analytics. Si l’ID apparaît sur une application de téléphone portable, vous pouvez décider que toutes les interactions utilisant cet ID doivent être disponibles pour le propriétaire du téléphone portable en question. Toutefois, s’il apparaît sur un appareil partagé, tel qu’un ordinateur domestique ou un ordinateur dans une bibliothèque ou un cybercafé, vous pouvez estimer que la distinction entre les différents utilisateurs de cet appareil n’est pas possible et que le risque de renvoyer des données relatives à un autre utilisateur est trop important pour permettre l’utilisation de ce type d’ID.

## Bonnes pratiques relatives aux ID pris en charge par Analytics {#best-practices-an}

Utilisez ce tableau pour déterminer les types d’ID que vous utiliserez lors de la soumission de demandes relatives à la Confidentialité des données à Analytics. Lorsque vous connaîtrez ces informations, vous pourrez déterminer plus facilement les autres étiquettes à utiliser pour vos variables.

<table id="table_E25612E32A03449A8E5DA00B88FCEB9E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type d’ID </th> 
   <th colname="col2" class="entry"> Recommandations </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID de cookie </p> 
    <ul id="ul_CB43CEA3054E490585CBF3AB46F95B5B"> 
     <li id="li_9174CB3910AF4EF8BA7165DB537765A5"> <a href="https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-privacy.html?lang=fr">Cookie Analytics (hérité)</a> </li> 
     <li id="li_7B6A9A788BBD47428315B3893FC07BC3"> <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr"> Cookie du service d’identités </a> (ECID), précédemment connu sous le nom de Marketing Cloud ID (MCID) </li> 
    </ul> </td> 
   <td colname="col2"> <p>Ces cookies identifient un appareil ou, plus spécifiquement, un navigateur pour un utilisateur d’un appareil. Pour un appareil partagé utilisant une connexion commune, cet ID peut être attribué à tous les utilisateurs de l’appareil. Adobe a créé du code <a href="https://developer.adobe.com/experience-platform-apis/references/privacy-service/">JavaScript unifié</a> que vous pouvez insérer dans votre site web pour collecter ces cookies si vous souhaitez autoriser leur utilisation pour les demandes relatives à la Confidentialité des données. </p> <p>Les utilisateurs du SDK Adobe Analytics Mobile disposent également d’un Experience Cloud ID (ECID). Des appels d’API destinés à lire cet ID sont présents dans le SDK. Ainsi, vous pouvez optimiser votre application pour le collecter en vue d’une demande relative à la Confidentialité des données. </p> <p>De nombreuses entreprises considèrent les ID de cookie du navigateur comme des ID d’appareils partagés. Par conséquent, en consultation avec leurs équipes juridiques, elles peuvent choisir de ne pas les utiliser comme ID acceptables pour les demandes d’accès à des informations personnelles. Elles peuvent également choisir de ne renvoyer qu’une quantité très limitée de données lorsque ces ID sont utilisés ou de ne les accepter que pour les demandes de suppression. </p> <p>Ces cookies ont une étiquette ID-DEVICE qui ne peut pas être modifiée (ainsi que des étiquettes I2 et DEL-DEVICE). La configuration par défaut d’Adobe Analytics renvoie uniquement les informations génériques relatives à l’appareil, telles que le type d’appareil, le système d’exploitation, le navigateur, etc. ainsi que l’heure et les dates auxquelles votre site web a été visité lors de l’utilisation de ces identifiants. Toutefois, si vous choisissez de prendre en charge ces ID pour les demandes relatives à la Confidentialité des données, comme indiqué ci-dessous, vous pouvez ajouter ou supprimer des étiquettes ACC-ALL pour configurer l’ensemble exact des champs que vous souhaitez inclure pour une demande d’accès relative à la Confidentialité des données. </p> <p>Si la suite de rapports correspond à une application mobile qui nécessite une connexion, vous pouvez décider que l’ID Experience Cloud de l’appareil ne correspond pas à un utilisateur ou une utilisatrice spécifique. Dans ce cas, vous pouvez étiqueter davantage de champs avec le libellé ACC-ALL, y compris les noms des pages visitées, les produits consultés, etc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID dans les variables personnalisées </p> </td> 
   <td colname="col2"> <p>Certains clients intègrent des ID dans <a href="/help/implement/vars/page-vars/evar.md">des variables de trafic personnalisées (props) ou des variables de conversion personnalisées (eVars)</a>. Si le plus courant est l’ID de gestion de la relation client, d’autres comprennent des adresses électroniques, des noms d’utilisateur de connexion, des numéros de fidélité des clients ou un hachage de ces valeurs. </p> 
    <ul id="ul_0B9492CF786046BB97E31CCF83A85FEA"> 
     <li id="li_D35B61CC6A8B485A8E09358A46D3F598">Si vous souhaitez utiliser l’un de ces ID pour les demandes relatives à la Confidentialité des données, vous devez attribuer au champ qui le contient une étiquette ID-PERSON. </li> 
     <li id="li_94541340B054436297C5565F074413DC">(Beaucoup moins fréquent) Si un ID dans l’une de ces variables personnalisées identifie uniquement un appareil pouvant être partagé par plusieurs personnes, alors vous pouvez utiliser une étiquette ID-DEVICE à la place. </li> 
     <li id="li_8115B999E8DA46CAB359BCF1F4A4DCAE">Ces champs requièrent également des étiquettes I1 ou I2 et doivent inclure une étiquette DEL-PERSON ou DEL-DEVICE. L’option PERSON/DEVICE de l’étiquette DEL correspondra généralement à l’option PERSON/DEVICE de l’étiquette d’identification. </li> 
    </ul> <p> Il est rare qu’une suite de rapports possède plus d’une ou deux variables personnalisées contenant des ID que vous souhaitez utiliser pour identifier les titulaires des données dans le cadre de demandes d’accès à des informations personnelles. Vous pouvez avoir plusieurs variables auxquelles sont attribuées des étiquettes I1 ou I2, mais généralement, seulement une ou deux d’entre elles auront aussi des étiquettes ID-PERSON ou ID-DEVICE. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identifiant visiteur personnalisé </p> </td> 
   <td colname="col2"> <p>Même si cette option n’est pas couramment utilisée, Analytics prend également en charge une mise en œuvre dans laquelle un identifiant visiteur personnalisé peut être fourni. Si celui-ci est présent, alors il est utilisé à la place du cookie de suivi hérité d’Analytics. Ce champ contient les étiquettes I2, ID-PERSON et DEL-PERSON. </p> <p>De nombreuses implémentations obtiennent cet ID d’un ID de CRM, il n’est donc présent que lorsqu’une personne est connectée au site correspondant. Cela permet d’utiliser le même identifiant visiteur personnalisé sur plusieurs appareils. L’inconvénient technique est que le suivi qui se fait avant que l’utilisateur se connecte ne peut pas être associé au suivi collecté après sa connexion. Si, à la place, vous utilisez l’identifiant visiteur personnalisé pour identifier simplement un appareil, vous devez changer les étiquettes ID-PERSON et DEL-PERSON en ID-DEVICE et DEL-DEVICE, respectivement. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Bonnes pratiques relatives à la définition de libellés de suppression {#best-practices-delete}

>[!NOTE]
>
>Les variables props ne respectent jamais la casse. Par défaut, les eVars ne respectent pas la casse, mais peuvent être configurées via l’assistance clientèle d’Adobe pour la respecter. Si vous avez une eVar sensible à la casse qui contient un ID, il est de votre responsabilité d’utiliser la casse appropriée lors de la soumission d’une demande relative à la Confidentialité des données afin que cette case corresponde à celle utilisée dans les accès contenant ces ID.

Les étiquettes de suppression DEL-DEVICE et DEL-PERSON doivent être utilisées modérément. Lorsqu’elles sont appliquées à une variable qui ne contient pas d’ID utilisé dans le cadre de la demande relative à la Confidentialité des données, les chiffres (mesures) des rapports antérieurs d’Analytics sont presque toujours modifiés.

* Nous recommandons que l’une de ces étiquettes soit appliquée à toute variable étiquetée I1, I2 ou S1. Elles ne peuvent pas être appliquées à une variable qui n’est pas étiquetée I1, I2 ou S1.
* Les étiquettes DEL- permettent d’[anonymiser](/help/admin/tools/privacy-labeling/labels.md#data-governance-labels) ces variables (l’ID sera remplacé par une chaîne aléatoire précédée de « Data Privacy »). La même valeur rendue anonyme remplacera toutes les instances de la valeur d’origine dans tous les accès identifiés par un ID utilisé dans la demande. Si la valeur d’origine dans ce champ était l’un de ces ID, alors les mesures du rapport ne changeraient pas.
* Généralement, si un champ possède l’étiquette ID-DEVICE, alors vous devez également attribuer l’étiquette DEL-DEVICE.
* De même, si un champ possède l’étiquette ID-PERSON, alors vous devez également attribuer l’étiquette DEL-PERSON.
* Si un champ ne possède pas d’étiquette d’identification, mais contient des informations d’identification que vous souhaitez rendre anonymes, alors l’étiquette appropriée (DEVICE ou PERSON) dépend de votre mise en œuvre. Si vous utilisez uniquement des ID de cookie pour les demandes relatives à la Confidentialité des données, alors vous devez utiliser DEL-DEVICE.
* Si vous utilisez des ID personnalisés dans un champ différent avec une étiquette ID-PERSON et que vous voulez que cette opération soit effacée uniquement sur les lignes où cet ID apparaît, alors utilisez l’étiquette DEL-PERSON.
* Notez que si une étiquette DEL-DEVICE ou DEL-PERSON est spécifiée pour une variable qui n’est pas également utilisée comme identifiant pour cette demande (y compris un ID étendu), les valeurs uniques de cette variable seront rendues anonymes uniquement pour les accès présentant un ID spécifié (ou étendu). Si d’autres accès contiennent la même valeur, celle-ci ne sera pas mise à jour dans les autres emplacements. Il peut en résulter la modification des chiffres (mesures).

  Ainsi, si vous avez trois accès contenant la valeur « foo » dans eVar7, mais que l’un d’entre eux contient également un identifiant dans une autre variable visée par une suppression, la valeur « foo » de cet accès sera alors modifiée en une valeur de type « Data Privacy-123456789 », tandis qu’il restera inchangé dans les deux autres accès. Un rapport mentionnant le nombre de valeurs uniques pour eVar7 indiquera désormais une valeur unique de plus que précédemment. Un rapport mentionnant les valeurs principales des eVars peut inclure « foo » avec seulement deux instances (au lieu de 3 précédemment) ; la nouvelle valeur apparaîtra également sous la forme d’une instance distincte.

## Bonnes pratiques pour définir les libellés d’accès {#best-practices-access}

Bien que très peu de champs comportent une des autres étiquettes, il arrive souvent que de nombreux champs disposent d’étiquettes ACC. Les étiquettes d’accès appropriées dépendront des ID que vous utilisez pour les demandes relatives à la Confidentialité des données.

<table id="table_A5B834CC08C641D99E2691A2361997E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Si vous utilisez... </th> 
   <th colname="col2" class="entry"> ... suivez ces Recommandations </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID d’appareil uniquement </p> </td> 
   <td colname="col2"> <p>Si les seuls ID que vous utilisez sont des ID de cookie ou ceux avec une étiquette ID-DEVICE, alors vous devez utiliser uniquement l’étiquette ACC-ALL. </p> <p>Vous obtiendrez une paire de fichiers pour chaque demande d’accès, l’un contenant une ligne pour chaque accès correspondant avec tous les champs ACC-ALL spécifiés et un second fichier récapitulatif contenant un résumé de ces données. </p> </td> 
  </tr> 
 </tbody> 
</table>
