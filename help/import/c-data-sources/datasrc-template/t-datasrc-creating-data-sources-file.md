---
description: Le fichier du modèle d’importation a pour but de vous aider à commencer l’importation.
seo-description: Le fichier du modèle d’importation a pour but de vous aider à commencer l’importation.
seo-title: Génération d'un modèle de fichier d'importation
solution: Analytics
subtopic: Sources de données
title: Génération d'un modèle de fichier d'importation
topic: Développeur et mise en œuvre
uuid: bcd 90 e 34-42 e 6-4 cd 1-b 67 e -87586 dea 25 d 8
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Génération d'un modèle de fichier d'importation

Le fichier du modèle d’importation a pour but de vous aider à commencer l’importation.

Vous pouvez ajouter d’autres colonnes à celles qui se trouvent déjà dans le modèle, à condition que la mesure ou la définition soit prise en charge pour le type de traitement de données sélectionné. Vous pouvez afficher les mesures et les dimensions prises en charge pour chaque type dans les sections suivantes : [Journal Web](../../../import/c-data-sources/c-datasrc-types/datasrc-web-log.md#concept_E25D89C8B90A41FEB7DF4E936CACEE2B), [trafic](../../../import/c-data-sources/c-datasrc-types/datasrc-traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC), [conversion](../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0), ID [de transaction](../../../import/c-data-sources/c-datasrc-types/datasrc-transactionid.md#concept_A97302E9EC45468A8F30285FACE8C776), [identifiant visiteur](../../../import/c-data-sources/c-datasrc-types/datasrc-visitorid.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5), [traitement complet](../../../import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#concept_975B1BB9981D49139B4EE09C78CDE6ED)). For example, for a traffic data type, you can add a column for any metric or dimensions listed in [Traffic](../../../import/c-data-sources/c-datasrc-types/datasrc-traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC).

Une fois le modèle créé, vous pouvez le télécharger, y entrer des données, puis transférer les données vers le site FTP de la fonctionnalité Sources de données. Une fois les données importées traitées par le serveur de sources de données, elles peuvent être utilisées dans vos rapports Analytics.

Le modèle Sources de données est un fichier .txt que vous pouvez ouvrir dans n’importe quel éditeur de texte. Il est toutefois plus facile d’utiliser le modèle dans Microsoft Excel ou un autre tableur. Le contenu du modèle varie en fonction de vos sélections dans l’Assistant d’activation de la source de données.

Reportez-vous à la section [Référence du fichier d’importation](../../../import/c-data-sources/datasrc-template/datasrc-import-file-reference.md#concept_472095E1D011434D98A21C101A4618BD) pour plus de détails.

1. Connexion à Analytics.
1. Dans l’en-tête de la Suite, cliquez sur **Admin** &gt; **[!UICONTROL Sources de données]**.
1. On the **[!UICONTROL Data Sources Create]** tab, select a template category and type.
1. Passez en revue les instructions et informations d’activation, puis cliquez sur **[!UICONTROL Activer]**.

   Résultat 1. Sélectionnez les options de génération de modèle dans l’Assistant d’activation de la source de données.

   | Page de l’Assistant | Champ | Description |
   |--- |--- |--- |
   | 1 | Nom | Nom du modèle affiché par Analytics dans le Gestionnaire des sources de données. |
   | 1 | Courriel | Adresse électronique à laquelle sont envoyées toutes les notifications relatives à l’utilisation de ce modèle. |
   | 1 | Case à cocher des frais associés | Cochez la case pour indiquer votre acceptation des frais associés à l'utilisation de ce modèle de source de données. |
   | 2 | Choisissez les mesures | Sélectionnez les mesures à importer à l’aide de cette source de données. Analytics recommande certaines mesures en fonction de la catégorie et du type de source de données sélectionnés à l'étape 3. Pour définir une autre mesure, saisissez son nom dans un champ vierge, puis cochez la case pour activer la mesure. |
   | 3 | Faire correspondre les mesures | Sélectionnez un événement Analytics pour recevoir chaque mesure importée sélectionnée dans l'assistant page 2. Il doit s’agir d’événements nouveaux et non attribués auxquels vous avez auparavant attribué des noms qui correspondent aux données de mesure importées qu’ils recevront par l’intermédiaire de la fonctionnalité Sources de données.  Si une variable eVar, Produit ou Code de suivi est une variable de destination et que les valeurs transférées correspondent aux valeurs captées existantes, les événements transférés ajoutent des mesures aux valeurs existantes. Par exemple, vous pouvez créer une mesure « Commandes hors ligne » avec une portée de données Produits qui a déjà comme mesures existantes les mesures Consultations produits, Passage en caisse et Commandes. |
   | 4 | Choisissez la portée des données | Sélectionnez les portées de données pour la ventilation des mesures importées à partir de cette source de données. Analytics recommande certaines portées de données en fonction du type de source de données sélectionné à l'étape 3. Pour définir une autre portée, saisissez son nom dans un champ vierge, puis cochez la case pour l’activer. |
   | 5 | Faites correspondre la portée des données | Sélectionnez un rapport ou une eVar standard pour recevoir chaque portée de données importée sélectionnée dans l’Assistant page 4. |

1. Une fois le modèle généré, copiez les données dans les colonnes appropriées du modèle de source de données, en veillant à respecter le format de données requis pour cette colonne.

   Résultat 1. Enregistrez le fichier en le nommant selon votre convenance. Adobe recommande d’appliquer une convention d’affectation de noms cohérente pour tous les fichiers de source de données. Utilisez une extension de fichier courante, telle que .txt ou .tsv (ou n’utilisez aucune extension).

