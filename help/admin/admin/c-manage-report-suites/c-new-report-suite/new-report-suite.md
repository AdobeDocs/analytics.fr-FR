---
description: Vous pouvez créer une suite de rapports en sélectionnant un modèle prédéfini ou en utilisant l’une de vos suites de rapports existantes pour servir de modèle.
title: Paramètres d’une nouvelle suite de rapports
feature: Report Suite Settings
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
exl-id: ea5f8543-058d-4e08-bc66-575e3a7460c2
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 96%

---

# Paramètres d’une nouvelle suite de rapports

Vous pouvez créer une suite de rapports en sélectionnant un modèle prédéfini ou en utilisant l’une de vos suites de rapports existantes pour servir de modèle.

Descriptions des éléments utilisés lors de la [création d’une suite de rapports](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md).

>[!NOTE]
>
>La [documentation sur les suites de rapports virtuelles](/help/components/vrs/c-workflow-vrs/vrs-create.md) indique comment créer des suites de rapports virtuelles.

| Élément | Description |
| --- | --- |
| Identifiant de suite de rapports | Indique un ID unique pouvant uniquement contenir des caractères alphanumériques. Une fois créé, il ne peut plus être modifié. Adobe définit le préfixe d’ID requis qui lui non plus ne peut pas être modifié.  Lorsque vous créez plusieurs suites de rapports, assurez-vous que la convention de nommage utilisée garantit l’unicité des ID. |
| Titre du site | Identifie la suite de rapports dans les outils d’administration. Ce titre est également utilisé dans la liste déroulante Suite de rapports qui se trouve dans l’en-tête de la suite. |
| Fuseau horaire | Planifie des événements et applique un horodatage aux données. |
| URL de base | (Facultatif) Définit le domaine de base de la suite de rapports. Cette URL fonctionne comme un filtre URL externe si vous ne définissez pas explicitement de tels filtres pour la suite de rapports. |
| Page par défaut | (Facultatif) Élimine les occurrences de la valeur Page par défaut des URL qu’elle rencontre. Si votre rapport de pages les plus populaires contient des URL plutôt que des noms de page, ce paramètre empêche l’existence de plusieurs URL pour la même page web.  Par exemple, les URL `https://example.com` et `https://example.com/index.html` représentent généralement la même page.<p> Vous pouvez supprimer des noms de fichier superflus, de sorte que ces URL s’affichent sous la forme `https://example.com` dans vos rapports. Si vous ne définissez pas cette valeur, Analytics supprime automatiquement les noms de fichier suivants des URL : `index.htm`, `index.html`, `index.cgi`, `index.asp`, `default.htm`, `default.html`, `default.cgi`, `default.asp`, `home.htm`, `home.html`, `home.cgi` et `home.asp`. Pour désactiver l’élimination du nom de fichier, indiquez une valeur Page par défaut qui ne se présentera jamais dans vos URL. |
| Date d’activation | Informe Adobe de la date prévue pour l’activation de cette suite de rapports. Si votre calendrier de déploiement change, indiquez une estimation actualisée de votre trafic à l’aide de l’outil Trafic prévisionnel permanent sous Gestion du trafic. |
| Estimation du nombre de pages vues par jour | Identifie le nombre de pages vues qu’il est prévu que cette suite de rapports prenne en charge quotidiennement. Les gros volumes de trafic exigent un processus d’approbation plus long. Pour éviter les retards de traitement, tâchez de faire une estimation aussi précise que possible. |
| Devise de base | Indique la devise par défaut utilisée pour stocker toutes les données monétaires. La fonction de création de rapports d’Analytics convertit, dans la devise de base, les transactions effectuées dans d’autres devises en utilisant le taux de conversion en vigueur à la réception des données. La création de rapports Analytics utilise la variable JavaScript currencyCode pour identifier la devise d’une transaction donnée. |
|  Désactiver la prise en charge de caractères multioctet | Désactive la prise en charge des caractères multioctet pour la suite de rapports. Si vous désactivez la prise en charge de caractères multioctet, le système suppose que ces données sont au format `ISO-8859-1`. Les pages web doivent spécifier leur jeu de caractères dans la variable JavaScript charSet. <p>La prise en charge des caractères multioctet stocke les caractères dans la suite de rapports à l’aide du codage UTF-8. À la réception des données, le système les convertit depuis le jeu de caractères de la page web au format UTF-8, de sorte que vous puissiez utiliser n’importe quelle langue dans vos rapports marketing.  Contactez votre équipe de compte d’Adobe ou l’assistance clientèle pour modifier la prise en charge de caractères complexes pour une suite de rapports existante. |

{style="table-layout:auto"}
