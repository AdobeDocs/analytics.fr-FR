---
title: zip
description: Permet de renseigner manuellement la dimension « Code postal » si les paramètres de la suite de rapports le permettent.
feature: Variables
exl-id: 1acf4bf7-3788-46bd-bcdb-9885c7b93b59
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 94%

---

# zip

La variable `zip` vous permet de renseigner manuellement la dimension « Code postal » si l’[!UICONTROL option de code postal] des paramètres de la suite de rapports l’autorise. Dans les versions précédentes d’Adobe Analytics, cette variable ne pouvait être définie manuellement que lors de la saisie d’informations d’expédition sur un site de vente au détail. Les améliorations apportées à Adobe Analytics permettent de définir automatiquement cette variable à l’aide des données de géolocalisation. Cette variable ne persiste pas au-delà de l’accès auquel elle est définie.

>[!IMPORTANT]
>
>Assurez-vous que l’[!UICONTROL option de code postal] des paramètres de la suite de rapports est définie sur la valeur souhaitée. Vous ne pouvez pas utiliser cette variable si [!UICONTROL geo zip] est toujours utilisé. Pour plus d’informations, consultez la section [Paramètres généraux du compte](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) du guide d’utilisation destiné à l’administrateur.

## Code postal utilisant l’extension Adobe Analytics

Vous pouvez définir le code postal lors de la configuration de l’extension Analytics (variables globales) ou sous des règles.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Règles], puis cliquez sur une règle (ou créez une règle).
4. Sous [!UICONTROL Actions], cliquez sur une action existante [!UICONTROL Adobe Analytics - Définir des variables] ou cliquez sur l’icône « + ».
5. Définissez la variable [!UICONTROL Extension] de la liste déroulante vers Adobe Analytics, et la variable [!UICONTROL Type d’action] to [!UICONTROL Définition de variables].
6. Recherchez la section [!UICONTROL Code postal].

Vous pouvez définir le code postal sur n’importe quelle valeur de chaîne, y compris les éléments de données.

## s.zip dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.zip` est une chaîne qui contient généralement un code postal, mais qui peut contenir toute valeur souhaitée jusqu’à 50 octets de longueur.

```js
s.zip = "84043";
```
