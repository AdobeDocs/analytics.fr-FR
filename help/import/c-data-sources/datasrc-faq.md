---
description: Cette rubrique fournit des réponses aux questions courantes.
subtopic: Data sources
title: FAQ sur les sources de données
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 2a5d38fe-5c5b-4275-bc44-e9cb02ec2f5d
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: ht
source-wordcount: '1496'
ht-degree: 100%

---

# FAQ sur les sources de données

Cette rubrique fournit des réponses aux questions courantes.

## Comment lier les données hors ligne aux événements en ligne ?  {#offline}

Pour que les sources de données d’ID de transaction lient des données hors ligne aux événements en ligne, vous devez activer l’enregistrement des identifiants de transaction. Voir [Enregistrement des ID de transaction](/help/import/c-data-sources/datasrc-integrating-offline-data.md#section_30D6D47AEC0F4A36B87EBFE4C858F20C) pour en savoir plus.

## Quel est le coût de l’utilisation de la fonctionnalité Sources de données ?  {#cost}

La fonctionnalité Sources de données n’engendre aucuns frais supplémentaires au-delà de l’appel au serveur standard. Des frais d’appel au serveur s’appliquent seulement pour les types de sources de données à traitement complet, quand des accès individuels sont envoyés sous forme de lignes de données. Les sources de données au niveau du trafic et de l’agrégat n’engendrent aucuns frais supplémentaires.

## Comment inclure des commentaires dans les fichiers de la fonctionnalité Sources de données ?  {#comments}

Chaque ligne d’un fichier de source de données qui commence par le symbole dièse (#) est traitée comme un commentaire.

## Dois-je inclure une colonne de dates dans ma feuille de calcul ?  {#date}

Oui. De nombreux rapports marketing pouvant être recherchés par date, vous devez inclure une colonne de dates.

## Puis-je stocker des données dans les variables que j’utilise déjà ?  {#variables}

Adobe recommande de sélectionner de nouvelles variables inutilisées pour importer les données à l’aide de la fonctionnalité Sources de données. Si vous ne connaissez pas la configuration de votre fichier de données ou si vous souhaitez mieux comprendre les risques inhérents à la réutilisation de variables, contactez l’assistance clientèle.

## Puis-je supprimer des données qui ont été importées à l’aide de la fonctionnalité Sources de données ?  {#imported}

Non. Il n’est pas possible, même pour des techniciens d’Adobe, de supprimer les données transférées dans les rapports à l’aide de la fonctionnalité Sources de données une fois qu’elles ont été importées. Ces données sont définitivement intégrées à vos données existantes et vous ne pouvez plus les distinguer des données entrées à l’aide de méthodes classiques de collecte de données (JavaScript, ActionSource, API d’insertion de données, etc.). En conséquence, Adobe vous recommande vivement de transférer ces données dans une suite de rapports test avant de les transférer dans une suite de production.

## Combien de données puis-je importer en même temps ?  {#amount}

Le traitement s’interrompt au-delà de 50 Mo et ne reprend qu’une fois que le total est inférieur à 50 Mo. Afin d’éviter les retards en termes de génération de rapports, ne transférez pas plus de 90 jours de données par jour.

## Lorsque j’importe des données au moyen de la fonctionnalité Sources de données, les données existantes sont-elles écrasées ?  {#overwrite}

Les données des sources de données ne remplaceront jamais les données existantes. Les données transférées à l’aide de la fonctionnalité Sources de données sont ajoutées aux données existantes.

## Lorsque je transfère mes données par l’intermédiaire de la fonctionnalité Sources de données, pourquoi mes mesures ne sont-elles pas elles aussi transférées ?  {#metrics}

Lorsque vous transférez des données de sources de données, vous transférez les mesures qui seront disponibles dans l’interface des rapports.

Si, par exemple, vous transférez les recettes du centre d’appels pour les produits que vous vendez sur votre site, ces données seront disponibles dans le même rapport que les recettes en ligne. Vous ne pourrez toutefois pas les utiliser conjointement avec les données Visites, car vous n’avez pas transféré le nombre de visites en même temps. Adobe peut uniquement reporter les mesures et éléments transférés au moyen de la fonctionnalité Sources de données (outre les mesures standard des rapports marketing).

## Que se passe-t-il si je transmets des valeurs négatives dans les rapports au moyen de la fonctionnalité Sources de données ?  {#negative}

La valeur est diminuée en conséquence.

## Quelle est la différence entre une source de données de trafic et de conversion (générique) ?  {#traffic}

Le transfert d’une source de données de trafic est beaucoup plus rapide, car il s’agit d’une simple mise à jour des valeurs récapitulatives dans les tableaux appropriés. La source de données générique avec données de conversion (événements, etc.) crée une correspondance pour chaque valeur dans la colonne à traiter.

Exemple de fichier :

<table id="table_D5408E0BDB984229B4C60A66BB53CEBB"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Date </code> </p> </td> 
   <td colname="col2"> <p> <code> Event15 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 01/01/2013 </code> </p> </td> 
   <td colname="col2"> <p> <code> 553 </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

L’exemple ci-dessus crée 553 correspondances à traiter dans le système de mémoire cache.

## La fonctionnalité Sources de données prend-elle en compte les sous-relations, les corrélations et les chemins d’accès ?  {#breakdown}

Le processus de source de données (pour les sources de données génériques, et non de trafic) génère des correspondances individuelles qui sont traitées par mémoire cache. Par conséquent, le processus des sous-relations est appliqué, mais pas celui des corrélations. Les chemins d’accès peuvent être traités, mais chaque correspondance correspond à sa propre visite ; aucun chemin d’accès n’est donc généré. Les données de cheminement sont générées pour les importations de journaux Web.

## Les extensions de fichiers respectent-elles la casse pour un transfert de source de données ou un fichier de classification ?  {#case}

Si les extensions d’un fichier de transfert de source de données ou d’un fichier de classification comportent des majuscules, les fichiers ne seront pas traités. Les extensions des fichiers de transfert de source de données doivent être en minuscules. Par exemple, [!DNL file.TXT] et [!DNL file.FIN] ne seront pas traités, de même que [!DNL .TAB] et [!DNL .FIN]. Toutefois, [!DNL .txt] et [!DNL .fin] sont traités.

## Puis-je ajouter des événements supplémentaires au modèle généré ou suis-je limité à trois ?  {#template}

Vous pouvez ajouter autant d’événements que vous le souhaitez. Toutefois, l’Assistant permet d’ajouter uniquement trois événements. Une fois le fichier de modèle créé, vous pouvez y ajouter autant d’événements que vous le souhaitez.

## Que devient un fichier de source de données si un ou plusieurs enregistrements n’ont pas le même nombre de colonnes que l’enregistrement de l’en-tête ?  {#header}

Si un fichier de source de données contient un ou plusieurs enregistrements qui n’ont pas le même nombre de colonnes que l’enregistrement de l’en-tête, les événements suivants se produisent :

* Un message électronique est envoyé au créateur de la source de données, pour l’informer de l’erreur.
* Le fichier n’est pas traité en raison de l’incohérence du nombre de colonnes.

## Les informations des sources de données sont-elles cumulées ?  {#rollup}

Les informations des sources de données peuvent être cumulées ; toutefois, l’assistance clientèle Adobe doit retraiter le cumul à partir de la date d’historique pour inclure les données d’historique. Si, par exemple, la date actuelle est le 31 octobre 2015 et que vous avez transféré des données pour la période du 1er au 15 août 2015 à l’aide de la fonctionnalité Sources de données, le cumul devra être défini pour les retraiter à partir du 1er août 2015, afin que les données nouvellement importées soient incluses.

Notez également que les données ne doivent jamais être transférées directement dans une suite de rapports de cumul à l’aide de la fonctionnalité Sources de données. Si vous souhaitez que ces données soient incluses dans un cumul, elles doivent être importées dans une suite de rapports standard, également appelée   *`child suite`* du cumul. Contactez l’assistance clientèle Adobe pour en savoir plus.

## Pourquoi le rapport Pages vues n’affiche-t-il aucune donnée de source de données pour un seul jour, mais affiche les données correctes pour une semaine ?  {#week}

La fonctionnalité Sources de données ne génère pas de données sur une base horaire. Or, lors de l’exécution d’un rapport pour un certain jour, les données peuvent être ventilées uniquement par heure. Par conséquent, rien ne s’affiche dans le rapport. Vous pourrez afficher les données uniquement lorsqu’elles sont ventilées par jour ou plus, en exécutant un rapport hebdomadaire ou mensuel.

## Comment sont calculés les visiteurs uniques dans un transfert au moyen de la fonctionnalité Sources de données du journal de serveur Web ?  {#unique}

Le nombre de visiteurs uniques dans un journal de serveur web est calculé sous forme de combinaisons distinctes d’*`IP Address`* et d’*`User Agent`* dans le journal web. Chaque combinaison unique de ces deux valeurs est comptée comme un visiteur unique. Si la colonne [!UICONTROL Agent utilisateur] est vierge (ou non incluse dans le journal Web), nous ne pouvons pas identifier le nombre de visiteurs uniques, et l’ensemble du transfert est compté comme un seul visiteur unique (même s’il y a plusieurs adresses IP).

## Dans les sources de données, comment puis-je savoir quel identifiant de connexion appartient à quelle suite de rapports ?  {#login}

Dans les sources de données, l’identifiant de suite de rapports correspond à la première partie de l’identifiant de connexion annexé par un numéro aléatoire qui identifie la source de données spécifique qui était configurée. Par exemple : `RSID-drmossdev5 Login-drmossdev5_0001343430`.

## Quelles sont les répercussions de la version 15 et de la segmentation sur les sources de données ?  {#segmentation}

Dans la version 15, les sources de données se comportent différemment selon le type de la source :

* Les sources de données de traitement complet, de journaux Web et d’ID de transaction s’affichent normalement. Lorsque des segments sont appliqués, les données sont filtrées selon les règles de segmentation.
* Les sources de données standard ou de conversion (campagnes publicitaires, gestion des relations client, satisfaction du client, performances du site, données récapitulatives génériques, achats en ligne, prospects et devis, données des canaux hors ligne) apparaissent dans la version 15. Toutefois, comme elles ne sont liées ni aux visites ni aux visiteurs, elles sont bloquées lors de l’application des segments.

## Les mesures importées à l’aide d’un ID de transaction sont-elles disponibles dans les flux de données de parcours de navigation et dans l’entrepôt de données ?  {#clickstream}

Les flux de données comprennent les mesures d’ID de transaction qui ont été reçues. Toutefois, si vous transférez des données d’ID de transaction pour une date dans le passé, la seule façon d’obtenir ces données consiste à retélécharger le flux de données pour cette journée.

## Les eVars actuellement persistantes dans le profil du visiteur attribué aux mesures sont-elles transférées à l’aide des sources de données ?  {#visitor}

Non pour le traitement complet, oui pour l’ID de transaction. Les sources de données à traitement complet sont traitées à l’aide de profils du visiteur distincts. Ainsi, même si les identifiants visiteurs correspondent, elles ne seront pas liées du point de vue de l’attribution des eVars. Les sources de données d’ID de transaction sont liées au profil du visiteur principal ; les eVars persistantes sont attribuées aux événements transférés à l’aide d’un ID de transaction.

## Les eVars transférées à l’aide de sources de données persistent-elles dans le comportement en ligne ultérieur ?  {#evars}

Non. Les eVars transférées au moyen des sources de données des ID de transaction liront uniquement les informations de profil stockées ; elles ne mettront pas à jour le profil.
Non. Les eVars sont les seules variables enregistrées dans l’instantané du profil du visiteur.

## Comment les événements numériques et monétaires fonctionnent-ils avec les sources de données ? {#numeric}

Le traitement complet ne prend en charge que les formats de liste dʼévénements hérités, à lʼexclusion de la valeur numérique/monétaire/compteur (plus de 1) de lʼévénement directement dans la liste des événements, à savoir `"eventNN,eventKK"` et non `"eventNN=#.##"`. Cela signifie quʼil ne prend en charge un événement compteur que sʼil est transmis dans la colonne des événements du fichier de source de données et quʼil sʼincrémente de 1.

Si des événements numériques, monétaires ou compteurs (plus de 1) sont requis, utilisez la liste de produit suivante :

```js
s.products="Footwear;Running Shoes;1;99.99;event1=4.50";
s.products="Footwear;Running Shoes;1;99.99;event1=4.50|event4=1.99";
```
