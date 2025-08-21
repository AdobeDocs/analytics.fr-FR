---
title: Sources de données des ID de transaction
description: Utilisez les valeurs stockées d’un accès en ligne pour enrichir les accès hors ligne qui partagent un identifiant de transaction.
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
role: Admin
source-git-commit: 0a65114d598b7c6d2871a2446ad4d574b9ca44bb
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 8%

---

# Sources de données des ID de transaction

Les sources de données d’ID de transaction sont une variante des sources de données de résumé qui vous permettent d’appliquer les valeurs enregistrées à partir d’un accès en ligne aux lignes hors ligne qui partagent le même ID de transaction. Cette approche est utile lorsque vous capturez une transaction en ligne, mais que vous recevez des détails ultérieurement d’un autre système. Les exemples Principal incluent les retours de produits, les annulations de réservation ou les résultats des interactions de centre d’appel.

>[!NOTE]
>
>Avant d’utiliser les sources de données d’ID de transaction, vous devez d’abord l’activer dans [Paramètres généraux du compte](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) pour la suite de rapports souhaitée.

## Fonctionnement

Le concept des ID de transaction nécessite deux parties :

* **Accès en ligne** : tout accès Analytics complet envoyé à une suite de rapports (AppMeasurement, Web SDK, API, etc.). Sur cet accès, vous définissez la variable d’implémentation [`transactionID`](/help/implement/vars/page-vars/transactionid.md).
* **Accès hors ligne** : ligne téléchargée via les sources de données. Dans le fichier , incluez la colonne `transactionID` avec une valeur correspondant à un accès en ligne.

Lorsque vous envoyez un accès en ligne contenant la variable d’implémentation `transactionID`, Adobe prend un « instantané » des dimensions suivantes qui ont été définies ou conservées à ce stade :

* [Catégorie](/help/components/dimensions/category.md)
* [Jours avant le premier achat](/help/components/dimensions/days-before-first-purchase.md)
* [Jours depuis le dernier achat](/help/components/dimensions/days-since-last-purchase.md)
* [eVars 1-250](/help/components/dimensions/evar.md)
* Dimensions spécifiques aux fonctionnalités activées dans [paramètres de la suite de rapports](/help/admin/admin/c-manage-report-suites/report-suites-admin.md) qui se comportent de la même manière que les eVars. Les cotes spécifiques aux fonctionnalités qui se comportent de la même manière que les props ne sont pas incluses.
* [Variables de liste](/help/implement/vars/page-vars/list.md)
* [Canal marketing](/help/components/dimensions/marketing-channel.md)
* [Détail des canaux marketing](/help/components/dimensions/marketing-detail.md)
* [Dimensions mobiles](/help/components/dimensions/mobile-dimensions.md)
* [Domaine référent initial](/help/components/dimensions/original-referring-domain.md)
* [Produit](/help/components/dimensions/product.md)
* [Domaine référent](/help/components/dimensions/referring-domain.md)
* [Moteur de recherche](/help/components/dimensions/search-engine.md)
* [Mot-clé de recherche](/help/components/dimensions/search-keyword.md)
* [Code de suivi](/help/components/dimensions/tracking-code.md)
* [Nombre de visites](/help/components/dimensions/visit-number.md)

>[!NOTE]
>
>Les mesures (telles que les [Commandes](/help/components/metrics/orders.md) ou [Événements personnalisés](/help/components/metrics/custom-events.md)) ne sont pas incluses dans l’« instantané ».

Lorsque vous chargez un accès hors ligne via des sources de données contenant un ID de transaction correspondant, toutes les dimensions disponibles dans l’« instantané » sont automatiquement ajoutées à la ligne de source de données. Si une dimension donnée est présente à la fois dans l’accès en ligne et dans l’accès hors ligne, la valeur de l’accès hors ligne est utilisée.

>[!IMPORTANT]
>
>Le concept des sources de données d’ID de transaction permet uniquement de remplir les lignes de source de données (accès hors ligne). Elles n’affectent pas et ne modifient pas l’accès en ligne.

## Considérations relatives à la source de données des ID de transaction

Les sources de données d’ID de transaction présentent les propriétés suivantes :

* Les données en ligne doivent d&#39;abord être collectées et traitées. Si une source de données d’ID de transaction est chargée avant qu’une suite de rapports ne traite un accès correspondant à cet ID de transaction, les données sont traitées comme une source de données de résumé.
* Les ID de transaction collectés à partir des accès en ligne expirent après 25 mois.
* Les sources de données chargées avec un ID de transaction expiré sont traitées de la même manière que les données chargées sans ID de transaction.
* Si vous définissez le même ID de transaction sur plusieurs accès en ligne, seul l’« instantané » de la première occurrence est utilisé. Les accès en ligne suivants aux ID de transaction en double sont traités comme s’ils n’avaient pas d’ID de transaction.
* Une fois que vous renseignez une valeur de `transactionID` donnée, l’« instantané » associé est considéré comme non modifiable jusqu’à l’expiration de cet identifiant de transaction.
* Si vous définissez le même ID de transaction sur plusieurs lignes de source de données, toutes les dimensions disponibles de l’accès en ligne sont ajoutées à chaque accès hors ligne. Les accès hors ligne pour le même ID de transaction ne se connaissent pas ; les données ne sont pas transmises entre les accès hors ligne.
