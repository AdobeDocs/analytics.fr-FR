---
description: Questions fréquentes sur Advertising Analytics.
title: Questions fréquentes sur Advertising Analytics
feature: Advertising Analytics
exl-id: 664a5641-1c79-439f-a9fb-2ff134574412
TQID: https://experienceleague.adobe.com/HC9F-en-nLFRkxsaY6Szdtb3jR5NgdpsbjSAX6kTBlQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: a9364d69-0c51-44bf-8b5f-6d99c04493b8id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c2296997-5d79-4905-b32e-99b5aa892429id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 1298
ht-degree: 32%

---

# Questions fréquentes

## Accès/Droits {#access}

+++ Dois-je être un client Adobe Advertising pour accéder à cette fonctionnalité ?

Non, cette fonctionnalité est disponible pour les clients non-Advertising. Les clients Adobe Advertising peuvent tirer parti de l’intégration Analytics + Advertising existante.

+++

+++ Quels SKU d’Adobe Analytics vous permettent d’utiliser Advertising Analytics ? 

Advertising Analytics est disponible pour Adobe Analytics

* [Sélectionner](https://www.adobe.com/fr/data-analytics-cloud/analytics/select.html)

* [Prime](https://www.adobe.com/fr/data-analytics-cloud/analytics/prime.html)

* [](https://www.adobe.com/fr/data-analytics-cloud/analytics/ultimate.html)

+++

+++ Dois-je payer un supplément pour utiliser Advertising Analytics ? 

Non, en dehors de l’approvisionnement de SKU approprié, Advertising Analytics n’entraîne pas de frais supplémentaires.

+++

+++ Advertising Analytics est-il comptabilisé dans l’utilisation des appels au serveur ?

Non, Advertising Analytics utilise un type de source de données spécial qui n’entraîne pas de coûts d’appel au serveur.

+++

+++ Si j’utilise déjà Adobe Advertising, puis-je toujours utiliser la fonctionnalité Advertising Analytics ?

Tout compte de moteur de recherche compatible sera transmis à Advertising Analytics et affiché en lecture seule. Toutes les modifications ou mises à jour doivent être gérées dans Advertising.

+++

+++ Je possède le SKU correct, mais je ne peux pas accéder à Advertising Analytics, pourquoi ? 

Advertising Analytics est disponible uniquement pour les administrateurs Adobe Analytics. Toutefois, les administrateurs peuvent accorder l’accès aux utilisateurs non administrateurs. Contactez votre administrateur au sujet des droits d’accès.

+++

## Utilisation d’Advertising Analytics {#using}

+++ Quels comptes de moteurs de recherche sont inclus dans Advertising Analytics ?

Les comptes de moteurs de recherche incluent Google Ads et Microsoft Advertising.

+++

+++ Où puis-je accéder à Advertising Analytics ?

Après vous être connecté à Adobe Analytics, accédez à l’[!UICONTROL Admin]. Sélectionnez ensuite  pour ajouter vos comptes de moteurs de recherche.

+++

+++ Comment les données sont-elles collectées et transmises à Analytics ? 

Advertising Analytics utilise une série d’API personnalisées pour transmettre des données des moteurs de recherche à Adobe Analytics via Adobe Advertising.

+++

+++ Quelles données de recherche puis-je obtenir avec cette intégration ? 

Vous obtenez :

* Impressions
* Clics
* Coûts
* note de qualité moyenne
* Position moyenne directement depuis les moteurs de recherche
* Instances ID AMO (cliquez sur Instances)

+++

+++ Puis-je ventiler mes données Advertising Analytics en fonction d’autres données Analytics (mesures/dimensions) ? 

Non, les données de recherche brutes seront entrées sous la forme d’un jeu de données indépendant. Cependant, il existe une version des Instances des données de clic qui peut être ventilée selon d’autres données Analytics.

+++

+++ Quelle est la définition des différents indicateurs de statut de mes comptes (En attente, Actif, En pause, etc.) ? Chacun de ces indicateurs de statut identifie l’étape du cycle de vie de chaque compte de moteur de recherche. 

* [!UICONTROL En attente]
* [!UICONTROL En pause] signifie que le compte a été initialement configuré, mais a été placé en mode inactif.
* [!UICONTROL Actif] signifie que le compte a été complètement configuré et extrait des données.

+++

+++ J’essaie de mapper mes comptes Advertising Analytics à une suite de rapports spécifique, mais elle n’est pas disponible dans la fenêtre modale Suite de rapports. Pourquoi ? 

Avant de pouvoir affecter une suite de rapports à un compte Advertising Analytics, la suite de rapports souhaitée doit être [configurée pour la création de rapports Advertising Analytics)](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md)
Pour ce faire, une page d’administration distincte est accessible à partir de : Admin > Suites de rapports > `[select report suite]` > Modifier les paramètres > Configuration Advertising Analytics.

+++

+++ Est-il possible d’affecter une suite de rapports virtuelle à un compte Advertising Analytics ? 

Les suites de rapports virtuelles ne collectent pas de données. Vous ne pouvez donc pas mapper directement un compte Advertising Analytics à une suite de rapports virtuelle. Cependant, vous pouvez mapper le compte Advertising Analytics à la suite de rapports parente de la suite de rapports virtuelle dans laquelle vous souhaitez afficher les données. Les mesures des moteurs de recherche (clics/coûts/impressions) peuvent ne pas s’afficher dans la suite de rapports virtuelle, sauf si vous incluez une condition « ou » dans la logique de segment en fonction de l’AMO ID (ou de sa classification). Exemple : ajouter « tous les accès dans lesquels l’AMO ID existe » permet d’inclure les mesures du moteur de recherche dans le segment.

+++

+++ Les mesures Advertising Analytics sont-elles déclarables dans le rapport *Canaux marketing* ? 

Non, ils ne sont pas inclus dans le rapport Canaux marketing .

+++

+++ Quand les données de recherche sont-elles extraites dans Analytics ? 

Les données de recherche sont extraites des moteurs de recherche vers 6 heures du matin (06:00) dans le fuseau horaire de votre centre de données Analytics. C’est à ce moment que les données AMO sont collectées et insérées dans la suite de rapports. Les données sont alors converties selon le fuseau horaire de la suite de rapports au cours de l’insertion des données dans Analytics.

+++

+++ Que peut-on *capturer avant le clic* ? Est-ce que nous apportons des impressions, des coûts, la position moyenne, etc. même sans le clic ?

L’ID AMO capture les mesures du moteur de recherche : Impressions, Coût, Clics, Position moyenne et Score de qualité moyen. En l’absence de clics, mais s’il y a des impressions, les données de note d’impression/de position/de qualité continueront à être envoyées à Analytics. En règle générale, l’absence de clics ne génère également aucun coût.

+++

+++ À quel niveau ces données sont-elles saisies ? *Visiteur ? Accès ?* 

Les mesures du moteur de recherche sont capturées au niveau de l’accès et connectées à l’AMO ID (et à ses classifications). Ce sont des données de niveau résumé, non liées aux visites/visiteurs. En tant que telles, les mesures du moteur de recherche peuvent être utilisées uniquement dans des segments dont la portée est de niveau accès et qui sont basés sur l’AMO ID (ou ses classifications).

L’AMO ID est également capturé sur la page de destination dans l’accès à cette page (qui le lie à la visite/au visiteur) et persistera en aval pour créditer d’autres mesures d’Analytics (jusqu’à expiration ou remplacement par un nouvel AMO ID). Il est entièrement intégré au jeu de données comme toute autre eVar.

+++

+++ Capturons-nous uniquement les versions google.com ou *country* (comme google.co.uk, google.it, google.fr ou google.de) également ? 

La classification Ad Platform capture les valeurs suivantes : « Google Adwords » et « Bing Ads ». Il est recommandé d’inclure le code de pays dans le nom des campagnes. Vous pouvez ensuite filtrer ou segmenter. Par exemple, si toutes les campagnes commencent par codepays_, la création d’un segment où Campagnes (AMO ID) commence par « FR_ » vous fournirait uniquement des données pour la France.

+++

+++ La mesure « Coût AMO » correspond au coût payé pour chaque mot-clé/annonce publicitaire, tel que signalé par le moteur de recherche. S’agit-il du coût net ou du coût brut ? 

« AMO cost » est seulement le coût payé aux moteurs de recherche. Il n’inclut aucuns frais d’agence ou d’optimisation de recherche/de plateforme de gestion.

+++

+++ Prévoyez-vous d’inclure d’autres canaux publicitaires tels que *Affichage* ou *Social* ? 

Non, actuellement, nous n&#39;avons pas de plan pour ces autres canaux sur la feuille de route.

+++


## Suivi automatique vs. manuel {#section_7437C4698A6D482EB7ED94A948390119}

+++ Lors de la configuration de mon compte Advertising, il est indiqué que le *suivi automatique* peut avoir des conséquences inattendues. Quel genre de conséquences peuvent survenir ? 

Le mode automatique tente d’ajouter des paramètres d’URL à la fin des modèles de tracking/URL de destination dans le bon format. Cependant, il est de votre responsabilité de vous assurer que les paramètres d’URL ajoutés persistent correctement sur la page de destination finale. Le mode automatique peut insérer des mot-clés dans l’URL d’entrée et votre serveur web peut ne pas prendre en charge les mots-clés contenant des caractères spéciaux.

+++

+++ Si je configure initialement le suivi manuel ou automatique, puis-je passer à l’autre mode de suivi ultérieurement ? Quelles sont les implications ? 

Oui, vous pouvez changer de mode de suivi, mais vous devez supprimer l’ancienne logique de suivi avant d’effectuer le changement. Cela peut entraîner une interruption du suivi le jour du changement (en particulier si vous passez du mode manuel au mode automatique). Par conséquent, nous recommandons de ne pas changer de fournisseur, sauf en cas d’absolue nécessité.

* Passer du manuel au automatique : supprimez les ajouts manuels aux modèles de suivi, puis basculez le bouton (bascule) du manuel au automatique dans l’interface utilisateur d’Advertising Analytics et enregistrez le paramètre. Notez qu’il peut s’écouler plusieurs heures avant que le système ne renseigne les codes de suivi automatiques.

* Passer d’automatique à manuel : mettez à jour le bouton (bascule) de manuel à automatique dans l’interface utilisateur de configuration d’Advertising Analytics, puis déployez les codes de suivi manuels aussi rapidement que possible. Lorsque vous déployez les codes de suivi manuel, si vous détectez des codes de suivi automatique dans les modèles de suivi du moteur de recherche, supprimez-les.

+++
