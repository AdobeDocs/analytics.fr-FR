---
title: Exclure par adresse IP
description: Empêchez l’affichage des données générées par certaines adresses IP dans les rapports.
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 85%

---


# Exclure par adresse IP

Vous pouvez exclure de vos rapports les données d’adresses IP spécifiques (activités internes du site web, tests du site et utilisation par les employés, par exemple). L’élimination de données améliore la précision du rapport en excluant des données d’adresse IP. De plus, vous pouvez supprimer les données des attaques par déni de service ou autres événements malveillants susceptibles de biaiser les résultats de vos rapports. Vous pouvez configurer l’exclusion en utilisant votre pare-feu.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Exclure par IP]**

>[!NOTE]
>
>Les accès exclus par adresse IP sont facturés en tant qu’[appels au serveur](https://docs.adobe.com/content/help/fr-FR/analytics/technotes/terms.html).

Vous pouvez utiliser des caractères de remplacement (*) pour exclure une plage d’adresses. Par exemple, `[!DNL 0.0.*.0]` exclut toutes les adresses IP comprises entre `[!DNL 0.0.0.0]` et `[!DNL 0.0.255.0]`. Vous pouvez exclure jusqu’à 50 adresses IP différentes.

>[!TIP]
>
>Les adresses IP privées ne doivent pas être exclues. Seules les adresses IP externes atteignent les serveurs de collecte de données d’Adobe. Les adresses privées sont `10.*.*.*`, `192.168.*.*`, `172.[16-31].*.*` et `169.254.*.*`.

## Impact de l’obscurcissement des adresses IP {#section_51B7529FFF16449CA016FDC51D87E2CA}

Si l’obscurcissement d’IP est activé, l’exclusion de l’adresse IP survient avant l’obscurcissement ; ainsi, les clients n’ont rien à changer lorsqu’ils activent cette option.

Si le dernier octet est supprimé, ceci a lieu avant le filtrage IP. Par conséquent, le dernier octet est remplacé par un 0 et les règles d’exclusion IP doivent être mises à jour afin de correspondre aux adresses IP avec un zéro à la fin. Le * correspondant doit correspondre à 0.
