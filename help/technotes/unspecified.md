---
description: Dans Adobe Analytics, divers rapports peuvent afficher Non spécifié, Aucun, Autre ou Inconnu selon le rapport spécifique consulté. En général, cet élément de ligne signifie que la variable n’a pas été définie ou n’est pas disponible.
title: Non spécifié, Aucun, Autre et Inconnu dans les rapports
feature: Analytics Basics
exl-id: 35451239-91f3-400a-981e-8c3fbc0e4185
TQID: https://experienceleague.adobe.com/JWT1oVZ-3Qcg9IxtPcEw9R9b8WHpe0O5GhDb3q-l7jo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: a421fb65-2c82-457a-921c-28c46b697a39
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2:
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 527
ht-degree: 96%

---

# « Non spécifié », « Aucun », « Autre » et « Inconnu » dans les rapports

Dans Adobe Analytics, de nombreux rapports peuvent afficher Non spécifié, Autre ou Inconnu selon le rapport spécifique consulté. En général, cet élément de ligne signifie que la variable n’a pas été définie ou n’est pas disponible. La liste complète suivante montre comment chaque rapport peut être associé à un de ces éléments de ligne.

## « Non spécifié » (ou « Aucun ») dans les rapports {#reporting}

Non spécifié est un élément de ligne assez courant dans les rapports. Il est aussi fréquemment appelé « Aucun ».

* **Événement déclenché sans variable de conversion :** par exemple, un utilisateur accède à votre site et effectue un achat sans déclencher de valeur eVar1. Si vous consultez les commandes à l’aide de la dimension eVar1, aucune valeur ne peut être attribuée à cette commande. La valeur Non spécifié lui est donc automatiquement attribuée.
* **Données non classifiées dans les rapports de classification :** lors de la consultation des données de classification, les valeurs dont les données ne sont pas associées à cette classification donnée renvoient la valeur Non spécifié. Pour résoudre ce problème, assurez-vous qu’une valeur de classification est associée à chaque élément de dimension parent.
* **Rapports de répartition dans lesquels une seule variable est déclenchée** : lorsque vous appliquez une répartition à une variable, chaque instance de cette variable doit être prise en compte. Si la seconde variable n’a pas pu être consultée ou si elle persiste d’un précédent accès, l’élément de dimension est « Non spécifié ».
* **Accès non mobiles dans les rapports mobiles :** les accès non mobiles des rapports mobiles sont répertoriés comme Non spécifié (Non mobile dans Reports &amp; Analytics).

## Valeur Autre dans les rapports {#other}

Bien qu’assez rare dans les rapports, la valeur Autre s’affiche dans plusieurs cas :

* **Les pages se déclenchent en dehors de vos filtres d’URL internes :** cette valeur est en place pour vous aider à vous protéger des fraudes aux données, par exemple si une autre organisation vole votre code source et le met en œuvre sur son propre site. Pour résoudre ce problème, veillez à ce que toutes les URL sur lesquelles votre code est mis en œuvre correspondent aux filtres d’URL internes des paramètres de vos suites de rapports.
* **Visiteurs utilisant un navigateur peu courant :** dans le rapport Types de navigateur, la valeur Autre apparaît comme répartition lorsque les visiteurs utilisent un type de navigateur peu courant. Nombre d’entreprises créent des navigateurs. Tous les navigateurs que les grandes entreprises n’ont pas créés sont classés dans la catégorie Autre afin d’éviter d’encombrer les rapports.

## Valeur Inconnu dans les rapports {#unknown}

La valeur Inconnu peut s’afficher dans plusieurs cas :

* **Accès d’un non-navigateur lors de la consultation des rapports technologiques :** si une bibliothèque AppMeasurement n’est pas en mesure de déterminer si une fonctionnalité est prise en charge, la valeur Inconnu s’affiche dans les rapports.
* **Utilisation de segments en cas d’inaccessibilité des composants :** assurez-vous que les variables utilisées dans un segment sont activées et que les utilisateurs peuvent y accéder. Si un utilisateur n’a pas accès à un composant de segment, ou si une variable est désactivée, la valeur Inconnu s’affiche.

## Filtrage de ces valeurs dans les rapports {#filter}

Dans la plupart des cas, ignorer ces éléments de ligne ne présente aucun problème. Le filtre de recherche peut être utilisé pour les supprimer, si nécessaire.

Certaines variables de données principales utilisent la valeur `::unspecified::` dans les rapports, bien qu’elle ne soit pas affichée dans l’interface. Si un filtre de recherche n’exclut pas les données, essayez d’utiliser cette valeur (y compris les deux-points).
