---
description: Les règles de robots vous permettent de supprimer de votre suite de rapports le trafic généré par des araignées et des robots (bots) connus. La suppression du trafic de robots permet d’obtenir une mesure plus précise de l’activité des utilisateurs sur votre site web.
title: Comprendre et configurer des règles de robot
feature: Bot Removal
role: Admin
exl-id: 1c0009f6-2746-4ef1-8dcb-e2693617e91e
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '1668'
ht-degree: 68%

---

# Comprendre et configurer des règles de robot

Les règles de robots vous permettent de supprimer du trafic de votre suite de rapports généré par des araignées et des robots connus. La suppression du trafic de robots permet d’obtenir une mesure plus précise de l’activité des utilisateurs sur votre site web.

Une fois les règles de robots définies, elles servent de critères de comparaison pour tout le trafic entrant. Le trafic qui correspond à l’une de ces règles n’est ni collecté dans la suite de rapports, ni inclus dans les mesures de trafic.

En règle générale, la suppression du trafic de robots réduit le volume des mesures de trafic et de conversion. De nombreux clients et clientes constatent que la suppression du trafic de robots entraîne une augmentation des taux de conversion et d’autres mesures d’utilisation.

Les données de trafic de robots sont stockées dans un référentiel distinct pour être affichées dans les rapports Robots et Pages de robots .

>[!NOTE]
>
>Adobe Experience Platform Edge Network fournit un [service de détection de robots](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=fr) qui classe les accès identifiés comme provenant de robots. Le processus de détection de robots utilisé dans Adobe Analytics est distinct et ne fait pas référence au score de robots inclus dans les données arrivant via Edge Network. Toutefois, les deux systèmes utilisent la même liste de robots IAB.

## Mise à jour ou chargement de règles de robots

>[!IMPORTANT]
>
>Avant de supprimer le trafic de robots, contactez les parties intéressées afin de vous assurer qu’elles sont en mesure d’apporter les modifications nécessaires aux indicateurs clés de performance à la suite de ce changement. Si possible, nous vous conseillons d’abord de supprimer le trafic de robots d’une petite suite de rapports afin d’évaluer l’impact potentiel.


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configurer des règles de robots](https://video.tv.adobe.com/v/335738/?quality=12){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


Pour mettre à jour ou charger des règles de robots :

1. Accédez à **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]**.

1. Sélectionnez la suite de rapports dans laquelle vous souhaitez mettre à jour les règles de robots, puis sélectionnez **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Général]** > **[!UICONTROL Règles de robots]**.

