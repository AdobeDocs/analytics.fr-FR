---
description: Formats de fichiers pris en charge par les ensembles de classifications
title: Formats de fichiers d’ensemble de classifications
feature: Classifications
exl-id: f3d429be-99d5-449e-952e-56043b109411
source-git-commit: c642664ecca24d9fc555944fb2b449f30eac879d
workflow-type: tm+mt
source-wordcount: '1023'
ht-degree: 1%

---

# Formats de fichiers d’ensemble de classifications

Les ensembles de classifications prennent en charge plusieurs formats de fichiers pour le chargement en masse de données de classification. Chaque format a des exigences spécifiques pour réussir les chargements de données.

Une fois que votre fichier est correctement formaté conformément à ces spécifications, vous pouvez le charger via l’interface des ensembles de classifications ou l’API. Pour obtenir des instructions de chargement détaillées :

* **Téléchargement Du Navigateur** : Voir [Schéma](manage/schema.md)
* **Chargement d’API** : voir [API de classifications Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/).

Les ensembles de classifications prennent en charge les formats de fichiers suivants :

* **JSON** : fichiers de notation d’objet JavaScript avec des données structurées
* **CSV** : fichiers de valeurs séparées par des virgules
* **TSV/TAB** : fichiers de valeurs séparées par des tabulations

## Exigences générales relatives aux fichiers

Tous les formats de fichier doivent respecter les exigences suivantes :

* **Encodage du fichier** : utilisez UTF-8 sans marques d’ordre des octets. Le codage Latin1 est également pris en charge.
* **Limites de caractères** : les valeurs de classification individuelles ont une limite maximale de 255 octets.
* **Exigences clés** : les valeurs de clé ne peuvent pas être vides ou contenir uniquement des espaces. Si des clés en double sont présentes, la dernière occurrence est utilisée.

+++**Détails du format JSON**

Le format de fichier JSON respecte les conventions relatives aux lignes JSON (JSONL). Le fichier doit contenir un objet JSON par ligne, où chaque objet représente un seul enregistrement de classification.

>[!NOTE]
>
>Malgré les conventions suivantes pour les lignes JSON, utilisez l’extension de fichier `.json` pour tous les chargements. L’utilisation de l’extension `.jsonl` peut entraîner des erreurs.

### Structure JSON

Chaque objet JSON doit contenir :

* `key` (obligatoire) : identifiant unique de l’enregistrement de classification
* `data` (obligatoire pour les mises à jour) : objet contenant les noms des colonnes de classification et leurs valeurs
* `action` (facultatif) : action à effectuer. Les valeurs acceptables sont : 
   * `update` (par défaut)
   * `delete-field`
   * `delete-key`
* `enc` (facultatif) : spécification du codage des données. Les valeurs acceptables sont : 
   * `utf8` ou `UTF8` (par défaut)
   * `latin1` ou `LATIN1`

Tous les noms de champ JSON (`key`, `data`, `action`, `enc`) sont sensibles à la casse et doivent être en minuscules.

### Exemples JSON

**Enregistrement de mise à jour de base :**

```json
{"key": "product123", "data": {"Product Name": "Basketball Shoes", "Brand": "Brand A", "Category": "Sports"}}
```

**Mise à jour avec encodage spécifié :**

```json
{"key": "product456", "enc": "utf8", "data": {"Product Name": "Running Shoes", "Brand": "Brand B"}}
```

**Supprimer des champs spécifiques :**

```json
{"key": "product789", "action": "delete-field", "data": {"Brand": null, "Category": null}}
```

**Supprimer la clé entière :**

```json
{"key": "product999", "action": "delete-key"}
```

### Règles de validation JSON

* Le champ `key` est obligatoire et ne peut pas être nul ou vide.
* Pour les actions `update`, le champ `data` est obligatoire et ne peut pas être vide.
* Pour `delete-field` actions, le champ `data` doit contenir les champs à supprimer.
* Pour les actions `delete-key`, le champ `data` ne doit pas être présent.
* Les valeurs de codage prises en charge ne respectent pas la casse et incluent des noms de jeux de caractères standard.

