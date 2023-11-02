---
product: analytics
audience: end-user
user-guide-title: Guide d’exportation Analytics
breadcrumb-title: Guide d’exportation
user-guide-description: Découvrez comment utiliser les flux de données, pour exporter des données brutes, ainsi que Data Warehouse, pour récupérer une sortie de données sous forme de feuille de calcul. Découvrez comment utiliser FTP et SFTP pour transférer des fichiers.
source-git-commit: a38ee68a1560200e55067ef0ea007f69ce8b575e
workflow-type: ht
source-wordcount: '309'
ht-degree: 100%

---


# Guide d’exportation dʼAdobe Analytics {#export}

+ [Guide d’exportation dʼAnalytics](home.md)
+ [Notes de mise à jour d’Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=fr)
+ Flux de données Analytics {#analytics-data-feed}
   + [Aperçu des flux de données](analytics-data-feed/data-feed-overview.md)
   + [Création ou modification d’un flux de données](analytics-data-feed/create-feed.md)
   + [Gestion des flux de données](analytics-data-feed/df-manage-feeds.md)
   + [Gestion des tâches relatives aux flux de données](analytics-data-feed/df-manage-jobs.md)
   + Contenu du flux de données {#data-feed-contents}
      + [Aperçu du contenu du flux de données](analytics-data-feed/c-df-contents/datafeeds-contents.md)
      + [Mesures calculées](analytics-data-feed/c-df-contents/datafeeds-calculate.md)
      + [Référence des colonnes de données](analytics-data-feed/c-df-contents/datafeeds-reference.md)
      + [Recherche d’événement de page](analytics-data-feed/c-df-contents/datafeeds-page-event.md)
      + [Recherches dynamiques](analytics-data-feed/c-df-contents/dynamic-lookups.md)
      + [Recherche d’eVar de marchandisage](analytics-data-feed/c-df-contents/merchandising-evar-lookup.md)
      + [Caractères spéciaux](analytics-data-feed/c-df-contents/datafeeds-spec-chars.md)
      + [Accès tardifs](analytics-data-feed/c-df-contents/late-arriving-hits.md)
   + [FAQ sur les flux de données](analytics-data-feed/df-faq.md)
   + [Bonnes pratiques relatives aux flux de données](analytics-data-feed/data-feeds-best-practices.md)
   + [Résolution des problèmes liés aux flux de données](analytics-data-feed/troubleshooting.md)
+ Data Warehouse {#data-warehouse}
   + [Data Warehouse - Aperçu](data-warehouse/data-warehouse.md)
   + [Ajouter un groupe d’utilisateurs dans Data Warehouse](data-warehouse/t-dw-group.md)
   + Créer une demande dans Data Warehouse {#dw-create-request}
      + [Créer une demande d’entrepôt de données](/help/export/data-warehouse/create-request/t-dw-create-request.md)
      + [Paramètres généraux](/help/export/data-warehouse/create-request/dw-general-settings.md)
      + [Créer votre rapport](/help/export/data-warehouse/create-request/dw-request-build-report.md)
      + [Destination du rapport](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
      + [Options de rapport](/help/export/data-warehouse/create-request/dw-request-report-options.md)
      + [Options de planification](/help/export/data-warehouse/create-request/dw-request-scheduling.md)
      + [E-mail de notification](/help/export/data-warehouse/create-request/dw-request-email.md)
   + [Heure de remise de la demande](data-warehouse/delivery-time.md)
   + [Fichier de données Tableau](data-warehouse/t-tableau.md)
   + [Tri par mesure](data-warehouse/sorting-by-metric.md)
   + [Gérer les demandes de Data Warehouse](data-warehouse/data-warehouse-requests-manage.md)
   + [Composants pris en charge dans Data Warehouse](data-warehouse/component-support.md)
   + [FAQ sur Data Warehouse](data-warehouse/faq.md)
   + [Bonnes pratiques relatives à Data Warehouse](data-warehouse/data-warehouse-bp.md)
+ FTP et SFTP {#ftp-and-sftp}
   + [Utilisation de FTP et SFTP avec Adobe Experience Cloud](ftp-and-sftp/ftp-overview.md)
   + Configuration de comptes FTP hébergés par Adobe {#set-up-ftp-accounts}
      + [Configuration de comptes FTP - Aperçu](ftp-and-sftp/c-set-up-ftp-accounts/ftp-accounts.md)
      + [Classifications](ftp-and-sftp/c-set-up-ftp-accounts/ftp-saint.md)
      + [Sources de données](ftp-and-sftp/c-set-up-ftp-accounts/ftp-datasources.md)
      + [Data Connectors](ftp-and-sftp/c-set-up-ftp-accounts/ftp-genesis.md)
      + [Flux de données](ftp-and-sftp/c-set-up-ftp-accounts/ftp-datafeeds.md)
      + [Rapports distribués sur Data Warehouse](ftp-and-sftp/c-set-up-ftp-accounts/ftp-dw-reports.md)
      + [Rapports distribués sur le Report Builder](ftp-and-sftp/c-set-up-ftp-accounts/ftp-arb-reports.md)
      + [Contrats de services techniques Adobe Engineering Services à l’aide du FTP](ftp-and-sftp/c-set-up-ftp-accounts/ftp-eng-services.md)
   + [Limitations du FTP et conservation des données](ftp-and-sftp/ftp-limits.md)
   + [Suppression des données et des comptes liés au FTP](ftp-and-sftp/ftp-delete.md)
   + [Restauration des données et des comptes FTP supprimés](ftp-and-sftp/ftp-restore.md)
   + [Mettre à niveau les serveurs FTP Adobe](ftp-and-sftp/ftp-upgrade.md)
   + [Utilisation du mode FTP passif](ftp-and-sftp/ftp-passive.md)
   + [Temps de traitement du FTP](ftp-and-sftp/ftp-processing.md)
   + Protocole de transfert de fichiers sécurisé {#secure-file-transfer-protocol}
      + [Mise à niveau des services SFTP - FAQ](ftp-and-sftp/c-sftp/sftp-upgrade.md)
      + [Protocole de transfert de fichiers sécurisé - Aperçu](ftp-and-sftp/c-sftp/ftp-sftp.md)
      + [Connexion à un compte FTP Adobe par SFTP](ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
      + [Envoi de données Adobe vers un compte FTP externe par SFTP](ftp-and-sftp/c-sftp/ftp-sftp-transfer.md)
      + [Envoi de requêtes Data Warehouse vers les serveurs SFTP](ftp-and-sftp/c-sftp/ftp-sftp-dw.md)
      + [Connexion à Adobe via SFTP sans mot de passe](ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
+ [Téléchargements Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=fr)
+ [ API Adobe Analytics ](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)
+ [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=fr)
