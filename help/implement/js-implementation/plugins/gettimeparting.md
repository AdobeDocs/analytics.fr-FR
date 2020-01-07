---
description: Le module externe getTimeParting renseigne les variables personnalisées avec les valeurs « heure du jour », « jour de la semaine », « jour du week-end » et « jour de semaine ». Analysis Workspace propose des dimensions de répartition des heures prêtes à l’emploi. Le module externe devrait être utilisé si des dimensions de répartition des heures sont requises dans d’autres solutions Analytics, hors d’Analysis Workspace.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getTimeParting
topic: Developer and implementation
uuid: 74f696a3-7169-4560-89b2-478b3d8385e1
translation-type: tm+mt
source-git-commit: 73d20b23e38bc619c156c418c95096a94d2fdfce

---


# getTimeParting

Le plug-in getTimeParting fournit une solution d’analyse complète qui vous permet de capturer les détails du moment où une activité mesurable se produit sur votre site.

Utilisez le plug-in getTimeParting si vous souhaitez ventiler vos mesures en fonction d’une division répétable du temps sur une période donnée.  Par exemple, le plug-in getTimeParting vous permet de comparer les taux de conversion entre deux jours différents de la semaine (par exemple, tous les dimanches et tous les jeudis), deux périodes différentes de la journée (par exemple, tous les matins et toutes les soirées) ou même deux minutes suivantes (par exemple, toutes les instances 10:00 du matin et toutes les instances 10:01 du matin) pour la plage de dates. vous spécifiez dans le rapport.

[!DNL Analysis Workspace] fournit des dimensions similaires prêtes à l’emploi, formatées légèrement différemment de ce que ce module externe fournit (voir [ici](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.html)).  Le service de conseil d’Adobe vous conseille de parcourir le reste de cette section d’aide pour déterminer si ce module externe fournit des données d’une manière plus adaptée à vos besoins.

Si vous n’avez pas besoin de ventiler vos mesures selon une division répétable du temps sur une période spécifique, vous n’aurez pas besoin d’utiliser le plug-in getTimeParting.  En outre, si vous trouvez que les dimensions de division du [!DNL Analysis Workspace] temps sont suffisantes, vous n’aurez pas besoin de mettre en oeuvre ce module externe.

>[!CAUTION] La solution fournie par la version 4.0+ du plug-in getTimeParting est bien différente de celle fournie par les versions antérieures du plug-in.  Si vous choisissez de mettre à niveau une version antérieure à la version 4.0, vous devez mettre en oeuvre la solution &quot;à partir de zéro&quot;.  En d’autres termes, vous devez configurer une eVar entièrement nouvelle - une eVar - pour conserver les données fournies par le module externe et lire attentivement cette documentation avant de mettre en oeuvre la solution.

>[!CAUTION] Aussi : Cette version du module externe n&#39;est pas *entièrement* compatible avec les navigateurs Microsoft Internet Explorer, bien que le module externe soit entièrement compatible avec les navigateurs Microsoft Edge.   Les visiteurs qui utilisent Internet Explorer pourront indiquer l’heure mais uniquement dans leur fuseau horaire *local* au lieu d’être convertis en fuseau horaire que vous spécifiez.  Reportez-vous aux exemples ci-dessous pour obtenir une solution qui n’inclura pas les données des navigateurs Internet Explorer, mais qui tiendra tout de même compte de leur présence.

> [!NOTE] Les instructions suivantes vous demandent de modifier le code de collecte de données sur votre site. Cela peut avoir une incidence sur la collecte des données sur votre site. Aussi, cette opération ne doit-elle être réalisée que par un développeur maîtrisant l’utilisation et l’implémentation d’[!DNL Analytics].

> [!WARNING] Testez toujours toutes les mises en oeuvre des modules externes avant de les déployer en production pour vous assurer que la collecte des données fonctionne comme prévu.

## Conditions préalables

Aucun

## Implémentation

* Copiez + Collez le code suivant n’importe où dans la section Plugins du code AppMeasurement :

```function getTimeParting(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])}```

