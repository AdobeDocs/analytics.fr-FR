---
title: Exclure par adresse IP
description: Empêchez les données générées par certaines adresses IP dʼapparaître dans les rapports.
exl-id: 315a3000-f043-434b-a677-d111aeed7971
feature: Admin Tools
role: Admin
source-git-commit: 4b4febd839682d88164b2f505245441d18ef2543
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 31%

---

# Exclure par adresse IP

Vous pouvez exclure de vos rapports les données d’adresses IP spécifiques (activités internes du site web, tests du site et utilisation par les employés, par exemple). L’élimination de données améliore la précision du rapport en excluant des données d’adresse IP. De plus, vous pouvez supprimer des données du déni de service ou d’autres événements malveillants susceptibles de fausser les données du rapport.

Pour exclure des données par adresse IP, vous pouvez configurer les exclusions comme décrit ci-dessous, ou [configurer votre pare-feu](/help/technotes/ip-addresses.md).

## Configuration des exclusions par adresse IP

>[!NOTE]
>
>Lors de la configuration des exclusions par adresse IP, tenez compte des points suivants :
>
>* Les accès exclus par adresse IP sont facturés en tant qu’[appels au serveur](/help/technotes/terms.md).
>* Les adresses IP privées ne doivent pas être exclues. Seules les adresses IP externes atteignent les serveurs de collecte de données dʼAdobe. Les adresses privées comprennent `10.*.*.*`, `192.168.*.*`, `172.[16-31].*.*` et `169.254.*.*`.
>* Vous pouvez utiliser des indicateurs génériques (&#42;) pour exclure une plage d’adresses. Par exemple, `[!DNL 0.0.*.0]` exclut toutes les adresses IP comprises entre `[!DNL 0.0.0.0]` et `[!DNL 0.0.255.0]`. Vous pouvez exclure jusqu’à 50 adresses IP différentes.
>* Les données provenant d’une adresse IP exclue sont exclues pour tout nouvel accès entrant dans le système dans les 5 minutes suivant la définition de l’exclusion.
>* Les données des accès capturées avant le moment où des modifications ont été apportées à l’adresse IP ne sont pas affectées. L’exclusion d’adresses IP s’applique uniquement aux données à partir de maintenant.
>* Les accès exclus sont toujours visibles dans les [Flux de données](/help/export/analytics-data-feed/data-feed-overview.md) (marqués comme `exclude_hit = 4`).

Pour configurer les exclusions par adresse IP :

1. Dans Adobe Analytics, sélectionnez **[!UICONTROL Admin]** > **[!UICONTROL Tous les administrateurs]**.

1. Sur la page Admin, sélectionnez **[!UICONTROL Exclure par IP]**.

## Impact de l’utilisation de l’obscurcissement des adresses IP avec l’exclusion des adresses IP

L’impact de l’utilisation de l’obscurcissement d’IP [IP](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) ainsi que de l’exclusion d’IP dépend du paramètre d’obscurcissement d’IP de chaque suite de rapports :

* **obscurcissement d’IP (dernier octet)** : l’adresse IP est partiellement obscurcie AVANT l’exécution de l’exclusion IP. Assurez-vous que les règles d’exclusion IP s’attendent toujours à une `0` comme dernier octet (les caractères génériques sont valides, car ils incluent `0`).
* **obscurcissement d’IP (supprimer l’adresse IP)** : l’adresse IP est entièrement obscurcie APRÈS l’exécution de l’exclusion IP. Aucune adaptation de règle d’exclusion IP n’est nécessaire.
