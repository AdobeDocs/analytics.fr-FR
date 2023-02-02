---
product: analytics
audience: admin
user-guide-title: Guide de lʼadministrateur dʼAnalytics
breadcrumb-title: Guide de l’administrateur
user-guide-description: Découvrez les tâches dʼadministration dans Analytics, qui vous permettent entre autres de gérer les utilisateurs et les produits dans Experience Cloud Admin Console, de configurer des suites de rapports et bien plus encore.
source-git-commit: 709483bd7a4573004100c9508f5bd78f1f3f253e
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 95%

---


# Guide de lʼadministrateur d’Adobe Analytics {#admin}

+ [Guide de lʼadministrateur dʼAnalytics](home.md)
+ [Notes de mise à jour d’Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
+ Adobe Admin Console {#admin-console}
   + [Aperçu](admin-console/home.md)
   + [Guide Adobe Analytics pour le premier administrateur](admin-console/first-admin-guide.md)
   + [Rôles d’administrateur dans Adobe Analytics](admin-console/admin-roles-in-analytics.md)
   + Résumé des autorisations pour les outils Analytics {#permissions}
      + [Autorisations Analytics dans Admin Console](admin-console/permissions/summary-tables.md)
      + [Profils de produit pour Adobe Analytics](admin-console/permissions/product-profile.md)
      + [Autorisations du profil de produit pour les outils de suites de rapports](admin-console/permissions/report-suite-tools.md)
      + [Autorisations du profil de produit pour les outils Analytics](admin-console/permissions/analytics-tools.md)
   + Gestion des utilisateurs et des produits (héritée) {#user-product-management}
      + [Gestion des utilisateurs et des produits (Hérité)](admin-console/user-management2/user-management.md)
      + Migration des utilisateurs vers Adobe Admin Console {#migrate-users}
         + [Migration des utilisateurs d’Analytics vers l’Admin Console](admin-console/user-management2/user-migration/c-migration-tool.md)
         + [Migration de comptes utilisateur Analytics sous la forme d’Adobe ID](admin-console/user-management2/user-migration/t-migrate-users.md)
         + [Migrer des comptes utilisateur Analytics sous la forme d’Enterprise ID et de Federated ID](admin-console/user-management2/user-migration/migrate-enterprise.md)
         + [Désactiver les comptes hérités](admin-console/user-management2/user-migration/t-disable-legacy-login.md)
         + [API affectées par la migration](admin-console/user-management2/user-migration/developer.md)
+ Outils d’administration Analytics {#admin-tools}
   + [Présentation des outils d’administration](admin/c-admin-tools.md)
   + [Facturation](admin/billing-admin.md)
   + [Gestionnaire de code](admin/code-manager-admin.md)
   + [Codes de devise](admin/currency.md)
   + [Sources de données](admin/data-sources.md)
   + [Mesures par défaut](admin/default-metrics.md)
   + [Exclure par adresse IP](admin/exclude-ip.md)
   + [Journaux](admin/logs.md)
   + [Compte rendu des performances sur la confidentialité](admin/privacy-reporting.md)
   + [Gestionnaire des activités de rapport](admin/reporting-activity.md)
   + [File d’attente des rapports planifiés](admin/scheduled-reports-admin.md)
   + Gestionnaire de suites de rapports {#manage-report-suites}
      + [Gérer les suites de rapports](admin/c-manage-report-suites/report-suites-admin.md)
      + [Suites de rapports globales et de cumul](admin/c-manage-report-suites/rollup-report-suite.md)
      + [Enregistrer une recherche de suite de rapports](admin/c-manage-report-suites/t-report-suite-saved-search.md)
      + [Télécharger les paramètres d’une suite de rapports](admin/c-manage-report-suites/t-download-rs-settings.md)
      + Nouvelle suite de rapports {#c-new-report-suite}
         + [Créer une suite de rapports](admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)
         + [Créer une suite de rapports de cumul](admin/c-manage-report-suites/c-new-report-suite/t-rollups.md)
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
         + [Génération de prospect](admin/c-manage-report-suites/c-report-suite-templates/lead-generation.md)
         + [Média d’assistance](admin/c-manage-report-suites/c-report-suite-templates/support-media.md)
      + Modifier les paramètres d’une suite de rapports {#edit-report-suite}
         + Général {#report-suite-general}
            + [Paramètres du compte général](admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)
            + [Filtres URL internes](admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)
            + Détection de référencement payant {#paid-search-detection}
               + [Détection de référencement payant - Présentation](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md)
               + [Configuration de la détection de référencement payant](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/t-paid-search-detection.md)
            + [Personnaliser les menus](admin/c-manage-report-suites/c-edit-report-suites/general/customize-menus.md)
            + [Personnaliser le calendrier](admin/c-manage-report-suites/c-edit-report-suites/general/custom-calendar.md)
            + Règles de traitement {#c-processing-rules}
               + [Règles de traitement - Présentation](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md)
               + Configuration des règles de traitement {#c-processing-rules-configuration}
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
               + [Règles de robots - Présentation](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)
               + [Signatures de robots courantes](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-signatures.md)
               + [Méthodes d’exclusion de robots](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-exclusion-methods.md)
            + [Paramètres de confidentialité](admin/c-manage-report-suites/c-edit-report-suites/general/privacy-settings.md)
            + [Dates et heures facultatives](admin/c-manage-report-suites/c-edit-report-suites/general/timestamp-optional.md)
            + Transfert côté serveur {#server-side-forwarding}
               + [Transfert côté serveur - Présentation](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)
               + [Conformité au RGPD et à la directive vie privée et communications électroniques, et transfert côté serveur](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-gdpr.md)
               + [Conditions requises pour le transfert côté serveur](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-requirements.md)
               + [Données et référence de code du transfert côté serveur](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-reference.md)
               + [Comment vérifier l’implémentation du transfert côté serveur](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-verify.md)
               + [Questions fréquentes relatives au transfert côté serveur](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-faq.md)
         + Variables de trafic {#traffic-variables}
            + [Variable de trafic (prop) - Présentation](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)
            + [Activer les rapports de variables de trafic](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/t-traffic-variable.md)
            + [Classifications de trafic](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-classifications.md)
            + [Descriptions des rapports personnalisés](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/custom-desc-admin.md)
         + Variables de conversion {#conversion-variables}
            + [Variables de conversion (eVars)](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)
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
         + [Canaux marketing](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels-admin.md)
         + Gestion du trafic {#traffic-management}
            + [Aperçu](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/traffic-management.md)
            + [Prévoir les pics](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md)
            + [Trafic permanent](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-permanent.md)
         + [Gestion des applications](admin/c-manage-report-suites/c-edit-report-suites/mobile-management.md)
         + Rapports en temps réel {#real-time-reports}
            + [Rapports en temps réel - Présentation](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md)
            + [Configuration des rapports en temps réel](admin/c-manage-report-suites/c-edit-report-suites/realtime/t-realtime-admin.md)
            + [Mesures et dimensions en temps réel prises en charge](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md)
   + Paramètres de l’entreprise {#company-settings}
      + [Paramètres d’entreprise - Aperçu](admin/company/c-company-settings.md)
      + [Gestionnaire de sécurité](admin/company/security-manager.md)
      + [Services web](admin/company/web-services-admin.md)
      + [Rapports du Report Builder](admin/company/report-builder-reports-admin.md)
      + [Authentification unique](admin/company/single-signon-admin.md)
      + [Alliance de marques](admin/company/co-branding-admin.md)
      + [Masquage des suites de rapports](admin/company/c-hide-report-suites.md)
      + [Gestionnaire de préférences](admin/company/preferences-manager.md)
      + [Actions en attente](admin/company/pending-actions-admin.md)
      + [Niveaux d’accès aux fonctions](admin/company/feature-access-levels.md)
   + [Gestion des vidéos](admin/video-management.md)
   + Utilisation des appels au serveur {#server-call-usage}
      + [Utilisation des appels au serveur - Aperçu](admin/c-server-call-usage/overage-overview.md)
      + [Affichage de l’utilisation actuelle des appels au serveur](admin/c-server-call-usage/server-call-usage-dashboard.md)
      + [Affichage de l’utilisation des suites de rapports](admin/c-server-call-usage/report-suite-usage.md)
      + [Alertes d’utilisation des appels au serveur](admin/c-server-call-usage/scu-alerts.md)
      + [FAQ sur l’utilisation des appels au serveur](admin/c-server-call-usage/overage-faq.md)
+ Gouvernance des données {#data-governance}
   + [Processus relatif à la confidentialité des données Adobe Analytics](c-data-governance/an-gdpr-workflow.md)
   + [Questions fréquentes](c-data-governance/gdpr-faq.md)
   + Étiquetage des données {#data-labels}
      + [Étiquettes relatives à la confidentialité des données pour les composants Analytics](c-data-governance/data-labeling/gdpr-labels.md)
      + [Étiqueter les données d’une suite de rapports](c-data-governance/data-labeling/gdpr-setup-reportsuite.md)
      + [Affichage/gestion des étiquettes de confidentialité de la suite de rapports](c-data-governance/data-labeling/gdpr-view-settings.md)
      + [Bonnes pratiques en matière d’étiquetage](c-data-governance/data-labeling/gdpr-analytics-ids.md)
      + [Exemple d’étiquetage](c-data-governance/data-labeling/gdpr-labeling-example.md)
      + [Espaces de noms](c-data-governance/data-labeling/gdpr-namespaces.md)
   + [Envoyer des demandes d’accès et de suppression](c-data-governance/gdpr-submit-access-delete.md)
   + [Extension d’ID](c-data-governance/gdpr-id-expansion.md)
   + [Exemption de consentement de la CNIL](c-data-governance/cnil-consent-exemption.md)
+ [API d’administration](c-admin-api/c-admin-api.md)
