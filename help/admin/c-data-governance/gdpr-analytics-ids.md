---
description: valeur nulle
seo-description: valeur nulle
seo-title: Bonnes pratiques en matière d’étiquetage
title: Bonnes pratiques en matière d’étiquetage
uuid: d1e9bfff-9b04-4e3e-9b4e-a6e527b1b2e3
translation-type: tm+mt
source-git-commit: 2e78524a1ec88ace687ef293332bbee532388c7a

---


# Bonnes pratiques en matière d’étiquetage

>[!NOTE]
>
>Souvenez-vous que l’étiquetage doit être vérifié chaque fois qu’une nouvelle suite de rapports est créée ou qu’une nouvelle variable est activée dans une suite de rapports existante. Il peut également être nécessaire de vérifier l’étiquetage lors de l’activation de nouvelles intégrations à des solutions puisque celles-ci peuvent exposer de nouvelles variables nécessitant un étiquetage. Une nouvelle implémentation de vos applications mobiles ou sites web peut modifier la manière dont les variables existantes sont utilisées, rendant nécessaire la mise à jour des étiquettes.

## ID directement ou indirectement identifiables {#section_030799AA1397433FBA61A2BC60A7A750}

Avant de déterminer les libellés à appliquer aux variables/champs, vous devez d’abord comprendre les identifiants que vous capturez dans vos données Analytics et déterminer ceux que vous utiliserez pour les demandes de confidentialité des données. La confidentialité des données étend la portée de ce qui peut être considéré comme un identifiant. Les ID se divisent en deux grandes catégories : directement identifiables (étiquette d’identité : I1) et indirectement identifiables (étiquette d’identité : I2).