1. Utilisez l’une des options suivantes pour mettre à jour ou charger des règles de robots pour la suite de rapports :

   * Sélectionnez [!UICONTROL **Activer les règles de filtrage des robots IAB**] pour supprimer les robots dans la liste internationale d’araignées et de robots IAB (Bureau international Advertising) afin de supprimer le trafic de robots.

     Nous vous recommandons de sélectionner cette option au minimum.

     Pour plus d’informations, consultez la section ci-dessous, [Règles de robots IAB standard](#standard-iab-bot-rules).

   * Sélectionnez [!UICONTROL **Ajouter une règle**] pour définir et ajouter des règles de robots personnalisées en fonction des agents utilisateurs, des adresses IP ou des plages d’adresses IP.

     Pour plus d’informations, consultez la section ci-dessous, [Règles de robots personnalisées](#custom-bot-rules).

   * En regard de la zone [!UICONTROL **Sélectionner le fichier de robot CSV à importer**], sélectionnez [!UICONTROL **Choisir un fichier**], puis sélectionnez le fichier CSV qui définit les règles de robot.

     Pour plus d’informations, consultez la section ci-dessous, [Chargement de règles de robots](#upload-bot-rules).

1. Sélectionnez [!UICONTROL **Enregistrer**].

## Règles de robots IAB standard

Activez les règles de robots IAB standard en cochant la case [!UICONTROL Activer les règles de filtrage de robots IAB]. Cette sélection va supprimer les robots de la liste internationale des robots (International Spiders &amp; Robots List) fournie par l’IAB (Bureau international de la publicité) pour supprimer le trafic de robots. Adobe met à jour cette liste de lʼIAB tous les mois.

![](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/assets/bot-iab-checkbox.png)

Adobe n’est pas en mesure de fournir la liste des robots IAB détaillée aux clients.Vous pouvez cependant utiliser le rapport Robots pour consulter la liste des robots qui ont accédé à votre site. Pour soumettre un robot à la liste de l’IAB, consultez l’[IAB](https://www.iab.com).

Pour plus d’informations sur l’activation des règles de robots IAB standard dans une suite de rapports, voir [Mise à jour ou chargement de règles de robots](#update-or-upload-bot-rules).

## Règles de robots personnalisées

>[!NOTE]
>
>Il est possible de définir manuellement 500 règles dans l’interface utilisateur. Au-delà de cette limite, les règles doivent être gérées en bloc au moyen des options Importer un fichier et Exporter des règles de robots.

Les règles de robots personnalisées vous permettent de filtrer les conditions basées sur le trafic que vous définissez. Pour lancer le processus d’activation des règles de robots personnalisées dans une suite de rapports, consultez [Mise à jour ou chargement de règles de robots](#update-or-upload-bot-rules).

Les règles de robots personnalisées sont définies à l’aide des types de conditions suivants :

* Agent utilisateur
* Adresse IP
* Plage IP

Plusieurs conditions peuvent être définies pour une seule règle. Dans le cas de conditions multiples, une correspondance est établie à l’aide de l’opérateur « OU ». Si vous indiquez, par exemple, une valeur pour Agent utilisateur et Adresse IP, le trafic est considéré comme du trafic de robots si l’une des conditions est remplie.

### Agent utilisateur

Une condition Agent utilisateur vérifie la valeur correspondante afin de déterminer si elle **[!UICONTROL contient]** ou **[!UICONTROL commence par]** la chaîne spécifiée. En cas de sélection de l’option **[!UICONTROL contient]**, une correspondance est établie avec la sous-chaîne si elle est présente dans l’agent utilisateur.

Des valeurs facultatives peuvent être incluses dans la liste **[!UICONTROL ne contient pas]** afin de définir les valeurs qui ne peuvent pas se trouver dans l’agent utilisateur pour qu’une correspondance soit établie. Vous pouvez inclure plusieurs valeurs, à raison d’une valeur par ligne. Si l’agent utilisateur répond aux critères spécifiés dans la chaîne de correspondance, mais contient également une chaîne reprise dans la liste « ne contient pas », il n’est pas considéré comme une correspondance.

Le champ **[!UICONTROL contient]** est limité à 100 caractères. La liste « ne contient pas » est limitée à 255 caractères, moins un caractère séparateur pour chaque nouvelle ligne. (Cela équivaut au nombre de chaînes - 1. Si vous spécifiez 4 *ne contient pas* chaînes, 3 caractères de séparation sont requis.) Toutes les correspondances de chaîne ne respectent pas la casse.

### Adresse IP (avec correspondances de caractères génériques)

Établit une correspondance avec une ou plusieurs adresses IP dans le même bloc à l’aide de caractères génériques (&#42;). Indiquez les valeurs numériques de l’adresse IP avec laquelle vous souhaitez établir une correspondance. Remplacez par &#42; toutes les valeurs que vous souhaitez faire correspondre à l’aide d’un caractère générique. La liste suivante contient des exemples de chaînes de correspondance d’adresses IP :

```
10.10.10.1
10.10.10.*
```

### Plage d’adresses IP

Indiquez les plages de début et de fin des adresses IP avec lesquelles vous souhaitez établir une correspondance. Remplacez par &#42; toutes les valeurs que vous souhaitez faire correspondre à l’aide d’un caractère générique.

### Définir une règle de robot personnalisée

1. Accédez à **[!UICONTROL Analytics]** > **[!UICONTROL Admin]**, sélectionnez une ou plusieurs suites de rapports, puis cliquez sur **[!UICONTROL Général]** > **[!UICONTROL Règles de robots]**.
1. Cliquez sur **[!UICONTROL Ajouter une règle]** et définissez ensuite une ou plusieurs conditions de correspondance.
1. Cliquez sur **[!UICONTROL Enregistrer]**. La modification doit normalement être prise en compte dans les 30 minutes.

## Télécharger des règles de robots

Pour importer des règles de robots en vrac, vous pouvez télécharger un fichier CSV qui les définit.

1. Pour lancer le processus de chargement de règles de robots dans une suite de rapports, consultez [Mise à jour ou chargement de règles de robots](#update-or-upload-bot-rules).

1. Créez un fichier CSV avec les colonnes suivantes, sur la ligne 1 de la feuille de calcul et dans l’ordre présenté :

   | Colonne 1, ligne 1 | Colonne 2, ligne 1 | Colonne 3, ligne 1 | Colonne 4, ligne 1 | Colonne 5, ligne 1 | Colonne 6, ligne 1 |
   |--- |--- |---|---|---|---|
   | Nom du robot | Début de l’adresse IP | Fin IP | Règle<br>(contient ou commence par)</br> | User Agent Include | Exclusion de l’agent utilisateur <br>(limite de 255 caractères)</br> |

   Vous pouvez définir trois types de règles de robots :

   * L’agent utilisateur contient ou commence par
   * Correspondance d’une seule adresse IP ou d’un seul caractère générique
   * Correspondance d’une plage d’adresses IP

   Chaque ligne du fichier d’importation ne peut contenir que l’une des définitions de robot suivantes :

   >[!NOTE]
   >
   >   Pour établir une correspondance avec un robot à l’aide d’une combinaison de règles associées par un opérateur « OU » (par exemple, agent utilisateur OU adresse IP), indiquez un nom identique pour toutes les règles à combiner dans le champ du nom de robot. Les correspondances « AND » ne sont pas prises en charge.


   * **L’agent utilisateur contient ou commence par** : indiquez une seule chaîne d’agent utilisateur avec laquelle établir une correspondance dans la colonne Agent - Inclure. Indiquez le type de correspondance à effectuer en indiquant *contient* ou *commence par* dans le champ Règle de correspondance de l’agent. Vous pouvez inclure une valeur facultative dans la colonne Agent - Exclure pour définir une ou plusieurs chaînes délimitées par une barre verticale (`|`) que l’agent ne contient pas. Les correspondances de chaînes ne sont pas sensibles à la casse. Les colonnes Début IP et Fin IP doivent, toutes deux, être vides.

   * **Correspondance d’une seule adresse IP ou d’un seul caractère générique** : pour établir une correspondance avec une seule adresse IP (`10.10.10.1`) ou une adresse IP avec un caractère générique (`10.10.*.*`), indiquez la même valeur dans les colonnes Début IP et Fin IP. Règle de correspondance de l’agent, Agent - Inclure et Agent - Exclure doivent être vides.

   * **Correspondance de plage IP** : définissez une plage d’adresses IP à l’aide des colonnes Début IP et Fin IP. Vous pouvez utiliser des caractères génériques pour faire correspondre des plages d’adresses IP ; par exemple `10.10.10.*` avec `10.10.20.*`. Règle de correspondance de l’agent, Agent - Inclure et Agent - Exclure doivent être vides.

1. Sur la page Règles de robots du Gestionnaire de suites de rapports, en regard de la zone [!UICONTROL **Sélectionner le fichier de robot CSV à importer**], sélectionnez [!UICONTROL **Choisir un fichier**], puis sélectionnez le fichier CSV qui définit les règles de robots à importer.

1. (Facultatif) Cochez la case **[!UICONTROL Remplacer les règles existantes]** pour supprimer toutes les règles existantes et les remplacer par les règles définies dans le fichier de chargement.

1. Sélectionnez [!UICONTROL **Importer un fichier**].

1. Dans la zone [!UICONTROL **Jeux de règles**] passez en revue les règles importées.

1. Sélectionnez [!UICONTROL **Enregistrer**].

## Exporter les règles de robots

Pour exporter toutes les règles définies dans l’interface utilisateur au format CSV :

1. Accédez à **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]**.

1. Sélectionnez la suite de rapports contenant les règles de robots à exporter, puis sélectionnez **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Général]** > **[!UICONTROL Règles de robots]**.

1. Sélectionnez **[!UICONTROL Exporter des règles de robots]**, puis enregistrez le fichier CSV dans votre système de fichiers.

## Incidence des règles de robots sur la collecte de données {#section_F01A3130E7A04A9993371CF26F6586F2}

Les règles de robots s’appliquent à toutes les données d’analyse. Les données supprimées par les règles de robots ne sont visibles que dans les rapports Robots et Pages de robots.

Les règles VISTA sont appliquées après les règles de robots. Consultez [Ordre de traitement](/help/technotes/processing-order.md) dans le guide d’utilisation des notes techniques.

**Traitement de visites enregistrant de nombreux accès** : si plus de 100 accès se produisent au cours d’une visite, la fonction de création de rapports détermine si la durée de la visite (en secondes) est inférieure ou égale au nombre d’accès. Dans ce cas, compte tenu des coûts de traitement des visites longues et intensives, la création de rapports recommence avec une nouvelle visite. Les visites qui enregistrent de nombreux accès sont généralement causées par des attaques de robots et ne sont pas considérées comme ses sessions de navigation normales effectuées par des visiteurs.

>[!NOTE]
>
>Les accès marqués comme *`bots`* sont facturés comme des [appels au serveur.](/help/admin/tools/server-call-usage/overage-overview.md)

## Impact de l’obscurcissement des adresses IP sur le filtrage des robots {#section_92E60B95BE8940D983F28C79E0CD6B12}

La liste des robots IAB est basée uniquement sur l’agent-utilisateur. De ce fait, le filtrage basé sur cette liste n’est pas affecté par les paramètres d’obscurcissement d’IP. Pour le filtrage des robots non IAB (règles personnalisées), l’IP peut faire partie des critères de filtrage. Si vous filtrez des robots à l’aide de l’IP, le filtrage se produit une fois que le dernier octet a été supprimé, si ce paramètre est activé, mais avant les autres options d’obscurcissement d’IP, par exemple la suppression de l’ensemble de l’IP ou son remplacement par un ID unique.

Si l’obscurcissement d’IP est activé, l’exclusion de l’adresse IP survient avant l’obscurcissement ; ainsi, les clients n’ont rien à changer lorsqu’ils activent cette option.

Si le dernier octet est supprimé, ceci a lieu avant le filtrage IP. Par conséquent, le dernier octet est remplacé par un 0 et les règles d’exclusion IP doivent être mises à jour afin de correspondre aux adresses IP avec un zéro à la fin. Le &#42; correspondant doit correspondre à 0.
