---
title: Sources de données des ID de transaction
description: Découvrez le processus général d’utilisation des sources de données des ID de transaction.
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
source-git-commit: 54c88a275b48f2b401be450ce35767ab3ea9d40b
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 10%

---

# Sources de données des ID de transaction

Les sources de données ID de transaction sont une variation des sources de données récapitulatives qui vous permettent de lier des données en ligne et hors ligne. Elles nécessitent l’utilisation de la variable [`transactionID`](/help/implement/vars/page-vars/transactionid.md) dans votre implémentation Analytics.

* Si une ligne d’un fichier de sources de données inclut un ID de transaction correspondant à un ID de transaction déjà collecté par AppMeasurement, les dimensions et les mesures sont ajoutées à l’accès en ligne.
* Si une ligne d’un fichier de sources de données contient un ID de transaction qui ne contient pas de correspondance, la ligne est traitée de la même manière que les sources de données récapitulatives.

>[!NOTE]
>
>Avant d’utiliser des sources de données d’ID de transaction, vous devez d’abord les activer dans [Paramètres du compte général](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) pour la suite de rapports souhaitée.

Lorsque vous envoyez un accès en ligne contenant une [`transactionID`](/help/implement/vars/page-vars/transactionid.md) , Adobe prend un &quot;instantané&quot; de toutes les variables définies ou conservées. Si un ID de transaction correspondant transféré via des sources de données est trouvé, les données hors ligne et en ligne sont liées.

Les sources de données des ID de transaction présentent les propriétés suivantes :

* Les données en ligne doivent d&#39;abord être collectées et traitées. Si une source de données d’ID de transaction est chargée avant qu’une suite de rapports ne traite un accès correspondant à cet ID de transaction, les données ne sont pas liées.
* Les identifiants de transaction collectés via AppMeasurement expirent après environ 90 jours. Si votre entreprise a besoin d’une fenêtre d’ID de transaction plus longue, contactez l’assistance clientèle d’Adobe.
* Les sources de données chargées avec un ID de transaction expiré sont traitées de la même manière que les données transférées sans ID de transaction.
* Si la même variable est incluse dans l’accès en ligne et la source de données de l’ID de transaction, la valeur de la source de données de l’ID de transaction est utilisée.
* Si une variable est incluse dans un accès en ligne, mais pas dans un accès de source de données d’ID de transaction correspondant, la variable d’accès en ligne est conservée.
* Si vous définissez le même ID de transaction sur plusieurs accès en ligne, seule la première occurrence est modifiée avec les données d’une source de données d’ID de transaction correspondante.
* Si vous définissez le même ID de transaction sur plusieurs lignes de source de données pour les mêmes dimensions, le dernier élément de dimension est utilisé.

Par exemple :

1. Vous envoyez une page vue depuis AppMeasurement où :
   * `eVar1` est égal à `blue`
   * `eVar2` est égal à `water`
   * `events` est égal à `event1`
   * `transactionID` est égal à `1256`
2. Une fois l’accès collecté et traité, vous transférez une source de données d’ID de transaction dans laquelle :
   * `eVar1` est égal à `yellow`
   * `eVar3` est égal à `bird`
   * `events` est égal à `event2`
   * `transactionID` est égal à `1256`
3. Une fois l’accès aux sources de données traité, vous affichez un rapport dans l’espace de travail. Les données présenteraient les éléments suivants :
   * `eVar1` est égal à `yellow`
   * `eVar2` est égal à `water`
   * `eVar3` est égal à `bird`
   * `events` est égal à `event2`

Valeur eVar1 `blue` et le `event1` ne sont pas présentes dans les rapports, car l’accès à l’ID de transaction remplace ces valeurs respectives.