+++

+++**détails du format CSV**

Les fichiers CSV (valeurs séparées par des virgules) utilisent des virgules pour séparer les champs de données de classification.

### Structure CSV

* **Ligne d’en-tête** : la première ligne doit contenir des en-têtes de colonne et la première colonne doit être la colonne clé. Les colonnes suivantes doivent correspondre aux noms dans votre schéma d’ensemble de classifications
* **Lignes de données** : chaque ligne suivante contient des données de classification
* **Délimiteurs** : les champs sont séparés par des virgules
* **Guillemet** : les champs contenant des virgules, des guillemets ou des nouvelles lignes doivent être placés entre guillemets doubles

### Exemples CSV

**Données de classification de base :**

```csv
Key,Product Name,Brand,Category,Price
product123,"Basketball Shoes",Brand A,Sports,89.99
product456,"Running Shoes",Brand B,Sports,79.99
product789,"Winter Jacket",Brand C,Clothing,149.99
```

**Supprimer la clé entière :**

```csv
Key,Product Name,Brand,Category,Price
product999,~deletekey~,,,
```

**Supprimer les champs spécifiques (associés aux mises à jour) :**

```csv
Key,Product Name,Brand,Category,Price
product123,"Updated Product Name",Brand A,Sports,89.99
product456,,~empty~,~empty~,79.99
```

### Règles de formatage CSV

* Les champs contenant des virgules doivent être placés entre guillemets doubles
* Les champs contenant des guillemets doubles doivent échapper les guillemets en les doublant (`""`)
* Les champs vides représentent des valeurs nulles pour cette classification
* Les espaces de début et de fin autour des champs sont automatiquement supprimés
* Les caractères spéciaux (tabulations, nouvelles lignes) contenus dans les champs entre guillemets sont conservés

**Opérations de suppression :**
* Utilisez `~deletekey~` dans n’importe quel champ pour supprimer la clé entière et toutes ses données de classification
* Utilisez des `~empty~` dans des champs spécifiques pour supprimer uniquement ces valeurs de classification (en laissant les autres champs intacts).
* Lorsque vous utilisez `~empty~`, vous pouvez combiner des suppressions et des mises à jour dans le même fichier

+++

+++**Détails du format TSV/TAB**

Les fichiers TSV (valeurs séparées par des tabulations) et TAB utilisent des caractères de tabulation pour séparer les champs de données de classification.

### Structure TSV/TAB

* **Ligne d’en-tête** : la première ligne doit contenir des en-têtes de colonne et la première colonne doit être la colonne clé. Les colonnes suivantes doivent correspondre aux noms dans votre schéma d’ensemble de classifications
* **Lignes de données** : chaque ligne suivante contient des données de classification
* **Délimiteurs** : les champs sont séparés par des tabulations (`\t`)
* **Guillemet** : en règle générale, aucun guillemet n’est nécessaire, mais certaines implémentations prennent en charge les champs entre guillemets

### Exemples TSV/TAB

**Données de classification de base :**

```tsv
Key    Product Name    Brand    Category    Price
product123    Basketball Shoes    Brand A    Sports    89.99
product456    Running Shoes    Brand B    Sports    79.99
product789    Winter Jacket    Brand C    Clothing    149.99
```

**Supprimer la clé entière :**

```tsv
Key    Product Name    Brand    Category    Price
product999    ~deletekey~            
```

**Supprimer les champs spécifiques (associés aux mises à jour) :**

```tsv
Key    Product Name    Brand    Category    Price
product123    Updated Product Name    Brand A    Sports    89.99
product456        ~empty~    ~empty~    79.99
```

### Règles de formatage TSV/TAB

* Les champs sont séparés par des caractères à une seule tabulation
* Les champs vides (onglets consécutifs) représentent des valeurs nulles
* Aucune citation spéciale n&#39;est généralement requise
* Les espaces de début et de fin sont conservés
* Les caractères de nouvelle ligne dans les champs doivent être évités

