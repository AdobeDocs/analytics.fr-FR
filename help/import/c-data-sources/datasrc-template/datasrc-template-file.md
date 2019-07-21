---
description: Informations sur un modèle de source de données, qui fournit une structure de données adaptée pour l’envoi d’un jeu spécifique de données externes vers les sources de données.
seo-description: Informations sur un modèle de source de données, qui fournit une structure de données adaptée pour l’envoi d’un jeu spécifique de données externes vers les sources de données.
seo-title: Présentation du modèle Sources de données
solution: Analytics
subtopic: Sources de données
title: Présentation du modèle Sources de données
topic: Développeur et mise en œuvre
uuid: e 768 bcff-a 996-44 c 7-a 7 f 2-9 a 2 c 651 ecad 9
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Présentation du modèle Sources de données

Informations sur un modèle de source de données, qui fournit une structure de données adaptée pour l’envoi d’un jeu spécifique de données externes vers les sources de données.

Le fichier de modèle généré par cet Assistant vous permet de commencer l’importation. Vous pouvez ajouter d’autres colonnes à celles qui se trouvent déjà dans le modèle, à condition que la mesure ou la définition soit prise en charge pour le type de traitement de données sélectionné.

Vous pouvez afficher les mesures et les dimensions prises en charge pour chaque type dans les sections suivantes :

* [Journal Web](../../../import/c-data-sources/c-datasrc-types/datasrc-web-log.md#concept_E25D89C8B90A41FEB7DF4E936CACEE2B)
* [Trafic](../../../import/c-data-sources/c-datasrc-types/datasrc-traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC) (n’est plus pris en charge)
* [Conversion](../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0)
* [ID de transaction](../../../import/c-data-sources/c-datasrc-types/datasrc-transactionid.md#concept_A97302E9EC45468A8F30285FACE8C776)
* [Visitor ID](../../../import/c-data-sources/c-datasrc-types/datasrc-visitorid.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5)
* [Traitement complet](../../../import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#concept_975B1BB9981D49139B4EE09C78CDE6ED)

For example, for a Visitor ID data type, you can add a column for any metric or dimensions listed in [Visitor ID](../../../import/c-data-sources/c-datasrc-types/datasrc-visitorid.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5).

Une fois le modèle créé, vous pouvez le télécharger, y entrer des données, puis transférer les données vers le site FTP de la fonctionnalité Sources de données. Une fois les données importées traitées par le serveur de sources de données, elles peuvent être utilisées dans vos rapports marketing.

The Data Source template is a [!DNL .txt] file that you can open with any text editor. Il est toutefois plus facile d’utiliser le modèle dans Microsoft Excel ou un autre tableur. Le contenu du modèle varie en fonction de vos sélections dans l’[!UICONTROL Assistant d’activation de la source de données].

Reportez-vous à la section [Référence du fichier d’importation](../../../import/c-data-sources/datasrc-template/datasrc-import-file-reference.md#concept_472095E1D011434D98A21C101A4618BD) pour plus de détails.
