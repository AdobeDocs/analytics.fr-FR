---
description: Informations relatives aux caractères spéciaux utilisés dans le flux de données.
keywords: Flux de données;tâche;caractères spéciaux;hit_data;variables à plusieurs valeurs;events_list;products_list;mvvars
subtopic: data feeds
title: Caractères spéciaux dans les flux de données
feature: Data Feeds
exl-id: b816ebc5-0b23-4420-aa8c-b88953d031e6
TQID: 'https://experienceleague.adobe.com/jNnPgkpVea1R-uUcOiV7UDRc8TdGjhov9yFCvgfitMA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: ede9f3ba-4ee4-4497-9d8e-e9da5848bda0
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 333
ht-degree: 90%

---

# Caractères spéciaux dans les flux de données

Adobe utilise une logique d’échappement pour s’assurer que les valeurs envoyées vers les serveurs de collecte des données ne corrompent pas ou n’ont pas d’effet négatif sur les fichiers de flux de données. Les caractères suivants sont réservés par Adobe aux fins suivantes dans `hit_data.tsv`.

## Caractères spéciaux quelle que soit la colonne

| Caractère | Description |
|--- |--- |
| `\t` | Représente un onglet. Marque la fin d’une colonne ou d’un champ de données. |
| `\n` | Représente une nouvelle ligne. Marque la fin d’une ligne ou d’un accès. |
| `\` | Barre oblique inverse. Échappe les caractères envoyés dans le cadre d’une collecte de données. |

Lorsque ces valeurs réservées sont précédées d’une barre oblique inverse, elles ont été envoyées dans le cadre d’une collecte de données.

| Caractère | Description |
|--- |--- |
| `\\t` | La valeur « `\t` » a été envoyée pendant la collecte des données, avec l’échappement d’Adobe. |
| `\\n` | La valeur « `\n` » a été envoyée pendant la collecte des données, avec l’échappement d’Adobe. |
| `\\` | La valeur « `\` » a été envoyée pendant la collecte des données, avec l’échappement d’Adobe. |

Par exemple, un visiteur de votre site utilise la recherche interne et recherche des `"search\nstring"`. Vous renseignez eVar1 avec des `"search\nstring"` et envoyez cette valeur à Adobe. Adobe reçoit cet accès et échappe la nouvelle ligne incluse dans la chaîne. La valeur réelle placée dans les données brutes est `"search\\nstring"`.

## Caractères spéciaux dans des variables à plusieurs valeurs (events_list, products_list, mvvars)

Les caractères suivants ont une signification spéciale dans les colonnes qui peuvent contenir plusieurs valeurs.

| Caractère | Description |
|--- |--- |
| `,` | Virgule. Représente la fin d’une valeur individuelle. Sépare les chaînes de produit, les identifiants d’événement ou d’autres valeurs. |
| `;` | Point-virgule. Représente la fin d’une valeur individuelle dans `product_list`. Sépare les champs ne comportant qu’une chaîne de produit unique. |
| `=` | Signe égal à. Attribue une valeur à un événement dans `product_list`. |
| `^` | Accent circonflexe. Échappe les caractères envoyés dans le cadre d’une collecte de données. |

Lorsque ces valeurs réservées sont précédées d’un accent circonflexe, elles ont été envoyées dans le cadre d’une collecte de données.

| Caractère | Description |
|--- |--- |
| `^,` | La valeur « `,` » a été envoyée pendant la collecte des données, avec l’échappement d’Adobe. |
| `^;` | La valeur « `;` » a été envoyée pendant la collecte des données, avec l’échappement d’Adobe. |
| `^=` | La valeur « `=` » a été envoyée pendant la collecte des données, avec l’échappement d’Adobe. |
| `^^` | La valeur « `^` » a été envoyée pendant la collecte des données, avec l’échappement d’Adobe. |
