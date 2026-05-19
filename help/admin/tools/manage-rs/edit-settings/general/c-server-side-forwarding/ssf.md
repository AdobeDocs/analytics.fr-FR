---
description: Le transfert côté serveur est conçu pour les clients qui souhaitent partager des données d’Analytics vers d’autres solutions d’entreprise CX en temps réel. Lorsqu’il est activé, le transfert côté serveur permet également à Analytics d’envoyer les données vers d’autres solutions d’entreprise CX et, pour ces solutions, d’envoyer les données vers Analytics pendant le processus de collecte de données.
solution: Analytics
title: Transfert côté serveur - Aperçu
feature: Report Suite Settings
exl-id: e3cd72d2-9588-4770-a7c2-64b13a1e9519
role: Admin
TQID: https://experienceleague.adobe.com/O03-5Ovxy3Lq-LZjPOseTpOlCXaS1kwD8n2ZM1yJuxY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 887
ht-degree: 84%

---

# Transfert côté serveur - Aperçu

Le transfert côté serveur est conçu pour les clients qui souhaitent partager des données d’Analytics vers d’autres solutions d’entreprise CX en temps réel. Lorsqu’il est activé, le transfert côté serveur permet également à Analytics d’envoyer les données vers d’autres solutions d’entreprise CX et, pour ces solutions, d’envoyer les données vers Analytics pendant le processus de collecte de données.

Le transfert côté serveur améliore la collecte de données car :

* Il réduit les appels provenant de la page. Avec la redirection côté serveur, les clients [!DNL Audience Manager] n’ont plus à utiliser le code DIL pour la collecte des données, car celles-ci sont transférées à partir d’Analytics. La suppression de code DIL implique l’élimination d’un appel `"/event"`. La diminution des appels permet d’améliorer le temps de chargement des pages, ce qui améliore l’expérience des clients sur votre site.
* Vous permet de tirer parti du partage de données entre les solutions d’entreprise CX.
* Il est conforme à nos bonnes pratiques relatives à l’implémentation et au déploiement du code d’Audience Manager.

>[!TIP]
>
>Les clients existants d’Audience Manager qui utilisent Analytics doivent migrer vers le transfert côté serveur. Les nouveaux clients d’Adobe Analytics et d’Audience Manager doivent implémenter le transfert côté serveur (au lieu de la collecte de données côté client (DIL)) comme méthode de collecte et de transfert de données par défaut.

>[!IMPORTANT]
>Conformément à la réglementation européenne sur les cookies, les sous-traitants de données (clientèle Analytics) ont maintenant la possibilité de restreindre les données de pré-consentement à Adobe Analytics et d’empêcher qu’elles ne soient transférées côté serveur à Adobe Audience Manager. Une nouvelle variable contextuelle de mise en œuvre permet d’identifier les accès pour lesquels aucun consentement n’a été reçu. La variable, une fois définie, empêche l’envoi de ces accès vers Adobe Audience Manager jusqu’à réception du consentement. Pour plus d’informations, voir [Conformité au RGPD et à la directive vie privée et communications électroniques et transfert côté serveur](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-gdpr.md).

Pour comprendre où se situe votre organisation en termes d’implémentation du transfert côté serveur, suivez les étapes de validation suivantes :

## ![image step1_icon.png](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/assets/step1_icon.png) Vérifiez l’implémentation du service ECID

Vérifiez si le service Experience Cloud ID (ECID) est implémenté en examinant la [demande de suivi Analytics](https://experienceleague.adobe.com/docs/id-service/using/implementation/test-verify.html?lang=fr).

Dans l’onglet Requête, vérifiez qu’une valeur ECID est en cours de définition. Cela vous indique si le service d’identité est correctement implémenté, ce qui est une condition requise du transfert côté serveur.

* Si vous voyez une valeur ECID, passez à l’étape 2.
* Si vous ne voyez pas de valeur ECID, [implémentez Identity Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html?lang=fr) avant de passer à l’étape 2.

## ![image step2_icon.png](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/assets/step2_icon.png) Vérification de la version de l’implémentation du transfert côté serveur

Vérifiez si une version du transfert côté serveur est déjà implémentée en [examinant la demande de suivi Analytics](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-verify.md).

Dans l’onglet « Réponse », vérifiez que la réponse contient les données d’Audience Manager. Si vous voyez :

* Une **réponse JSON provenant d’Audience Manager qui inclut des éléments tels que « postbacks » ou « dcs_region »**, alors une version du transfert côté serveur est déjà activée. Passez à l’étape 3.
* **« status »:« SUCCESS »** : le module de gestion de l’audience est implémenté, mais le transfert côté serveur n’est pas correctement configuré. Passez à l’étape 3.
* Une **image 2 x 2** : ni le transfert côté serveur, ni le module de gestion de l’audience ne sont implémentés. Pour résoudre ce problème :

   * **Clientèle Adobe Audience Manager avec DIL** : coordonnez étroitement les deux éléments suivants :

      1. Supprimez le code DIL et installez le code de la page du [module de gestion de l’audience](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=fr).
      1. Activez le transfert côté serveur dans l’interface utilisateur d’administration d’Analytics comme décrit à l’étape 3. L’activation de ce paramètre avant la suppression du code DIL duplique les données et crée des appels serveur facturés supplémentaires à Audience Manager.

   * **Nouvelle clientèle Adobe Audience Manager** : installez le code de page [Module de gestion de l’audience](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=fr) et passez à l’étape 3. Les données ne sont pas envoyées à Audience Manager tant que le transfert côté serveur n’est pas activé à l’étape 3.

## ![image step3_icon.png](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/assets/step3_icon.png) Vérification de l’implémentation du transfert côté serveur de la suite de rapports

Vérifiez si le transfert côté serveur est implémenté au niveau des suites de rapports. L’approche par suite de rapports est préférable à l’approche par serveur de suivi hérité.

Le transfert côté serveur au niveau des suites de rapports est recommandé par rapport à l’approche par serveur de suivi hérité car vous pouvez contrôler à un niveau plus fin les données qui sont partagées à partir d’Analytics. Il s’agit également d’une condition requise de l’intégration d’Audience Analytics.

Accédez à **Analytics** > **Admin** > **Suites de rapports** > (sélectionnez des **suites de rapports**) > **Modifier les paramètres** > **Général** > **Transfert côté serveur**. Si la case à cocher est :

* **Inactive** (vous ne pouvez pas effectuer de sélection ou le menu n’existe pas) : les suites de rapports sélectionnées ne sont pas mappées à un ID d’organisation. Contactez l’assistance clientèle pour vous assurer que la suite de rapports est correctement mappée.
* **Désactivée** : le nouveau transfert côté serveur n’est pas activé. Lisez le contenu de la page, puis procédez à l’activation de la fonctionnalité.
* **Activée** : le nouveau transfert côté serveur est activé. Vous pouvez également configurer l’intégration d’Audience Analytics.

>[!NOTE]
>
>Les données n’apparaîtront pas dans d’autres solutions d’entreprise CX, telles que [](https://docs.adobe.com/content/help/fr-FR/experience-cloud/user-guides/home.html) ou [Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=fr) tant que les 3 étapes ne seront pas terminées. Après leur activation, comptez plusieurs heures avant que ces paramètres ne prennent effet.
