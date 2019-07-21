---
description: Le transfert côté serveur est conçu pour les clients qui souhaitent partager des données Analytics avec d’autres solutions Experience Cloud en temps réel. Une fois activé, le transfert côté serveur permet également à Analytics de transmettre des données vers d’autres solutions Experience Cloud et à ces solutions de transmettre des données à Analytics au cours du processus de collecte de données.
seo-description: Le transfert côté serveur est conçu pour les clients qui souhaitent partager des données Analytics avec d’autres solutions Experience Cloud en temps réel. Une fois activé, le transfert côté serveur permet également à Analytics de transmettre des données vers d’autres solutions Experience Cloud et à ces solutions de transmettre des données à Analytics au cours du processus de collecte de données.
seo-title: Présentation du transfert côté serveur
solution: Audience Manager
title: Présentation du transfert côté serveur
uuid: 22 ddbde 5-6805-4 eba -8 f 82-62772644 dcaa
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Présentation du transfert côté serveur

Le transfert côté serveur est conçu pour les clients qui souhaitent partager des données Analytics avec d’autres solutions Experience Cloud en temps réel. Une fois activé, le transfert côté serveur permet également à Analytics de transmettre des données vers d’autres solutions Experience Cloud et à ces solutions de transmettre des données à Analytics au cours du processus de collecte de données.

Le transfert côté serveur améliore la collecte de données car :

* Il réduit les appels provenant de la page. With server-side forwarding, [!DNL Audience Manager] customers no longer need to use DIL for data collection because it is being forwarded from Analytics. Removing DIL means eliminating an `"/event"` call. La diminution des appels permet d’améliorer le temps de chargement des pages, ce qui améliore l’expérience des clients sur votre site.
* Il permet de bénéficier du partage de données entre les solutions Experience Cloud.
* Il est conforme à nos bonnes pratiques relatives à l’implémentation et au déploiement du code d’Audience Manager.

>[!TIP]
>
>Les clients Audience Manager actuels qui utilisent Analytics doivent migrer vers le transfert côté serveur. Les nouveaux clients d’Adobe Analytics et d’Audience Manager doivent implémenter le transfert côté serveur (au lieu de la collecte de données côté client (DIL)) comme méthode de collecte et de transfert de données par défaut.

>[!IMPORTANT]
>Conformément à la réglementation européenne sur les cookies, les responsables du traitement (clients Analytics) ont maintenant la possibilité de restreindre les données de pré-consentement à Adobe Analytics et d’empêcher qu’elles ne soient transférées côté serveur à Adobe Audience Manager (AAM). Une nouvelle variable contextuelle de mise en œuvre permet d’identifier les accès pour lesquels aucun consentement n’a été reçu. Une fois définie, la variable empêche l’envoi de ces accès vers AAM jusqu’à réception du consentement. Pour plus d’informations, voir Conformité au RGPD et à la 
directive vie privée et communications électroniques et transfert côté serveur.

Pour comprendre où se situe votre organisation en termes d’implémentation du transfert côté serveur, suivez les étapes de validation suivantes :

## ![étape 1_ icon. png Image](assets/step1_icon.png) Vérifier l'implémentation du service MID

Vérifiez si le service Experience Cloud ID (MID) est implémenté en examinant la [demande de suivi Analytics](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-test-verify.html).

Dans l’onglet Demande, vérifiez qu’une valeur MID est en cours de définition. Cela vous indique que le service d'identité est correctement mis en œuvre, c'est-à-dire une prérequis pour le transfert côté serveur.

* Si vous voyez une valeur MID, passez à l’étape 2.
* If you do not see a MID value, [implement Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html) before proceeding to step 2.

## ![step 2_ icon. png image](assets/step2_icon.png) Vérification du transfert côté serveur de la mise en œuvre

Verify whether you already have a version of server-side forwarding implemented, by [inspecting the Analytics tracking request](../../../admin/admin/c-server-side-forwarding/ssf-verify.md).

Dans l’onglet « Réponse », vérifiez que la réponse contient les données d’Audience Manager. Si vous voyez :

* Une **réponse JSON provenant d’Audience Manager qui inclut des éléments tels que "postbacks" ou "dcs_region"**, alors une version du transfert côté serveur est déjà activée. Passez à l’étape 3.
* **"status":"SUCCESS"** : le module de gestion de l’audience est implémenté, mais le transfert côté serveur n’est pas correctement configuré. Passez à l’étape 3.
* Une **image 2 x 2** : ni le transfert côté serveur, ni le module de gestion de l’audience ne sont implémentés. Pour résoudre ce problème :

   * **Clients du module de gestion de l’audience (AAM) avec collecte de données côté client (DIL)** : coordonnez les deux éléments suivants en conjonction étroite :

      1. Supprimez le code DIL et installez le code de la page du [module de gestion de l’audience](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html).
      1. Activez le transfert côté serveur dans l’interface utilisateur d’administration d’Analytics comme décrit à l’étape 3. L’activation de ce paramètre avant la suppression du code DIL duplique les données et crée des appels serveur facturés supplémentaires à Audience Manager.
   * **Nouveaux clients du module de gestion de l’audience (AAM)** : installez la page de code du [module de gestion de l’audience](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html) et passez à l’étape 3. Les données ne sont pas envoyées à Audience Manager tant que le transfert côté serveur n’est pas activé à l’étape 3.


## ![image 3_ icon. png Image](assets/step3_icon.png) Vérifier l'implémentation du transfert côté serveur de la suite de rapports

Vérifiez si le transfert côté serveur est implémenté au niveau des suites de rapports. L’approche par suite de rapports est préférable à l’approche par serveur de suivi hérité.

Le transfert côté serveur au niveau des suites de rapports est recommandé par rapport à l’approche par serveur de suivi hérité car vous pouvez contrôler à un niveau plus fin les données qui sont partagées à partir d’Analytics. Il s’agit également d’une condition requise de l’intégration d’Audience Analytics.

Go to **Analytics** &gt; **Admin** &gt; **Report Suites** &gt; (select **report suites**) &gt; **Edit Settings** &gt; **General** &gt; **Server Side Forwarding**. Si la case à cocher est :

* **Inactive** (vous ne pouvez pas effectuer de sélection ou le menu n’existe pas) : les suites de rapports sélectionnées ne sont pas mappées à votre organisation IMS. Assurez-vous que les suites de rapports applicables sont mappées à l’organisation IMS appropriée à l’aide de [l’interface utilisateur de mappage des suites de rapports](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).
* **Désactivée** : le nouveau transfert côté serveur n’est pas activé. Lisez le contenu de la page, puis procédez à l’activation de la fonctionnalité.
* **Activée** : le nouveau transfert côté serveur est activé. Vous pouvez également configurer l’intégration d’Audience Analytics.

<!-- Meike, check Report Suite Mapping UI link above -->

>[!NOTE]
>
>Data will not appear in other Experience Cloud solutions, such as [Audience Manager](https://marketing.adobe.com/resources/help/en_US/aam/c_aam_home.html) or [Audiences](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html) until all 3 steps are complete. Après leur activation, comptez plusieurs heures avant que ces paramètres ne prennent effet.

