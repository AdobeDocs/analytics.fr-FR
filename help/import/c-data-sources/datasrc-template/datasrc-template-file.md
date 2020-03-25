---
description: Informations sur un modèle de source de données, qui fournit une structure de données adaptée pour l’envoi d’un jeu spécifique de données externes vers les sources de données.
subtopic: Data sources
title: Modèle de sources de données - Aperçu
topic: Developer and implementation
uuid: e768bcff-a996-44c7-a7f2-9a2c651ecad9
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Modèle de sources de données - Aperçu

Informations sur un modèle de source de données, qui fournit une structure de données adaptée pour l’envoi d’un jeu spécifique de données externes vers les sources de données.

Le fichier de modèle généré par cet Assistant vous permet de commencer l’importation. Vous pouvez ajouter d’autres colonnes à celles qui se trouvent déjà dans le modèle, à condition que la mesure ou la définition soit prise en charge pour le type de traitement de données sélectionné.

Vous pouvez afficher les mesures et les dimensions prises en charge pour chaque type dans les sections suivantes :

* [Journal Web](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md)
* [Trafic](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) (n’est plus pris en charge)
* [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md)
* [ID de transaction](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md)
* [Identifiant visiteur](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md)
* [Traitement complet](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md)

Par exemple, pour un type de données Identifiant visiteur, vous pouvez ajouter une colonne pour chaque mesure ou dimension répertoriée dans [Identifiant visiteur](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md).

Une fois le modèle créé, vous pouvez le télécharger, y entrer des données, puis transférer les données vers le site FTP de la fonctionnalité Sources de données. Une fois les données importées traitées par le serveur de sources de données, elles peuvent être utilisées dans vos rapports marketing.

Le modèle de source de données est un fichier [!DNL .txt] que vous pouvez ouvrir dans n’importe quel éditeur de texte. Il est toutefois plus facile d’utiliser le modèle dans Microsoft Excel ou un autre tableur. Le contenu du modèle varie en fonction de vos sélections dans l’[!UICONTROL Assistant d’activation de la source de données].

Reportez-vous à la section [Référence du fichier d’importation](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md) pour plus de détails.
