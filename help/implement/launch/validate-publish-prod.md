---
title: Validation de la mise en œuvre d’un développement et publication en production
description: Découvrez comment utiliser les balises Adobe Experience Platform pour déployer Adobe Analytics dans votre environnement de production.
exl-id: 2f5bcfee-d75e-4dac-bea9-91c6cc545173
source-git-commit: 5368e808a862a3e320f5d079433db96ab79b45c8
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 64%

---

# Validation de la mise en œuvre d’un développement et publication en production

Une fois votre bibliothèque de balises envoyée en production, votre entreprise peut commencer à utiliser Adobe Analytics pour extraire des rapports de base.

>[!NOTE]
>Adobe Experience Platform Launch a été rebaptisé en tant que suite de technologies de collecte de données dans Experience Platform. Plusieurs modifications terminologiques ont par conséquent été apportées à la documentation du produit. Reportez-vous au [document](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) suivant pour consulter une référence consolidée des modifications terminologiques.

## Conditions préalables

[Déployez votre mise en œuvre d’Analytics dans votre environnement de développement](deploy-dev.md) : une mise en œuvre d’Analytics doit être publiée dans votre environnement de développement pour suivre cette page.

## Validez votre mise en œuvre de développement à l’aide du débogueur Experience Cloud.

Le débogueur Experience Cloud est un plug-in Chrome qui affiche toutes les balises Experience Cloud présentes sur une page.

1. Ouvrez [le navigateur web Chrome](https://www.google.com/intl/fr/chrome/) et accédez à [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) sur le Chrome Web Store pour installer l’extension.
2. Accédez au site web de développement sur lequel vous avez implémenté des balises.
3. Cliquez sur l’icône d’Adobe Experience Cloud Debugger dans l’angle supérieur droit de Chrome.
4. Si tout est correctement mis en oeuvre, le contenu doit s’afficher dans Adobe Analytics, les balises et le service d’identification des visiteurs Adobe Experience Cloud :

![débogueur][assets/debugger.png]

## Déployez votre mise en œuvre de développement vers l’évaluation/la production

Une fois que vous avez validé les données affichées, vous pouvez transmettre votre mise en œuvre à la version en direct de votre site.

1. Accédez à [experience.adobe.com](https://experience.adobe.com) et connectez-vous lorsque vous y êtes invité.
1. Sélectionnez **[!UICONTROL Lancer / Collecte de données]**.
1. Cliquez sur **[!UICONTROL Aller à Launch / Collecte de données]**, puis sélectionnez **[!UICONTROL Balises]**.
1. Cliquez sur la propriété de balise que vous avez l’intention d’implémenter sur votre site.
1. Cliquez sur l’onglet **[!UICONTROL Publication]** et localisez votre bibliothèque dans la colonne de développement.
1. Cliquez sur la liste déroulante de la bibliothèque, puis sélectionnez **[!UICONTROL Soumettre pour approbation]**. Cliquez sur **[!UICONTROL Envoyer]** dans la fenêtre modale.
1. Cliquez à nouveau sur la liste déroulante de la bibliothèque (maintenant dans la colonne Envoyé), puis sélectionnez **[!UICONTROL Créer pour l’évaluation]**.
1. Après quelques instants, la lumière jaune de la bibliothèque devient verte, ce qui indique une création réussie.
1. Cliquez à nouveau sur la liste déroulante de la bibliothèque, puis sélectionnez **[!UICONTROL Approuver pour publication]**.
1. Cliquez à nouveau sur la liste déroulante de la bibliothèque (maintenant dans la colonne [!UICONTROL Approuvé]), puis sélectionnez **[!UICONTROL Créer et publier en production]**.
1. Accédez à l’onglet Environnements , puis cliquez sur **[!UICONTROL Environnement de production]**.
1. Copiez le code d’en-tête de production + de pied de page et communiquez-le aux propriétaires de votre site web. Demandez-leur de mettre en œuvre ce code dans l’environnement de production de votre site.

## Validation de votre mise en œuvre de production

Confirmez que vous voyez des données sur la version en direct de votre site et commencez la collecte officielle des données pour Adobe Analytics.

1. Une fois que vous avez confirmé auprès des propriétaires de votre site web qu’ils ont envoyé le code de balise en production, accédez à la page d’accueil de votre site web dans Chrome et ouvrez le [!UICONTROL débogueur Adobe Experience Cloud].
2. Si tout fonctionne correctement, vous devriez voir des données similaires à vos tests dans votre environnement de développement. À ce stade, vous collectez maintenant des données sur votre site et vous pouvez maintenant commencer à utiliser Adobe Analytics pour la création de rapports.

## Résolution des problèmes

**Aucune donnée n’apparaît dans le débogueur**.

Sur votre site, ouvrez la console de développement du navigateur (généralement F12). Examinez le code source de la page et assurez-vous que les conditions suivantes sont remplies :

* Il n’y a aucune erreur JavaScript dans la console. Consultez les propriétaires du site web de votre organisation pour vous assurer que toutes les erreurs JS sont résolues.
* Le code d’en-tête est correctement mis en œuvre : assurez-vous que le code d’en-tête se trouve à l’intérieur de la balise `<head>` et que le fichier existe.
* La bibliothèque AppMeasurement existe : accédez directement à la source JS pour vous assurer que le fichier JS contient du code. Dans le cas contraire, assurez-vous que chaque environnement est créé et que la bibliothèque est publiée dans son environnement respectif.
* Plug-ins d’interférence : certains plug-ins Chrome peuvent empêcher les demandes d’images de s’exécuter. Désactivez les plug-ins susceptibles d’empêcher l’envoi de données aux serveurs d’Adobe.

## Étapes suivantes

Maintenant qu’une implémentation de base est configurée, votre rôle au sein de votre organisation peut influencer le chemin sur lequel vous souhaitez davantage d’informations :

* [Création d’un document de conception de solution](../prepare/solution-design.md) : planifier l’utilisation des variables personnalisées, puis les intégrez à votre mise en œuvre
* [Prise en main de l’utilisation d’Analysis Workspace](/help/analyze/analysis-workspace/home.md) : passer directement à Adobe Analytics à l’aide de la fonctionnalité phare de l’outil.
