---
description: Vous pouvez créer une suite de rapports en sélectionnant un modèle prédéfini ou en utilisant l’une de vos suites de rapports existantes pour servir de modèle.
title: Paramètres d’une nouvelle suite de rapports
topic: Admin tools
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Paramètres d’une nouvelle suite de rapports

Vous pouvez créer une suite de rapports en sélectionnant un modèle prédéfini ou en utilisant l’une de vos suites de rapports existantes pour servir de modèle.

Descriptions des éléments utilisés lors de la [création d’une suite de rapports](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md).

>[!NOTE] La [documentation sur les suites de rapports virtuelles](/help/components/vrs/c-workflow-vrs/vrs-create.md) indique comment créer des suites de rapports virtuelles.

<table id="table_F739FBD8DB8D409E916F12F61C5953D0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Identifiant de suite de rapports </span> </td> 
   <td colname="col2"> <p>Spécifie un identifiant unique qui ne peut contenir que des caractères alphanumériques. Cet ID ne peut plus être modifié après sa création. Adobe définit le préfixe d’ID requis et ne peut pas non plus le modifier. </p> <p>Lorsque vous créez plusieurs suites de rapports, assurez-vous que la convention d’affectation des noms utilisée garantit l’unicité des identifiants. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Titre du site</span> </td> 
   <td colname="col2">Identifie la suite de rapports dans les <span class="wintitle"> Outils d’administration</span>. Ce titre est également utilisé dans la liste déroulante <span class="wintitle"> Suite de rapports</span> dans l’en-tête de la suite. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Fuseau horaire</span> </td> 
   <td colname="col2"> Planifie des événements et applique un horodatage aux données. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> URL de base</span> </td> 
   <td colname="col2"> (Facultatif) Définit le domaine de base de la suite de rapports. Cette URL fonctionne comme un filtre d’URL interne si vous ne définissez pas explicitement les  d’URL internes pour la suite de rapports. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Page par défaut</span> </td> 
   <td colname="col2"> <p>(Facultatif) Cette option élimine les occurrences de la valeur <span class="wintitle"> Page par défaut</span> des URL qu’elle rencontre. Si votre rapport <span class="wintitle">Pages les plus populaires</span> contient des URL plutôt que des noms de page, ce paramètre empêche l’existence de plusieurs URL pour la même page web. </p> <p>Par exemple, les URL <span class="filepath">https://monsite.com</span> et <span class="filepath">https://monsite.com/index.html</span> représentent généralement la même page. Vous pouvez supprimer des noms de fichier superflus, de sorte que ces URL s’affichent sous la forme <span class="filepath">https://monsite.com</span> dans vos rapports. </p> <p>Si vous ne définissez pas cette valeur, Analytics supprime automatiquement les noms de fichier suivants des URL : <span class="filepath"> index.htm</span>, <span class="filepath"> index.html</span>, <span class="filepath"> index.cgi</span>, <span class="filepath"> index.asp</span>, <span class="filepath"> default.htm</span>, <span class="filepath"> default.html</span>, <span class="filepath"> default.cgi</span>, <span class="filepath"> default.asp</span>, <span class="filepath"> home.htm</span>, <span class="filepath"> home.html</span>, <span class="filepath"> home.cgi</span> et <span class="filepath"> home.asp</span>. </p> <p>Pour désactiver le dépouillement des noms de fichier, spécifiez une valeur Page par défaut qui ne se produira jamais dans vos URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Date Go Live </p> </td> 
   <td colname="col2">Informe Adobe de la date prévue pour l’activation de cette suite de rapports. Si votre calendrier de déploiement change, indiquez une estimation actualisée de votre trafic à l’aide de l’outil <span class="wintitle">Trafic prévisionnel permanent</span> sous <a href="/help/admin/c-traffic-management/traffic-management.md"> Gestion du trafic</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Estimation du nombre de pages vues par jour</span> </td> 
   <td colname="col2"> Identifie le nombre estimé de de pages  que cette suite de rapports devrait prendre en charge en une journée. Les volumes de trafic importants nécessitent un processus d’approbation plus long. Pour éviter les retards de traitement, soyez aussi précis que possible avec cette estimation. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Devise de base</span> </td> 
   <td colname="col2"> <p>Indique la devise par défaut utilisée pour stocker toutes les données monétaires. Le Analytics  convertit les transactions effectuées dans d’autres devises dans la devise de base, en utilisant le actuel au moment où il reçoit les données. </p> <p> La fonction de création de rapports d’Analytics utilise la variable JavaScript <span class="varname"> currencyCode</span> pour identifier la devise d’une transaction donnée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Désactiver la prise en charge de caractères complexes</span> </td> 
   <td colname="col2"> <p>Désactive la prise en charge des caractères complexes pour la suite de rapports. Si vous désactivez la prise en charge des caractères multioctets, le système suppose que les données sont au format ISO-8859-1. Les pages Web doivent spécifier leur jeu de caractères dans la Variable JavaScript <span class="varname">charSet</span>. </p> <p>La prise en charge des caractères complexes stocke les caractères dans la suite de rapports à l’aide du codage UTF-8. Dès réception, le système convertit les données du jeu de caractères de votre page Web en jeu de caractères UTF-8, de sorte que vous puissiez utiliser n’importe quelle langue dans vos rapports marketing. </p> <p>Contactez votre gestionnaire de compte ou le service à la clientèle pour modifier la prise en charge des caractères multioctets pour une suite de rapports existante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Activer l’Ad Hoc Analysis pour cette suite</span> </td> 
   <td colname="col2"> Permet de visualiser cette suite de rapports lorsque vous effectuez une Ad Hoc Analysis. </td> 
  </tr> 
 </tbody> 
</table>

