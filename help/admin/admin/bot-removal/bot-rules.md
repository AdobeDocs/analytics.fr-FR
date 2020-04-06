---
description: Les règles de robots vous permettent de supprimer de votre suite de rapports le trafic généré par des araignées et des robots connus. La suppression du trafic de robots peut fournir une mesure plus précise des d’utilisateurs   sur votre site Web.
subtopic: Bot rules
title: Règles de robots - Aperçu
topic: Admin tools
uuid: 3cb9e29d-1c37-43de-b7ac-34441093a60e
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Règles de robots - Aperçu

Les règles de robots vous permettent de supprimer du trafic de votre suite de rapports généré par des araignées et des robots connus. La suppression du trafic de robots peut fournir une mesure plus précise des d’utilisateurs   sur votre site Web.

Une fois les règles de robots définies, tout le trafic entrant est comparé aux règles définies. Le trafic qui correspond à l’une de ces règles n’est pas collecté dans la suite de rapports et n’est pas inclus dans les mesures de trafic.

Pour mettre à jour ou télécharger des règles de robots, accédez à **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**. Sélectionnez la suite de rapports appropriée, puis cliquez sur **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Bot Rules]**.

La suppression du trafic de robots réduit généralement le volume des mesures de trafic et de conversion. De nombreux clients estiment que la suppression du trafic de robots entraîne une augmentation des  de et des autres mesures de convivialité. Avant de supprimer le trafic de robots, communiquez avec les parties prenantes pour s’assurer qu’elles peuvent apporter les ajustements nécessaires aux indicateurs de performances clés à la suite de ce changement. Si possible, nous vous conseillons d’abord de supprimer le trafic de robots d’une petite suite de rapports afin d’évaluer l’impact potentiel.

Les données de trafic de robots sont stockées dans un référentiel distinct en vue d’être affichées dans les rapports Robots et Pages de robots. Il existe deux options pour activer le filtrage des robots :

