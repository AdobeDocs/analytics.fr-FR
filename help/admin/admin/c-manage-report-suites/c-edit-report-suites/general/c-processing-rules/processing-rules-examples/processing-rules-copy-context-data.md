---
description: Les règles de traitement servent à déplacer des valeurs des variables Données contextuelles vers des props et des eVars.
subtopic: Processing rules
title: Copier une variable de données contextuelles dans une eVar
feature: Admin Tools
role: Admin
exl-id: f52c2c6c-da3d-43d6-be13-92d0820c93b4
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 100%

---

# Copier une variable de données contextuelles dans une eVar

Les règles de traitement servent à déplacer des valeurs des variables Données contextuelles vers des props et des eVars. Sans règles de traitement, les variables de données contextuelles n’ont aucun sens et ne renseignent des données dans aucun rapport dans Analytics.

La liste [!UICONTROL Variables contextuelles] contient toutes les variables qui ont été envoyées à la suite de rapports au cours des 30 derniers jours. Si vous connaissez le nom de la variable de données contextuelles, mais ne l’avez pas envoyée dans la suite de rapports actuelle, vous pouvez ajouter une valeur en entrant le nom de la variable et en cliquant sur **[!UICONTROL Ajouter les données contextuelles nom de la variable]** :

![Ajouter](assets/add-context-variable.png)

L’exemple suivant utilise la variable de données contextuelles `search_term` et place sa valeur dans `eVar3` :

![Définir](assets/set-context-data.png)

L’exemple ci-dessus fonctionne bien lorsqu’il n’y a que quelques eVars à renseigner. Si votre entreprise dispose de centaines de variables de données contextuelles qui nécessitent chacune leur propre eVar, vous pouvez utiliser des instructions conditionnelles. Une règle de traitement unique peut contenir des dizaines d’instructions conditionnelles, ce qui permet à votre entreprise de renseigner toutes les eVars d’une suite de rapports sans avoir à respecter la limite de 150 règles de traitement.

L’exemple suivant renseigne `prop7` avec la variable de données contextuelles `testhierarchy`, mais uniquement en cas de définition de `testhierarchy` :

![Conditionnel](assets/add-conditional.png)

Pour plus d’informations sur l’implémentation des variables de données contextuelles, reportez-vous à [Variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md) dans le guide de l’utilisateur Mise en œuvre.
