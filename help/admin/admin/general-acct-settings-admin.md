---
description: Description des champs Paramètres du compte général d’une suite de rapports dans Admin.
seo-description: Description des champs Paramètres du compte général d’une suite de rapports dans Admin.
seo-title: Paramètres du compte général
solution: Analytics
title: Paramètres du compte général
topic: Outils d’administration
uuid: c 1 ab 5 c 34-2 c 41-4 d 12-a 706-0 e 760 dff 8 a 95
translation-type: tm+mt
source-git-commit: 0cecb6f66046b7db8471ce125237d74fdfc9323b

---


# Paramètres du compte général

Description des champs Paramètres du compte général d’une suite de rapports dans Admin.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Modifier les paramètres]** &gt; **[!UICONTROL Général]** &gt; **[!UICONTROL Paramètres du compte général]**

Ces paramètres contiennent des options d’édition pour les fonctionnalités de base des suites de rapports, ainsi que le nom et le fuseau horaire.

<table id="table_5448A694DC0A48D2B20C7F1332509F6E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Titre du site</span> </td> 
   <td colname="col2"> <p>Identifie votre site. Attribuez un nom de site unique à chaque suite de rapports. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> URL de base</span> </td> 
   <td colname="col2"> <p>Indique le site web principal de la suite de rapports. L’URL de base n’affecte pas le filtrage par référent. Utilisez plutôt des <a href="../../admin/admin/internal-url-filter-admin.md#concept_D6BB8358DB7643F0B13E5DC9B7607998" format="dita" scope="local"> filtres URL internes</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Fuseau horaire</span> </td> 
   <td colname="col2"> <p>Détermine l’heure et la date associées aux données du rapport. </p> <p>Le changement du fuseau horaire d’une suite de rapports active crée un pic ou un creux dans les données du rapport. Adobe conseille de changer de fuseau horaire pendant les heures creuses pour éviter de biaiser les données. </p> <p>Par exemple, si vous changez le fuseau horaire de Moscou sur celui de Paris à 15h00, l’heure de la suite de rapports passe à 13h00. Étant donné que l’outil de création de rapports a déjà collecté les données pour 13h00, un pic de trafic apparaît dans les rapports entre 13h00 et 15h00. </p> <p>Si vous changez le fuseau horaire de Moscou sur celui d’Abu Dhabi à 15h00, l’heure de la suite de rapports passe à 16h00. Les rapports n’affichent alors aucune donnée entre 15h00 et 16h00 le jour du changement d’heure. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Niveau de conversion</span> </td> 
   <td colname="col2"> <p> Active ou désactive les variables de commerce électronique telles que les eVars et les campagnes. Utilisez l’option <span class="uicontrol">Activé, sans panier</span> pour masquer tous les rapports Panier si votre site ne comporte pas de panier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Page par défaut</span> </td> 
   <td colname="col2"> <p> Si votre rapport <span class="wintitle">Pages les plus populaires</span> contient des URL plutôt que des noms de page, ce paramètre empêche plusieurs URL de représenter la même page. For example, the URLs <span class="filepath"> https://mysite.com</span> and <span class="filepath"> https://mysite.com/index.html</span> are typically the same page. You can remove default filenames so that these two URLs would both show up as <span class="filepath"> https://mysite.com</span>. </p> <p>Si la zone n’est pas renseignée, les noms de fichier suivants sont supprimés des URL : <span class="filepath">index.htm</span>, <span class="filepath">index.html</span>, <span class="filepath">index.cgi</span>, <span class="filepath">index.asp</span>, <span class="filepath">default.htm</span>, <span class="filepath">default.html</span>, <span class="filepath">default.cgi</span>, <span class="filepath">default.asp</span>, <span class="filepath">home.htm</span>, <span class="filepath">home.html</span>, <span class="filepath">home.cgi</span> et <span class="filepath">home.asp</span>. </p> <p>Pour désactiver entièrement cette option de réduction des noms de fichier, entrez une valeur qui n’existera jamais dans vos URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Remplacer le dernier octet des adresses IP par 0 </span> </td> 
   <td colname="col2"> <p>Le dernier octet est remplacé avant le filtrage IP. Par conséquent, le dernier octet est remplacé par un 0 et les règles d’exclusion IP doivent être mises à jour afin de correspondre aux adresses IP avec un zéro à la fin. Le * correspondant doit correspondre à 0. </p> <p>Si cette option est activée, l’adresse IP est altérée avant d’être traitée. Par exemple, l’adresse IP 134.123.567.780 est remplacée par 134.123.567.0. Les données de géosegmentation ne sont pas aussi exactes que lorsque l’adresse IP complète est utilisée. Plus précisément, la précision de la ville sera plus affectée que la précision du pays ou de la région. Les règles de robot et les règles VISTA sont affectées puisqu’elles n’ont pas accès à l’adresse IP complète. En outre, les règles de traitement basées sur les adresses IP (y compris les règles de canaux marketing et les règles de traitement des suites de rapports) sont affectées par ce paramètre. </p> <p>Remarque : Ce paramètre est activé par défaut pour toutes les suites de rapports créées dans le centre de données de Londres après janvier 2019, mais seulement si les paramètres de ces suites de rapports sont copiés à partir d’un modèle répertorié dans Admin Console. Les suites de rapports dont les paramètres sont copiés depuis d’autres suites de rapports hériteront de tous les paramètres de la suite de rapports sélectionnée. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Obscurcissement d’IP</span> </td> 
   <td colname="col2"> <p>Transforme les adresses IP en chaînes impossibles à reconnaître, en les supprimant essentiellement des entrepôts de données d’Adobe. Lorsque l’option Obscurcissement d’IP est activée, les adresses IP d’origine sont définitivement perdues. </p> <p>Remarque : Les adresses IP sont obscurcies partout dans Analytics, y compris dans Data Warehouse. Toutefois, le paramètre IP dans Target est contrôlé individuellement, de sorte que ce paramètre n’a aucune incidence sur Target. </p> <p>Si l’obscurcissement d’IP est activé, l’exclusion de l’adresse IP survient avant l’obscurcissement ; ainsi, les clients n’ont rien à changer lorsqu’ils activent cette option. </p> <p>Si <span class="uicontrol">Désactivé</span> est coché, l’adresse IP est conservée dans les données. </p> <p>Cochez l’option <span class="uicontrol">Obscurcir les adresses IP</span> pour remplacer l’adresse IP par une valeur de hachage (par ex., 234abc6493872038). </p> <p>Cochez l’option <span class="uicontrol">Supprimer les adresses IP</span> pour remplacer l’adresse IP par x.x.x.x dans les données, après la recherche géographique. </p> <p>Note: This setting might require changes to custom <a href="../../admin/admin/bot-rules/bot-rules.md#concept_A306689C65EB4D0F9AE65E3FD48ED5F7" format="dita" scope="local"> bot rules</a> or<a href="../../admin/admin/exclude-ip.md#concept_265A95A803F740629CAAAA7EB8BE81A4" format="dita" scope="local"> IP exclusions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Stockage de l’ID de transaction</span> </td> 
   <td colname="col2"> <p>Permet d’utiliser des sources de données <a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html?f=c_Transaction_ID" format="https" scope="external">ID de transaction</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Activer les Ad Hoc Analysis</span> </td> 
   <td colname="col2"> <p>Indique si la suite de rapports en question est présentée comme une suite de rapports disponible dans les Ad Hoc Analysis. Utilisez ce paramètre pour contrôler quelles suites de rapports s’affichent comme une option pour les Ad Hoc Analysis. Par exemple, vous pouvez désactiver les Ad Hoc Analysis pour les suites de rapports de développement et de contrôle qualité. </p> </td> 
  </tr> 
  <tr> 
   <td><span class="wintitle"> Activer Data Warehouse</span> </td> 
   <td colname="col2"> <p>Active l’interface utilisateur de Data Warehouse sous <span class="uicontrol">Outils</span> &gt; <span class="uicontrol">Data Warehouse</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

