---
description: Définition des éléments d’interface sur les pages du créateur de règles de classification.
subtopic: Classifications
title: Règles de classification – Définitions
topic: Admin tools
uuid: 77af8669-6e11-435c-9cc3-b03eb627c855
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Règles de classification – Définitions

Définition des éléments d’interface sur les pages du créateur de règles de classification.

## Page Règles {#section_4A5BF384EEEE4994B6DC888339833529}

Cette page affiche les règles d’un jeu.

![](assets/classification_rules_page.png)

**Définitions**

<table id="table_2B3A8BB7BDE14836ACA6A1D444B011CD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Sélection de suites de rapports et de variables </p> </td> 
   <td colname="col2"> <p><b>Suite de rapports</b> </p> <p>Suites de rapports auxquelles s’applique le jeu de règles. </p> <p><b>Variable</b> </p> <p>Vous ne pouvez appliquer qu’une seule variable lors de la création d’un jeu de règles de classification. Si vous souhaitez créer plusieurs jeux de règles pour une seule variable, vous devez appliquer chacun d’eux à plusieurs suites de rapports. </p> <p>Remarque : Vous ne pouvez utiliser que les variables auxquels vous avez accès dans vos suites de rapports. Les variables s’affichent dans le panneau <span class="wintitle">Nouveau jeu de règles</span> uniquement une fois qu’au moins une classification est définie pour la variable. </p> <p>Par exemple, pour que <span class="term"> Pages</span> soit disponible sous forme de variable pour le jeu de règles, assurez-vous que les <a href="https://marketing.adobe.com/resources/help/fr_FR/reference/traffic_classifications.html"  >classifications de trafic</a> de la suite de rapports sont mises en œuvre pour <span class="term"> Page</span>. </p> <p> Vous pouvez créer des classifications sur une variable dans <span class="uicontrol">Admin</span> &gt; <span class="uicontrol">Report Suites</span> &gt; <span class="uicontrol">Trafic</span> &gt; <span class="uicontrol">Classifications de trafic</span> (ou <span class="uicontrol">Conversion</span> &gt; <span class="uicontrol">Classifications des conversions</span>). Sélectionnez ensuite la variable et cliquez sur <span class="uicontrol">Ajouter une classification</span>. </p> <p>Reportez-vous aux rubriques <a href="https://marketing.adobe.com/resources/help/fr_FR/reference/traffic_classification_admin.html"  >Classifications de trafic</a> et <a href="https://marketing.adobe.com/resources/help/fr_FR/reference/conversion_classifications.html"  >Classifications des conversions</a> dans l’Aide de l’administration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Activer</span> </p> </td> 
   <td colname="col2"> <p>Valide et active une règle. Les règles actives sont traitées tous les jours ; elles examinent les données de classification remontant généralement à un mois. Les règles recherchent automatiquement les nouvelles valeurs et téléchargent les classifications. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Désactiver</span> </p> </td> 
   <td colname="col2"> <p>Désactive les règles de telle sorte que vous puissiez les modifier et les tester. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configuration des suites de rapports et des variables </p> </td> 
   <td colname="col2"> <p>Affiche la page <span class="wintitle">Suites de rapports disponibles</span> dans laquelle vous pouvez sélectionner une ou plusieurs suites de rapports disponibles à utiliser pour tous vos jeux de règles. (Cette page s’affiche également lorsque vous exécutez le <span class="wintitle">Créateur de règles de classification</span> pour la première fois.) </p> <p>Cette fonctionnalité a pour objectif de réduire le temps de chargement des suites de rapports, dans le cas où vous avez des centaines de suites de rapports disponibles. </p> <p>Les suites de rapports que vous sélectionnez ici sont disponibles au niveau des règles lorsque vous cliquez sur <span class="uicontrol">Ajouter des suites</span> lors de la création d’une règle. </p> <p>Remarque : une suite de rapports devient disponible <span class="term"> uniquement</span> lorsque les suites de rapports comportent au moins une classification définie pour la variable dans <span class="wintitle"> Outils d’administration</span>. <p>(Voir <span class="term"> Variable</span> dans <a href="/help/components/c-classifications2/crb/classification-rule-set.md"  >Jeux de règles de classification</a> pour obtenir une explication sur cette condition préalable.) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Les règles remplacent toutes les valeurs existantes. </p> </td> 
   <td colname="col2"> <p> (Paramètre par défaut) Remplace toujours les clés de classification existantes, y compris les classifications transférées au moyen de l’importateur (SAINT). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Les règles remplacent uniquement les valeurs non définies. </p> </td> 
   <td colname="col2"> <p>Seules les cellules vides (non définies) sont remplies. Les classifications existantes restent inchangées. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intervalle de recherche en amont </p> </td> 
   <td colname="col2"> <p>Lorsque vous activez et validez des règles, vous pouvez indiquer si elles doivent remplacer des classifications existantes pour les clés affectées. (Seules les clés classées qui ont été transmises à <span class="keyword">Adobe Analytics</span> au cours de la période spécifiée sont affectées.) </p> <p>Si vous n’indiquez aucun <span class="term"> intervalle de recherche</span>, les règles s’exécutent en boucle pendant environ un mois (en fonction du jour du mois). Les classifications existantes ne sont jamais remplacées, sauf si vous activez cette option. </p> <p><b>Centre de développement</b> : les partenaires peuvent créer des règles de classification dans le <span class="wintitle">Centre de développement</span>. Ces règles sont déployées lorsque le client active une intégration. Dans le <span class="wintitle">Centre de développement</span>, l’option <span class="uicontrol">Remplacer depuis</span> permet au partenaire de spécifier si le client peut déterminer la valeur de remplacement lors de l’activation ou de la modification d’une intégration. </p> <p>Reportez-vous à la section <a href="/help/components/c-classifications2/crb/classification-quickstart-rules.md"  >Méthode de traitement des règles</a> pour en savoir plus sur le traitement des règles. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="/help/components/c-classifications2/crb/classification-quickstart-rules.md"  > Ajouter une règle </a> </td> 
   <td colname="col2"> <p>Permet d’ajouter des règles au jeu de règles. </p> <p>Remarque : Si une valeur est trouvée plusieurs fois dans un jeu de règles, le système utilise la dernière règle pour la classer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Version préliminaire</span> </td> 
   <td colname="col2"> Permet d’indiquer qu’une règle se trouve en mode préliminaire. L’état Version préliminaire vous permet de tester la règle avant de l’exécuter. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Dupliquer</span> </td> 
   <td colname="col2"> Duplique (copie) un jeu de règles, de telle sorte que vous puissiez l’appliquer à une autre variable ou à la même variable dans une autre suite de rapports. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/components/c-classifications2/crb/classification-quickstart-rules.md"  > Tester le jeu de règles </a> </p> </td> 
   <td colname="col2"> <p>Permet de tester la validité d’un jeu de règles. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Condition de correspondance</span> </td> 
   <td colname="col2"> Indique les conditions souhaitées pour la règle. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Action de classification</span> </td> 
   <td colname="col2"> <p>Indique l’action à effectuer lorsque la condition de correspondance se produit. </p> <p>Vous pouvez, par exemple, définir un nom de campagne sur 2 $, ce qui identifie la position 2 dans le code de suivi comme nom de campagne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> #</span> </td> 
   <td colname="col2"> <p>Numéro de rôle. </p> <p>Voir  <a href="/help/components/c-classifications2/crb/classification-quickstart-rules.md"  > Méthode de traitement des règles</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Sélectionner le type de règle</span> </td> 
   <td colname="col2"> <p>Chaque règle s’applique à une variable spécifique. Les sélections valides sont les suivantes : </p> 
    <ul id="ul_6A8E06BB4AF2402B99C215823CB3D59D"> 
     <li id="li_5C702D4F460841D38A59621A5161A3BC">Commence par </li> 
     <li id="li_8052A741D9F34A2FBC136C181600193E">Se termine par </li> 
     <li id="li_D0FA6EA4F09644FFBC9E6BC568BE80AC">Contient </li> 
     <li id="li_48675FE5253942ED887C6A72D1DCEF54"> <a href="/help/components/c-classifications2/crb/classification-quickstart-rules.md"  > Expression régulière </a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Entrer les critères de recherche</span> </td> 
   <td colname="col2"> Schéma de texte que vous recherchez dans une clé. Ces critères peuvent être des termes de recherche, des caractères ou des expressions régulières. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Définir la classification</span> </td> 
   <td colname="col2"> Colonne de classification que vous souhaitez définir si les critères de correspondance sont respectés. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> À</span> </td> 
   <td colname="col2"> Valeur que vous souhaitez spécifier pour la colonne de classification sélectionnée si les critères de correspondance sont respectés. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtrer </td> 
   <td colname="col2"> Permet de rechercher des règles. </td> 
  </tr> 
 </tbody> 
