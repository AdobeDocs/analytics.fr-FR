---
description: Le transfert côté serveur est conçu pour les clients qui souhaitent partager en temps réel des données d’Analytics vers d’autres solutions Experience Cloud. Lorsqu’il est activé, le transfert côté serveur permet également à Analytics de transmettre des données à d’autres solutions Experience Cloud et à ces solutions de transmettre des données à Analytics pendant le processus de collecte des données.
solution: Audience Manager
title: Transfert côté serveur - Aperçu
uuid: 22ddbde5-6805-4eba-8f82-62772644dcaa
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Transfert côté serveur - Aperçu

Le transfert côté serveur est conçu pour les clients qui souhaitent partager en temps réel des données d’Analytics vers d’autres solutions Experience Cloud. Lorsqu’il est activé, le transfert côté serveur permet également à Analytics de transmettre des données à d’autres solutions Experience Cloud et à ces solutions de transmettre des données à Analytics pendant le processus de collecte des données.

Le transfert côté serveur améliore la collecte des données, car il permet :

* Réduit les appels de la page. Avec la redirection côté serveur, les clients [!DNL Audience Manager] n’ont plus à utiliser le code DIL pour la collecte des données, car celles-ci sont transférées à partir d’Analytics. La suppression de code DIL implique l’élimination d’un appel `"/event"`. Un nombre moins élevé d’appels permet d’améliorer les temps de chargement des pages, ce qui améliore la satisfaction des clients sur votre site.
* Vous permet de tirer parti du partage de données entre les solutions Experience Cloud.
* Conforme à nos meilleures pratiques pour  l’implémentation et le déploiement du code  Manager.

>[!TIP]
>
>Les clients existants d’Audience Manager qui utilisent Analytics doivent migrer vers le transfert côté serveur. Les nouveaux clients d’Adobe Analytics et d’Audience Manager doivent implémenter le transfert côté serveur (au lieu de la collecte de données côté client (DIL)) comme méthode de collecte et de transfert de données par défaut.

>[!IMPORTANT]
>Conformément à la réglementation européenne sur les cookies, les responsables du traitement (clients Analytics) ont maintenant la possibilité de restreindre les données de pré-consentement à Adobe Analytics et d’empêcher qu’elles ne soient transférées côté serveur à Adobe Audience Manager (AAM). Une nouvelle variable de contexte d’implémentation vous permet d’indiquer les accès pour lesquels le consentement n’a pas été reçu. Une fois définie, la variable empêche l’envoi de ces accès vers AAM jusqu’à réception du consentement. For more information, see [GDPR_ePrivacy compliance and server-side forwarding](/help/admin/admin/c-server-side-forwarding/ssf-gdpr.md).

Pour comprendre où se situe votre organisation en termes d’implémentation du transfert côté serveur, suivez les étapes de validation suivantes :

## ![image step1_icon.png](assets/step1_icon.png) Vérifiez l’implémentation du service ECID

Vérifiez si le service Experience Cloud ID (ECID) est implémenté en examinant la [demande de suivi Analytics](https://marketing.adobe.com/resources/help/fr_FR/mcvid/mcvid-test-verify.html).

Dans l’onglet Requête, vérifiez qu’une valeur ECID est en cours de définition. Cela vous indique si le service d’identité est correctement implémenté, ce qui est une condition requise du transfert côté serveur.

* Si vous voyez une valeur ECID, passez à l’étape 2.
* Si vous ne voyez pas de valeur ECID, [implémentez Identity Service](https://marketing.adobe.com/resources/help/fr_FR/mcvid/mcvid-implementation-guides.html) avant de passer à l’étape 2.

## ![image step2_icon.png](assets/step2_icon.png) Vérification de la version de l’implémentation du transfert côté serveur

Vérifiez si une version du transfert côté serveur est déjà implémentée en [examinant la demande de suivi Analytics](/help/admin/admin/c-server-side-forwarding/ssf-verify.md).

Dans l’onglet « Réponse », vérifiez que la réponse contient les données d’Audience Manager. Si vous voyez :

* Une **réponse JSON provenant d’Audience Manager qui inclut des éléments tels que « postbacks » ou « dcs_region »**, alors une version du transfert côté serveur est déjà activée. Passez à l’étape 3.
* **« status »:« SUCCESS »** : le module de gestion de l’audience est implémenté, mais le transfert côté serveur n’est pas correctement configuré. Passez à l’étape 3.
* Image **** 2 x 2 : le transfert côté serveur ou le module de gestion  n’est pas mis en oeuvre. Pour corriger :

   * **Clients AAM avec DIL**: coordonnez étroitement les deux éléments suivants :

      1. Supprimez le code DIL et installez le code de page du module [de gestion des ](https://docs.adobe.com/content/help/fr-FR/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html) .
      1. Activez le transfert côté serveur dans l’interface utilisateur d’administration d’Analytics, comme décrit à l’étape 3. L’activation de ce paramètre avant de supprimer le code DIL va les données et créer des appels serveur facturés supplémentaires à  Gestionnaire de  de.
   * **Nouveaux clients** AAM : installez le code de page du module [de gestion des ](https://docs.adobe.com/content/help/fr-FR/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html) et continuez l’étape 3. Les données ne seront pas envoyées à  Gestionnaire  de tant que le transfert côté serveur n’est pas activé à l’étape 3.


## ![image step3_icon.png](assets/step3_icon.png) Vérification de l’implémentation du transfert côté serveur de la suite de rapports

Vérifiez si le transfert côté serveur est implémenté au niveau de la suite de rapports, plutôt que l’approche de serveur de suivi héritée.

Le transfert côté serveur au niveau de la suite de rapports est recommandé par rapport à l’approche serveur de suivi héritée car vous pouvez contrôler à un niveau plus précis les données qui sont partagées à partir d’Analytics. Il s’agit également d’une condition préalable à cette intégration   Analytics.

Accédez à **Analytics** > **Admin** > **Suites de rapports** > (sélectionnez des **suites de rapports**) > **Modifier les paramètres** > **Général** > **Transfert côté serveur**. Si la case à cocher est :

* **Inactive** (vous ne pouvez pas effectuer de sélection ou le menu n’existe pas) : les suites de rapports sélectionnées ne sont pas mappées à votre organisation IMS. Assurez-vous que les suites de rapports applicables sont mappées à l’organisation Experience Cloud appropriée à l’aide de [l’interface utilisateur de mappage des suites de rapports](https://docs.adobe.com/content/help/fr-FR/core-services/interface/about-core-services/report-suite-mapping.html).
* **Désactivé**: Le nouveau transfert côté serveur n’est pas activé. Lisez le contenu de la page, puis passez à l’activation de la fonctionnalité.
* **Activé**: Vous êtes configuré pour le nouveau transfert côté serveur. Vous pouvez également configurer cette  d’intégration  Analytics.

>[!NOTE] Les données n’apparaîtront pas dans les autres solutions Experience Cloud telles qu’[Audience Manager](https://docs.adobe.com/content/help/fr-FR/audience-manager/user-guide/aam-home.html) ou [Audiences](https://marketing.adobe.com/resources/help/fr_FR/mcloud/audience_library.html) tant que les 3 étapes ne sont pas terminées. Après leur activation, comptez plusieurs heures avant que ces paramètres ne prennent effet.

