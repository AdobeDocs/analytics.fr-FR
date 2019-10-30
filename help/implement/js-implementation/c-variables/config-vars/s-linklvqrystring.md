---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.linkLeaveQueryString

Par défaut, les chaînes de requête sont exclues de tous les rapports.

Pour certains liens de sortie et de téléchargement, la partie importante de l’URL peut se trouver dans la chaîne de requête, comme illustré dans l’exemple d’URL ci-dessous.

```js
https://www.mycompany.com/download.asp?filename=myfile.exe
```

Le nom du fichier de téléchargement peut être défini dans la chaîne de requête et, par conséquent, cette dernière est nécessaire pour une meilleure précision du rapport [!UICONTROL Téléchargements de fichiers].

La variable *`linkLeaveQueryString`* détermine si la chaîne de requête doit être incluse dans les rapports [!UICONTROL Liens de sortie] et [!UICONTROL Téléchargements de fichiers].

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|--- |--- |--- |--- |
| N/D | N/D | Téléchargements de fichiers de liens de sortie | false |

> [!NOTE] Si vous définissez `linkLeaveQueryString=true`, tous les paramètres de chaîne de requête sont inclus pour l’ensemble des liens de sortie et de téléchargement.

## du lien personnalisé

```js
s.linkLeaveQueryString=[false/true]
```

## Exemples

```js
s.linkLeaveQueryString=false
```

## Valeurs possibles

```js
s.linkLeaveQueryString=false
```

```js
s.linkLeaveQueryString=true
```

## Paramètres de configuration

Aucune configuration n’est nécessaire pour cette variable.

## Pièges, questions et conseils

* Si vous définissez `s.linkLeaveQueryString=true`, tous les paramètres de chaîne de requête sont inclus pour l’ensemble des liens de sortie et de téléchargement.
* La variable `linkLeaveQueryString` n’a aucune incidence sur les URL de page enregistrées, la mise en correspondance des clics des visiteurs ou les rapports [!UICONTROL Chemin].
