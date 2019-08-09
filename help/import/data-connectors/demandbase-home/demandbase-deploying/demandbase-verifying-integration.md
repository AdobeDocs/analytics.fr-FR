---
description: Validez que l'intégration capture correctement les données en vérifiant le suivi et la création de rapports en direct.
seo-description: Validez que l'intégration capture correctement les données en vérifiant le suivi et la création de rapports en direct.
seo-title: Vérification de l'intégration
title: Vérification de l'intégration
uuid: a 9 a 0746 a -4845-41 ae -919 e-e 85 d 95 c 305 be be
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Vérification de l'intégration{#verifying-the-integration}

Validez que l'intégration capture correctement les données en vérifiant le suivi et la création de rapports en direct.

## Suivi en direct {#section-9c20e8ff6b404ae09387ee07d675c9e2}

Utilisez l'outil digitalpulse Debugger pour vérifier que les données de dimension Demandbase sont envoyées à Adobe Analytics. Après avoir supprimé vos cookies, rechargez une page de votre site Web où le code d'intégration a été déployé. En supposant que votre IP actuelle mappe vers une organisation reconnue par Demandbase, les résultats sont normalement semblables à ceux de la suivante.

**Rapports et analyses (anciennement sitecatalyst) comprend les deux variables de données contextuelles Demandbase :**

![](assets/debugger1.png)

** La mbox Target comprend les paramètres Demandbase Profile : **

Vous n'y voyez que si Target est implémenté sur la page ET que cette intégration est configurée pour Adobe Target - voir l'étape 4 de l'assistant d'intégration Adobe.

![](assets/debugger2.png)

## Création de rapports {#section-1792fe75dc3249d0ad063dfd87a89162}

Examinez vos rapports Demandbase dans Adobe Analytics à l'aide du tableau de bord qui a été automatiquement créé à l'aide de l'assistant d'intégration Adobe (étape 7).

Vous pouvez également accéder aux rapports Demandbase dans la structure de menu d'Adobe Analytics - voir captures d'écran ci-dessous.

>[!NOTE]
>
>Ces données doivent apparaître dans les 24 à 48 heures suivant le déploiement réussi.

![](assets/reporting1.png)

![](assets/reporting2.png)

## Questions fréquentes {#section-d926b160a2ef4f07b43ea1bc67ac2a0a}

**Que signifie « [n/a] » ?**

Le Connecteur de données Demandbase indique quand un attribut est « Non disponible » en définissant cette valeur par défaut. Il existe deux scénarios courants dans lesquels la valeur par défaut est définie :

* Demandbase détecte que le visiteur provient d'une adresse IP qui n'appartient pas à une société.
* Un attribut de contrôle de compte (commençant par « watch_ list ») est utilisé, mais la société ne figure pas dans votre liste de contrôle de compte.

** Pourquoi « [n/a] » apparaît-il plus souvent pour certains attributs ? **

Demandbase classe toutes les adresses IP et fournit les attributs audience et audience_ segment même lorsque le visiteur ne provient pas d'une IP d'entreprise. Lorsque l'audience renvoie des valeurs telles que « Résidence », « Sans fil » et « Hébergement », le reste des attributs ne sont probablement pas disponibles.

Parfois, le public d'un visiteur sera « SMB », mais d'autres attributs afficheront « [n/a] ». Cela signifie que Demandbase est en mesure de classer le visiteur comme une petite activité, mais que le profil complet de l'entreprise n'est pas disponible. Cela survient généralement pour les plus petites entreprises, lorsque plusieurs petites entreprises utilisent le même fournisseur de services ou le même bloc d'adresses IP.

## Considérations sur les développeurs {#section-d33fff55bc4b4db99f82dee418ef1bc2}

Si vous devez ajuster la valeur par défaut dans votre implémentation, mettez à jour la ligne :

```
_db._nonOrgMatchLabel = "[n/a]";
```

