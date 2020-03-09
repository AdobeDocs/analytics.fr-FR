---
description: Dans le panneau Options, vous pouvez spécifier les paramètres de date, les paramètres de latence (données actives), consigner des informations et configurer des mises à jour.
title: Options du Report Builder
topic: Report builder
uuid: f2920dee-4245-4617-a02e-03726dde2bb5
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Options du Report Builder

Dans le panneau Options, vous pouvez spécifier les paramètres de date, les paramètres de latence (données actives), consigner des informations et configurer des mises à jour.

1. Dans la barre d’outils Compléments, cliquez sur **[!UICONTROL Options]** ![](assets/options_icon.png) :

| Élément | Description |
|--- |--- |
| [!UICONTROL À partir de la date] |  |
| Définir sur la date actuelle | Permet de définir ou réinitialiser le champ [!UICONTROL À partir de la date], de telle sorte que le Créateur de rapports utilise la date actuelle ou vous demande la date à utiliser lors d’une opération d’actualisation. |
| Me rappeler de définir cette option lors de l’actualisation | Permet de définir le champ [!UICONTROL À partir de la date] lors de l’actualisation d’une requête. |
| [!UICONTROL Récence des données] |  |
| [!UICONTROL Inclure les données actives] | Permet d’afficher la latence des données (également appelée [!UICONTROL récence des données]) à la minute près dans les rapports d’analyse et parfois même avant leur traitement par Adobe Analytics.<br>Lorsque vous n’utilisez pas cette option, le mode finalisé (traité) est utilisé, ce qui est généralement plus [latent](https://marketing.adobe.com/resources/help/fr_FR/reference/data_latency.html).<br>Ce paramètre s’applique à toutes les requêtes du classeur qui sont compatibles avec les données actives. Si une requête n’est pas compatible, le mode finalisé est appliqué.<br>Notez les situations suivantes pour l’utilisation du mode [!UICONTROL Inclure les données actives], en particulier les <br>**Options de format ** : vous pouvez choisir d’afficher ou non ces informations ([!UICONTROL Récence des données]) lors de la[mise en forme des en-têtes d’affichage](/help/analyze/report-builder/layout/t-format-display-headers.md).<br>**Ventilations** : elles ne sont pas prises en charge. Si le mode [!UICONTROL Récence des données] est défini sur les données actives et si une des requêtes contient un élément de ventilation, celle-ci passe en mode autre que données actives. Toutefois, les autres requêtes continuent à utiliser le mode Données actives.<br>**Gestionnaire de requêtes ** : contient une colonne Données actives pour que vous puissiez voir si le paramètre est appliqué à une requête planifiée.<br>**Classeurs planifiés** : ce mode est stocké pendant le processus de planification au niveau des classeurs. Si vous ouvrez un classeur planifié qui utilise des données finalisées et que vous avez recours à l’option [!UICONTROL Inclure les données actives], le mode actif est utilisé par la suite.<br>**Permissions ** : cette option est masquée pour les utilisateurs qui n’ont pas accès aux données actives.  Lorsque cette option est activée, si une ou plusieurs requêtes ne peuvent pas être appliquées, un avertissement s’affiche. |
| Désactiver les avertissements de requête incompatible avec les données actives | Affiche des avertissements si le mode [!UICONTROL Inclure les données actives] est sélectionné mais que le mode des données ne peut pas être appliqué à la requête modifiée.  Par exemple, si vous définissez [!UICONTROL Inclure les données] et si vous modifiez ensuite une requête avec un segment sélectionné, un avertissement s’affiche. |
| Enregistrer les requêtes du Créateur de rapports dans un fichier local (à des fins de dépannage) | Permet d’enregistrer les requêtes dans un fichier local. Utilisez ce fichier journal à des fins de dépannage. |
| Interpréter la valeur saisie | Interprète la valeur saisie dans le contrôle de filtre comme un emplacement de cellule avant de la considérer comme une expression de filtre.<br>Si, par exemple, vous créez une requête sur les 10 meilleures pages à l’aide d’un filtre sur les chaussures, la requête affiche une cellule contenant un élément similaire à :   Filtre : 1 à 10 meilleures pages, page contenant des chaussures |
| Mettre à jour lorsqu’une nouvelle version est disponible | Indique au système de vous avertir lorsqu’il existe une nouvelle version à installer. |
