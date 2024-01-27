---
title: Exclure par adresse IP
description: Empêchez les données générées par certaines adresses IP dʼapparaître dans les rapports.
exl-id: 315a3000-f043-434b-a677-d111aeed7971
feature: Admin Tools
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 94%

---

# Exclure par adresse IP

Vous pouvez exclure de vos rapports les données d’adresses IP spécifiques (activités internes du site web, tests du site et utilisation par les employés, par exemple). L’élimination de données améliore la précision du rapport en excluant des données d’adresse IP. De plus, vous pouvez supprimer les données des attaques par déni de service ou autres événements malveillants susceptibles de biaiser les résultats de vos rapports. Vous pouvez configurer l’exclusion en utilisant votre pare-feu.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Tous les administrateurs]** > **[!UICONTROL Exclure par adresse IP]**

>[!NOTE]
>
>Les accès exclus par adresse IP sont facturés en tant qu’[appels au serveur](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=fr).

Vous pouvez utiliser des indicateurs de caractères génériques (&#42;) pour exclure une plage d’adresses. Par exemple, `[!DNL 0.0.*.0]` exclut toutes les adresses IP comprises entre `[!DNL 0.0.0.0]` et `[!DNL 0.0.255.0]`. Vous pouvez exclure jusqu’à 50 adresses IP différentes.

>[!TIP]
>
>Les adresses IP privées ne doivent pas être exclues. Seules les adresses IP externes atteignent les serveurs de collecte de données dʼAdobe. Les adresses privées comprennent `10.*.*.*`, `192.168.*.*`, `172.[16-31].*.*` et `169.254.*.*`.

## Impact de l’obscurcissement des adresses IP {#section_51B7529FFF16449CA016FDC51D87E2CA}

Si l’obscurcissement d’IP est activé, l’exclusion de l’adresse IP survient avant l’obscurcissement ; ainsi, les clients n’ont rien à changer lorsqu’ils activent cette option.

Si le dernier octet est supprimé, ceci a lieu avant le filtrage IP. Par conséquent, le dernier octet est remplacé par un 0 et les règles d’exclusion IP doivent être mises à jour afin de correspondre aux adresses IP avec un zéro à la fin. Le &#42; correspondant doit correspondre à 0.
