---
description: Le fichier du modèle d’importation a pour but de vous aider à commencer l’importation.
subtopic: Data sources
title: Génération d’un modèle de fichier d’importation
topic: Developer and implementation
uuid: bcd90e34-42e6-4cd1-b67e-87586dea25d8
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Génération d’un modèle de fichier d’importation

Le fichier du modèle d’importation a pour but de vous aider à commencer l’importation.

Vous pouvez ajouter d’autres colonnes à celles qui se trouvent déjà dans le modèle, à condition que la mesure ou la définition soit prise en charge pour le type de traitement de données sélectionné. Vous pouvez afficher les mesures et les dimensions prises en charge pour chaque type dans les sections suivantes : [Journal web](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md), [Trafic](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md), [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md), [ID de transaction](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md), [Identifiant visiteur](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md), [Traitement complet](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md). Par exemple, pour un type de données Trafic, vous pouvez ajouter une colonne pour chaque mesure ou dimension répertoriée dans [Trafic](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md).

Une fois le modèle créé, vous pouvez le télécharger, y entrer des données, puis transférer les données vers le site FTP de la fonctionnalité Sources de données. Une fois les données importées traitées par le serveur de sources de données, elles peuvent être utilisées dans vos rapports Analytics.

Le modèle Sources de données est un fichier .txt que vous pouvez ouvrir dans n’importe quel éditeur de texte. Il est toutefois plus facile d’utiliser le modèle dans Microsoft Excel ou un autre tableur. Le contenu du modèle varie en fonction de vos sélections dans l’Assistant d’activation de la source de données.

Reportez-vous à la section [Référence du fichier d’importation](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md) pour plus de détails.

1. Connexion à Analytics.
1. Dans l’en-tête de la Suite, cliquez sur **[!UICONTROL Admin]** > **[!UICONTROL Sources de données]**.
1. Sur l’onglet **[!UICONTROL Créer]**, sélectionnez une catégorie et un type de modèle.
1. Passez en revue les instructions et informations d’activation, puis cliquez sur **[!UICONTROL Activer]**.

   Résultat de l’étape 1. Sélectionnez les options de génération de modèle dans l’Assistant d’activation de la source de données.

   | Page de l’Assistant | Champ | Description |
   |--- |--- |--- |
   | 1 | Nom | Nom du modèle affiché par Analytics dans le gestionnaire de la fonctionnalité Sources de données. |
   | 1 | Courriel | Adresse électronique à laquelle sont envoyées toutes les notifications relatives à l’utilisation de ce modèle. |
   | 1 | Case à cocher des frais associés | Cochez cette case pour indiquer que vous acceptez les frais associés à l’utilisation de ce modèle. |
   | 2 | Choisissez les mesures | Sélectionnez les mesures à importer à l’aide de cette source de données. Analytics recommande certaines mesures en fonction de la catégorie et du type de source de données sélectionnés à l’étape 3.  Pour définir une autre mesure, saisissez son nom dans un champ vierge, puis cochez la case pour activer la mesure. |
   | 3 | Faire correspondre les mesures | Sélectionnez un événement Analytics pour recevoir chaque mesure importée sélectionnée dans la page 2 de l’assistant.  Il doit s’agir d’événements nouveaux et non attribués auxquels vous avez auparavant attribué des noms qui correspondent aux données de mesure importées qu’ils recevront par l’intermédiaire de la fonctionnalité Sources de données.  Si une variable eVar, Produit ou Code de suivi est une variable de destination et que les valeurs transférées correspondent aux valeurs captées existantes, les événements transférés ajoutent des mesures aux valeurs existantes. Par exemple, vous pouvez créer une mesure « Commandes hors ligne » avec une dimension de données Produits qui comporte déjà les mesures existantes suivantes : Consultations des produits, Achats et Commandes. |
   | 4 | Choisissez la portée des données | Sélectionnez les portées de données pour la ventilation des mesures importées à partir de cette source de données. Analytics recommande certaines dimensions de données en fonction du type de source de données sélectionné à l’étape 3.  Pour définir une autre portée, saisissez son nom dans un champ vierge, puis cochez la case pour l’activer. |
   | 5 | Faites correspondre la portée des données | Sélectionnez un rapport ou une eVar standard pour recevoir chaque portée de données importée sélectionnée dans l’Assistant page 4. |

1. Une fois le modèle généré, copiez les données dans les colonnes appropriées du modèle de source de données, en veillant à respecter le format de données requis pour cette colonne.

   Résultat de l’étape 1. Enregistrez le fichier en le nommant selon votre convenance. Adobe recommande d’appliquer une convention d’affectation de noms cohérente pour tous les fichiers de source de données. Utilisez une extension de fichier courante, telle que .txt ou .tsv (ou n’utilisez aucune extension).