* **Un ID directement identifiable (I1)** : nomme la personne ou fournit une méthode directe pour la contacter. Parmi les exemples on retrouve les noms (même un nom commun comme John Smith qui peut être celui de centaines de personnes), les numéros de téléphone ou adresses électroniques, etc. des individus. Une adresse postale sans nom peut être considérée comme directement identifiable, même si elle ne peut identifier qu’un ménage ou une entreprise plutôt qu’une personne spécifique au sein de ce ménage ou de cette entreprise.
* **Un ID indirectement identifiable (I2)** : ne permet pas l’identification d’un individu en soi, mais peut être combiné avec d’autres informations (qui peuvent être ou non en votre possession), pour identifier une personne. Parmi les exemples on retrouve les numéros de fidélité des clients, ou les ID uniques à chaque client utilisés par le système de gestion de la relation client d’une entreprise. Dans la section Confidentialité des données, les identifiants anonymes stockés dans les cookies de suivi utilisés par Analytics peuvent être considérés comme une identification indirecte, même s’ils peuvent uniquement identifier un périphérique plutôt qu’un individu ; sur un périphérique partagé, ces cookies ne peuvent pas faire la distinction entre les différents utilisateurs du système. Par exemple, bien que le cookie ne puisse pas être utilisé pour trouver un ordinateur contenant le cookie, si quelqu’un accède à l’ordinateur et localise le cookie, il peut alors ré-associer les données du cookie Analytics à l’ordinateur.

   Une adresse IP est également considérée comme indirectement identifiable, car à tout moment, elle pourrait uniquement être attribuée à un seul appareil. Cependant, les FAI peuvent changer les adresses IP, ce qu’ils font d’ailleurs régulièrement pour la plupart de leurs abonnés, si bien que dans le temps, une même adresse IP peut avoir été utilisée par n’importe lequel de leurs utilisateurs. Il n’est pas rare non plus que de nombreux clients d’un FAI ou plusieurs employés d’une entreprise utilisant le même intranet partagent la même adresse IP externe. Because of this, Adobe will not support using an IP address as the ID for a [Data Privacy request.](../../admin/c-data-governance/gdpr-submit-access-delete.md#submit-requests) Cependant, lorsqu’un ID que nous acceptons est utilisé dans le cadre d’une demande de suppression, les adresses IP y étant associées seront également supprimées. Vous devez décider s’il existe d’autres ID que vous collectez qui peuvent appartenir à cette catégorie, I1 ou I2, mais qui ne peuvent pas être utilisés comme identifiant distinctif pour les demandes de confidentialité des données.

Même si votre entreprise collecte de nombreux identifiants différents dans vos données Analytics, vous pouvez choisir d’utiliser uniquement un sous-ensemble de ces identifiants pour les demandes de confidentialité des données. Les raisons de ce choix pourraient être les suivantes :

* Au sein de vos propres systèmes, il se peut que vous mappiez l’un des ID (par exemple, l’adresse électronique) à un ID différent (tel que l’ID de gestion de la relation client) ; Ensuite, pour des raisons de cohérence, vous décidez de n’utiliser que l’ID CRM pour les demandes de confidentialité des données dans votre traitement de confidentialité des données.
* Vous n’avez pas de méthode pour confirmer si la personne est réellement celle associée à l’ID. Par exemple, cela peut être très difficile de confirmer si une adresse IP n’a été utilisée que par une seule personne et si la personne qui soumet la demande est réellement cette personne.
* Certains ID peuvent correspondre à plusieurs personnes et vous ne voulez pas risquer de renvoyer des informations relatives à une personne à quelqu’un d’autre possédant le même ID. Par exemple, même si vous pouvez vérifier que le nom de la personne est John Smith, vous ne voulez peut-être pas renvoyer l’intégralité des données relatives à tous les John Smith de votre système.
* Un autre exemple concerne un ID d’appareil, tel que l’ID de cookie Analytics. Si l’ID apparaît sur une application de téléphone portable, vous pouvez décider que toutes les interactions utilisant cet ID doivent être disponibles pour le propriétaire du téléphone portable en question. Toutefois, s’il apparaît sur un appareil partagé, tel qu’un ordinateur domestique ou un ordinateur dans une bibliothèque ou un cybercafé, vous pouvez estimer que la distinction entre les différents utilisateurs de cet appareil n’est pas possible et que le risque de renvoyer des données relatives à un autre utilisateur est trop important pour permettre l’utilisation de ce type d’ID.

## Bonnes pratiques pour les ID pris en charge par Analytics {#section_B6481505FF1949498D4B4B35B780D050}

Utilisez ce tableau pour déterminer les types d’ID que vous utiliserez lors de l’envoi de demandes de confidentialité des données à Analytics. Lorsque vous connaîtrez ces informations, vous pourrez déterminer plus facilement les autres étiquettes à utiliser pour vos variables.

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
     <li id="li_9174CB3910AF4EF8BA7165DB537765A5"> <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_analytics.html" format="html" scope="external">Cookie Analytics (hérité)</a> </li> 
     <li id="li_7B6A9A788BBD47428315B3893FC07BC3"> <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Cookie du service Identity </a> (ECID), précédemment connu sous le nom de Marketing Cloud ID (MCID) </li> 
    </ul> </td> 
   <td colname="col2"> <p>Ces cookies identifient un appareil ou, plus spécifiquement, un navigateur pour un utilisateur d’un appareil. Pour un appareil partagé utilisant une connexion commune, cet ID peut être attribué à tous les utilisateurs de l’appareil. Adobe has created some <a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm" format="html" scope="external"> unified JavaScript </a> that you can place on your website to collect these cookies if you want to allow them to be used for Data Privacy requests. </p> <p>Les utilisateurs du SDK Adobe Analytics Mobile disposent également d’un Experience Cloud ID (ECID). Il existe des appels d’API dans le SDK pour lire cet ID. Vous pouvez donc améliorer votre application pour la collecter dans le cadre d’une demande de confidentialité des données. </p> <p>De nombreuses entreprises considèrent les ID de cookie du navigateur comme des ID d’appareils partagés. Par conséquent, en consultation avec leurs équipes juridiques, ils peuvent choisir de ne pas les prendre en charge en tant qu’ID acceptables pour les demandes de confidentialité des données, ou choisir de ne renvoyer qu’une quantité très limitée de données lorsque ces ID sont utilisés ou de ne les accepter que pour les demandes de suppression. </p> <p>Ces cookies ont une étiquette ID-DEVICE qui ne peut pas être modifiée (ainsi que des étiquettes I2 et DEL-DEVICE). La configuration par défaut d’Adobe Analytics renvoie uniquement les informations génériques relatives à l’appareil, telles que le type d’appareil, le système d’exploitation, le navigateur, etc. ainsi que l’heure et les dates auxquelles votre site web a été visité lors de l’utilisation de ces identifiants. Cependant, si vous choisissez de prendre en charge ces ID pour les demandes de confidentialité des données, comme expliqué ci-dessous, vous pouvez ajouter ou supprimer des étiquettes ACC-ALL pour configurer l’ensemble exact de champs que vous souhaitez voir renvoyer pour une demande d’accès à la confidentialité des données. </p> <p>Vous pouvez décider que l’Experience Cloud ID de l’appareil correspond à un utilisateur spécifique et que vous allez donc vouloir étiqueter davantage de champs avec l’étiquette ACC-ALL, incluant les noms des pages visitées, les produits consultés, etc., en particulier si la suite de rapports correspond à une application mobile et que votre application mobile nécessite un identifiant. </p> <p>Remarque :  Si vous spécifiez l’option "expandedIds" dans votre requête de confidentialité des données, vos requêtes incluront toujours des ID de cookie, en plus des autres ID que vous spécifiez. Pour plus de détails, voir <a href="../../admin/c-data-governance/gdpr-id-expansion.md" format="dita" scope="local">Extension d’ID</a>. Dans ces instances, les accès qui ont uniquement un ID de cookie (et aucun autre ID), renverront uniquement les données étiquetées ACC-ALL pour la demande d’accès. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID dans les variables personnalisées </p> </td> 
   <td colname="col2"> <p>Certains clients intègrent des ID dans <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/props_eVars.html" format="html" scope="external">des variables de trafic personnalisées (props) ou des variables de conversion personnalisées (eVars) </a>. Si le plus courant est l’ID de gestion de la relation client, d’autres comprennent des adresses électroniques, des noms d’utilisateur de connexion, des numéros de fidélité des clients ou un hachage de ces valeurs. </p> 
    <ul id="ul_0B9492CF786046BB97E31CCF83A85FEA"> 
     <li id="li_D35B61CC6A8B485A8E09358A46D3F598">Si vous souhaitez utiliser l’un de ces identifiants pour les demandes de confidentialité des données, vous devez attribuer au champ qui le contient une étiquette ID-PERSON. </li> 
     <li id="li_94541340B054436297C5565F074413DC">(Beaucoup moins fréquent) Si un ID dans l’une de ces variables personnalisées identifie uniquement un appareil pouvant être partagé par plusieurs personnes, alors vous pouvez utiliser une étiquette ID-DEVICE à la place. </li> 
     <li id="li_8115B999E8DA46CAB359BCF1F4A4DCAE">Ces champs requièrent également des étiquettes I1 ou I2 et doivent inclure une étiquette DEL-PERSON ou DEL-DEVICE. L’option PERSON/DEVICE de l’étiquette DEL correspondra généralement à l’option PERSON/DEVICE de l’étiquette d’identification. </li> 
    </ul> <p> Il est rare qu’une suite de rapports contienne plusieurs variables personnalisées contenant des identifiants que vous souhaiteriez utiliser pour identifier les personnes concernées par les demandes de confidentialité des données. Vous pouvez avoir plusieurs variables auxquelles sont attribuées des étiquettes I1 ou I2, mais généralement, seulement une ou deux d’entre elles auront aussi des étiquettes ID-PERSON ou ID-DEVICE. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identifiant visiteur personnalisé </p> </td> 
   <td colname="col2"> <p>Même si cette option n’est pas couramment utilisée, Analytics prend également en charge une mise en œuvre dans laquelle un identifiant visiteur personnalisé peut être fourni. Si celui-ci est présent, alors il est utilisé à la place du cookie de suivi hérité d’Analytics. Ce champ contient les étiquettes I2, ID-PERSON et DEL-PERSON. </p> <p>De nombreuses mises en œuvre obtiennent cet ID d’un ID de gestion de la relation client, donc il n’est présent que lorsqu’une personne est connectée au site correspondant. Cela permet d’utiliser le même identifiant visiteur personnalisé sur plusieurs appareils. L’inconvénient technique est que le suivi qui se fait avant que l’utilisateur se connecte ne peut pas être associé au suivi collecté après sa connexion. Si, à la place, vous utilisez l’identifiant visiteur personnalisé pour identifier simplement un appareil, vous devez changer les étiquettes ID-PERSON et DEL-PERSON en ID-DEVICE et DEL-DEVICE, respectivement. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Bonnes pratiques pour définir les étiquettes de suppression {#section_08166C99B48E49218392FAC18922C10E}

>[!NOTE]
>
>Les variables props sont toujours insensibles à la casse. Par défaut, les eVars sont insensibles à la casse, mais peuvent être configurées via l’assistance clientèle d’Adobe pour le devenir. Si vous disposez d’une eVar sensible à la casse qui contient un identifiant, il vous incombe d’utiliser la casse appropriée lors de l’envoi d’une demande de confidentialité des données afin que la casse utilisée dans la demande corresponde à celle utilisée dans les accès contenant ces identifiants.

Les étiquettes de suppression DEL-DEVICE et DEL-PERSON doivent être utilisées modérément. Lorsqu’elle est appliquée à une variable qui ne contient pas d’ID utilisé dans le cadre de la demande de confidentialité des données, les décomptes (mesures) dans les rapports Analytics historiques changent presque toujours.

* Nous recommandons que l’une de ces étiquettes soit appliquée à toute variable étiquetée I1, I2 ou S1. Elles ne peuvent pas être appliquées à une variable qui n’est pas étiquetée I1, I2 ou S1.
* The DEL-labels will result in these variables being [anonymized](../../admin/c-data-governance/gdpr-labels.md#section_F3DEE591671A4B16A8E043F91C137ECB) (the ID will be replaced with a random string prefixed with "Data Privacy-"). La même valeur rendue anonyme remplacera toutes les instances de la valeur d’origine dans tous les accès identifiés par un ID utilisé dans la demande. Si la valeur d’origine dans ce champ était l’un de ces ID, alors les mesures du rapport ne changeraient pas.
* Généralement, si un champ possède l’étiquette ID-DEVICE, alors vous devez également attribuer l’étiquette DEL-DEVICE.
* De même, si un champ possède l’étiquette ID-PERSON, alors vous devez également attribuer l’étiquette DEL-PERSON.
* Si un champ ne possède pas d’étiquette d’identification, mais contient des informations d’identification que vous souhaitez rendre anonymes, alors l’étiquette appropriée (DEVICE ou PERSON) dépend de votre mise en œuvre. Si vous utilisez uniquement des ID de cookie pour les demandes de confidentialité des données, vous devez utiliser DEL-DEVICE.
* Si vous utilisez des ID personnalisés dans un champ différent avec une étiquette ID-PERSON et que vous voulez que cette opération soit effacée uniquement sur les lignes où cet ID apparaît, alors utilisez l’étiquette DEL-PERSON.
* Si vous utilisez une extension d’ID et souhaitez que toutes les valeurs soient effacées pour tous les accès sur tous les appareils identifiés, alors utilisez l’étiquette DEL-DEVICE. Dans ce cas, si vous préférez, vous pouvez appliquer les étiquettes DEL-DEVICE et DEL-PERSON. L’étiquette DEL-PERSON n’est toutefois pas nécessaire, car l’extension d’ID implique que toutes les lignes correspondant à un ID de personne correspondront également à un ID d’appareil.
* Si vous ne voulez pas spécifier l’utilisation de l’extension d’ID, mais que vous utiliserez à la fois des identifiants d’appareil et de personne pour différentes demandes, vous pouvez alors spécifier les étiquettes DEL-DEVICE et DEL-PERSON pour les variables qui doivent être supprimées lors de l’utilisation de l’un des types d’ID.
* Notez que si une étiquette DEL-DEVICE ou DEL-PERSON est spécifiée pour une variable qui n’est pas également utilisée comme identifiant pour cette demande (y compris un ID étendu), les valeurs uniques de cette variable seront rendues anonymes uniquement pour les accès présentant un ID spécifié (ou étendu). Si d’autres accès contiennent la même valeur, celle-ci ne sera pas mise à jour dans les autres emplacements. Il peut en résulter la modification des chiffres (mesures).

   Par exemple, si trois accès contiennent la valeur "foo" dans eVar7, mais qu’un seul d’entre eux contient également un identifiant dans une variable différente qui correspond à une suppression, "foo" sur cet accès sera modifié en une valeur du type "Data Privacy-123456789", alors qu’il restera inchangé dans les deux autres accès. Un rapport mentionnant le nombre de valeurs uniques pour eVar7 indiquera désormais une valeur unique de plus que précédemment. Un rapport mentionnant les valeurs principales des eVars peut inclure « foo » avec seulement deux instances (au lieu de 3 précédemment) ; la nouvelle valeur apparaîtra également sous la forme d’une instance distincte.

## Bonnes pratiques pour définir les étiquettes d’accès {#section_AC7E216F81C141FCA6A62F8836E06EE7}

Bien que très peu de champs comportent une des autres étiquettes, il arrive souvent que de nombreux champs disposent d’étiquettes ACC. Les étiquettes d’accès appropriées dépendent des ID que vous utilisez pour les demandes de confidentialité des données.

<table id="table_A5B834CC08C641D99E2691A2361997E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Si vous utilisez... </th> 
   <th colname="col2" class="entry"> ... suivez ces Recommendations </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID d’appareil uniquement </p> </td> 
   <td colname="col2"> <p>Si les seuls ID que vous utilisez sont des ID de cookie ou ceux avec une étiquette ID-DEVICE, alors vous devez utiliser uniquement l’étiquette ACC-ALL. </p> <p>Vous obtiendrez deux fichiers pour chaque demande d’accès, l’un contenant une ligne pour chaque accès correspondant avec tous les champs ACC-ALL spécifiés et un second contenant un résumé de ces données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de personne sans extension d’ID </p> </td> 
   <td colname="col2"> <p>Si vous utilisez uniquement des ID personnalisés, comportant l’étiquette ID-PERSON, qui ne procèdent pas à une extension d’ID, alors vous devez utiliser les étiquettes ACC-PERSON. Cependant, vous n’avez pas besoin de modifier les étiquettes ACC-ALL par défaut. Ces champs seront automatiquement inclus dans la demande d’accès. </p> <p>Vous obtiendrez deux fichiers pour chaque demande d’accès, l’un contenant une ligne pour chaque accès correspondant avec tous les champs ACC-DEVICE et ACC-PERSON spécifiés et un second contenant un résumé de ces données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID mixtes et/ou extension d’ID </p> </td> 
   <td colname="col2"> <p>Si vous incluez des ID de périphérique et de personne dans les demandes de confidentialité des données ou si vous utilisez des ID personnalisés (ID de visiteur personnalisé ou ID dans une prop ou une eVar), vous devez prêter attention aux libellés ACC que vous utilisez. Chaque demande d’accès renvoie deux paires de fichiers de données, une paire contenant des données issues d’accès avec un ID de personne correspondant et une seconde contenant des données issues d’accès qui ne correspondent pas à un ID de personne, mais à un ID d’appareil. </p> <p>Les fichiers « ID de personne » contiennent des données sur tous les accès qui correspondent aux ID de personne dont tous les champs possèdent une étiquette ACC-PERSON ou ACC-ALL (un fichier avec tous les accès correspondants et un autre servant de résumé). </p> <p>Les fichiers « ID d’appareil » contiennent uniquement les champs ayant une étiquette ACC-ALL et ne contiennent également que des accès qui ne comportent aucun ID de personne correspondant. Ces fichiers peuvent contenir des données générées par d’autres utilisateurs d’un appareil partagé. Ainsi, vous allez vouloir examiner attentivement l’ensemble des champs qui contiennent l’étiquette ACC-ALL. L’étiquetage par défaut dans Analytics n’applique cette étiquette qu’aux champs d‘informations génériques liés à l’appareil (type d’appareil, système d’exploitation, navigateur, etc.) ainsi que l’heure et les dates de chaque accès. </p> <p>Vous pouvez choisir de recevoir d’Adobe les deux ensembles de fichiers de personne et d’appareil, puis de partager uniquement les fichiers de personne, afin de ne pas partager les données potentiellement générées par d’autres utilisateurs d’un appareil partagé. Vous pouvez également combiner les données de l’un ou des deux ensembles avec d’autres informations que vous connaissez sur le sujet des données et les renvoyer dans votre propre format. </p> </td> 
  </tr> 
 </tbody> 
</table>

