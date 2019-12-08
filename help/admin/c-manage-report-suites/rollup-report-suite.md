---
description: Les suites de rapports de cumul combinent les données de plusieurs suites de rapports affiliées et les affichent dans un jeu de données résumé.
title: Suites de rapports globales et de cumul
topic: Admin tools
uuid: c90b8e38-2c95-4318-8165-a362106b6142
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Suites de rapports globales et de cumul

Les suites de rapports de cumul combinent les données de plusieurs suites de rapports affiliées et les affichent dans un jeu de données résumé. Ils offrent un emplacement pratique pour afficher les totaux cumulés, tels que les pages vues, les recettes ou d’autres dimensions de base. Ils sont utilisés fréquemment, dans la mesure où ils ne nécessitent aucune implémentation supplémentaire.

## Définition des types de suite de rapports

**Report Suite** globale : L’implémentation est modifiée pour envoyer des demandes d’image entre domaines dans une seule suite de rapports globale. Si des accès sont également envoyés à des suites de rapports individuelles, cette pratique est connue sous le nom de balisage multi-suite.

**Suite de rapports de cumul** : elle est créée dans les outils d’administration. Cette suite calcule la somme de chaque mesure à la fin de chaque journée.

* Les cumuls sont gratuits et n’augmentent pas l’utilisation des appels serveur.
* Les cumuls fournissent des données totales, mais ne génèrent pas de rapports sur des valeurs individuelles. Ainsi, les valeurs eVar1 ne sont pas incluses, mais le total cumulé peut l’être.
* Les données ne sont pas dédupliquées lorsqu’elles sont combinées dans des suites de rapports.
* Les cumuls sont exécutés de nuit.
* Lors de l’ajout d’une suite de rapports à un cumul existant, les données historiques ne sont pas intégrées au cumul.
* Toutes les suites de rapports affiliées doivent comporter des données pour qu’un cumul fonctionne. Si vous intégrez de nouvelles suites de rapports dans un cumul, veillez à leur envoyer au moins une page vue.
* Les suites de rapports de cumul sont limitées à 40 suites enfants.
* Les suites de rapports de cumul sont limitées à 100 événements.
* Les données contenues dans les suites de rapports de cumul ne prennent pas en charge les ventilations ou les segments.
* Le rapport Pages est remplacé par le rapport Sites les plus populaires, qui indique les mesures au niveau de la suite enfant.

## Suites de rapports globales et de cumul

**Appels** du serveur secondaire : Les cumuls n’impliquent aucun appel serveur supplémentaire au-delà de ce qu’une seule suite de rapports collecte. Si votre entreprise utilise le balisage multi-suite, des appels au serveur secondaire sont effectués pour chaque suite de rapports supplémentaire incluse dans une demande d’image.

> [!TIP] Si vous utilisez uniquement une suite de rapports globale avec des suites [de rapports](../../components/vrs/vrs-considerations.md)virtuelles, aucun appel au serveur secondaire n’est nécessaire.

**Modifications** de l’implémentation : Les cumuls ne nécessitent aucune modification de l’implémentation, tandis que les suites de rapports globales nécessitent que vous incluiez l’identifiant de suite de rapports globale dans votre implémentation.

**Duplication** : contrairement aux cumuls, les suites de rapports globales dédupliquent les visiteurs uniques. Ainsi, si un utilisateur visite trois ou quatre de vos domaines le même jour, les cumuls comptabilisent trois visiteurs uniques par jour. Quant aux suites de rapports globales, elles n’en comptabilisent qu’un seul.

**Période** : les cumuls ne sont traités qu’à minuit, tous les jours, alors que les suites de rapports globales génèrent des rapports sur les données avec une latence standard.

**Largeur**: Les cumuls ne permettent pas de communiquer entre les suites de rapports. Les suites de rapports globales peuvent attribuer du crédit aux variables de conversion entre les suites de rapports, ainsi que fournir un cheminement entre les suites de rapports.

**Données historiques** : les cumuls peuvent agréger des données historiques, alors que les suites de rapports globales ne génèrent des rapports qu’à partir du point où les données ont été implémentées.

**Rapports**: Les suites de rapports globales fournissent des données sur toutes les dimensions ; les cumuls fournissent des données agrégées uniquement sur les rapports de haut niveau.

**Produits** pris en charge : Les cumuls ne peuvent être utilisés que dans les rapports et analyses. Ils ne sont pas pris en charge dans Analysis Workspace, l’entrepôt de données ou les analyses ad hoc. Les suites de rapports globales peuvent être utilisées pour tous les produits.

**Nombre de suites** de rapports agrégées : Les cumuls ne prennent en charge que 40 suites de rapports enfants au maximum. Les suites de rapports globales peuvent être implémentées sur n’importe quel nombre de domaines ou d’applications que vous détenez.
