---
title: stockage
description: Utilisez cette variable pour lier des données en ligne et hors ligne.
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# stockage

La `transactionID` variable identifie de manière unique une transaction afin que l’accès puisse être lié aux données transférées via la fonctionnalité Sources de données. Cette variable s’avère utile lorsque vous souhaitez utiliser les données d’autres canaux et les lier aux données collectées avec AppMeasurement.

> [!NOTE] Assurez-vous que le stockage [!UICONTROL des identifiants de] transaction est activé dans une suite de rapports avant d’utiliser cette variable. See [General Account Settings](/help/admin/admin/general-acct-settings-admin.md) in the Admin user guide for more information.

Lorsque vous définissez `transactionID` un accès, Adobe prend un &quot;instantané&quot; de toutes les variables Analytics définies ou conservées à ce moment précis. Les données transférées via la fonctionnalité Sources de données avec un ID de transaction correspondant sont liées de manière permanente à ces valeurs de variable.

Par défaut, Adobe mémorise toutes les valeurs d’ID de transaction (liées et non liées) pendant 90 jours au maximum. Si votre processus d’interaction hors ligne dure plus de 90 jours, contactez le service à la clientèle pour que cette limite soit étendue.

## ID de transaction dans Adobe Experience Platform Launch

Vous pouvez définir l’ID de transaction lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur une propriété.
3. Accédez à l’onglet [!UICONTROL Règles] , puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône &quot;+&quot;.
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics et le type [!UICONTROL d’] action sur [!UICONTROL Définir des variables].
6. Recherchez la section ID [!UICONTROL de] transaction.

Vous pouvez définir l’ID de transaction sur n’importe quelle valeur de chaîne, y compris les éléments de données.

## s.transactionID dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.transactionID` variable est une chaîne contenant un identifiant unique pour une transaction. Les valeurs valides comprennent des caractères alphanumériques d’une longueur maximale de 100 octets. Sa valeur par défaut est une chaîne vide.

```js
s.transactionID = "ABC123";
```

Si vous disposez de plusieurs ID de transaction pour un accès, vous pouvez les délimiter par une virgule. Plusieurs ID de transaction sont toujours soumis à la limite de 100 octets.

```js
s.transactionID = "ABC123,XYZ456";
```

> [!NOTE] Si vous intégrez plusieurs canaux hors ligne à l’aide de cette variable, assurez-vous que différents canaux ne chevauchent pas les ID de transaction. Si, par exemple, vous avez une valeur d’ID de transaction de centre d’appels de `1234` et une valeur d’ID de transaction de piste commerciale de `1234`, elles peuvent entrer en conflit et entraîner des résultats inattendus. Assurez-vous que les ID de transaction contiennent des formats uniques par canal hors ligne et faites-les la différence si nécessaire. Par exemple, définissez l’ID de transaction de votre centre d’appels sur `call_1234` et l’ID de transaction de votre piste de vente `lead_1234` dans les sources de données et AppMeasurement.
