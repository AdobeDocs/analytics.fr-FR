---
description: Description des champs Paramètres du compte général d’une suite de rapports dans Admin.
title: Paramètres du compte général
topic: Outils d’administration
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
translation-type: tm+mt
source-git-commit: d0fe97b9368cbc4c9e79f9e56adf9786b58dce1a
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 88%

---


# Paramètres du compte général

Description des champs Paramètres du compte général d’une suite de rapports dans Admin.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Général]** > **[!UICONTROL Paramètres du compte général]**

Ces paramètres contiennent des options d’édition pour les fonctionnalités de base de la suite de rapports, ainsi que le nom et le fuseau horaire.

| Option | Description |
|--- |--- |
| Titre du site | Identifie votre site. Attribuez un nom de site unique à chaque suite de rapports. |
| URL de base | Indique le site Web principal de la suite de rapports. L’URL de base n’affecte pas le filtrage par référent. Utiliser [filtres URL internes](/help/admin/admin/internal-url-filter-admin.md). |
| Fuseau horaire | Détermine l’heure et la date associées aux données du rapport.  Le changement du fuseau horaire d’une suite de rapports active crée un pic ou un creux dans les données du rapport. Adobe conseille de changer de fuseau horaire pendant les heures creuses pour éviter de biaiser les données.  Par exemple, si vous changez le fuseau horaire de Moscou sur celui de Paris à 15h00, l’heure de la suite de rapports passe à 13h00. Étant donné que l’outil de création de rapports a déjà collecté les données pour 13h00, un pic de trafic apparaît dans les rapports entre 13h00 et 15h00.  Si vous changez le fuseau horaire de Moscou sur celui d’Abu Dhabi à 15h00, l’heure de la suite de rapports passe à 16h00. Les rapports n’affichent aucune donnée entre 15h00 et 16h00 le jour du changement d’heure. |
| Page par défaut | Si votre rapport [!UICONTROL Pages les plus populaires] contient des URL plutôt que des noms de page, ce paramètre empêche plusieurs URL de représenter la même page. Par exemple, les URL `https://example.com` et `https://example.com/index.html` représentent généralement la même page. Vous pouvez supprimer les noms de fichier par défaut, de telle sorte que ces deux URL s’affichent sous la forme `https://example.com`.  Si la zone n’est pas renseignée, les noms de fichier suivants sont supprimés des URL : index.htm, index.html, index.cgi, index.asp, default.htm, default.html, default.cgi, default.asp, home.htm, home.html, home.cgi et home.asp.  Pour désactiver entièrement cette option de réduction des noms de fichier, entrez une valeur qui n’existera jamais dans vos URL. |
| Remplacer le dernier octet des adresses IP par 0 | La suppression du dernier octet est effectuée avant tout traitement de l’accès, y compris avant le filtrage/exclusion IP, avant la vérification des règles de robots, avant les recherches de géosegmentation, etc. Par conséquent, le dernier octet est remplacé par un 0 et les règles d’exclusion IP doivent être mises à jour afin de correspondre aux adresses IP avec un zéro à la fin. Le * correspondant doit correspondre à 0. Par exemple, l’adresse IP 11.22.33.44 est remplacée par 11.22.33.0. Les données de géosegmentation ne sont pas aussi exactes que lorsque l’adresse IP complète est utilisée. Plus précisément, la précision au niveau de la ville va être plus affectée que la précision au niveau du pays ou de la région. Les règles de robot et les règles VISTA sont affectées puisqu’elles n’ont pas accès à l’adresse IP complète. En outre, les règles de traitement basées sur les adresses IP (y compris les règles de canaux marketing et les règles de traitement des suites de rapports) sont affectées par ce paramètre. <br> **Remarque** : ce paramètre est activé par défaut pour toutes les suites de rapports créées dans le centre de données de Londres après janvier 2019, mais seulement si les paramètres de ces suites de rapports sont copiés à partir d’un modèle répertorié dans Admin Console. Les suites de rapports dont les paramètres sont copiés depuis d’autres suites de rapports hériteront de tous les paramètres de la suite de rapports sélectionnée. |
| Obscurcissement d’IP | Transforme les adresses IP en chaînes impossibles à reconnaître, en les supprimant essentiellement des entrepôts de données d’Adobe. Lorsque l’option Obscurcissement d’IP est activée, les adresses IP d’origine sont définitivement perdues.  <br> **Remarque** : les adresses IP sont obscurcies partout dans Analytics, y compris dans Data Warehouse. Toutefois, le paramètre IP dans Target est contrôlé individuellement, de sorte que ce paramètre n’a aucune incidence sur Target.<br> Si l’obscurcissement d’IP est activé, tous les traitements nécessaires, y compris le filtrage/l’exclusion IP, les règles de robots et les recherches de géosegmentation, sont effectués avant que l’adresse IP ne soit obscurcie. Il n’est pas nécessaire de modifier quoi que ce soit lorsque vous activez l’obscurcissement d’IP.<ul><li>Si **Désactivé** est coché, l’adresse IP est conservée dans les données.</li><li>Si vous cochez la case **Obscurcir l&#39;adresse IP**, l&#39;adresse IP devient deux points suivis d&#39;une valeur hachée (par exemple, `::1932023538`).</li><li>Cochez l’option **Supprimer les adresses IP**`::X.X.X.X` pour remplacer l’adresse IP par dans les données, après la recherche géographique.</li></ul>**Remarque** : ce paramètre peut nécessiter de modifier les [règles de robots personnalisées](/help/admin/admin/bot-removal/bot-rules.md) ou des [exclusions IP](/help/admin/admin/exclude-ip.md). |
| Stockage de l’ID de transaction | Permet d’utiliser des sources de données [ID de transaction](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md). |
| Activer Data Warehouse | Active l’interface utilisateur de Data Warehouse dans Analytics > Outils > Data Warehouse. |
