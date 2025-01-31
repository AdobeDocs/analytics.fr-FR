---
description: Description des champs Paramètres du compte général d’une suite de rapports dans Admin.
title: Paramètres du compte général
feature: Admin Tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
exl-id: f49babb2-8e26-4cc6-b264-b4d7be93f130
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 84%

---

# Paramètres du compte général

Description des champs Paramètres du compte général d’une suite de rapports dans Admin.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Général]** > **[!UICONTROL Paramètres du compte général]**

Ces paramètres contiennent des options d’édition pour les fonctionnalités de base de la suite de rapports, ainsi que le nom et le fuseau horaire.


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuration des paramètres généraux du compte](https://video.tv.adobe.com/v/332330/?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]

| Option | Description |
|--- |--- |
| Titre du site | Identifie votre site. Attribuez un nom de site unique à chaque suite de rapports. |
| URL de base | Indique le site Web principal de la suite de rapports. L’URL de base n’affecte pas le filtrage par référent. Utiliser [filtres URL internes](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md). |
| Fuseau horaire | Détermine l’heure et la date associées aux données du rapport.  Le changement du fuseau horaire d’une suite de rapports active crée un pic ou un creux dans les données du rapport. Adobe conseille de changer de fuseau horaire pendant les heures creuses pour éviter de biaiser les données.  Par exemple, si vous changez le fuseau horaire de Moscou sur celui de Paris à 15h00, l’heure de la suite de rapports passe à 13h00. Étant donné que l’outil de création de rapports a déjà collecté les données pour 13h00, un pic de trafic apparaît dans les rapports entre 13h00 et 15h00.  Si vous changez le fuseau horaire de Moscou sur celui d’Abu Dhabi à 15h00, l’heure de la suite de rapports passe à 16h00. Les rapports n’affichent aucune donnée entre 15h00 et 16h00 le jour du changement d’heure. |
| Page par défaut | Si votre rapport [!UICONTROL Pages les plus populaires] contient des URL plutôt que des noms de page, ce paramètre empêche plusieurs URL de représenter la même page. Par exemple, les URL `https://example.com` et `https://example.com/index.html` représentent généralement la même page. Vous pouvez supprimer les noms de fichier par défaut, de telle sorte que ces deux URL s’affichent sous la forme `https://example.com`.  Si la zone n’est pas renseignée, les noms de fichier suivants sont supprimés des URL : index.htm, index.html, index.cgi, index.asp, default.htm, default.html, default.cgi, default.asp, home.htm, home.html, home.cgi et home.asp.  Pour désactiver entièrement cette option de réduction des noms de fichier, entrez une valeur qui n’existera jamais dans vos URL. |
| Remplacer le dernier octet des adresses IP par 0 | Lorsqu’elle est activée, remplace le dernier octet des adresses IP par un zéro. Cela se produit avant que les rapports géographiques ne soient renseignés et peut donc avoir une incidence sur l’exactitude de ces rapports. |
| Obscurcissement d’IP | Transforme les adresses IP en chaînes impossibles à reconnaître, en les supprimant essentiellement des entrepôts de données d’Adobe. Lorsque l’option Obscurcissement d’IP est activée, les adresses IP d’origine sont définitivement perdues. <br> **Remarque** : les adresses IP sont obscurcies partout dans Analytics, y compris dans Data Warehouse. Toutefois, le paramètre IP dans Target est contrôlé individuellement, de sorte que ce paramètre n’a aucune incidence sur Target.<br> Si l’obscurcissement d’IP est activé, tout le traitement nécessaire, y compris le filtrage/l’exclusion IP, les règles de robots et les recherches de géosegmentation, est effectué avant l’obscurcissement de l’adresse IP. Vous ne devez rien changer lorsque vous activez l’obscurcissement d’IP.<ul><li>Cochez l’option **Désactivé** pour conserver l’adresse IP dans les données.</li><li>Cochez l’option **Obscurcir les adresses IP** pour remplacer l’adresse IP par deux fois deux points suivis d’une valeur de hachage (par exemple, `::1932023538`).</li><li>Cochez l’option **Supprimer les adresses IP** pour remplacer l’adresse IP par `::X.X.X.X` dans les données, après la recherche géographique.</li></ul>**Remarque** : ce paramètre peut nécessiter des modifications des [règles de robots](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) ou des [exclusions d’adresses IP](/help/admin/admin/exclude-ip.md) personnalisées.<br> **Remarque** : les données collectées à l’aide de Web SDK peuvent faire l’objet d’un obscurcissement des adresses IP au niveau de l’Edge Network via [configuration du flux de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html#@advanced-options). Si l’obscurcissement d’IP est appliqué à l’Edge Network, il l’est déjà lorsqu’il atteint Analytics. Cette obfuscation a un impact sur les règles de robots et les recherches géographiques. |
| Stockage de l’ID de transaction | Permet d’utiliser des sources de données [ID de transaction](/help/import/data-sources/transactionid.md). |
| Activer Data Warehouse | Active l’interface utilisateur de Data Warehouse dans Analytics > Outils > Data Warehouse. |
| Option de code postal | Vous permet de spécifier le code postal au lieu d’utiliser les résultats de la recherche géographique d’adresses IP. |
| Prise en charge des caractères à plusieurs octets | La prise en charge des caractères à plusieurs octets stocke les caractères dans la suite de rapports à l’aide du codage UTF-8. À la réception des données, le système les convertit depuis le jeu de caractères de la page Web au format UTF-8, afin que vous puissiez utiliser n’importe quelle langue dans vos rapports marketing. Contactez votre équipe Adobe en charge des comptes ou le service d’assistance clientèle pour modifier la prise en charge des caractères à plusieurs octets d’une suite de rapports existante. |
| Activation | Indique si cette suite de rapports est activée ou non. |
| Devise de base | Permet de définir la [devise](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/currencycode.html?lang=fr) de base pour cette suite de rapports. |
| ID d’organisation | ID dʼorganisation associé à la société Experience Cloud activée. Cet identifiant correspond à une chaîne de 24 caractères alphanumériques, suivie de @AdobeOrg (obligatoire). |
