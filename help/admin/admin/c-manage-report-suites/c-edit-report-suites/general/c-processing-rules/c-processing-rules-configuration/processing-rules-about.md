---
description: Les règles de traitement vous permettent de modifier des données en fonction de conditions définies. Lorsque des attributs ou valeurs satisfont les conditions définies, les valeurs peuvent être définies et supprimées, et les événements peuvent être définis.
subtopic: Processing rules
title: Fonctionnement des règles de traitement
feature: Processing Rules
role: Admin
exl-id: 9d2d9f2d-1e16-486f-9191-2c43776374da
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 94%

---

# Fonctionnement des règles de traitement

Les règles de traitement vous permettent de modifier des données en fonction de conditions définies. Lorsque des attributs ou valeurs satisfont les conditions définies, les valeurs peuvent être définies et supprimées, et les événements peuvent être définis.

Les règles de traitement sont appliquées aux données lors de leur collecte. Des règles sont également appliquées à toutes les données qui transitent par les bibliothèques AppMeasurement et par l’API d’insertion de données. Elles s’appliquent également aux sources de données complètes ou de journaux. Ces sources contiennent des données qui représentent un *`hit`* ou une action effectuée par un utilisateur. Les règles de traitement ne s’appliquent pas à d’autres sources de données.

## Concepts importants {#section_EB138775E7C64C74B0D1D3213F7A823C}

Le tableau ci-dessous décrit les principaux concepts liés à l’utilisation des règles de traitement :

<table id="table_287C606AE26E47AA8F737411990ACEB2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Concept </p> </th> 
   <th colname="col2" class="entry"> <p>Détails </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Les règles s’appliquent à une seule suite de rapports. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md"> Copier des règles de traitement dans une autre suite de rapports </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Les règles de traitement sont appliquées dans l’ordre indiqué. </p> </td> 
   <td colname="col2"> <p>Si une action modifie une valeur, les conditions suivantes utilisent la nouvelle valeur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Les règles de traitement sont appliquées immédiatement à la suite de rapports dès qu’elles sont enregistrées. </p> </td> 
   <td colname="col2"> <p>Les modifications provenant des règles de traitement devraient être visibles dans votre suite de rapports quelques minutes après leur enregistrement. Lors du test des règles de traitement, nous vous recommandons de configurer des <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/t-realtime-admin.md"> rapports en temps réel </a> dans votre suite de rapports de test afin que vous puissiez rapidement consulter les résultats d’une règle de traitement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Les règles de traitement constituent la seule méthode d’accès aux variables de données contextuelles. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md"> Copier une variable de données contextuelles dans une eVar </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Les règles de traitement sont appliquées avant les règles VISTA et les règles Canal marketing. </p> </td> 
   <td colname="col2"> <p> <a href="/help/technotes/processing-order.md"> Ordre de traitement </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Il est impossible d’exclure les accès. </p> </td> 
   <td colname="col2"> <p>Vous pouvez utiliser des règles VISTA pour exclure les accès. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Il est impossible de modifier la chaîne de produit, le référent et l’agent utilisateur. </p> </td> 
   <td colname="col2"> <p>Le référent et l’agent utilisateur sont en lecture seule. La chaîne de produit n’est pas disponible. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Les classifications et attributs de l’appareil portable ne sont pas disponibles. </p> </td> 
   <td colname="col2"> <p>La recherche d’appareils portables s’effectue avant les règles de traitement, mais les attributs ne sont pas disponibles dans les règles de traitement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Si vous exécutez JavaScript AppMeasurement H.25.2 ou version antérieure, la lecture des paramètres de chaîne de requête s’avère impossible au-delà des 255 premiers caractères d’une URL. JavaScript AppMeasurement H.25.3 et versions ultérieures fournissent une URL complète comprenant tous les paramètres de chaîne de requête vers les règles de traitement. </p> </td> 
   <td colname="col2"> <p>Effectuez une mise à jour vers la version H.25.3 ou ultérieure, ou procédez à la lecture des paramètres de chaîne de requête d’URL longues côté client et stockez les valeurs dans des variables Données contextuelles. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Les valeurs de chaîne de requête doivent être codées au format Unicode ou UTF-8 pour être lues par des règles de traitement. </p> </td> 
   <td colname="col2"> <p>Cela peut avoir une incidence sur les caractères à plusieurs octets transmis à l’aide de chaînes de requête. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vous êtes limité à 150 règles de 30 conditions pour chaque suite de rapports. </p> </td> 
   <td colname="col2"> <p>Les limites de règles de traitement s’appliquent par suite de rapports, et non par société. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Les règles de traitement doivent être configurées de manière à récupérer des variables de données contextuelles avant l’envoi des données. </p> </td> 
   <td colname="col2"> <p>Les règles de traitement sont traitées à mesure que les appels serveur sont envoyés. Les valeurs stockées dans des variables de données contextuelles sont ignorées si elles ne sont pas copiées à l’aide de règles de traitement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Les comparaisons de valeurs dans l’interface utilisateur ne respectent pas la casse. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md"> Nettoyer les valeurs d’un rapport </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Les noms de variable de données contextuelles peuvent comporter uniquement des caractères alphanumériques, des traits de soulignement et des points. Tout caractère supplémentaire est supprimé. </p> </td> 
   <td colname="col2"> <p>Par exemple, la variable de données contextuelles <code> login_page-home</code> devient automatiquement <code> login_pagehome</code>. Toutes les données envoyées à la variable <code> login_page-home</code> sont allouées à <code> login_pagehome</code>. </p> <p>Seules les variables de données contextuelles qui contiennent des caractères pris en charge peuvent être ajoutées dans l’interface Règles de traitement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le caret (^) est un caractère spécial dans le système des règles de traitement. </p> </td> 
   <td colname="col2"> <p>Pour afficher un seul caret, saisissez-en deux (^^). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Conditions des règles de traitement {#section_387390EEE9BA4DA98698522A84326DB4}

Les conditions recherchent une valeur correspondante dans les variables de page ou vérifient si une valeur est présente. Plusieurs conditions peuvent être ajoutées et vous pouvez indiquer si toutes les conditions doivent être réunies.

Vous pouvez créer une règle sans conditions de manière à toujours exécuter les actions définies.

La recherche de valeurs ne s’effectue pas automatiquement dans les variables avant l’exécution des actions. Ainsi, Prop1 contient une valeur « quelconque » et eVar1 est vide. Si vous configurez la valeur Prop1 pour qu’elle soit égale à eVar1, les deux valeurs seront vides. Si vous devez éviter ce cas de figure, ajoutez une condition qui recherche la présence d’une valeur.

## Actions des règles de traitement {#section_E2285C9D008442C7BF136E52A9A4CC06}

Les actions définissent des variables de page, suppriment de telles variables ou déclenchent des événements. Elles peuvent également concaténer des valeurs à afficher dans un rapport.

Vous pouvez, par exemple, afficher `category:product` en concaténant deux variables.