> [!NOTE] Vous pouvez également utiliser un gestionnaire de balises tel qu’Adobe Launch pour déployer le code du module externe sans avoir à le joindre à AppMeasurement ou à toute autre solution d’analyse

* Exécutez la fonction getTimeParting comme décrit ci-dessous dans la fonction doPlugins ou à tout autre emplacement où vous devez capturer les données de répartition du temps.

**Arguments à transmettre**

* t : (**FACULTATIF mais recommandé**, chaîne) Nom du fuseau horaire dans lequel convertir l’heure locale du visiteur.  La valeur par défaut est &quot;Etc/GMT&quot; ou &quot;UTC/GMT time&quot; lorsqu’elle n’est pas définie.  Consultez [https://en.wikipedia.org/wiki/List_of_tz_database_time_zones] pour obtenir la liste complète des valeurs à saisir.

Les valeurs courantes sont les suivantes :

* &quot;Amérique/New_York&quot; pour l&#39;heure de l&#39;Est
* &quot;Amérique/Chicago&quot; pour l&#39;heure centrale
* &quot;Amérique/Denver&quot; pour l&#39;heure de la montagne
* &quot;Amérique/Los_Angeles&quot; pour le Pacifique

## Retours

Le plug-in getTimeParting renvoie une chaîne contenant les éléments suivants :

* L&#39;année en cours
* Le mois en cours
* Date actuelle (c.-à-d. jour du mois)
* Jour actuel (c.-à-d. jour de la semaine)
* L&#39;heure actuelle (heure non militaire)

Chacun des éléments ci-dessus est délimité par une barre verticale (&quot;|&quot;).

## Exemples d’appels

Utilisez le code suivant si vous vous trouvez à Paris en France et souhaitez utiliser eVar10 (dans Adobe Analytics) pour capturer les données de répartition du temps :

```s.eVar10 = getTimeParting("Europe/Paris")```

Utilisez le code suivant si vous vous trouvez à San Jose, en Californie :

```s.eVar10 = getTimeParting("America/Los_Angeles")```

Utilisez le code suivant si vous vous trouvez dans le pays africain du Ghana :

```s.eVar10 = getTimeParting();```

Le Ghana se trouve dans le fuseau horaire UTC/GMT.  Ainsi, cet exemple montre qu’aucun argument de module externe ne sera nécessaire dans de telles circonstances.

Utilisez le code suivant si vous vous trouvez à New York et ne souhaitez pas inclure de données provenant des visiteurs d’Internet Explorer (puisque les valeurs renvoyées par les navigateurs IE peuvent être fournies uniquement à l’heure locale du visiteur).

```if(!document.documentMode) s.eVar10 = getTimeParting("America/New_York");```
```else s.eVar10 = "Internet Explorer Visitors";```

**Résultats des appels**

Si un visiteur de Denver, au Colorado, visite un site le 31 août 2020 à 9h15, le code suivant...

```s.eVar10 = getTimeParting("Europe/Athens");```

...définirait s.eVar10 sur **year=2020| month=August| date=31| day=Monday| time=6:15 PM**

Le code suivant...

```s.eVar10 = getTimeParting("America/Nome");```

... définirait plutôt s.eVar10 sur **year=2020| month=August| date=31| day=Monday| time=6:15 AM**

Le code suivant...

```s.eVar10 = getTimeParting("Asia/Calcutta");```

... définirait plutôt s.eVar10 sur **year=2020| month=August| date=31| day=Monday| time=20h45**

Le code suivant...

```s.eVar10 = getTimeParting("Australia/Sydney");```

... définirait plutôt s.eVar10 sur **year=2020| month=Septembre| date=1| day=mardi| time=1:15 AM**

## Configuration d’Adobe Analytics

Si vous souhaitez capturer les données de division du temps dans Adobe Analytics, configurez une nouvelle eVar avec les caractéristiques suivantes :

* Nom : Division du temps
* Affectation : Le plus récent (Dernier)
* Expire après : Visite
* Tous les autres attributs utilisent les valeurs par défaut fournies
