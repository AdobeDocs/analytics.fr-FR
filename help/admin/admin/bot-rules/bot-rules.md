---
description: Les règles de robots vous permettent de supprimer de votre suite de rapports le trafic généré par des araignées et des robots (bots) connus. La suppression du trafic de robots permet d’obtenir une mesure plus précise de l’activité des utilisateurs sur votre site web.
seo-description: Les règles de robots vous permettent de supprimer de votre suite de rapports le trafic généré par des araignées et des robots (bots) connus. La suppression du trafic de robots permet d’obtenir une mesure plus précise de l’activité des utilisateurs sur votre site Web.
seo-title: Règles de robots
solution: Analytics
subtopic: Règles de robots
title: Règles de robots
topic: Outils d’administration
uuid: 3 cb 9 e 29 d -1 c 37-43 de-b 7 ac -34441093 a 60 e
translation-type: tm+mt
source-git-commit: 92ac6c03013bd68326e4136a5d512171fc831689

---


# Règles de robots

Les règles de robots vous permettent de supprimer le trafic de votre suite de rapports générée par des araignées et des robots connus. La suppression du trafic de robots permet d’obtenir une mesure plus précise de l’activité des utilisateurs sur votre site web.

Une fois les règles de robots définies, elles servent de critères de comparaison pour tout le trafic entrant. Le trafic qui correspond à l’une de ces règles n’est ni collecté dans la suite de rapports, ni inclus dans les mesures de trafic.

To update or upload bot rules, navigate to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**. Select the correct Report Suite, and then go to **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL General]** &gt; **[!UICONTROL Bot Rules]**.

En règle générale, la suppression du trafic de robots réduit le volume des mesures de trafic et de conversion. Pour de nombreux utilisateurs, la suppression du trafic de robots se traduit par une augmentation des taux de conversion et d’autres mesures d’utilisation. Avant de supprimer le trafic de robots, contactez les parties intéressées afin de vous assurer qu’elles sont en mesure d’apporter les modifications nécessaires aux indicateurs de performance clés à la suite de ce changement. Si possible, nous vous conseillons d’abord de supprimer le trafic de robots d’une petite suite de rapports afin d’évaluer l’impact potentiel.

>[!NOTE] Il est recommandé de ne pas définir plus de 500 règles de bots par suite de rapports. Il est possible de définir manuellement 500 règles dans l’interface utilisateur. Une fois cette limite atteinte, les règles doivent être gérées en vrac par l’intermédiaire des options [Importer un fichier](../../../admin/admin/bot-rules/t-upload-bot-rules.md#task_95868D8564564E6A996163335C119806) et Exporter des règles de bots.

Les données de trafic de robots sont stockées dans un référentiel distinct en vue d’être affichées dans les rapports [!UICONTROL Robots] et [!UICONTROL Pages de robots].

| Type de règle | Description |
|--- |--- |
| IAB | Selecting [!UICONTROL Include IAB] uses the IAB's (International Advertising Bureau's) International Spiders &amp; Bots List to remove bot traffic. Cette liste est mise à jour tous les mois par l’IAB. <br>Pour envoyer un robot à la liste IAB, rendez-vous sur [la page IAB](https://www.iab.net/sites/spiders/form.php). <br>Adobe n’est pas en mesure de fournir la liste des robots IAB détaillée aux clients. Vous pouvez cependant utiliser le rapport Robots pour consulter la liste des robots qui ont accédé à votre site. |
| Règles de robots personnalisées | Voir [Créer une règle de robot personnalisée](../../../admin/admin/bot-rules/t-create-bot-rules.md). |

## Incidence des règles de robots sur la collecte de données {#section_F01A3130E7A04A9993371CF26F6586F2}

Les règles de robots s’appliquent à toutes les données d’analyse. Les données supprimées par les règles de robots ne sont visibles que dans les rapports Robots et Pages de robots.

VISTA rules are applied after Bot Rules (see [Processing Order](../../../admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md#concept_8A6BBEA7F50C40C8A8D8755D4F579B1E)).

**Traitement de visites enregistrant de nombreux accès** : si plus de 100 accès se produisent au cours d’une visite, la fonction de création de rapports détermine si la durée de la visite (en secondes) est inférieure ou égale au nombre d’accès. Dans ce cas, compte tenu des coûts de traitement des visites longues et intensives, la création de rapports recommence avec une nouvelle visite. Les visites qui enregistrent de nombreux accès sont généralement causées par des attaques de robots et ne sont pas considérées comme ses sessions de navigation normales effectuées par des visiteurs.

>[!NOTE]
>
>Accès marqués comme *`bots`* étant facturés comme [appels au serveur](https://docs.adobe.com/content/help/en/analytics/admin/server-call-usage/overage-overview.html).

## Impact de l’obscurcissement des adresses IP sur le filtrage des robots {#section_92E60B95BE8940D983F28C79E0CD6B12}

La liste des robots IAB est basée uniquement sur l’agent-utilisateur. De ce fait, le filtrage basé sur cette liste n’est pas affecté par les paramètres d’obscurcissement d’IP. Pour le filtrage des robots non IAB (règles personnalisées), l’IP peut faire partie des critères de filtrage. Si vous filtrez des robots à l’aide de l’IP, le filtrage se produit une fois que le dernier octet a été supprimé, si ce paramètre est activé, mais avant les autres options d’obscurcissement d’IP, par exemple la suppression de l’ensemble de l’IP ou son remplacement par un identifiant unique.

Si l’obscurcissement d’IP est activé, l’exclusion de l’adresse IP survient avant l’obscurcissement ; ainsi, les clients n’ont rien à changer lorsqu’ils activent cette option.

Si le dernier octet est supprimé, ceci a lieu avant le filtrage IP. Par conséquent, le dernier octet est remplacé par un 0 et les règles d’exclusion IP doivent être mises à jour afin de correspondre aux adresses IP avec un zéro à la fin. Le * correspondant doit correspondre à 0.
