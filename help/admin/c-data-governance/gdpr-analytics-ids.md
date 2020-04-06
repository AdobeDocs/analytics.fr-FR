---
description: 'null'
title: Bonnes pratiques en matière d’étiquetage
uuid: d1e9bfff-9b04-4e3e-9b4e-a6e527b1b2e3
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Bonnes pratiques en matière d’étiquetage

>[!NOTE] Souvenez-vous que l’étiquetage doit être vérifié chaque fois qu’une nouvelle suite de rapports est créée ou qu’une nouvelle variable est activée dans une suite de rapports existante. Il peut également être nécessaire de vérifier l’étiquetage lors de l’activation de nouvelles intégrations à des solutions puisque celles-ci peuvent exposer de nouvelles variables nécessitant un étiquetage. Une réimplémentation de vos applications mobiles ou sites Web peut modifier la manière dont les variables existantes sont utilisées, ce qui peut également nécessiter des mises à jour des étiquettes.

## ID directement ou indirectement identifiables {#section_030799AA1397433FBA61A2BC60A7A750}

Avant de pouvoir déterminer quelles étiquettes doivent être appliquées à tel ou tel champ/variable, vous devez d’abord comprendre les ID que vous capturez dans vos données Analytics et définir ceux qui seront utilisés pour les demandes relatives à la Confidentialité des données. La Confidentialité des données donne une dimension plus large de ce qui peut être considéré comme un ID. Les identifiants appartiennent à deux grandes classes : directement identifiable (étiquette d&#39;identité: I1) et indirectement identifiable (étiquette d&#39;identité: I2).

* **Un ID directement identifiable (I1)** : nomme la personne ou fournit une méthode directe pour la contacter. Parmi les exemples on retrouve les noms (même un nom commun comme John Smith qui peut être celui de centaines de personnes), les numéros de téléphone ou adresses électroniques, etc. des individus. Une adresse postale sans nom peut être considérée comme directement identifiable, même si elle ne peut identifier qu&#39;un ménage ou une entreprise plutôt qu&#39;une personne particulière au sein de ce ménage ou de cette entreprise.
* **Un ID indirectement identifiable (I2)** : ne permet pas l’identification d’un individu en soi, mais peut être combiné avec d’autres informations (qui peuvent être ou non en votre possession), pour identifier une personne. Parmi les exemples on retrouve les numéros de fidélité des clients, ou les ID uniques à chaque client utilisés par le système de gestion de la relation client d’une entreprise. En vertu de la Confidentialité des données, les ID anonymes stockés dans les cookies de suivi utilisés par Analytics sont réputés pour être identifiables indirectement, même s’ils ne peuvent identifier qu’un appareil plutôt qu’un individu. Sur un appareil partagé, ces cookies ne peuvent pas distinguer les différents utilisateurs du système. Par exemple, si le cookie ne peut pas être utilisé pour trouver un ordinateur contenant le cookie, si un utilisateur a accès à l’ordinateur et localise le cookie, il peut alors lier les données du cookie Analytics à l’ordinateur.

   Une adresse IP est également considérée comme indirectement identifiable, car à tout moment, elle pourrait uniquement être attribuée à un seul appareil. Cependant, les FAI peuvent changer les adresses IP, ce qu’ils font d’ailleurs régulièrement pour la plupart de leurs abonnés, si bien que dans le temps, une même adresse IP peut avoir été utilisée par n’importe lequel de leurs utilisateurs. Il n’est pas rare non plus que de nombreux clients d’un FAI ou plusieurs employés d’une entreprise utilisant le même intranet partagent la même adresse IP externe. Pour cette raison, les adresses IP utilisées en tant qu’ID ne sont pas prises en charge par Adobe pour les [demandes relatives à la Confidentialité des données.](/help/admin/c-data-governance/gdpr-submit-access-delete.md#submit-requests) Cependant, lorsqu’un ID que nous acceptons est utilisé dans le cadre d’une demande de suppression, les adresses IP y étant associées seront également supprimées. Vous devez décider s’il existe d’autres ID collectés qui peuvent appartenir à cette catégorie (I1 ou I2), mais qui ne peuvent pas être utilisés comme ID distinctif pour les demandes relatives à la Confidentialité des données.

Même si votre entreprise collecte de nombreux ID différents dans vos données Analytics, vous pouvez choisir d’utiliser uniquement un sous-ensemble de ces ID pour les demandes relatives à la Confidentialité des données. Les raisons de cette situation peuvent être les suivantes :

* Au sein de vos propres systèmes, il se peut que vous mappiez l’un des ID (par exemple, l’adresse électronique) à un ID différent (tel que l’ID de gestion de la relation client) ; puis, par souci de cohérence, que vous décidiez d’utiliser uniquement l’ID de gestion de la relation client pour les demandes relatives à la Confidentialité des données lors de votre traitement en vertu de la Confidentialité des données.
* Vous n’avez pas de méthode pour confirmer si la personne est réellement celle associée à l’ID. Par exemple, il peut être très difficile de valider qu’une adresse IP n’a été utilisée que par une seule personne et que la personne qui a soumis la demande est en fait cette personne.
* Certains ID peuvent correspondre à plusieurs personnes et vous ne voulez pas risquer de renvoyer des informations relatives à une personne à quelqu’un d’autre possédant le même ID. Par exemple, même si vous pouvez vérifier que le nom d’une personne est John Smith, vous pouvez ne pas renvoyer toutes les données sur tous les John Smiths de votre système.
* Un autre exemple concerne un ID d’appareil, tel que l’ID de cookie Analytics. Si l’ID apparaît sur une application de téléphone portable, vous pouvez décider que toutes les interactions utilisant cet ID doivent être disponibles pour le propriétaire du téléphone portable en question. Cependant, si elle survient sur un périphérique partagé, tel qu’un ordinateur domestique ou dans une bibliothèque ou un cybercafé, vous pouvez décider que vous ne pouvez pas faire la distinction entre les utilisateurs de ce périphérique et que le risque de renvoyer des données pour un autre utilisateur est trop grand pour permettre l’utilisation de ce type d’ID.

## Bonnes pratiques pour les ID pris en charge par Analytics  {#section_B6481505FF1949498D4B4B35B780D050}

Utilisez ce tableau pour déterminer les types d’ID que vous utiliserez lors de la soumission de demandes relatives à la Confidentialité des données à Analytics. Une fois ces informations connues, il sera plus facile de déterminer les autres libellés à utiliser pour vos variables.

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
     <li id="li_9174CB3910AF4EF8BA7165DB537765A5"> <a href="https://marketing.adobe.com/resources/help/fr_FR/whitepapers/cookies/cookies_analytics.html">Cookie Analytics (hérité)</a> </li> 
     <li id="li_7B6A9A788BBD47428315B3893FC07BC3"> <a href="https://marketing.adobe.com/resources/help/fr_FR/mcvid/"> Cookie du service Identity </a> (ECID), précédemment connu sous le nom de Marketing Cloud ID (MCID) </li> 
    </ul> </td> 
   <td colname="col2"> <p>Ces cookies identifient un appareil ou, plus spécifiquement, un navigateur pour un utilisateur d’un appareil. Pour un appareil partagé utilisant une connexion commune, cet ID peut être attribué à tous les utilisateurs de l’appareil. Adobe a créé du code <a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm">JavaScript unifié</a> que vous pouvez insérer dans votre site web pour collecter ces cookies si vous souhaitez autoriser leur utilisation pour les demandes relatives à la Confidentialité des données. </p> <p>Les utilisateurs du SDK Adobe Analytics Mobile disposent également d’un Experience Cloud ID (ECID). Des appels d’API destinés à lire cet ID sont présents dans le SDK. Ainsi, vous pouvez optimiser votre application pour le collecter en vue d’une demande relative à la Confidentialité des données. </p> <p>De nombreuses entreprises considèrent les ID de cookie du navigateur comme des ID d’appareils partagés. Par conséquent, après consultation de leurs équipes juridiques, elles peuvent choisir de ne pas les utiliser comme ID acceptables pour les demandes relatives à la Confidentialité des données, de ne renvoyer qu’une quantité très limitée de données lorsque ces ID sont utilisés ou de ne les accepter que pour les demandes de suppression. </p> <p>Ces cookies ont une étiquette ID-DEVICE qui ne peut pas être modifiée (ainsi que des étiquettes I2 et DEL-DEVICE). La configuration par défaut d’Adobe Analytics renvoie uniquement les informations génériques relatives à l’appareil, telles que le type d’appareil, le système d’exploitation, le navigateur, etc. ainsi que l’heure et les dates auxquelles votre site web a été visité lors de l’utilisation de ces identifiants. Toutefois, si vous choisissez de prendre en charge ces ID pour les demandes relatives à la Confidentialité des données, comme indiqué ci-dessous, vous pouvez ajouter ou supprimer des étiquettes ACC-ALL pour configurer l’ensemble exact des champs que vous souhaitez inclure pour une demande d’accès relative à la Confidentialité des données. </p> <p>Vous pouvez décider que l’Experience Cloud ID de l’appareil correspond à un utilisateur spécifique et que vous allez donc vouloir étiqueter davantage de champs avec l’étiquette ACC-ALL, incluant les noms des pages visitées, les produits consultés, etc., en particulier si la suite de rapports correspond à une application mobile et que votre application mobile nécessite un identifiant. </p> <p>Remarque : si vous spécifiez l’option « expandIds » dans votre demande relative à la Confidentialité des données, vos demandes incluront toujours les ID de cookies en plus des autres ID spécifiés. Pour plus de détails, voir <a href="/help/admin/c-data-governance/gdpr-id-expansion.md">Extension d’ID</a>. Dans ces cas, les accès qui n’ont qu’un ID de cookie, mais pas un autre ID, ne renverront que les données étiquetées ACC-ALL dans le cadre de la demande d’accès. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID dans les variables personnalisées </p> </td> 
   <td colname="col2"> <p>Certains clients intègrent des ID dans <a href="https://marketing.adobe.com/resources/help/fr_FR/sc/implement/props_eVars.html">des variables de trafic personnalisées (props) ou des variables de conversion personnalisées (eVars)</a>. Si le plus courant est l’ID de gestion de la relation client, d’autres comprennent des adresses électroniques, des noms d’utilisateur de connexion, des numéros de fidélité des clients ou un hachage de ces valeurs. </p> 
    <ul id="ul_0B9492CF786046BB97E31CCF83A85FEA"> 
     <li id="li_D35B61CC6A8B485A8E09358A46D3F598">Si vous souhaitez utiliser l’un de ces ID pour les demandes relatives à la Confidentialité des données, vous devez attribuer au champ qui le contient une étiquette ID-PERSON. </li> 
     <li id="li_94541340B054436297C5565F074413DC">(Beaucoup moins fréquent) Si un ID dans l’une de ces variables personnalisées identifie uniquement un appareil pouvant être partagé par plusieurs personnes, alors vous pouvez utiliser une étiquette ID-DEVICE à la place. </li> 
     <li id="li_8115B999E8DA46CAB359BCF1F4A4DCAE">Ces champs nécessitent également des étiquettes I1 ou I2 et doivent inclure une étiquette DEL-PERSON ou DEL-DEVICE. En règle générale, l’option PERSONNE/PÉRIPHÉRIQUE du libellé DEL correspond à l’option PERSONNE/PÉRIPHÉRIQUE du libellé de l’ID. </li> 
    </ul> <p> Il est rare qu’une suite de rapports possède plus d’une ou deux variables personnalisées contenant des ID que vous souhaitez utiliser pour identifier les sujets des données dans le cadre de demandes relatives à la Confidentialité des données. Plusieurs variables peuvent se voir attribuer des libellés I1 ou I2, mais en règle générale, seulement une ou deux d’entre elles portent également des libellés ID-PERSON ou ID-DEVICE. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identifiant visiteur personnalisé </p> </td> 
   <td colname="col2"> <p>Même si cette option n’est pas couramment utilisée, Analytics prend également en charge une mise en œuvre dans laquelle un identifiant visiteur personnalisé peut être fourni. Si celui-ci est présent, alors il est utilisé à la place du cookie de suivi hérité d’Analytics. Ce champ porte les libellés I2, ID-PERSON et DEL-PERSON. </p> <p>De nombreuses mises en œuvre obtiennent cet ID d’un ID de gestion de la relation client, donc il n’est présent que lorsqu’une personne est connectée au site correspondant. Cela permet d’utiliser le même identifiant visiteur personnalisé sur plusieurs appareils. L’inconvénient technique est que le suivi qui se fait avant que l’utilisateur se connecte ne peut pas être associé au suivi collecté après sa connexion. Si, à la place, vous utilisez l’ID de personnalisé pour identifier simplement un périphérique, vous devez remplacer les libellés ID-PERSON et DEL-PERSON par ID-DEVICE et DEL-DEVICE, respectivement. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Bonnes pratiques pour définir les étiquettes de suppression {#section_08166C99B48E49218392FAC18922C10E}

>[!NOTE] Les variables props sont toujours insensibles à la casse. Par défaut, les eVars sont insensibles à la casse, mais peuvent être configurées via l’assistance clientèle d’Adobe pour le devenir. Si vous avez une eVar sensible à la casse qui contient un ID, il est de votre responsabilité d’utiliser la casse appropriée lors de la soumission d’une demande relative à la Confidentialité des données afin que cette case corresponde à celle utilisée dans les accès contenant ces ID.

Les étiquettes de suppression DEL-DEVICE et DEL-PERSON doivent être utilisées modérément. Lorsqu’elles sont appliquées à une variable qui ne contient pas d’ID utilisé dans le cadre de la demande relative à la Confidentialité des données, les chiffres (mesures) des rapports antérieurs d’Analytics sont presque toujours modifiés.

* Nous recommandons que l’une de ces étiquettes soit appliquée à toute variable étiquetée I1, I2 ou S1. Elles ne peuvent pas être appliquées à une variable qui n’est pas étiquetée I1, I2 ou S1.
* Les étiquettes DEL- permettent d’[anonymiser](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels) ces variables (l’ID sera remplacé par une chaîne aléatoire accompagnée du terme « Data Privacy »). La même valeur rendue anonyme remplacera toutes les instances de la valeur d’origine dans tous les accès identifiés par un ID utilisé dans la demande. Si la valeur d’origine dans ce champ était l’un de ces identifiants, les mesures des rapports ne changent pas.
* En règle générale, si un champ a l’étiquette ID-APPAREIL, vous devez également attribuer l’étiquette DEL-APPAREIL.
* De même, si un champ a l’étiquette ID-PERSON, vous devez également attribuer l’étiquette DEL-PERSON.
* Si un champ ne possède pas d’étiquette d’identification, mais contient des informations d’identification que vous souhaitez rendre anonymes, alors l’étiquette appropriée (DEVICE ou PERSON) dépend de votre mise en œuvre. Si vous utilisez uniquement des ID de cookie pour les demandes relatives à la Confidentialité des données, alors vous devez utiliser DEL-DEVICE.
* Si vous utilisez des identifiants personnalisés sur un champ différent avec une étiquette ID-PERSONNE et que vous souhaitez que cette information soit effacée sur les lignes où cet identifiant se produit, utilisez DEL-PERSON.
* Si vous utilisez une extension d’ID et souhaitez que toutes les valeurs soient effacées pour tous les accès sur tous les appareils identifiés, alors utilisez l’étiquette DEL-DEVICE. Dans ce cas, vous pouvez appliquer les libellés DEL-DEVICE et DEL-PERSON, mais le libellé DEL-PERSON n’est pas nécessaire, car l’extension d’ID signifie que toutes les lignes qui correspondent à un ID de personne correspondront également à un ID de périphérique.
* Si vous n’indiquez pas d’utiliser l’extension d’ID, mais que vous utiliserez un mélange d’ID de périphérique et de personne pour différentes requêtes, vous souhaiterez peut-être spécifier les libellés DEL-DEVICE et DEL-PERSON pour les variables qui doivent être supprimées lorsque l’un ou l’autre type d’ID est utilisé.
* Notez que si une étiquette DEL-DEVICE ou DEL-PERSON est spécifiée sur une variable qui n’est pas également utilisée comme ID pour cette requête (y compris un ID étendu), les valeurs uniques de cette variable ne seront anonymisées que sur les accès où survient un ID spécifié (ou étendu). Si d’autres accès contiennent la même valeur, ils ne seront pas mis à jour à ces autres emplacements. Cela peut entraîner une modification du nombre (mesures).

   Ainsi, si vous avez trois accès contenant la valeur « foo » dans eVar7, mais que l’un d’entre eux contient également un identifiant dans une autre variable visée par une suppression, la valeur « foo » de cet accès sera alors modifiée en une valeur de type « Data Privacy-123456789 », tandis qu’il restera inchangé dans les deux autres accès. Un rapport mentionnant le nombre de valeurs uniques pour eVar7 indiquera désormais une valeur unique de plus que précédemment. Un rapport mentionnant les valeurs principales des eVars peut inclure « foo » avec seulement deux instances (au lieu de 3 précédemment) ; la nouvelle valeur apparaîtra également sous la forme d’une instance distincte.

## Bonnes pratiques pour définir les étiquettes d’accès  {#section_AC7E216F81C141FCA6A62F8836E06EE7}

Bien que très peu de champs comportent une des autres étiquettes, il arrive souvent que de nombreux champs disposent d’étiquettes ACC. Les étiquettes d’accès appropriées dépendront des ID que vous utilisez pour les demandes relatives à la Confidentialité des données.

<table id="table_A5B834CC08C641D99E2691A2361997E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Si vous utilisez... </th> 
   <th colname="col2" class="entry"> ...utiliser ces recommandations </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID de périphérique uniquement </p> </td> 
   <td colname="col2"> <p>Si les seuls identifiants que vous utilisez sont les identifiants de cookie ou ceux qui possèdent une étiquette ID-PÉRIPHÉRIQUE, vous ne devez utiliser que l’étiquette ACC-ALL. </p> <p>Vous obtiendrez une paire de fichiers pour chaque demande d’accès, une ligne pour chaque accès correspondant avec tous les champs ACC-ALL spécifiés et une seconde contenant un résumé de ces données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de personne sans extension d’ID </p> </td> 
   <td colname="col2"> <p>Si vous utilisez uniquement des ID personnalisés, comportant l’étiquette ID-PERSON, qui ne procèdent pas à une extension d’ID, alors vous devez utiliser les étiquettes ACC-PERSON. Toutefois, vous n’avez pas besoin de modifier les étiquettes ACC-ALL par défaut ; ces champs seront automatiquement inclus dans la demande d’accès. </p> <p>Vous obtiendrez une paire de fichiers pour chaque demande d’accès, une ligne pour chaque accès correspondant avec tous les champs ACC-DEVICE et ACC-PERSON spécifiés et une seconde contenant un résumé de ces données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID mixtes et/ou extension d’ID </p> </td> 
   <td colname="col2"> <p>Si vous incluez les ID d’appareil et de personne dans les demandes relatives à la Confidentialité des données, ou si vous utilisez des ID personnalisés (identifiant visiteur personnalisé ou ID dans une prop ou une eVar), alors vous devez faire attention aux étiquettes ACC que vous utilisez. Chaque demande d’accès renvoie deux paires de fichiers de données, une paire contenant des données issues d’accès avec un ID de personne correspondant et une seconde contenant des données issues d’accès qui ne correspondent pas à un ID de personne, mais à un ID d’appareil. </p> <p>Les fichiers "ID de personne" contiennent des données sur tous les accès qui correspondent aux identifiants de personne avec tous les champs qui possèdent une étiquette ACC-PERSON ou ACC-ALL (un fichier avec tous les accès correspondants et l’autre en résumé). </p> <p>Les fichiers « ID d’appareil » contiennent uniquement les champs ayant une étiquette ACC-ALL et ne contiennent également que des accès qui ne comportent aucun ID de personne correspondant. Ces fichiers peuvent contenir des données générées par d’autres utilisateurs d’un appareil partagé. Ainsi, vous allez vouloir examiner attentivement l’ensemble des champs qui contiennent l’étiquette ACC-ALL. L’étiquette par défaut dans Analytics s’applique uniquement aux champs d’informations génériques relatifs au périphérique (type de périphérique, système d’exploitation, navigateur, etc.). plus la date et l’heure de chaque accès. </p> <p>Vous pouvez choisir de recevoir d’Adobe les deux ensembles de fichiers de personne et d’appareil, puis de partager uniquement les fichiers de personne, afin de ne pas partager les données potentiellement générées par d’autres utilisateurs d’un appareil partagé. Vous pouvez aussi combiner des données provenant d'un ensemble ou des deux ensembles avec d'autres informations que vous connaissez sur la personne concernée et les renvoyer dans votre propre format. </p> </td> 
  </tr> 
 </tbody> 
</table>

