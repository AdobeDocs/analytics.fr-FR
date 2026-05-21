---
description: En savoir plus sur les options de Report Builder.
title: À propos des options de Report Builder
uuid: f2920dee-4245-4617-a02e-03726dde2bb5
feature: Report Builder
role: User, Admin
exl-id: d3388990-7919-461d-a96e-4c996b8bdb8b
TQID: https://experienceleague.adobe.com/56Wyy-f9kDXxFSanTNILr4rNQ0OB3YtbIFPcRT082sc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 474
ht-degree: 53%

---

# Options du Report Builder

{{legacy-arb}}

Dans le panneau Options, vous pouvez spécifier les paramètres de date, les paramètres de latence (données actives), consigner des informations et configurer des mises à jour.

1. Dans la barre d&#39;outils Compléments, cliquez sur **[!UICONTROL Options]** ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) :

| Élément | Description |
|--- |--- |
| [!UICONTROL À partir de la date] |  |
| Définir sur la date actuelle | Permet de spécifier ou de réinitialiser la [!UICONTROL À partir de la date] de sorte que Report Builder utilise la date actuelle ou vous demande quelle date utiliser lors de l’actualisation. |
| Me rappeler de définir cette option lors de l’actualisation | Permet de définir le champ [!UICONTROL À partir de la date] lors de l’actualisation d’une requête. |
| [!UICONTROL Récence des données] |  |
| [!UICONTROL Inclure les données actives] | Permet d’afficher la latence des données (également appelée [!UICONTROL Récence des données]) jusqu’à la minute dans les rapports, parfois même avant que ces données ne soient traitées par Adobe Analytics.<br>Lorsque vous n’utilisez pas cette option, le mode finalisé (traité) est utilisé, généralement plus latent.<br>Ce paramètre s’applique à toutes les requêtes du classeur qui sont compatibles avec les données actives. Si une requête n’est pas compatible, le mode finalisé est appliqué.<br>Notez les situations suivantes pour l’utilisation du mode [!UICONTROL Inclure les données actives] :<br>**Options de format** : vous pouvez spécifier si ces informations doivent être affichées ([!UICONTROL Récence des données]) lorsque [formatage des en-têtes d’affichage](/help/analyze/legacy-report-builder/layout/t-format-display-headers.md).<br>**Répartitions** : non pris en charge. Si le mode [!UICONTROL Récence des données] est défini sur les données actives et si une des requêtes contient un élément de ventilation, celle-ci passe en mode autre que données actives. Toutefois, d’autres requêtes continuent d’utiliser le mode Données actives.<br>**Gestionnaire de requêtes** : contient une colonne Données actives pour que vous puissiez voir si le paramètre est appliqué à une requête planifiée.<br>**Classeurs planifiés** : ce mode est stocké pendant le processus de planification au niveau des classeurs. Si vous ouvrez un classeur planifié qui utilise les données finalisées et appliquez [!UICONTROL Inclure les données actives], le mode actif est utilisé par la suite.<br>**Autorisations** : pour les utilisateurs qui n’ont pas accès aux données actives, cette option est masquée.  Lorsque vous activez cette option, si une ou plusieurs requêtes ne peuvent pas être appliquées, un avertissement est émis. |
| Désactiver les avertissements de requête incompatibles avec les données actuelles | Affiche des avertissements si le mode [!UICONTROL Inclure les données actives] est sélectionné mais que le mode des données ne peut pas être appliqué à la requête modifiée.  Par exemple, si vous définissez [!UICONTROL Inclure les données] et si vous modifiez ensuite une requête avec un segment sélectionné, un avertissement s’affiche. |
| Enregistrer les requêtes Report Builder dans un fichier local (pour le dépannage) | Permet d’enregistrer les requêtes dans un fichier local. Utilisez ce fichier journal pour résoudre les problèmes. |
| Interpréter la valeur saisie... | Interprète la valeur saisie dans le contrôle de filtre comme un emplacement de cellule avant de la considérer comme une expression de filtre.<br>Si, par exemple, vous créez une requête sur les 10 meilleures pages à l’aide d’un filtre sur les chaussures, la requête affiche une cellule contenant un élément similaire à :   Filtre : 1 à 10 meilleures pages, page contenant des chaussures |
| Mettre à jour lorsqu’une nouvelle version est disponible | Indique au système de vous avertir si une nouvelle version est disponible pour installation. |