**Opérations de suppression :**
* Utilisez `~deletekey~` dans n’importe quel champ pour supprimer la clé entière et toutes ses données de classification
* Utilisez des `~empty~` dans des champs spécifiques pour supprimer uniquement ces valeurs de classification (en laissant les autres champs intacts).
* Lorsque vous utilisez `~empty~`, vous pouvez combiner des suppressions et des mises à jour dans le même fichier

+++

## Traitement des erreurs

Problèmes courants de chargement et solutions :

### Erreurs générales de format de fichier

* **Format de fichier non valide** : vérifiez que votre extension de fichier correspond au format de contenu (.json, .csv, .tsv ou .tab).
* **« En-tête inconnu »** : les noms des colonnes doivent correspondre à votre schéma d’ensemble de classifications (s’applique à tous les formats).

### Erreurs spécifiques à CSV/TSV

* **« La clé doit figurer dans la première colonne »** Assurez-vous que votre fichier CSV/TSV comporte une ligne d’en-tête appropriée avec la colonne clé en premier.
* **« Au moins deux éléments d’en-tête sont requis »** : les fichiers CSV/TSV doivent avoir au moins une colonne « Clé » et une colonne de classification.
* **« La première colonne d&#39;en-tête doit être appelée &#39;Key&#39;«** : Le premier en-tête de colonne doit être exactement « Key » (K majuscule, sensible à la casse).
* **« Les en-têtes vides ne sont pas autorisés »** : tous les en-têtes de colonne CSV/TSV doivent avoir un nom.
* **« Le nombre de colonnes ne correspond pas aux en-têtes »** : Chaque ligne de données CSV/TSV doit comporter le même nombre de champs que la ligne d’en-tête.
* **« Document incorrect »** : vérifiez les guillemets CSV, la séparation correcte des onglets dans les fichiers TSV, etc.

### Erreurs spécifiques à JSON

* **« La clé est un champ obligatoire »** : tous les enregistrements JSON doivent avoir un champ `"key"` non vide (en minuscules, sensible à la casse).
* **« Les données sont un champ obligatoire lors de l’utilisation d’action=update »** : les actions de mise à jour JSON doivent inclure un champ `"data"`.
* **« Les données sont un champ obligatoire lors de l’utilisation d’action=delete-field »** : les actions JSON delete-field doivent spécifier les champs à supprimer dans le champ `"data"`.
* **« Les données ne doivent pas être présentes lors de l’utilisation d’action=delete-key »** : les actions de suppression JSON ne peuvent pas inclure un champ de `"data"`.
* **« Encodage non pris en charge »** : utilisez uniquement les valeurs de codage prises en charge dans le champ `"enc"` (utf8, UTF8, latin1, LATIN1).
* **Syntaxe JSON non valide** : assurez-vous que le fichier JSON est formaté correctement, en respectant les conventions JSONL. Recherchez également une mise en forme JSON générale, des guillemets manquants, des virgules, des crochets, etc.

### Erreurs de limite de taille

* **« La clé dépasse la taille maximale »** : les clés individuelles ne peuvent pas dépasser 255 octets.
* **« La valeur de la colonne dépasse la taille maximale »** : les valeurs de classification individuelles ne peuvent pas dépasser 255 octets.

## Bonnes pratiques

* **Taille du fichier** : 50 Mo est la taille de fichier maximale pour les chargements de navigateur et d’API.
* **Traitement par lots** : pour les jeux de données volumineux, envisagez de diviser en fichiers plus petits.
* **Validation des données** : testez un petit fichier d’exemple avant de charger des jeux de données volumineux.
* **Sauvegarde** : conservez des copies de vos fichiers de données sources.
* **Mises à jour incrémentielles** : utilisez le format JSON pour un contrôle précis des mises à jour et suppressions d’enregistrements individuels.