</table>

## Page Expression régulière {#section_C932A5469E774841B2229965A154163C}

Vous pouvez modifier des expressions régulières sur la page [!UICONTROL Expression régulière].

![](assets/regex_tracking_code.png)

**Définitions**

| Élément | Description |
|---|---|
| Exemple de clé | Chaîne de test à utiliser. Vous pouvez, par exemple, créer une classification à partir de caractères spécifiques d’un code de suivi. Vous pouvez établir des correspondances avec des caractères, des mots ou des schémas de caractères donnés. |
| Groupes correspondants | Affiche la correspondance entre l’expression régulière et les caractères d’identification de la campagne, de sorte que vous puissiez classer une position dans l’identifiant de campagne. |
| Résultat correspondant | Affiche les parties d’une chaîne qui correspondent à l’expression régulière. |

Voir  [Expressions régulières dans les règles de classification](/help/components/c-classifications2/crb/classification-quickstart-rules.md).

## Page Tests {#section_EC926F97901C4E65901413F9683AA70A}

Cette page vous permet de tester des règles d’un jeu.

**Définitions**

| Élément | Description |
|---|---|
| Exécuter le test | Lorsque vous testez le jeu de règles, utilisez des clés du rapport afin de déterminer l’impact sur celles-ci. |
| Filtrer | Filtre les valeurs du panneau [!UICONTROL Résultats]. |

