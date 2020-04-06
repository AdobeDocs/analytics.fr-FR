---
title: Sérialisation d’événements
description: Permet la déduplication des mesures sur votre site.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Sérialisation de l’identifiant d’événement

La sérialisation des événements est le processus consistant à implémenter des mesures pour empêcher les événements en double d’entrer dans la création de rapports d’Analytics. La déduplication des événements est importante lorsque vous ne souhaitez pas que les mesures soient exagérées par les visiteurs qui actualisent la page.

>[!NOTE] Les sources de données ne prennent pas en charge la sérialisation ou la déduplication des événements.

## Configuration de la sérialisation des événements

Vous devez d’abord définir un  de [!UICONTROL Unique Event Recording] sur [!UICONTROL Use Event ID] dans les paramètres de la suite de rapports. Voir [Événements de réussite](/help/admin/admin/c-success-events/success-event.md) dans le guide d’utilisation Administrateur.

Lors de l’utilisation des identifiants d’événement, la déduplication se produit aux niveaux suivants :

* Chaque variable utilise sa propre table pour la déduplication. Par exemple, `event1:ABC` et `event2:ABC` sont tous deux comptabilisés dans les rapports.
* La déduplication se produit globalement pour tous les visiteurs. Si le visiteur A envoie `event1:ABC` puis le visiteur B envoie également `event1:ABC`, Adobe ignore la deuxième instance du visiteur B.
* La déduplication n’expire pas. Si un visiteur envoie `event1:ABC` puis revient 2 ans plus tard et renvoie `event1:ABC`, Adobe ignore la seconde instance.

>[!TIP] Si vous souhaitez dédupliquer l’événement [`purchase`](event-purchase.md), utilisez plutôt la variable [`purchaseID`](../purchaseid.md).

## Utilisation d’identifiants d’événement dans Adobe Experience Platform Launch

Vous pouvez définir le champ Identifiant d’événement lors de la configuration de l’extension Analytics (variables globales) ou en tant qu’action dans une règle.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Sous [!UICONTROL Actions], cliquez sur une [!UICONTROL Adobe Analytics - Set Variables] action existante ou cliquez sur l’icône &quot;+&quot;.
5. Définissez la [!UICONTROL Extension] liste déroulante sur Adobe Analytics et la [!UICONTROL Action Type] sur [!UICONTROL Set Variables].
6. Localisez la [!UICONTROL Events] section, où chaque  contient un [!UICONTROL Event ID] champ.

Les valeurs valides sont des caractères alphanumériques d’une longueur maximale de 20 octets.

## Utilisation d’identifiants d’événement dans AppMeasurement et l’éditeur de code personnalisé de Launch

La sérialisation des événements fait partie de la variable `s.events`. Attribuez un identifiant à chaque événement à l’aide d’un deux-points dans la chaîne.

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

Si la sérialisation d’un événement est activée mais ne contient pas d’identifiant de sérialisation, l’événement est toujours comptabilisé.
