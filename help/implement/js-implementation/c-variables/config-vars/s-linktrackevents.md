---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.linkTrackEvents

La variable  est une liste d’événements séparés par des virgules, qui sont envoyés avec un lien [!UICONTROL personnalisé], de [!UICONTROL sortie] ou de [!UICONTROL téléchargement].

Si un événement ne figure pas dans la variable *`linkTrackEvents`*, il n’est pas envoyé à [!DNL Analytics], même s’il est renseigné dans l’événement [!UICONTROL onClick] d’un lien, comme illustré dans l’exemple suivant :

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

Dans le premier lien pointant vers [!DNL help.php], vous pouvez constater que la variable « events » conserve la valeur qui était définie avant que l’utilisateur ne clique. Cela permet à event1 d’être envoyé avec le lien personnalisé. Dans le deuxième exemple, le lien pointant vers [!DNL test.php], event2 n’est pas enregistré, car il ne figure pas dans *`linkTrackEvents`*.

Pour éviter toute confusion et tout problème potentiel, Adobe recommande de renseigner *`linkTrackVars`* et *`linkTrackEvents`* dans l’événement [!UICONTROL onClick] d’un lien utilisé pour le suivi des liens.

La variable *`linkTrackEvents`* contient les événements qui doivent être envoyés avec des liens [!UICONTROL personnalisés], de [!UICONTROL téléchargement] et de [!UICONTROL sortie]. Cette variable n’est prise en compte que si *`linkTrackVars`* contient « events ».

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| N/D | N/D | Conversion | "Aucun" |

## Syntaxe et valeurs possibles

La variable *`linkTrackEvents`* est une liste d’événements séparés par des virgules (aucun espace).

```js
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

Seuls les noms d’événement sont autorisés dans *`linkTrackEvents`*. Ces événements sont répertoriés à la section [Événements](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html). Si le nom de l’événement est précédé ou suivi d’un espace, il ne peut pas être envoyé avec des demandes d’images de lien.

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

* Le fichier JavaScript utilise uniquement *`linkTrackEvents`* si *`linkTrackVars`* contient la variable « events ». La variable « events » ne doit être incluse dans *`linkTrackVars`* uniquement lorsque la variable *`linkTrackEvents`* est définie.

* Soyez vigilant si un événement est déclenché sur une page et répertorié dans *`linkTrackEvents`*. Cet événement est à nouveau enregistré avec tout lien de [!UICONTROL sortie], de [!UICONTROL téléchargement] ou [!UICONTROL personnalisé], sauf si la variable « events » est réinitialisée avant qu’il ne se produise (dans l’événement [!UICONTROL onClick] d’un lien ou après l’appel à la fonction *`t()`*).

* Si la variable *`linkTrackEvents`* contient des espaces entre les noms d’événements, les événements ne sont pas enregistrés.
