---
description: Questions fréquentes sur Advertising Analytics.
title: Questions fréquentes sur les analyses publicitaires
feature: Advertising Analytics
exl-id: 664a5641-1c79-439f-a9fb-2ff134574412
source-git-commit: 591b82e271cc7474e9b413015804d4fe37d9050c
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 50%

---

# Questions fréquentes 

## Accès/Droits {#access}

+++ Dois-je être un client Adobe Advertising Cloud ou Adobe Advertising Cloud (AMO) pour accéder à cette fonctionnalité ?

Non, cette fonctionnalité est disponible pour les clients non-Advertising Cloud et non-AMO. </p> <p>Les clients AMO peuvent utiliser l’intégration Analytics-AMO existante, mais ne seront pas en mesure d’utiliser Ad Analytics.

+++

+++ Quels SKU Adobe Analytics vous permettent d’utiliser Advertising Analytics ?

Advertising Analytics est disponible pour Adobe Analytics

* [Select](https://www.adobe.com/fr/data-analytics-cloud/analytics/select.html)

* [Prime](https://www.adobe.com/fr/data-analytics-cloud/analytics/prime.html)

* [Ultimate](https://www.adobe.com/fr/data-analytics-cloud/analytics/ultimate.html)

+++

+++ Dois-je payer un supplément pour utiliser Advertising Analytics ?

Non, en dehors de la configuration de SKU correcte, Advertising Analytics n’entraîne pas de frais supplémentaires.

+++

+++ Advertising Analytics est-il décompté de mon utilisation de l’appel au serveur ?

Non, Advertising Analytics utilise un type de source de données spécial qui n’entraîne pas de coûts d’appel au serveur.

+++

+++ Si j’utilise déjà Advertising Cloud/AMO, puis-je continuer à utiliser la fonctionnalité Advertising Analytics ?

Tout compte de moteur de recherche compatible sera transmis à Advertising Analytics et affiché en lecture seule. Toutes les modifications et les mises à jour doivent être gérées dans Advertising Cloud/AMO.

+++

+++ Je possède le SKU approprié, mais je ne peux pas accéder à Advertising Analytics, pourquoi ?

Advertising Analytics est disponible uniquement pour les administrateurs d’Adobe Analytics. Toutefois, les administrateurs peuvent accorder l’accès à des non-administrateurs. Contactez votre administrateur au sujet des droits d’accès.

+++

## Utilisation d’Advertising Analytics  {#using}

+++ Quels comptes de moteur de recherche sont inclus dans Advertising Analytics ?

Les comptes de moteur de recherche incluent Google AdWords et Microsoft Bing.

+++

+++ Où puis-je accéder à Advertising Analytics ?

Une fois connecté à Adobe Analytics, accédez à la [!UICONTROL Administration]. Sélectionnez [!UICONTROL Advertising Analytics] pour ajouter vos comptes de moteur de recherche.

+++

+++ Comment les données sont-elles collectées et transmises à Analytics ?

Advertising Analytics utilise une série d’API personnalisées pour transmettre des données des moteurs de recherche via Adobe Advertising Cloud dans Analytics.

+++

+++ Quelles données de recherche obtiendrai-je avec cette intégration ?

Vous aurez

* Impressions
* Clics
* Coûts
* note de qualité moyenne
* Position moyenne directement à partir des moteurs de recherche, ainsi que
* Instances AMO ID (cliquez sur Instances).

+++

+++ Puis-je ventiler mes données Advertising Analytics selon d’autres données Analytics (mesures/dimensions) ?

Non, les données de recherche brutes entreront dans un jeu de données indépendant. Cependant, il existe une version des Instances des données de clic qui peut être ventilée selon d’autres données Analytics.

+++ Quelle est la définition des différents indicateurs d’état de mes comptes (en attente, actif, en pause, etc.) ? Chacun de ces indicateurs d’état identifie l’étape du cycle de vie de chaque compte de moteur de recherche.

* [!UICONTROL En attente]
* [!UICONTROL En pause] signifie que le compte a été initialement configuré, mais a été placé en mode inactif.
* [!UICONTROL Actif] signifie que le compte a été complètement configuré et extrait des données.

+++

+++ J’essaie de mapper mes comptes Advertising Analytics à une suite de rapports spécifique, mais elle n’est pas disponible dans le modal Suite de rapports. Pourquoi ?

Avant d’affecter une suite de rapports à un compte Advertising Analytics, la suite de rapports souhaitée doit être [configuré pour les rapports Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md)
Pour ce faire, accédez à une page d’administration distincte accessible à partir de : Admin > Suites de rapports > [sélectionner une suite de rapports] > Modifier les paramètres > Configuration Advertising Analytics.

+++

+++ Est-il possible d’affecter une suite de rapports virtuelle à un compte Advertising Analytics ?

Les suites de rapports virtuelles ne collectent pas de données. Vous ne pouvez donc pas mapper directement un compte Advertising Analytics à une suite de rapports virtuelle. Cependant, vous pouvez mapper le compte Advertising Analytics à la suite de rapports parente de la suite de rapports virtuelle dans laquelle vous souhaitez afficher les données. Les mesures du moteur de recherche (clic/coût/impressions) peuvent ne pas s’afficher dans la suite de rapports virtuelle, sauf si vous incluez une condition &quot;ou&quot; dans votre logique de segment en fonction de l’AMO ID (ou de sa classification). Exemple : ajouter « tous les accès dans lesquels l’AMO ID existe » permet d’inclure les mesures du moteur de recherche dans le segment.

+++

+++ Les mesures Advertising Analytics peuvent-elles être reportées dans la variable <b>Canaux marketing</b> rapport ?

Non, elles ne sont pas incluses dans le rapport Canaux marketing .

+++

+++ Q. : Quand les données de recherche sont-elles transférées dans Analytics ?

Les données de recherche sont extraites des moteurs de recherche vers 6 heures du matin (06:00) selon le fuseau horaire de votre centre de données Analytics. C’est à ce moment que les données AMO sont collectées et insérées dans la suite de rapports. Les données sont alors converties selon le fuseau horaire de la suite de rapports au cours de l’insertion des données dans Analytics.

+++

+++ Ce qui peut <b>capturé avant le clic</b>? Est-ce que nous fournissons le nombre d’impressions, le coût, la position moyenne, etc. même sans clic ? </p> </td>

L’AMO ID capture les mesures du moteur de recherche : Impressions, Coût, Clics, Position moyenne et Note de qualité moyenne. En l’absence de clics, mais s’il y a des impressions, les données de note d’impression/de position/de qualité continueront à être envoyées à Analytics. En règle générale, l’absence de clics ne génère également aucun coût.

+++

+++ À quel niveau ces données sont-elles capturées ? <b>Visiteur ? Accès ?</b>

Les mesures du moteur de recherche sont capturées au niveau de l’accès et connectées à l’AMO ID (et à ses classifications). Ce sont des données de niveau résumé, non liées aux visites/visiteurs. En tant que telles, les mesures du moteur de recherche peuvent être utilisées uniquement dans des segments dont la portée est de niveau accès et qui sont basés sur l’AMO ID (ou ses classifications).

L’AMO ID est également capturé sur la page de destination dans l’accès à cette page (qui le lie à la visite/au visiteur) et persistera en aval pour créditer d’autres mesures d’Analytics (jusqu’à expiration ou remplacement par un nouvel AMO ID). Il est entièrement intégré au jeu de données comme toute autre eVar.

+++

+++ Ne capturons-nous que google.com ou <b>versions de pays</b> (comme google.co.uk, google.it, google.fr ou google.de) également ?

La classification de la plateforme d’annonces publicitaires capture les valeurs suivantes : &quot;Google AdWords&quot; et &quot;Bing Ads&quot;. Il est recommandé d’inclure le code de pays dans le nom des campagnes. Vous pouvez ensuite filtrer ou segmenter. Par exemple, si toutes les campagnes commencent par codepays_, la création d’un segment où Campagnes (AMO ID) commence par « FR_ » vous fournirait uniquement des données pour la France.

+++

+++ La mesure &quot;Coût AMO&quot; correspond au coût payé pour chaque mot-clé/annonce publicitaire, comme indiqué par le moteur de recherche. S’agit-il du coût net ou du coût brut ?

&quot;Coût AMO&quot; est le seul coût payé aux moteurs de recherche. Il n’inclut aucuns frais d’agence ou d’optimisation de recherche/de plateforme de gestion.

+++

+++ prévoit-il d’inclure d’autres canaux publicitaires tels que <b>Affichage</b> ou <b>Social</b>?

Non, nous n&#39;avons actuellement pas de plans pour ces autres canaux sur la feuille de route.

+++


## Suivi automatique vs. manuel  {#section_7437C4698A6D482EB7ED94A948390119}

<table id="table_9738FF8459574ED2937A860A665BE739"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Réponse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Q. : Lors du paramétrage de mon compte Advertising, il est stipulé que le <b>Suivi automatique</b> peut entraîner des conséquences imprévues. Quel genre de conséquences peuvent survenir ? </p> </td> 
   <td colname="col2"> <p>A : 
     <ul id="ul_59EFF4A2ECE947EBBDB6A9FF6D072FE0"> 
      <li id="li_8731E4B7D6ED4F0996B3630A35D5BAC4">Le mode automatique tentera d’ajouter les paramètres d’URL à la fin du modèle de suivi ou de l’URL de destination dans un format correct. <b>Cependant, il vous appartient de vous assurer que les paramètres d’URL ajoutés demeurent correctement à la dernière page de destination. </b> </li> 
      <li id="li_1202FE1FC88342378A60E8FE65E5426B">Le mode automatique peut insérer des mot-clés dans l’URL d’entrée et votre serveur web peut ne pas prendre en charge les mots-clés contenant des caractères spéciaux. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Q. : Si je configure d’abord un suivi manuel ou automatique, <b>puis-je changer</b> de mode de suivi plus tard ? Quelles sont les implications ? </p> </td> 
   <td colname="col2"> <p>R. : Oui, vous pouvez changer, mais vous devrez supprimer l’ancienne logique de suivi avant de passer à l’autre mode. Cela peut entraîner une interruption du suivi le jour du changement (en particulier si vous passez du mode manuel au mode automatique). Il est donc recommandé de ne pas changer de mode à moins que cela ne soit absolument nécessaire. </p> 
    <ul id="ul_3F3CADD1C97B4947A13837CEE63A599D"> 
     <li id="li_CB9265951FD040388AEAB9EAD790A36E"><b>Passer du mode manuel au mode automatique</b> : supprimez les ajouts manuels apportés aux modèles de suivi puis basculez le bouton de manuel à automatique dans l’interface utilisateur d’Advertising Analytics et enregistrez cette configuration. Notez que le système peut prendre x heures pour renseigner les codes de suivi automatique. </li> 
     <li id="li_2B6ED1342E2D443B8AF26D03532AB8E4"><b>Passer du mode automatique au mode manuel</b> : basculez le bouton de manuel à automatique dans l’interface de configuration d’Advertising Analytics puis déployez les codes de suivi manuel aussi vite que possible. Lorsque vous déployez les codes de suivi manuel, si vous détectez des codes de suivi automatique dans les modèles de suivi du moteur de recherche, supprimez-les. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
