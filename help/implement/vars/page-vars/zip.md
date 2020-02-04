---
title: zip
description: Renseignez manuellement la dimension "Code postal" si les paramètres de la suite de rapports le permettent.
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# zip

La `zip` variable vous permet de renseigner manuellement la dimension &quot;Code postal&quot; si l’option  zip des paramètres de la suite de rapports l’autorise. Dans les versions précédentes d’Adobe Analytics, cette variable ne pouvait être définie manuellement que lors de la saisie d’informations d’expédition sur un site de vente au détail. Les améliorations apportées à Adobe Analytics permettent de définir automatiquement cette variable à l’aide des données de géolocalisation. Cette variable ne persiste pas au-delà de l’accès qu’elle est définie.

> [!IMPORTANT] Assurez-vous que l’option  zip des paramètres de la suite de rapports est définie sur la valeur souhaitée. Vous ne pouvez pas utiliser cette variable si [!UICONTROL geo zip] est toujours utilisé. See [General Account Settings](/help/admin/admin/general-acct-settings-admin.md) in the Admin user guide for more information.

## Code postal dans Adobe Experience Platform Launch

Vous pouvez définir le code postal lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur une propriété.
3. Accédez à l’onglet [!UICONTROL Règles] , puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône &quot;+&quot;.
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le type [!UICONTROL d’] action sur [!UICONTROL Définir des variables].
6. Recherchez la section [!UICONTROL zip] .

Vous pouvez définir le code postal sur n’importe quelle valeur de chaîne, y compris les éléments de données.

## s.zip dans AppMeasurement et Lancement de l’éditeur de code personnalisé

La `s.zip` variable est une chaîne qui contient généralement un code postal, mais qui peut contenir toute valeur souhaitée jusqu’à 50 octets de longueur.

```js
s.zip = "84043";
```
