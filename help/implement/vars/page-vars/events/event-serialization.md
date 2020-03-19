---
title: Sérialisation d’événements
description: Aide à la déduplication des mesures sur votre site.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Sérialisation des identifiants 

La sérialisation des événements est le processus consistant à implémenter des mesures pour empêcher les événements en double d’entrer dans la création de rapports d’Analytics. La déduplication des  de est importante lorsque vous ne souhaitez pas que les mesures soient exagérées par les qui actualisent la page.

> [!NOTE] Les sources de données ne prennent pas en charge la sérialisation ou la déduplication des événements.

## Configuration de la sérialisation 

Vous devez d’abord définir un  de [!UICONTROL Unique Event Recording] sur [!UICONTROL Use Event ID] dans les paramètres de la suite de rapports. See [Success Events](/help/admin/admin/c-success-events/success-event.md) in the Admin user guide.

Lors de l’utilisation d’ID de , la déduplication se produit aux niveaux suivants :

* Chaque variable utilise sa propre table pour la déduplication. Par exemple, `event1:ABC` et `event2:ABC` sont tous deux comptabilisés dans les .
* La déduplication se produit globalement dans tous les. Si l’A envoie `event1:ABC` puis l’B `event1:ABC`envoie également, Adobe ignore la deuxième instance de l’B.
* La déduplication n’expire pas. Si un envoie `event1:ABC` puis revient 2 ans plus tard et `event1:ABC` revient à nouveau, Adobe ignore la seconde instance.

> [!TIP] Si vous souhaitez annuler l’ de l’ [`purchase`](event-purchase.md) , utilisez plutôt la [`purchaseID`](../purchaseid.md) variable.

## Utiliser des ID de  dans Adobe Experience Platform Launch

Vous pouvez définir le champ ID de  du lors de la configuration de l’extension Analytics (variables globales) ou en tant qu’action dans une règle.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’ [!UICONTROL Rules] onglet, puis cliquez sur la règle souhaitée (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une [!UICONTROL Adobe Analytics - Set Variables] action existante ou cliquez sur l’icône &quot;+&quot;.
5. Définissez la [!UICONTROL Extension] liste déroulante sur Adobe Analytics et la [!UICONTROL Action Type] sur [!UICONTROL Set Variables].
6. Localisez la [!UICONTROL Events] section, où chaque  contient un [!UICONTROL Event ID] champ.

Les valeurs valides sont des caractères alphanumériques d’une longueur maximale de 20 octets.

## Utilisation des ID  de dans AppMeasurement et lancement de l’éditeur de code personnalisé

La sérialisation  fait partie de la `s.events` variable. Attribuez un identifiant à chaque  à l’aide d’un deux-points dans la chaîne.

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

Si la sérialisation d’un  est activée mais ne contient pas d’ID de sérialisation, le  de est toujours comptabilisé.
