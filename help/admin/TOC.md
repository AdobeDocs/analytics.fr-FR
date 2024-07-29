---
product: analytics
audience: admin
user-guide-title: Guide de lʼadministrateur dʼAnalytics
breadcrumb-title: Guide de l’administrateur
user-guide-description: Découvrez les tâches dʼadministration dans Analytics, qui vous permettent entre autres de gérer les utilisateurs et les produits dans Experience Cloud Admin Console, de configurer des suites de rapports et bien plus encore.
source-git-commit: 8bb879b86126c59b7d22505657ecdb46106822e8
workflow-type: ht
source-wordcount: '637'
ht-degree: 100%

---


# Guide de lʼadministrateur d’Adobe Analytics {#admin}

+ [Guide de lʼadministrateur dʼAnalytics](home.md)
+ [Notes de mise à jour d’Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
+ Adobe Admin Console {#admin-console}
   + [Vue d’ensemble](admin-console/home.md)
   + [Guide Adobe Analytics pour le premier administrateur](admin-console/first-admin-guide.md)
   + [Rôles d’administrateur dans Adobe Analytics](admin-console/admin-roles-in-analytics.md)
   + Résumé des autorisations pour les outils Analytics {#permissions}
      + [Profils de produit pour Adobe Analytics](admin-console/permissions/product-profile.md)
      + [Autorisations du profil de produit pour les outils de suites de rapports](admin-console/permissions/report-suite-tools.md)
      + [Autorisations du profil de produit pour les outils Analytics](admin-console/permissions/analytics-tools.md)
+ Outils d’administration Analytics {#admin-tools}
   + [Présentation des outils d’administration](admin/c-admin-tools.md)
   + [Gestionnaire de code](admin/code-manager-admin.md)
   + [Sources de données](admin/data-sources.md)
   + [Exclure par adresse IP](admin/exclude-ip.md)
   + [Journaux](admin/logs.md)
   + Personne responsable des activités de rapport {#reporting-activity-manager}
      + [Vue d’ensemble](admin/reporting-activity-manager/reporting-activity-overview.md)
      + [Afficher l’activité de rapport](admin//reporting-activity-manager/reporting-activity.md)
      + [Annuler des requêtes de création de rapports](admin/reporting-activity-manager/reporting-activity-cancel-requests.md)
   + Migration des composants {#component-migration}
      + [Se préparer à la migration](admin/component-migration/prepare-component-migration.md)
      + [Workflow de migration](admin/component-migration/component-migration.md)
   + Gestionnaire de suites de rapports {#manage-report-suites}
      + Modifier les paramètres d’une suite de rapports {#edit-report-suite}
         + Général {#report-suite-general}
            + [Paramètres du compte général](admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)
            + [Filtres URL internes](admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)
            + [Personnaliser le calendrier](admin/c-manage-report-suites/c-edit-report-suites/general/custom-calendar.md)
            + Détection de référencement payant {#paid-search-detection}
               + [Détection de référencement payant - Aperçu](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md)
               + [Configuration de la détection de référencement payant](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/t-paid-search-detection.md)
            + Règles de traitement {#c-processing-rules}
               + [Vue d’ensemble des règles de traitement](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md)
               + Règles de traitement {#c-processing-rules-configuration}
                  + [Fonctionnement des règles de traitement](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/processing-rules-about.md)
                  + [Créer des règles de traitement](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md)
                  + [Afficher les règles de traitement actives](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-view.md)
                  + [Afficher l’historique des règles de traitement](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rule-view-history.md)
                  + [Restaurer des règles de traitement](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-restore.md)
                  + [Copier des règles de traitement dans une autre suite de rapports](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md)
                  + [Dimensions disponibles pour les règles de traitement](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rule-dimensions.md)
               + Exemples de règles de traitement {#processing-rules-examples}
                  + [Exemples de règles de traitement](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-examples.md)
                  + [Renseigner un identifiant de campagne à partir d’un paramètre de chaîne de requête](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-populate-campaign-id.md)
                  + [Définir l’événement d’affichage de produit à partir de la page d’aperçu des produits](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/setting-the-product-view-event.md)
                  + [Ajouter une sous-catégorie en concaténant le nom de page et de catégorie](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/subcategory-concatenating.md)
                  + [Déterminer un chemin en copiant une valeur eVar sur une valeur prop](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-determining-path.md)
                  + [Nettoyer les valeurs d’un rapport](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md)
                  + [Renseigner les termes de recherche interne à l’aide d’un paramètre de chaîne de requête](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-populating-internal-search.md)
                  + [Copier une variable de données contextuelles dans une eVar](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md)
                  + [Définir un événement à l’aide d’une variable de données contextuelles](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md)
                  + [Supprimer un événement d’un accès](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-remove-event.md)
               + [Astuces et conseils concernant les règles de traitement](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-tips.md)
            + Règles de robots {#bot-removal}
               + [Suppression de robots](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md)
               + [Comprendre et configurer des règles de robot](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)
               + [Signatures de robots courantes](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-signatures.md)
               + [Méthodes d’exclusion de robots](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-exclusion-methods.md)
            + [Paramètres de confidentialité](admin/c-manage-report-suites/c-edit-report-suites/general/privacy-settings.md)
            + [Configuration des horodatages](admin/c-manage-report-suites/c-edit-report-suites/general/timestamp-optional.md)
            + Transfert côté serveur {#server-side-forwarding}
               + [Transfert côté serveur - Aperçu](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)
               + [Conformité au RGPD et à la directive vie privée et communications électroniques, et transfert côté serveur](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-gdpr.md)
               + [Conditions requises pour le transfert côté serveur](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-requirements.md)
               + [Données et référence de code du transfert côté serveur](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-reference.md)
               + [Comment vérifier l’implémentation du transfert côté serveur](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-verify.md)
               + [Questions fréquentes relatives au transfert côté serveur](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-faq.md)
         + Trafic {#traffic-variables}
            + [Variables de trafic](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)
            + [Classifications de trafic](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-classifications.md)
            + [Descriptions des rapports personnalisés](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/custom-desc-admin.md)
         + Conversion {#conversion-variables}
            + [Variables de conversion](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)
            + [Méthodes de recherche](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/finding-methods.md)
            + [Classifications des conversions](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-classifications.md)
            + Variable de visiteur unique {#unique-visitor-variable}
               + [Définir la variable de visiteur unique](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
               + [Scénario d’utilisation - Extraction d’ID de visiteur](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
            + Événements de succès {#success-events}
               + [Événements de succès - Aperçu](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md)
               + [Configurer des événements de succès](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/t-success-events.md)
               + [À propos du changement de type d’événement](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/event-type.md)
            + [Hiérarchies de classification](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/classification-hierarchies.md)
            + [Variables de liste](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)
            + [eVars de marchandisage](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/merchandising-evars.md)
         + Canaux marketing {#marketing-channels}
            + [Gestionnaire de canaux marketing](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md)
            + [Règles de traitement des canaux marketing](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md)
            + [Classifications de canaux marketing](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/classifications-mchannel.md)
            + [Expiration du canal marketing](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/visitor-engagement.md)
         + Gestion du trafic {#traffic-management}
            + [Vue d’ensemble](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/traffic-management.md)
            + [Prévoir les pics](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md)
            + [Trafic permanent](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-permanent.md)
         + [Mesures par défaut](admin/c-manage-report-suites/c-edit-report-suites/default-metrics.md)
         + Gestion des applications {#app-management}
            + [Rapports d’application](admin/c-manage-report-suites/c-edit-report-suites/app-reporting.md)
            + [Classifications d’application](admin/c-manage-report-suites/c-edit-report-suites/app-classifications.md)
         + [Gestion des médias](admin/c-manage-report-suites/c-edit-report-suites/media-management.md)
         + [Activity Map](admin/c-manage-report-suites/c-edit-report-suites/activity-map.md)
         + [AEM](admin/c-manage-report-suites/c-edit-report-suites/adobe-experience-manager.md)
         + [Adobe Campaign](admin/c-manage-report-suites/c-edit-report-suites/adobe-campaign.md)
         + [Compte rendu des performances sur la confidentialité](admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md)
         + Gestion de Document Cloud {#doc-cloud-mgt}
            + [Configurer Document Cloud avec Adobe Analytics](admin/c-manage-report-suites/c-edit-report-suites/document-cloud-mgt.md)
            + [Configurer les rapports de Document Cloud](admin/c-manage-report-suites/c-edit-report-suites/document-cloud-config.md)
         + [Configuration Advertising Analytics](admin/c-manage-report-suites/c-edit-report-suites/advertising-analytics-config.md)
         + Temps réel {#real-time-reports}
            + [Rapports en temps réel - Aperçu](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md)
            + [Configuration des rapports en temps réel](admin/c-manage-report-suites/c-edit-report-suites/realtime/t-realtime-admin.md)
            + [Mesures et dimensions en temps réel prises en charge](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md)
      + [Gérer les suites de rapports](admin/c-manage-report-suites/report-suites-admin.md)
      + [Suites de rapports globales](admin/c-manage-report-suites/rollup-report-suite.md)
      + [Enregistrer une recherche de suite de rapports](admin/c-manage-report-suites/t-report-suite-saved-search.md)
      + [Télécharger les paramètres d’une suite de rapports](admin/c-manage-report-suites/t-download-rs-settings.md)
      + Nouvelle suite de rapports {#c-new-report-suite}
         + [Créer une suite de rapports](admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)
         + [Créer un groupe de suites de rapports](admin/c-manage-report-suites/c-new-report-suite/t-create-rs-group.md)
         + [Paramètres d’une nouvelle suite de rapports](admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md)
         + [Paramètres non copiés depuis une suite de rapports source](admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md)
      + Modèles de suite de rapports {#report-suite-templates}
         + [Modèles de suite de rapports - Aperçu](admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)
         + [Portail d’agrégation](admin/c-manage-report-suites/c-report-suite-templates/aggregator-portal.md)
         + [Commerce](admin/c-manage-report-suites/c-report-suite-templates/commerce-admin.md)
         + [Contenu et média](admin/c-manage-report-suites/c-report-suite-templates/content-media.md)
         + [Modèle par défaut](admin/c-manage-report-suites/c-report-suite-templates/default-rs-template.md)
         + [Services financiers](admin/c-manage-report-suites/c-report-suite-templates/financial-services.md)
         + [Portail d’emploi](admin/c-manage-report-suites/c-report-suite-templates/job-portal.md)
         + [Génération de piste](admin/c-manage-report-suites/c-report-suite-templates/lead-generation.md)
         + [Média d’assistance](admin/c-manage-report-suites/c-report-suite-templates/support-media.md)
   + Paramètres de l’entreprise {#company-settings}
      + [Paramètres d’entreprise - Aperçu](admin/company/c-company-settings.md)
      + [Gestionnaire de sécurité](admin/company/security-manager.md)
      + [Services web](admin/company/web-services-admin.md)
      + [Rapports du Report Builder](admin/company/report-builder-reports-admin.md)
      + [Authentification unique](admin/company/single-signon-admin.md)
      + [Masquer des suites de rapports](admin/company/c-hide-report-suites.md)
      + [Gestionnaire de préférences](admin/company/preferences-manager.md)
      + [Actions en attente](admin/company/pending-actions-admin.md)
      + [Niveaux d’accès aux fonctions](admin/company/feature-access-levels.md)
   + Étiquetage de confidentialité de la gouvernance des données {#data-governance}
      + [Workflow relatif à la confidentialité des données d’Adobe Analytics](admin/c-data-governance/an-gdpr-workflow.md)
      + [Questions fréquentes](admin/c-data-governance/gdpr-faq.md)
      + Étiquetage des données {#data-labels}
         + [Étiquettes relatives à la confidentialité des données pour les composants Analytics](admin/c-data-governance/data-labeling/gdpr-labels.md)
         + [Étiqueter les données d’une suite de rapports](admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md)
         + [Affichage/gestion des étiquettes de confidentialité de la suite de rapports](admin/c-data-governance/data-labeling/gdpr-view-settings.md)
         + [Bonnes pratiques en matière d’étiquetage](admin/c-data-governance/data-labeling/gdpr-analytics-ids.md)
         + [Exemple d’étiquetage](admin/c-data-governance/data-labeling/gdpr-labeling-example.md)
         + [Espaces de noms](admin/c-data-governance/data-labeling/gdpr-namespaces.md)
      + [Extension d’ID](admin/c-data-governance/gdpr-id-expansion.md)
      + [Exemption de consentement de la CNIL](admin/c-data-governance/cnil-consent-exemption.md)
   + Utilisation des appels au serveur {#server-call-usage}
      + [Utilisation des appels au serveur - Aperçu](admin/c-server-call-usage/overage-overview.md)
      + [Affichage de l’utilisation actuelle des appels au serveur](admin/c-server-call-usage/server-call-usage-dashboard.md)
      + [Affichage de l’utilisation des suites de rapports](admin/c-server-call-usage/report-suite-usage.md)
      + [Alertes d’utilisation des appels au serveur](admin/c-server-call-usage/scu-alerts.md)
      + [FAQ sur l’utilisation des appels au serveur](admin/c-server-call-usage/overage-faq.md)
   + Gestion des utilisateurs et utilisatrices et des produits (héritée) {#user-product-management}
      + [Gestion des utilisateurs et utilisatrices et des produits (héritée)](admin/user-management2/user-management.md)
      + [Gestion des ressources, des expirations et des comptes d’utilisation hérités](admin/user-management2/users-assets.md)
      + Migration des utilisateurs vers Adobe Admin Console {#migrate-users}
         + [Migration des utilisateurs d’Analytics vers l’Admin Console](admin/user-management2/user-migration/c-migration-tool.md)
         + [Migration de comptes d’utilisateurs Analytics sous la forme d’Adobe ID](admin/user-management2/user-migration/t-migrate-users.md)
         + [Migration de comptes d’utilisateurs Analytics sous la forme d’Enterprise ID et de Federated ID](admin/user-management2/user-migration/migrate-enterprise.md)
         + [Désactiver les comptes hérités](admin/user-management2/user-migration/t-disable-legacy-login.md)
         + [API affectées par la migration](admin/user-management2/user-migration/developer.md)
+ [API d’administration](c-admin-api/c-admin-api.md)
+ [Questions fréquentes sur la fin de vie des API Adobe Analytics 1.4](c-admin-api/c-admin-14-api-eol.md)

