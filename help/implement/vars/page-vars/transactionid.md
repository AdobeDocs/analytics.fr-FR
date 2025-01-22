---
title: transactionID
description: Utilisez cette variable pour lier des données en ligne et hors ligne.
feature: Variables
exl-id: 525e90d8-99a7-4f4f-9bce-1395bf72fd8f
role: Admin, Developer
source-git-commit: e281d43204e1c5b10508661f04b880125fe8671c
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 89%

---

# transactionID

La variable `transactionID` identifie de manière unique une transaction afin que l’accès puisse être lié aux données chargées via la fonctionnalité Sources de données. Cette variable s’avère utile lorsque vous souhaitez utiliser les données d’autres canaux et les lier aux données collectées avec AppMeasurement.

>[!NOTE]
>
>Assurez-vous que le stockage des [!UICONTROL identifiants de transaction] est activé dans une suite de rapports avant d’utiliser cette variable. Pour plus d’informations, consultez la section [Paramètres généraux du compte](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) du guide d’utilisation destiné à l’administrateur.

Lorsque vous définissez `transactionID` sur un accès, Adobe prend un « instantané » de toutes les variables Analytics définies ou conservées à ce moment précis. Les données chargées via la fonctionnalité Sources de données avec un identifiant de transaction correspondant sont liées de manière permanente à ces valeurs de variable.

L’Adobe mémorise toutes les valeurs d’ID de transaction (liées et non liées) pendant 25 mois au maximum.

## Identifiant de transaction utilisant le SDK Web

L’identifiant de transaction est mappé sur les variables suivantes :

* [Objet XDM](/help/implement/aep-edge/xdm-var-mapping.md) : `xdm.commerce.order.payments[0].transactionID`
* [Objet de données](/help/implement/aep-edge/data-var-mapping.md) : `data.__adobe.analytics.transactionID` ou `data.__adobe.analytics.xact`

## Identifiant de transaction utilisant l’extension Adobe Analytics

Vous pouvez définir l’identifiant de transaction lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la liste déroulante [!UICONTROL Extension] sur Adobe Analytics, et le [!UICONTROL Type d’action] sur [!UICONTROL Définir les variables].
6. Recherchez la section [!UICONTROL identifiant de transaction].

Vous pouvez définir l’identifiant de transaction sur n’importe quelle valeur de chaîne, y compris les éléments de données.

## s.transactionID dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.transactionID` est une chaîne contenant un identifiant unique pour une transaction. Les valeurs valides comprennent des caractères alphanumériques d’une longueur maximale de 100 octets. Sa valeur par défaut est une chaîne vide.

```js
s.transactionID = "ABC123";
```

Si vous disposez de plusieurs identifiants de transaction pour un accès, vous pouvez les délimiter par une virgule. Plusieurs identifiants de transaction sont toujours soumis à la limite de 100 octets.

```js
s.transactionID = "ABC123,XYZ456";
```

>[!TIP]
>
>Si vous intégrez plusieurs canaux hors ligne à l’aide de cette variable, assurez-vous que différents canaux ne chevauchent pas les identifiants de transaction. Si, par exemple, vous avez une valeur d’identifiant de transaction de centre d’appels de `1234` et une valeur d’identifiant de transaction de piste commerciale de `1234`, elles peuvent entrer en conflit et entraîner des résultats inattendus. Assurez-vous que les identifiants de transaction contiennent des formats uniques par canal hors ligne et différenciez-les si nécessaire. Par exemple, définissez l’identifiant de transaction de votre centre d’appels sur `call_1234` et l’identifiant de transaction de votre piste de vente `lead_1234` dans les sources de données et AppMeasurement.
