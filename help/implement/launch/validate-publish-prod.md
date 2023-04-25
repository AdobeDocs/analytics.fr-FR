---
title: Validation de la mise en œuvre d’un développement et publication en production
description: Découvrez comment utiliser les balises Adobe Experience Platform pour déployer Adobe Analytics dans votre environnement de production.
feature: Launch Implementation
exl-id: 2f5bcfee-d75e-4dac-bea9-91c6cc545173
source-git-commit: 78cfb1f3c4d45fc983982a8da11b66f2b2c9ecbc
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 72%

---

# Validation de la mise en œuvre d’un développement et publication en production

Une fois que votre bibliothèque de balises est envoyée en production, votre organisation peut commencer à utiliser Adobe Analytics pour extraire des rapports de base.

## Conditions préalables

[Déployez votre mise en œuvre d’Analytics dans votre environnement de développement](deploy-dev.md) : une mise en œuvre d’Analytics doit être publiée dans votre environnement de développement pour suivre cette page.

## Validez votre mise en œuvre de développement à l’aide du débogueur Experience Cloud.

Le débogueur Experience Cloud est une extension qui affiche toutes les balises Experience Cloud présentes sur une page.

1. Installez l’extension pour : [Chrome](https://chrome.google.com/webstore/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob) ou [Firefox](https://addons.mozilla.org/fr/firefox/addon/adobe-experience-platform-dbg/).
2. Accédez à votre site web de développement, sur lequel vous avez implémenté les balises.
3. Cliquez sur l’icône du débogueur Adobe Experience Cloud dans votre navigateur.
4. Si tout est correctement mis en oeuvre, le contenu doit s’afficher dans Adobe Analytics, les balises et le service d’identification des visiteurs Adobe Experience Cloud.

## Déployez votre mise en œuvre de développement vers l’évaluation/la production

Une fois que vous avez validé l’affichage des données, vous pouvez transmettre votre mise en oeuvre à la version en ligne de votre site.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise que vous prévoyez d’implémenter sur votre site.
1. Cliquez sur l’onglet **[!UICONTROL Publication]** et recherchez votre bibliothèque dans la colonne de développement.
1. Cliquez sur la liste déroulante de la bibliothèque, puis sélectionnez **[!UICONTROL Envoyer pour approbation]**. Cliquez sur **[!UICONTROL Envoyer]** dans la fenêtre modale.
1. Cliquez à nouveau sur la liste déroulante de la bibliothèque (maintenant dans la colonne Envoyé), puis sélectionnez **[!UICONTROL Créer pour l’évaluation]**.
1. Après quelques instants, la lumière jaune de la bibliothèque devient verte, ce qui indique une création réussie.
1. Cliquez à nouveau sur la liste déroulante de la bibliothèque, puis sélectionnez **[!UICONTROL Approuver pour publication]**.
1. Cliquez à nouveau sur la liste déroulante de la bibliothèque (maintenant dans la [!UICONTROL Approuvé] ), puis sélectionnez **[!UICONTROL Création et publication en production]**.
1. Accédez à l’onglet Environnements, puis cliquez sur **[!UICONTROL Environnement de production]**.
1. Copiez le code d’installation de production et fournissez-le aux propriétaires de votre site web. Demandez-leur de mettre en œuvre ce code dans l’environnement de production de votre site.

## Validation de votre mise en œuvre de production

Confirmez que vous voyez des données sur la version en direct de votre site et commencez la collecte officielle des données pour Adobe Analytics.

1. Une fois que vous avez confirmé auprès des propriétaires de votre site web qu’ils ont envoyé le code des balises en production, accédez à la page d’accueil de votre site web dans Chrome et ouvrez [!UICONTROL Adobe Experience Cloud debugger].
2. Si tout fonctionne correctement, vous devriez voir des données similaires à vos tests dans votre environnement de développement. À ce stade, vous collectez maintenant des données sur votre site et vous pouvez maintenant commencer à utiliser Adobe Analytics pour la création de rapports.

## Résolution des problèmes

**Aucune donnée n’apparaît dans le débogueur**.

Sur votre site, ouvrez la console de développement du navigateur (généralement F12). Examinez le code source de la page et assurez-vous que les conditions suivantes sont remplies :

* Il n’y a aucune erreur JavaScript dans la console. Consultez les propriétaires du site web de votre organisation pour vous assurer que toutes les erreurs JS sont résolues.
* Le code d’en-tête est correctement mis en œuvre : assurez-vous que le code d’en-tête se trouve à l’intérieur de la balise `<head>` et que le fichier existe.
* La bibliothèque AppMeasurement existe : accédez directement à la source JS pour vous assurer que le fichier JS contient du code. Dans le cas contraire, assurez-vous que chaque environnement est créé et que la bibliothèque est publiée dans son environnement respectif.
* Interfération d’extensions : Certaines extensions, telles que les bloqueurs d’annonces publicitaires, peuvent empêcher les demandes d’image de se déclencher. Désactivez toutes les extensions qui peuvent empêcher l’envoi de données à Adobe.

## Étapes suivantes

Maintenant qu’une implémentation de base est configurée, votre rôle au sein de votre organisation peut influencer le chemin sur lequel vous souhaitez davantage d’informations :

* [Création d’un document de conception de solution](../prepare/solution-design.md) : planifier l’utilisation des variables personnalisées, puis les intégrez à votre mise en œuvre
* [Prise en main de l’utilisation d’Analysis Workspace](/help/analyze/analysis-workspace/home.md) : passer directement à Adobe Analytics à l’aide de la fonctionnalité phare de l’outil.
