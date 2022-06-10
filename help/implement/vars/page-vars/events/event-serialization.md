---
title: Sérialisation d’événements
description: Permet la déduplication des mesures sur votre site.
feature: Variables
exl-id: 54de0fd7-9056-44af-bd59-b8eb55fc816e
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 74%

---

# Sérialisation de l’identifiant d’événement

La sérialisation des événements est le processus consistant à implémenter des mesures pour empêcher les événements en double d’entrer dans la création de rapports d’Analytics. La déduplication des événements est importante lorsque vous ne souhaitez pas que les mesures soient exagérées par les visiteurs qui actualisent la page.

>[!NOTE]
>
>Les sources de données ne prennent pas en charge la sérialisation ou la déduplication des événements.

## Configuration de la sérialisation des événements

Vous devez d’abord définir l’[!UICONTROL enregistrement d’événements uniques] d’un événement pour [!UICONTROL utiliser l’identifiant d’événement] dans les paramètres de la suite de rapports. Voir [Événements de réussite](/help/admin/admin/c-success-events/success-event.md) dans le guide d’utilisation destiné à l’administrateur.

Lors de l’utilisation des identifiants d’événement, la déduplication se produit aux niveaux suivants :

* Chaque variable utilise sa propre table pour la déduplication. Par exemple, `event1:ABC` et `event2:ABC` sont tous deux comptabilisés dans les rapports.
* La déduplication se produit globalement pour tous les visiteurs. Si le visiteur A envoie `event1:ABC` puis le visiteur B envoie également `event1:ABC`, Adobe ignore la deuxième instance du visiteur B.
* La déduplication n’expire pas. Si un visiteur envoie `event1:ABC` puis revient 2 ans plus tard et renvoie `event1:ABC`, Adobe ignore la seconde instance.

>[!TIP]
>
>Si vous souhaitez dédupliquer l’événement [`purchase`](event-purchase.md), utilisez plutôt la variable [`purchaseID`](../purchaseid.md).

## Utilisation des ID d’événement à l’aide du SDK Web

La sérialisation des événements est [mappé pour Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) sous le champ XDM d’événement souhaité `id`. Le chemin XDM complet dépend de l’événement que vous souhaitez sérialiser.

Par exemple, si vous souhaitez sérialiser la mesure Ajouts au panier, définissez la variable `commerce.productListAdds.id` Champ XDM vers la valeur de sérialisation souhaitée. Si vous souhaitez sérialiser l’événement personnalisé 20, définissez la variable `_experience.analytics.event1to100.event20` Champ XDM vers la valeur de sérialisation souhaitée.

## Utilisation des ID d’événement à l’aide de l’extension Adobe Analytics

Vous pouvez définir le champ Identifiant d’événement lors de la configuration de l’extension Analytics (variables globales) ou en tant qu’action dans une règle.

1. Connectez-vous à [Collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le [!UICONTROL type d’action] sur [!UICONTROL Définir des variables].
6. Recherchez la section [!UICONTROL Événements], où chaque événement contient un champ [!UICONTROL Identifiant d’événement].

Les valeurs valides sont des caractères alphanumériques d’une longueur maximale de 20 octets. Si vous saisissez une valeur de plus de 20 octets, le système la tronque sur les 20 premiers octets.

## Utilisation des ID d’événement dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La sérialisation des événements fait partie de la variable `s.events`. Attribuez un identifiant à chaque événement à l’aide d’un deux-points dans la chaîne.

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

Si la sérialisation d’un événement est activée mais ne contient pas d’identifiant de sérialisation, l’événement est toujours comptabilisé.
