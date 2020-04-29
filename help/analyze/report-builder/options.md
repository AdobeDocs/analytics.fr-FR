---
description: Dans le panneau Options, vous pouvez spécifier les paramètres de date, les paramètres de latence (données actives), consigner des informations et configurer des mises à jour.
title: Options du Report Builder
topic: Report builder
uuid: f2920dee-4245-4617-a02e-03726dde2bb5
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Options du Report Builder

Dans le panneau Options, vous pouvez spécifier les paramètres de date, les paramètres de latence (données actives), consigner des informations et configurer des mises à jour.

1. Dans la barre d’outils Compléments, cliquez sur **[!UICONTROL Options]**![](assets/options_icon.png)  :

| Élément | Description |
|--- |--- |
| [!UICONTROL As Of Date] |  |
| Définir sur la date actuelle | Lets you specify or reset the  [!UICONTROL As Of Date] so that report builder uses the current date or asks you which date to use upon refresh. |
| Me rappeler de définir cette option lors de l’actualisation | Vous permet de définir la variable [!UICONTROL As Of Date] lors de l’actualisation d’une requête. |
| [!UICONTROL Data Recency] |  |
| [!UICONTROL Include Current Data] | Lets you view data latency (also known as  [!UICONTROL Data Recency]) down to the minute in reporting, occasionally even before this data has been processed by  Adobe Analytics.<br>Lorsque vous n’utilisez pas cette option, le mode finalisé (traité) est utilisé, ce qui est généralement plus [latent](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/current-data.html).<br>Ce paramètre s’applique à toutes les requêtes du classeur qui sont compatibles avec les données actives. Si une requête n’est pas compatible, le mode finalisé est appliqué.<br>Notez les situations suivantes pour l’utilisation du mode [!UICONTROL Include Current Data] :Options<br>**de **format : Vous pouvez indiquer si ces informations doivent être affichées ([!UICONTROL Data Recency]) lors du[formatage des en-têtes](/help/analyze/report-builder/layout/t-format-display-headers.md)d’affichage.<br>**Ventilations** : elles ne sont pas prises en charge. If the  [!UICONTROL Data Recency] mode is set to the Current Data, and one of the requests contains a break-down element, this request reverts to non-current data mode. Toutefois, les autres requêtes continuent à utiliser le mode Données actives.<br>**Gestionnaire de requêtes ** : contient une colonne Données actives pour que vous puissiez voir si le paramètre est appliqué à une requête planifiée.<br>**Classeurs planifiés** : ce mode est stocké pendant le processus de planification au niveau des classeurs. If you open a scheduled workbook that is using finalized data, and apply [!UICONTROL Include Current Data], current mode is used thereafter.<br>**Permissions ** : cette option est masquée pour les utilisateurs qui n’ont pas accès aux données actives.  Lorsque cette option est activée, si une ou plusieurs requêtes ne peuvent pas être appliquées, un avertissement s’affiche. |
| Désactiver les avertissements de requête incompatible avec les données actives | Displays warnings if the  [!UICONTROL Include Current Data] mode is selected but the data mode cannot be applied to the edited request.  For example, if you set [!UICONTROL Include Current Data], and then edit a request that has a segment selected, a warning is issued. |
| Enregistrer les requêtes du Créateur de rapports dans un fichier local (à des fins de dépannage) | Permet d’enregistrer les requêtes dans un fichier local. Utilisez ce fichier journal à des fins de dépannage. |
| Interpréter la valeur saisie | Interprète la valeur saisie dans le contrôle de filtre comme un emplacement de cellule avant de la considérer comme une expression de filtre.<br>Si, par exemple, vous créez une requête sur les 10 meilleures pages à l’aide d’un filtre sur les chaussures, la requête affiche une cellule contenant un élément similaire à :   Filtre : 1 à 10 meilleures pages, page contenant des chaussures |
| Mettre à jour lorsqu’une nouvelle version est disponible | Indique au système de vous avertir lorsqu’il existe une nouvelle version à installer. |
