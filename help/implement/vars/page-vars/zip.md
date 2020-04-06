---
title: zip
description: Permet de renseigner manuellement la dimension « Code postal » si les paramètres de la suite de rapports le permettent.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# zip

The `zip` variable allows you to manually populate the &#39;Zip Code&#39; dimension if the [!UICONTROL Zip Option] in report suite settings allows it. Dans les versions précédentes d’Adobe Analytics, cette variable ne pouvait être définie manuellement que lors de la saisie d’informations d’expédition sur un site de vente au détail. Les améliorations apportées à Adobe Analytics permettent de définir automatiquement cette variable à l’aide des données de géolocalisation. Cette variable ne persiste pas au-delà de l’accès auquel elle est définie.

>[!IMPORTANT] Assurez-vous que les paramètres [!UICONTROL Zip Option] de la suite de rapports sont définis sur la valeur souhaitée. Vous ne pouvez pas utiliser cette variable si [!UICONTROL geo zip] est toujours utilisé. Pour plus d’informations, consultez la section [Paramètres généraux du compte](/help/admin/admin/general-acct-settings-admin.md) du guide d’utilisation Administrateur.

## Code postal dans Adobe Experience Platform Launch

Vous pouvez définir le code postal lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Sous [!UICONTROL Actions], cliquez sur une [!UICONTROL Adobe Analytics - Set Variables] action existante ou cliquez sur l’icône &quot;+&quot;.
5. Définissez la [!UICONTROL Extension] liste déroulante sur Adobe Analytics et la [!UICONTROL Action Type] sur [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Zip] section.

Vous pouvez définir le code postal sur n’importe quelle valeur de chaîne, y compris les éléments de données.

## s.zip dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.zip` est une chaîne qui contient généralement un code postal, mais qui peut contenir toute valeur souhaitée jusqu’à 50 octets de longueur.

```js
s.zip = "84043";
```
