---
title: Variables dynamiques
description: Copiez des variables sans augmenter la longueur de la demande d’image.
feature: Variables
exl-id: 41aab44d-01fd-45fe-892d-637d69488d98
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 78%

---

# Variables dynamiques

Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans augmenter la longueur de la demande d’image. Elles s’avèrent utiles lors de la capture des mêmes données dans plusieurs variables.

Dans les versions précédentes d’Analytics, la longueur des demandes d’image était importante pour empêcher la troncature des données. Les améliorations apportées à AppMeasurement permettent des chaînes de requête de demande d’image beaucoup plus longues, de sorte que les variables dynamiques ne sont généralement pas nécessaires.

Les variables dynamiques prennent en charge les paramètres de chaîne de requête ou les en-têtes HTTP dans une demande d’image. Voir [Paramètres de requête de collecte de données](../../validate/query-parameters.md) pour obtenir la liste complète des paramètres disponibles à référencer. Voir [Champs de requête standard](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields#Request_fields) sur Wikipédia pour obtenir la liste complète des champs de requête HTTP à référencer.

Lorsqu’Adobe reconnaît un préfixe de variable dynamique, il copie automatiquement la chaîne de requête ou la valeur d’en-tête HTTP dans votre suite de rapports. Cette action se produit avant tout autre traitement, y compris les règles de traitement et les règles VISTA.

>[!TIP]
>
>Gardez à l’esprit les limites maximales de caractères lors de la copie de variables. Par exemple, en cas de copie de `eVar1` vers `prop1`, `prop1` peut avoir une valeur tronquée puisqu’elle est limitée à 100 octets (alors que `eVar1` est limitée à 255 octets).

## Variables dynamiques à l’aide du SDK Web

Utilisez le mappage de flux de données pour envoyer des données à plusieurs variables Analytics à partir d’un seul champ XDM.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur **[!UICONTROL Datastreams]** dans le rail de gauche.
1. Cliquez sur le flux de données souhaité.
1. Cliquez sur **[!UICONTROL Modifier le mappage]** à droite.
1. Faites correspondre les [!UICONTROL Champ source] à la [!UICONTROL Champ cible]. Un champ source unique peut correspondre à n’importe quel nombre de champs cibles.

## Variables dynamiques utilisant l’extension Adobe Analytics

Vous pouvez utiliser des variables dynamiques dans n’importe quel champ de dimension qui accepte une chaîne. Les éléments de dimension sont généralement définis lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la variable [!UICONTROL Extension] de la liste déroulante vers Adobe Analytics, et de la variable [!UICONTROL Type d’action] to [!UICONTROL Définition de variables].
6. Recherchez l’élément de dimension souhaité.

Placez le préfixe de variable dynamique dans le champ de texte, suivi du paramètre de chaîne de requête ou de l’en-tête HTTP à référencer. Par défaut, le préfixe de variable dynamique est `D=`.

## Variables dynamiques dans AppMeasurement et éditeur de code personnalisé de l’extension Analytics

Les variables dynamiques sont des chaînes de texte affectées à d’autres variables. Le préfixe de variable dynamique par défaut est `D=`. Les variables dynamiques sont sensibles à la casse.

```js
// Copy eVar1 into eVar2. The query string parameter of eVar1 is v1.
s.eVar1 = "Example value";
s.eVar2 = "D=v1";

// Take the user agent string found in the image request HTTP header and place it in eVar1.
s.eVar1 = "D=User-Agent";

// Copy the page URL and place it in eVar1. The query string parameter of page URL is g.
s.eVar1 = "D=g";
```

>[!NOTE]
>
>Les variables dynamiques apparaissent sous forme de chaînes lors du débogage de votre mise en œuvre. Les valeurs sont copiées côté serveur par les serveurs de collecte de données Adobe.