| Type de règle | Description |
|--- |--- |
| Règles de robots IAB standard | Selecting [!UICONTROL Enable IAB Bot Filtering Rules] uses the [IAB&#39;s](https://www.iab.com) (International Advertising Bureau&#39;s) International Spiders &amp; Bots List to remove bot traffic. La plupart des clients sélectionnent au moins cette option. |
| Règles de robots personnalisées | Vous pouvez définir et ajouter des règles de robots personnalisées basées sur des agents utilisateurs, des adresses IP ou des plages d’adresses IP. |

## Règles de robots IAB standard

Les règles de robots IAB standard peuvent être activées en cochant la [!UICONTROL Enable IAB Bot Filtering Rules] case. Cette sélection va supprimer les robots de la liste internationale des robots (International Spiders &amp; Robots List) fournie par l’IAB (Bureau international de la publicité) pour supprimer le trafic de robots. L’IAB met cette liste à jour tous les mois.

![](assets/bot-iab-checkbox.png)

Adobe n’est pas en mesure de fournir la liste des robots IAB détaillée aux clients.Vous pouvez cependant utiliser le rapport Robots pour consulter la liste des robots qui ont accédé à votre site. Pour soumettre un robot à la liste de l’IAB, consultez l’[IAB](https://www.iab.com).

## Règles de robots personnalisées

>[!Note] : il est possible de définir manuellement 500 règles dans l’interface utilisateur. Au-delà de cette limite, les règles doivent être gérées en bloc au moyen des options Importer un fichier et Exporter des règles de robots.

Les règles de robots personnalisées vous permettent de filtrer les conditions de trafic que vous définissez.

Les règles de robots personnalisées sont définies à l’aide des types de condition suivants :

* Agent utilisateur
* Adresse IP
* Plage IP

Plusieurs conditions peuvent être définies pour une seule règle. Plusieurs conditions sont mises en correspondance à l’aide de &quot;ou&quot;. Si, par exemple, vous indiquez une valeur pour l’agent utilisateur et l’adresse IP, le trafic est considéré comme du trafic de robots si l’une des conditions est remplie.

### Agent utilisateur

A User Agent condition checks the user agent value to see if it **[!UICONTROL starts with]** or **[!UICONTROL contains]** the specified string. If **[!UICONTROL contains]** is selected, the substring is matched if it occurs anywhere in the user agent.

Optional values can be included in the **[!UICONTROL does not contain]** list to define values that the user agent must not contain for a successful match. Plusieurs valeurs peuvent être spécifiées en incluant une valeur par ligne. Si l’agent utilisateur répond aux critères spécifiés dans la chaîne de correspondance, mais qu’il contient également une chaîne sur la chaîne ne contient pas de , il n’est pas considéré comme une correspondance.

The **[!UICONTROL contains]** field is limited to 100 characters. Le  ne contient pas est limité à 255 caractères moins un séparateur pour chaque nouvelle ligne. (Il s’agit du nombre de chaînes - 1. Si vous spécifiez 4 *ne contient* pas de chaînes, 3 caractères de séparation sont requis.) Toutes les correspondances de chaînes ne sont pas sensibles à la casse.

### Adresse IP (avec correspondances de caractères génériques)

Correspond à une ou plusieurs adresses IP dans le même bloc à l’aide de caractères génériques (*). Indiquez les valeurs numériques de l’adresse IP que vous souhaitez faire correspondre. Remplacez * par les valeurs que vous souhaitez faire correspondre à l’aide d’un caractère générique. Le  suivant contient des exemples de chaîne de correspondance d’adresse IP :

```
10.10.10.1
10.10.10.*
```

### Plage d’adresses IP

Fournissez les  et plages de fin des adresses IP à associer. Remplacez * par les valeurs que vous souhaitez faire correspondre à l’aide d’un caractère générique.

### Définir une règle de robot personnalisée

1. Accédez à **[!UICONTROL Analytics]** > **[!UICONTROL Admin]**, sélectionnez une ou plusieurs suites de rapports et cliquez sur **[!UICONTROL General]** > **[!UICONTROL Bot Rules]**.
1. Click **[!UICONTROL Add Rule]** and define one or more match conditions.
1. Cliquez sur **[!UICONTROL Save]**. La modification doit normalement être prise en compte dans les 30 minutes.

## Télécharger des règles de robots

Pour importer des règles de robots en bloc, vous pouvez télécharger un fichier CSV qui définit les règles.

Créez un fichier CSV avec les colonnes suivantes, en respectant l’ordre indiqué :

| Colonne 1 | Colonne 2 | Colonne 3 | Colonne 4 | Colonne 5 |
|--- |--- |---|---|---|
| Nom du robot | Début IP | Fin IP | Règle de correspondance de l’agent<br>(contient ou commence par)</br> | Agent - Exclure<br>(255 caractères max.)</br> |

Vous pouvez définir trois types de règles de robots :

* L’agent utilisateur contient ou  avec
* Correspondance d’adresse IP unique ou de caractère générique
* Correspondance de plage IP

Chaque ligne du fichier d’importation ne peut contenir qu’une seule des définitions de robots suivantes :

* **L’agent utilisateur contient ou  avec**: Fournissez une seule chaîne d’agent utilisateur à faire correspondre dans la colonne Agent - Inclure. Indiquez le type de correspondance que vous souhaitez effectuer en plaçant *contient* ou avec ** dans le champ Règle de correspondance de l’agent. Vous pouvez inclure une valeur facultative dans la colonne Agent - Exclure pour définir une ou plusieurs chaînes délimitées par une barre verticale (`|`) que l’agent ne contient pas. Les correspondances de chaînes ne sont pas sensibles à la casse. Les colonnes  de l’IP et Fin d’IP doivent être vides.

* **Correspondance d’une seule adresse IP ou d’un seul caractère générique** : pour établir une correspondance avec une seule adresse IP (`10.10.10.1`) ou une adresse IP avec un caractère générique (`10.10.*.*`), indiquez la même valeur dans les colonnes Début IP et Fin IP. Règle de correspondance de l’agent, Agent - Inclure et Agent - Exclure doivent être vides.

* **Correspondance** de plage IP : Définissez une plage d’adresses IP à l’aide des colonnes  d’IP et Fin d’IP. Vous pouvez utiliser des caractères génériques pour faire correspondre des plages d’adresses IP ; par exemple `10.10.10.*` avec `10.10.20.*`. Règle de correspondance de l’agent, Agent - Inclure et Agent - Exclure doivent être vides.

### Combinaison de plusieurs règles avec l’opérateur « OU »

Pour faire correspondre un robot à l’aide d’une combinaison de règles associées à un opérateur OU (par exemple, agent utilisateur ou adresse IP), attribuez un nom identique à toutes les règles que vous souhaitez combiner dans le champ du nom du robot. Les correspondances ET ne sont pas prises en charge.

### Remplacer toutes les règles par un fichier de téléchargement

Select the **[!UICONTROL Overwrite existing rules]** checkbox to delete all existing rules and replace them with the rules defined in the upload file.

### Exporter des règles

The **[!UICONTROL Export Uploaded Bot File]** button exports all rules defined in the UI in a CSV format.


## Incidence des règles de robots sur la collecte de données {#section_F01A3130E7A04A9993371CF26F6586F2}

Les règles de robots s’appliquent à toutes les données d’analyse. Les données supprimées par les règles de robots ne sont visibles que dans les rapports Robots et Pages de robots.

Les règles VISTA sont appliquées après les règles de robots (voir [Ordre de traitement).](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md)

**Traitement des visites à accès élevé :** Si plus de 100 accès se produisent au cours d’une visite, le  de détermine si la durée de la visite en secondes est inférieure ou égale au nombre d’accès de la visite. Dans cette situation, en raison du coût du traitement de longues et intenses visites, les  de la  avec une nouvelle visite. Les visites à accès élevé sont généralement causées par des attaques de robots et ne sont pas considérées comme une navigation normale.

>[!NOTE] Les accès marqués comme *`bots`* sont facturés comme des [appels au serveur.](/help/admin/c-server-call-usage/overage-overview.md)

## Impact de l’obscurcissement des adresses IP sur le filtrage des robots {#section_92E60B95BE8940D983F28C79E0CD6B12}

Le de robots IAB est basé uniquement sur l’agent utilisateur. Le filtrage basé sur ce n’est donc pas affecté par les paramètres d’obscurcissement d’IP. Pour le filtrage des robots non IAB (règles personnalisées), l’IP peut faire partie des critères de filtrage. Si vous filtrez des robots à l’aide de l’adresse IP, le filtrage des robots se produit après la suppression du dernier octet si ce paramètre est activé, mais avant les autres options d’obscurcissement d’IP, comme la suppression de l’intégralité de l’adresse IP ou son remplacement par un identifiant unique.

Si l’obscurcissement d’IP est activé, l’exclusion d’IP survient avant que l’adresse IP ne soit obscurcie. Les clients n’ont donc rien à changer lorsqu’ils activent l’obscurcissement d’IP.

Si le dernier octet est supprimé, cela se fait avant le filtrage IP. Ainsi, le dernier octet est remplacé par un 0 et les règles d’exclusion IP doivent être mises à jour pour correspondre aux adresses IP avec un zéro à la fin. Le * correspondant doit correspondre à 0.
