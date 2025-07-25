---
description: Le transfert côté serveur est conçu pour les clients qui souhaitent partager des données Analytics avec d’autres solutions Experience Cloud en temps réel. Une fois activé, le transfert côté serveur permet également à Analytics de transmettre des données vers d’autres solutions Experience Cloud et à ces solutions de transmettre des données à Analytics au cours du processus de collecte de données.
solution: Analytics
title: Transfert côté serveur - Aperçu
feature: Report Suite Settings
exl-id: e3cd72d2-9588-4770-a7c2-64b13a1e9519
role: Admin
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Transfert côté serveur - Aperçu

Le transfert côté serveur est conçu pour les clients qui souhaitent partager des données Analytics avec d’autres solutions Experience Cloud en temps réel. Une fois activé, le transfert côté serveur permet également à Analytics de transmettre des données vers d’autres solutions Experience Cloud et à ces solutions de transmettre des données à Analytics au cours du processus de collecte de données.

Le transfert côté serveur améliore la collecte de données car :

* Il réduit les appels provenant de la page. Avec la redirection côté serveur, les clients [!DNL Audience Manager] n’ont plus à utiliser le code DIL pour la collecte des données, car celles-ci sont transférées à partir d’Analytics. La suppression de code DIL implique l’élimination d’un appel `"/event"`. La diminution des appels permet d’améliorer le temps de chargement des pages, ce qui améliore l’expérience des clients sur votre site.
* Il permet de bénéficier du partage de données entre les solutions Experience Cloud.
* Il est conforme à nos bonnes pratiques relatives à l’implémentation et au déploiement du code d’Audience Manager.

>[!TIP]
>
>Les clients existants d’Audience Manager qui utilisent Analytics doivent migrer vers le transfert côté serveur. Les nouveaux clients d’Adobe Analytics et d’Audience Manager doivent implémenter le transfert côté serveur (au lieu de la collecte de données côté client (DIL)) comme méthode de collecte et de transfert de données par défaut.

>[!IMPORTANT]
>Conformément à la réglementation européenne sur les cookies, les sous-traitants de données (clientèle Analytics) ont maintenant la possibilité de restreindre les données de pré-consentement à Adobe Analytics et d’empêcher qu’elles ne soient transférées côté serveur à Adobe Audience Manager. Une nouvelle variable contextuelle de mise en œuvre permet d’identifier les accès pour lesquels aucun consentement n’a été reçu. La variable, une fois définie, empêche l’envoi de ces accès vers Adobe Audience Manager jusqu’à réception du consentement. Pour plus d’informations, voir [Conformité au RGPD et à la directive vie privée et communications électroniques et transfert côté serveur](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-gdpr.md).

Pour comprendre où se situe votre organisation en termes d’implémentation du transfert côté serveur, suivez les étapes de validation suivantes :

## ![image step1_icon.png](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step1_icon.png) Vérifiez l’implémentation du service ECID

Vérifiez si le service Experience Cloud ID (ECID) est implémenté en examinant la [demande de suivi Analytics](https://experienceleague.adobe.com/docs/id-service/using/implementation/test-verify.html?lang=fr).

Dans l’onglet Requête, vérifiez qu’une valeur ECID est en cours de définition. Cela vous indique si le service d’identité est correctement implémenté, ce qui est une condition requise du transfert côté serveur.

* Si vous voyez une valeur ECID, passez à l’étape 2.
* Si vous ne voyez pas de valeur ECID, [implémentez Identity Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html?lang=fr) avant de passer à l’étape 2.

## ![image step2_icon.png](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step2_icon.png) Vérification de la version de l’implémentation du transfert côté serveur

Vérifiez si une version du transfert côté serveur est déjà implémentée en [examinant la demande de suivi Analytics](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-verify.md).

Dans l’onglet « Réponse », vérifiez que la réponse contient les données d’Audience Manager. Si vous voyez :

* Une **réponse JSON provenant d’Audience Manager qui inclut des éléments tels que « postbacks » ou « dcs_region »**, alors une version du transfert côté serveur est déjà activée. Passez à l’étape 3.
* **« status »:« SUCCESS »** : le module de gestion de l’audience est implémenté, mais le transfert côté serveur n’est pas correctement configuré. Passez à l’étape 3.
* Une **image 2 x 2** : ni le transfert côté serveur, ni le module de gestion de l’audience ne sont implémentés. Pour résoudre ce problème :

   * **Clientèle Adobe Audience Manager avec DIL** : coordonnez étroitement les deux éléments suivants :

      1. Supprimez le code DIL et installez le code de la page du [module de gestion de l’audience](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=fr).
      1. Activez le transfert côté serveur dans l’interface utilisateur d’administration d’Analytics comme décrit à l’étape 3. L’activation de ce paramètre avant la suppression du code DIL duplique les données et crée des appels serveur facturés supplémentaires à Audience Manager.

   * **Nouvelle clientèle Adobe Audience Manager** : installez le code de page [Module de gestion de l’audience](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=fr) et passez à l’étape 3. Les données ne sont pas envoyées à Audience Manager tant que le transfert côté serveur n’est pas activé à l’étape 3.

## ![image step3_icon.png](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step3_icon.png) Vérification de l’implémentation du transfert côté serveur de la suite de rapports

Vérifiez si le transfert côté serveur est implémenté au niveau des suites de rapports. L’approche par suite de rapports est préférable à l’approche par serveur de suivi hérité.

Le transfert côté serveur au niveau des suites de rapports est recommandé par rapport à l’approche par serveur de suivi hérité car vous pouvez contrôler à un niveau plus fin les données qui sont partagées à partir d’Analytics. Il s’agit également d’une condition requise de l’intégration d’Audience Analytics.

Accédez à **Analytics** > **Admin** > **Suites de rapports** > (sélectionnez des **suites de rapports**) > **Modifier les paramètres** > **Général** > **Transfert côté serveur**. Si la case à cocher est :

* **Inactive** (vous ne pouvez pas effectuer de sélection ou le menu n’existe pas) : les suites de rapports sélectionnées ne sont pas mappées à un ID d’organisation. Contactez l’assistance clientèle pour vous assurer que la suite de rapports est correctement mappée.
* **Désactivée** : le nouveau transfert côté serveur n’est pas activé. Lisez le contenu de la page, puis procédez à l’activation de la fonctionnalité.
* **Activée** : le nouveau transfert côté serveur est activé. Vous pouvez également configurer l’intégration d’Audience Analytics.

>[!NOTE]
>
>Les données n’apparaîtront pas dans les autres solutions Experience Cloud telles qu’[Audience Manager](https://docs.adobe.com/content/help/fr-FR/experience-cloud/user-guides/home.html) ou [Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=fr) tant que les 3 étapes ne sont pas terminées. Après leur activation, comptez plusieurs heures avant que ces paramètres ne prennent effet.
