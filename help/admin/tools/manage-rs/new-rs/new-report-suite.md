---
description: Vous pouvez créer une suite de rapports en sélectionnant un modèle prédéfini ou en utilisant l’une de vos suites de rapports existantes pour servir de modèle.
title: Paramètres d’une nouvelle suite de rapports
feature: Report Suite Settings
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
exl-id: ea5f8543-058d-4e08-bc66-575e3a7460c2
TQID: https://experienceleague.adobe.com/9wZ2rIgzZtJduhFAx6XcD53H2qzB2SZMr0pbxCopBvk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
  - id: f52db89b-2666-4cad-9c50-9da4d3ffcfd0
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 541
ht-degree: 95%

---

# Paramètres d’une nouvelle suite de rapports

Vous pouvez créer une suite de rapports en sélectionnant un modèle prédéfini ou en utilisant l’une de vos suites de rapports existantes pour servir de modèle.

Descriptions des éléments utilisés lors de la [création d’une suite de rapports](/help/admin/tools/manage-rs/new-rs/t-create-a-report-suite.md).

>[!NOTE]
>
>La [documentation sur les suites de rapports virtuelles](/help/components/vrs/c-workflow-vrs/vrs-create.md) indique comment créer de telles suites.

| Élément | Description |
| --- | --- |
| Identifiant de suite de rapports | Indique un ID unique pouvant uniquement contenir des caractères alphanumériques. Une fois créé, il ne peut plus être modifié. Adobe définit le préfixe d’ID requis qui lui aussi ne peut pas être modifié.  Lorsque vous créez plusieurs suites de rapports, assurez-vous que la convention de nommage utilisée garantit l’unicité des ID. |
| Titre du site | Identifie la suite de rapports dans les outils d’administration. Ce titre est également utilisé dans la liste déroulante Suite de rapports qui se trouve dans l’en-tête de la suite. |
| Fuseau horaire | Planifie des événements et applique un horodatage aux données. |
| URL de base | (Facultatif) Définit le domaine de base de la suite de rapports. Cette URL fonctionne comme un filtre URL externe si vous ne définissez pas explicitement de tels filtres pour la suite de rapports. |
| Page par défaut | (Facultatif) Élimine les occurrences de la valeur Page par défaut des URL qu’elle rencontre. Si votre rapport de pages les plus populaires contient des URL plutôt que des noms de page, ce paramètre empêche l’existence de plusieurs URL pour la même page web.  Par exemple, les URL `https://example.com` et `https://example.com/index.html` représentent généralement la même page.<p> Vous pouvez supprimer des noms de fichier superflus, de sorte que ces URL s’affichent sous la forme `https://example.com` dans vos rapports. Si vous ne définissez pas cette valeur, Analytics supprime automatiquement les noms de fichier suivants des URL : `index.htm`, `index.html`, `index.cgi`, `index.asp`, `default.htm`, `default.html`, `default.cgi`, `default.asp`, `home.htm`, `home.html`, `home.cgi` et `home.asp`. Pour désactiver l’élimination du nom de fichier, indiquez une valeur Page par défaut qui ne se présentera jamais dans vos URL. |
| Date d’activation | Informe Adobe de la date prévue pour l’activation de cette suite de rapports. Si votre calendrier de déploiement change, indiquez une estimation actualisée de votre trafic à l’aide de l’outil Trafic prévisionnel permanent sous Gestion du trafic. |
| Estimation du nombre de pages vues par jour | Identifie le nombre de pages vues qu’il est prévu que cette suite de rapports prenne en charge quotidiennement. Les gros volumes de trafic exigent un processus d’approbation plus long. Pour éviter les retards de traitement, tâchez de faire une estimation aussi précise que possible. |
| Devise de base | Indique la devise par défaut utilisée pour stocker toutes les données monétaires. La fonction de création de rapports d’Analytics convertit, dans la devise de base, les transactions effectuées dans d’autres devises en utilisant le taux de conversion en vigueur à la réception des données. La création de rapports Analytics utilise la variable JavaScript currencyCode pour identifier la devise d’une transaction donnée. |
| Activer le traitement des mots-clés japonais | Active la prise en charge de caractères multioctet pour la suite de rapports. Si vous désactivez la prise en charge de caractères multioctet, le système suppose que ces données sont au format `ISO-8859-1`. Les pages web doivent spécifier leur jeu de caractères dans la variable JavaScript charSet. <p>La prise en charge des caractères multioctet stocke les caractères dans la suite de rapports à l’aide du codage UTF-8. À la réception des données, le système les convertit depuis le jeu de caractères de la page Web au format UTF-8, afin que vous puissiez utiliser n’importe quelle langue dans vos rapports marketing.  Contactez votre équipe Adobe en charge des comptes ou le service d’assistance clientèle pour modifier la prise en charge des caractères à plusieurs octets d’une suite de rapports existante. |
| Utilisation du menu de navigation simplifié | Cette fonctionnalité faisait partie de [Reports &amp; Analytics](https://new.express.adobe.com/webpage/WFCyq7w8kijmB ?), qui n’est plus pris en charge. |

{style="table-layout:auto"}
