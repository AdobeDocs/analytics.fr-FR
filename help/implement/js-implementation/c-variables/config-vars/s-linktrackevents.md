---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.linkTrackEvents

The  variable is a comma-separated list of events that are sent with a [!UICONTROL custom], [!UICONTROL exit], or [!UICONTROL download] link.

If an event is not in *`linkTrackEvents`*, it is not sent to [!DNL Analytics], even if it is populated in the [!UICONTROL onClick] event of a link, as shown in the following example:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

Dans le premier lien pointant vers [!DNL help.php], vous pouvez constater que la variable « events » conserve la valeur qui était définie avant que l’utilisateur ne clique. Cela permet à event1 d’être envoyé avec le lien personnalisé. Dans le deuxième exemple, le lien pointant vers [!DNL test.php], event2 n’est pas enregistré, car il ne figure pas dans *`linkTrackEvents`*.

Pour éviter toute confusion et tout problème potentiel, Adobe recommande de renseigner *`linkTrackVars`* et *`linkTrackEvents`* dans l’événement [!UICONTROL onClick] d’un lien utilisé pour le suivi des liens.

The *`linkTrackEvents`* variable contains the events that should be sent with [!UICONTROL custom], [!UICONTROL download], and [!UICONTROL exit] links. Cette variable n’est prise en compte que si *`linkTrackVars`* contient "events".

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | Conversion | "Aucun" |

## Syntaxe et valeurs possibles

La syntaxe de la variable *`linkTrackEvents`* est une liste d’événements séparés par des virgules (aucun espace).

```js
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

Seuls les noms d’événement sont autorisés dans *`linkTrackEvents`*. These events are listed in [Events](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html). Si le nom de l’événement est précédé ou suivi d’un espace, il ne peut pas être envoyé avec des demandes d’images de lien.

## Exemples

```js
s.linkTrackEvents="purchase,event1"
```

```js
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

## Paramètres de configuration

Aucun

## Pièges, questions et conseils

* Le fichier JavaScript utilise uniquement *`linkTrackEvents`* si *`linkTrackVars`* contient la variable "events". "events" ne doit être inclus dans *`linkTrackVars`* que lorsque *`linkTrackEvents`* est défini.

* Beware if an event is fired on a page, and is listed in *`linkTrackEvents`*. That event is recorded again with any [!UICONTROL exit], [!UICONTROL download], or [!UICONTROL custom] links unless the events variable is reset prior to that event (in the [!UICONTROL onClick] of a link or after the call to the *`t()`* function).

* If *`linkTrackEvents`* contains spaces between event names, the events are not recorded.
