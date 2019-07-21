---
description: Dans le panneau Options, vous pouvez spécifier les paramètres de date, les paramètres de latence (données actives), consigner des informations et configurer des mises à jour.
seo-description: Dans le panneau Options, vous pouvez spécifier les paramètres de date, les paramètres de latence (données actives), consigner des informations et configurer des mises à jour.
seo-title: Options du créateur de rapports
solution: Analytics
title: Options du créateur de rapports
topic: Créateur de rapports
uuid: f 2920 dee -4245-4617-a 02 e -03726 dde 2 bb 5
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Options du créateur de rapports

Dans le panneau Options, vous pouvez spécifier les paramètres de date, les paramètres de latence (données actives), consigner des informations et configurer des mises à jour.

1. Dans la barre d’outils Compléments, cliquez sur **[!UICONTROL Options]** ![](assets/options_icon.png):

| Élément | Description |
|--- |--- |
| [!UICONTROL À partir de la date] |  |
| Définir sur la date actuelle | Permet de définir ou réinitialiser le champ [!UICONTROL À partir de la date], de telle sorte que le Créateur de rapports utilise la date actuelle ou vous demande la date à utiliser lors d’une opération d’actualisation. |
| Me rappeler de définir cette option lors de l’actualisation | Permet de définir le champ [!UICONTROL À partir de la date] lors de l’actualisation d’une requête. |
| [!UICONTROL Récence des données] |  |
| [!UICONTROL Inclure les données actives] | Permet d’afficher la latence des données (également appelée [!UICONTROL récence des données]) à la minute près dans les rapports d’analyse et parfois même avant leur traitement par Adobe Analytics.<br>Lorsque vous n'utilisez pas cette option, le mode finalisé (traité) est utilisé, ce qui est généralement plus [latent](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=data_latency).<br>Ce paramètre s’applique à toutes les requêtes du classeur qui sont compatibles avec les données actives. Si une requête n’est pas compatible, le mode finalisé est appliqué.<br>Notez les situations suivantes pour l'utilisation du [!UICONTROL mode Inclure les données] actives :<br>**Options de format**: Vous pouvez indiquer si ces informations doivent être affichées ([!UICONTROL récence des données]) lors [du formatage des en-têtes d'affichage](../../analyze/report-builder/layout/t-format-display-headers.md).<br>**Ventilations** : elles ne sont pas prises en charge. Si le mode [!UICONTROL Récence des données] est défini sur les données actives et si une des requêtes contient un élément de ventilation, celle-ci passe en mode autre que données actives. Toutefois, les autres requêtes continuent à utiliser le mode Données actives.<br>**Gestionnaire de requêtes** : contient une colonne Données actives pour que vous puissiez voir si le paramètre est appliqué à une requête planifiée.<br>**Classeurs planifiés** : ce mode est stocké pendant le processus de planification au niveau des classeurs. If you open a scheduled workbook that is using finalized data, and apply [!UICONTROL Include Current Data], current mode is used thereafter.<br>**Permissions** : cette option est masquée pour les utilisateurs qui n’ont pas accès aux données actives.  Lorsque cette option est activée, si une ou plusieurs requêtes ne peuvent pas être appliquées, un avertissement s’affiche. |
| Désactiver les avertissements de requête incompatible avec les données actives | Affiche des avertissements si le mode [!UICONTROL Inclure les données actives] est sélectionné mais que le mode des données ne peut pas être appliqué à la requête modifiée.  Par exemple, si vous définissez [!UICONTROL Inclure les données] et si vous modifiez ensuite une requête avec un segment sélectionné, un avertissement s’affiche.  |
| Enregistrer les requêtes du Créateur de rapports dans un fichier local (à des fins de dépannage) | Permet d’enregistrer les requêtes dans un fichier local. Utilisez ce fichier journal à des fins de dépannage. |
| Interpréter la valeur saisie | Interprète la valeur saisie dans le contrôle de filtre comme un emplacement de cellule avant de la considérer comme une expression de filtre. <br>Par exemple, si vous créez une requête 10 premières pages, à l'aide d'un filtre, la requête affiche une cellule contenant des éléments similaires à : Filtre : 1 à 10 premières pages, Page contient Chaussures |
| Mettre à jour lorsqu’une nouvelle version est disponible | Indique au système de vous avertir lorsqu’il existe une nouvelle version à installer. |
