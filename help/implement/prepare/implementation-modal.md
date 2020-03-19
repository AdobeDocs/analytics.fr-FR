---
title: Fenêtre modale de mise en œuvre
description: Si vous êtes un nouvel utilisateur, découvrez ce que vous devez savoir sur la mise en œuvre d’Adobe Analytics.
translation-type: ht
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# Fenêtre modale de mise en œuvre

<!-- https://activation.adobedtm.com/index.php?redirected=1 -->

La fenêtre modale « Bienvenue dans Adobe Analytics » simplifie le processus de création d’une suite de rapports. Adobe conseille d’utiliser ce processus chaque fois que davantage de suites de rapports sont nécessaires dans votre entreprise.

![Copie d’écran de la fenêtre modale](assets/implementation-modal.png)

## Conditions préalables

Votre Adobe ID doit avoir accès à Adobe Analytics et à Adobe Experience Platform Launch. Si vous n’avez pas accès à Launch, vous pouvez être placé dans une boucle d’authentification où il vous est demandé de vérifier vos informations d’identification indéfiniment. Contactez un administrateur système de votre entreprise pour obtenir l’accès à Launch.

## Accès à la fenêtre modale

Accédez à la fenêtre modale pour créer une suite de rapports à l’aide des étapes suivantes.

1. Connectez-vous à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur l’icône à neuf carrés en haut de l’écran, puis sur [!UICONTROL Adobe Analytics].
3. Si vous n’avez pas encore créé de suite de rapports, la fenêtre modale s’affiche automatiquement. S’il existe une suite de rapports pour cette société de connexion, cliquez sur l’icône Aide en haut à droite, puis sur [!UICONTROL Bienvenue dans Adobe Analytics].

> [!NOTE] L’option [!UICONTROL Bienvenue dans Adobe Analytics] s’affiche uniquement si vous vous connectez via Adobe Experience Cloud. Si vous vous connectez par le biais de domaines hérités, la fenêtre modale n’est pas disponible.

## Création d’une suite de rapports

Cliquez sur le bouton [!UICONTROL Démarrer la configuration] pour lancer le processus de création de la suite de rapports.

![Assistant RS](assets/analytics-implementation-rs-wizard.png)

### Type de propriété

Le type de propriété permet à Adobe de déterminer certains paramètres d’arrière-plan en fonction de l’emplacement de mise en œuvre d’Analytics.

* **Site web** : si vous avez l’intention de mettre en œuvre Adobe Analytics uniquement pour un site web.
* **Application mobile native** : si vous avez l’intention de mettre en œuvre Adobe Analytics uniquement pour une application mobile.
* **Les deux** : si cette suite de rapports contient des données pour un site web et une application mobile.

### Secteurs d’activité

Spécifiez votre modèle d’entreprise principal. Ce paramètre permet à Adobe de préconfigurer certains noms de variable et paramètres en fonction de votre modèle commercial principal.

### Couche de données

Une [couche de données](data-layer.md) désigne un objet JavaScript qui classe toutes les variables utilisées dans votre mise en œuvre dans un seul emplacement utile. Pour plus d’informations, reportez-vous à la section [Couches de données](data-layer.md).

### Référentiel de données

Donnez un nom convivial à votre suite de rapports. L’identifiant de votre suite de rapports (RSID) est généré automatiquement en fonction du nom convivial et du nom de la société de connexion.

### Fuseau horaire

Vérifiez qu’Adobe a détecté le bon fuseau horaire pour la suite de rapports.

### Estimation du nombre de pages vues par jour

Estimez le volume de trafic de votre site web ou de votre application par jour. Ces informations permettent à Adobe d’allouer le montant correct des ressources de traitement à votre suite de rapports.

### Devise de base

Déterminez dans quelle devise la suite de rapports stocke les valeurs monétaires.

> [!IMPORTANT] Veillez à indiquer la devise appropriée, en particulier si vous avez des exigences de création de rapports concernant les recettes. Il est difficile de modifier la devise de base une fois la collecte des données commencée.

## Ressources de mise en œuvre

Une fois la suite de rapports créée, vous disposez de l’une des deux options pour poursuivre votre mise en œuvre :

* **Accéder à Adobe Experience Platform Launch** : vous redirige vers [launch.adobe.com](https://launch.adobe.com) pour configurer votre mise en œuvre et télécharger le code de déploiement. Voir [Mise en œuvre avec Launch](../launch/overview.md). Adobe recommande d’utiliser Launch dans la plupart des cas.
* **Télécharger le code de mise en œuvre** : fournit un lien direct pour télécharger des fichiers JavaScript pour une mise en œuvre manuelle de JavaScript. Voir [AppMeasurement pour JavaScript](../js/overview.md).
