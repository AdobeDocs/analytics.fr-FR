---
product: analytics
audience: admin
user-guide-title: Guide de lʼadministrateur dʼAnalytics
breadcrumb-title: Guide de l’administrateur
user-guide-description: Découvrez les tâches dʼadministration dans Analytics, qui vous permettent entre autres de gérer les utilisateurs et les produits dans Experience Cloud Admin Console, de configurer des suites de rapports et bien plus encore.
source-git-commit: 35675c2e65456a175d1516dd421b80d2af809286
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 99%

---


# Guide de lʼadministrateur d’Adobe Analytics {#admin}

+ [Guide d’administration d’Analytics](home.md)
+ [Notes de mise à jour d’Analytics](https://experienceleague.adobe.com/fr/docs/analytics/release-notes/latest)
+ Adobe Admin Console {#admin-console}
   + [Vue d’ensemble](admin-console/home.md)
   + [Guide Adobe Analytics pour le premier administrateur](admin-console/first-admin-guide.md)
   + [Rôles d’administrateur dans Adobe Analytics](admin-console/admin-roles-in-analytics.md)
   + Résumé des autorisations pour les outils Analytics {#permissions}
      + [Profils de produit pour Adobe Analytics](admin-console/permissions/product-profile.md)
      + [Autorisations du profil de produit pour les outils de suites de rapports](admin-console/permissions/report-suite-tools.md)
      + [Autorisations du profil de produit pour les outils Analytics](admin-console/permissions/analytics-tools.md)
+ Outils d’administration Analytics {#admin-tools}
   + [Vue d’ensemble des outils d’administration](tools/c-admin-tools.md)
   + [Gestionnaire de code](tools/code-manager-admin.md)
   + [Inventaire Analytics](tools/analytics-inventory.md)
   + [Sources de données](tools/data-sources.md)
   + [Exclure par adresse IP](tools/exclude-ip.md)
   + [Journaux](tools/logs.md)
   + Gestionnaire des activités de rapport {#reporting-activity-manager}
      + [Vue d’ensemble](tools/reporting-activity-manager/reporting-activity-overview.md)
      + [Afficher l’activité de rapport](tools//reporting-activity-manager/reporting-activity.md)
      + [Annuler des demandes de création de rapports](tools/reporting-activity-manager/reporting-activity-cancel-requests.md)
   + Migration des composants {#component-migration}
      + [Se préparer à la migration](tools/component-migration/prepare-component-migration.md)
      + [Workflow de migration](tools/component-migration/component-migration.md)
   + Gestionnaire de suites de rapports {#manage-report-suites}
      + Modifier les paramètres d’une suite de rapports {#edit-report-suite}
         + Général {#report-suite-general}
            + [Paramètres du compte général](tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)
            + [Filtres URL internes](tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)
            + [Personnaliser le calendrier](tools/manage-rs/edit-settings/general/custom-calendar.md)
            + Détection de recherche payante {#paid-search-detection}
               + [Détection de référencement payant - Aperçu](tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md)
               + [Configuration de la détection de référencement payant](tools/manage-rs/edit-settings/general/paid-search-detection/t-paid-search-detection.md)
            + Règles de traitement {#processing-rules}
               + [Vue d’ensemble](tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)
               + [Interface](tools/manage-rs/edit-settings/general/processing-rules/pr-interface.md)
               + [Afficher l’historique](tools/manage-rs/edit-settings/general/processing-rules/pr-view-history.md)
               + [Copier des règles](tools/manage-rs/edit-settings/general/processing-rules/pr-copy.md)
               + [Dimensions et mesures disponibles](tools/manage-rs/edit-settings/general/processing-rules/pr-variables.md)
               + [Cas d’utilisation](tools/manage-rs/edit-settings/general/processing-rules/pr-use-cases.md)
            + Règles de robots {#bot-removal}
               + [Suppression de robots](tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md)
               + [Comprendre et configurer des règles de robot](tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)
               + [Signatures de robots courantes](tools/manage-rs/edit-settings/general/bot-removal/bot-signatures.md)
               + [Méthodes d’exclusion de robots](tools/manage-rs/edit-settings/general/bot-removal/bot-exclusion-methods.md)
            + [Paramètres de confidentialité](tools/manage-rs/edit-settings/general/privacy-settings.md)
            + [Configuration des horodatages](tools/manage-rs/edit-settings/general/timestamp-configuration.md)
            + Transfert côté serveur {#server-side-forwarding}
               + [Transfert côté serveur - Aperçu](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)
               + [Conformité au RGPD et à la directive vie privée et communications électroniques, et transfert côté serveur](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-gdpr.md)
               + [Conditions requises pour le transfert côté serveur](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-requirements.md)
               + [Données et référence de code du transfert côté serveur](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-reference.md)
               + [Comment vérifier l’implémentation du transfert côté serveur](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-verify.md)
               + [Questions fréquentes relatives au transfert côté serveur](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-faq.md)
         + Trafic {#traffic-variables}
            + [Variables de trafic](tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)
            + [Classifications de trafic](tools/manage-rs/edit-settings/c-traffic-variables/traffic-classifications.md)
            + [Descriptions des rapports personnalisés](tools/manage-rs/edit-settings/c-traffic-variables/custom-desc-admin.md)
         + Conversion {#conversion-variables}
            + [Variables de conversion](tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md)
            + [Méthodes de recherche](tools/manage-rs/edit-settings/conversion-var-admin/finding-methods.md)
            + [Classifications des conversions](tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md)
            + Variable de visiteur unique {#unique-visitor-variable}
               + [Définir la variable de visiteur unique](tools/manage-rs/edit-settings/conversion-var-admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
               + [Scénario d’utilisation - Extraction d’ID de visiteur](tools/manage-rs/edit-settings/conversion-var-admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
            + [Événements de succès](tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md)
            + [Hiérarchies de classification](tools/manage-rs/edit-settings/conversion-var-admin/classification-hierarchies.md)
            + [Variables de liste](tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md)
            + [eVars de marchandisage](tools/manage-rs/edit-settings/conversion-var-admin/merchandising-evars.md)
         + Canaux marketing {#marketing-channels}
            + [Gestionnaire de canaux marketing](tools/manage-rs/edit-settings/marketing-channels/c-channels.md)
            + [Règles de traitement des canaux marketing](tools/manage-rs/edit-settings/marketing-channels/c-rules.md)
            + [Classifications de canaux marketing](tools/manage-rs/edit-settings/marketing-channels/classifications-mchannel.md)
            + [Expiration du canal marketing](tools/manage-rs/edit-settings/marketing-channels/visitor-engagement.md)
         + Gestion du trafic {#traffic-management}
            + [Vue d’ensemble](tools/manage-rs/edit-settings/c-traffic-management/traffic-management.md)
            + [Prévoir les pics](tools/manage-rs/edit-settings/c-traffic-management/t-traffic-schedule-spike.md)
            + [Trafic permanent](tools/manage-rs/edit-settings/c-traffic-management/t-traffic-permanent.md)
         + [Mesures par défaut](tools/manage-rs/edit-settings/default-metrics.md)
         + Gestion des applications {#app-management}
            + [Rapports d’application](tools/manage-rs/edit-settings/app-reporting.md)
            + [Classifications d’application](tools/manage-rs/edit-settings/app-classifications.md)
         + [Gestion des médias](tools/manage-rs/edit-settings/media-management.md)
         + [Activity Map](tools/manage-rs/edit-settings/activity-map.md)
         + [AEM](tools/manage-rs/edit-settings/adobe-experience-manager.md)
         + [Adobe Campaign](tools/manage-rs/edit-settings/adobe-campaign.md)
         + [Compte rendu des performances sur la confidentialité](tools/manage-rs/edit-settings/privacy-reporting.md)
         + Gestion de Document Cloud {#doc-cloud-mgt}
            + [Configurer Document Cloud avec Adobe Analytics](tools/manage-rs/edit-settings/document-cloud-mgt.md)
            + [Configurer les rapports de Document Cloud](tools/manage-rs/edit-settings/document-cloud-config.md)
         + [Configuration Advertising Analytics](tools/manage-rs/edit-settings/advertising-analytics-config.md)
         + Temps réel {#real-time-reports}
            + [Rapports en temps réel - Aperçu](tools/manage-rs/edit-settings/realtime/realtime.md)
            + [Configuration des rapports en temps réel](tools/manage-rs/edit-settings/realtime/t-realtime-admin.md)
            + [Mesures et dimensions en temps réel prises en charge](tools/manage-rs/edit-settings/realtime/realtime-metrics.md)
      + [Gérer les suites de rapports](tools/manage-rs/report-suites-admin.md)
      + [Suites de rapports globales](tools/manage-rs/rollup-report-suite.md)
      + [Enregistrer une recherche de suite de rapports](tools/manage-rs/t-report-suite-saved-search.md)
      + [Télécharger les paramètres d’une suite de rapports](tools/manage-rs/t-download-rs-settings.md)
      + Nouvelle suite de rapports {#c-new-report-suite}
         + [Créer une suite de rapports](tools/manage-rs/new-rs/t-create-a-report-suite.md)
         + [Créer un groupe de suites de rapports](tools/manage-rs/new-rs/t-create-rs-group.md)
         + [Paramètres d’une nouvelle suite de rapports](tools/manage-rs/new-rs/new-report-suite.md)
         + [Paramètres non copiés depuis une suite de rapports source](tools/manage-rs/new-rs/settings-not-copied-from-rs.md)
      + Modèles de suite de rapports {#report-suite-templates}
         + [Modèles de suite de rapports - Aperçu](tools/manage-rs/rs-templates/report-suite-templates.md)
         + [Portail d’agrégation](tools/manage-rs/rs-templates/aggregator-portal.md)
         + [Commerce](tools/manage-rs/rs-templates/commerce-admin.md)
         + [Contenu et média](tools/manage-rs/rs-templates/content-media.md)
         + [Modèle par défaut](tools/manage-rs/rs-templates/default-rs-template.md)
         + [Services financiers](tools/manage-rs/rs-templates/financial-services.md)
         + [Portail d’emploi](tools/manage-rs/rs-templates/job-portal.md)
         + [Génération de piste](tools/manage-rs/rs-templates/lead-generation.md)
         + [Média d’assistance](tools/manage-rs/rs-templates/support-media.md)
   + Paramètres de l’entreprise {#company-settings}
      + [Vue d’ensemble des paramètres d’entreprise](tools/company/c-company-settings.md)
      + [Gestionnaire de sécurité](tools/company/security-manager.md)
      + [Services web](tools/company/web-services-admin.md)
      + [Rapports du Report Builder](tools/company/report-builder-reports-admin.md)
      + [Authentification unique](tools/company/single-signon-admin.md)
      + [Masquer des suites de rapports](tools/company/c-hide-report-suites.md)
      + [Gestionnaire de préférences](tools/company/preferences-manager.md)
      + [Actions en attente](tools/company/pending-actions-admin.md)
      + [Niveaux d’accès aux fonctions](tools/company/feature-access-levels.md)
   + Étiquetage de confidentialité {#privacy-labeling}
      + [Vue d’ensemble](tools/privacy-labeling/labeling-overview.md)
      + [Étiquettes relatives à la confidentialité des données pour les composants Analytics](tools/privacy-labeling/labels.md)
      + [Affichage/gestion des étiquettes de confidentialité de la suite de rapports](tools/privacy-labeling/view-settings.md)
      + [Bonnes pratiques en matière d’étiquetage](tools/privacy-labeling/best-practices.md)
      + [Exemple d’étiquetage](tools/privacy-labeling/examples.md)
      + [Espaces de noms](tools/privacy-labeling/namespaces.md)
   + Utilisation des appels au serveur {#server-call-usage}
      + [Utilisation des appels au serveur - Aperçu](tools/server-call-usage/overage-overview.md)
      + [Affichage de l’utilisation actuelle des appels au serveur](tools/server-call-usage/server-call-usage-dashboard.md)
      + [Affichage de l’utilisation des suites de rapports](tools/server-call-usage/report-suite-usage.md)
      + [Alertes d’utilisation des appels au serveur](tools/server-call-usage/scu-alerts.md)
      + [FAQ sur l’utilisation des appels au serveur](tools/server-call-usage/overage-faq.md)
   + Gestion des utilisateurs et utilisatrices et des produits (héritée) {#user-product-management}
      + [Gestion des utilisateurs et utilisatrices et des produits (héritée)](tools/user-management/user-management.md)
      + [Gestion des ressources, des expirations et des comptes d’utilisation hérités](tools/user-management/users-assets.md)
      + Migrer des utilisateurs et utilisatrices vers Adobe Admin Console {#migrate-users}
         + [Migration des utilisateurs d’Analytics vers l’Admin Console](tools/user-management/user-migration/c-migration-tool.md)
         + [Migration de comptes d’utilisateurs Analytics sous la forme d’Adobe ID](tools/user-management/user-migration/t-migrate-users.md)
         + [Migration de comptes d’utilisateurs Analytics sous la forme d’Enterprise ID et de Federated ID](tools/user-management/user-migration/migrate-enterprise.md)
         + [Désactiver les comptes hérités](tools/user-management/user-migration/t-disable-legacy-login.md)
         + [API affectées par la migration](tools/user-management/user-migration/developer.md)
+ [API d’administration](c-admin-api/c-admin-api.md)
+ [Questions fréquentes sur la fin de vie des API Adobe Analytics 1.4](c-admin-api/c-admin-14-api-eol.md)

