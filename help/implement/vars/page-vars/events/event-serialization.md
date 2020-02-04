---
title: Sérialisation d’événements
description: Aide à la déduplication des mesures sur votre site.
translation-type: tm+mt
source-git-commit: c5a60bc9756af2742740dbc6a26a081f55ee3235

---


# Sérialisation de l’ID d’événement

La sérialisation des événements est le processus consistant à implémenter des mesures pour empêcher les événements en double d’entrer dans la création de rapports d’Analytics. La déduplication des événements est importante lorsque vous ne souhaitez pas que les mesures soient exagérées par les visiteurs qui actualisent la page.

> [!NOTE] Les sources de données ne prennent pas en charge la sérialisation ou la déduplication des événements.

## Configuration de la sérialisation d’événements

Vous devez d’abord définir l’enregistrement [!UICONTROL d’événements] uniques d’un événement pour [!UICONTROL utiliser l’ID] d’événement dans les paramètres de la suite de rapports. See [Success Events](../../../../admin/admin/c-success-events/success-event.md) in the Admin user guide.

Lors de l’utilisation des ID d’événement, la déduplication se produit aux niveaux suivants :

* Chaque variable utilise sa propre table pour la déduplication. Par exemple, `event1:ABC` et `event2:ABC` sont tous deux comptabilisés dans les rapports.
* La déduplication se produit globalement pour tous les visiteurs. Si le visiteur A envoie `event1:ABC` puis le visiteur B `event1:ABC`envoie également, Adobe ignore la deuxième instance du visiteur B.
* La déduplication n’expire pas. Si un visiteur envoie `event1:ABC` puis revient 2 ans plus tard et `event1:ABC` revient, Adobe ignore la seconde instance.

> [!TIP] Si vous souhaitez dédupliquer l’ `purchase` événement, utilisez plutôt la `purchaseID` variable.

## Utiliser des ID d’événement dans Adobe Experience Platform Launch

Vous pouvez définir le champ ID d’événement lors de la configuration de l’extension Analytics (variables globales) ou en tant qu’action dans une règle.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur une propriété.
3. Accédez à l’onglet [!UICONTROL Règles] , puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône &quot;+&quot;.
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le type [!UICONTROL d’] action sur [!UICONTROL Définir des variables].
6. Recherchez la section [!UICONTROL Evénements] , où chaque événement contient un champ ID [!UICONTROL d’] événement.

Les valeurs valides sont des caractères alphanumériques d’une longueur maximale de 20 octets.

## Utiliser des ID d’événement dans AppMeasurement et lancer l’éditeur de code personnalisé

La sérialisation d’événements fait partie de la `s.events` variable. Attribuez un identifiant à chaque événement à l’aide d’un deux-points dans la chaîne.

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

Si la sérialisation d’un événement est activée mais ne contient pas d’identifiant de sérialisation, l’événement est toujours comptabilisé.
