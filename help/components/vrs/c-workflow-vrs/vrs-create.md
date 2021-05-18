---
description: Avant de créer des suites de rapports virtuelles, vous devez tenir compte des quelques points suivants.
keywords: Suite de rapports virtuelle
title: Création des suites de rapports virtuelles
feature: Concepts de base de Reports & Analytics
uuid: 022a6656-808e-4c92-b7ec-4d2a42e84fa8
exl-id: 5ff6ff1a-5b99-41cc-a3a7-928197ec9ef9
source-git-commit: 20bd38fc38fb14d724603b492bf093d313acbb7d
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 73%

---

# Création des suites de rapports virtuelles

Avant de créer des suites de rapports virtuelles, vous devez tenir compte des quelques points suivants.

* Les utilisateurs qui ne sont pas administrateurs ne peuvent pas visualiser le Gestionnaire de suites de rapports virtuelles.
* Les suites de rapports virtuelles ne peuvent pas être partagées. Le « partage » est effectué par le biais de groupes/autorisations.
* Dans le Gestionnaire de suites de rapports virtuelles, vous ne pouvez afficher que vos propres suites de rapports virtuelles. Vous devez cliquer sur « Tout afficher » pour afficher les suites de rapports virtuelles des autres utilisateurs.

1. Accédez à **[!UICONTROL Composants]** > **[!UICONTROL Suites de rapports virtuelles]**.
1. Cliquez sur **[!UICONTROL Ajouter +]**.

   ![](assets/new_vrs.png)

## Définir les paramètres

Dans l&#39;onglet [!UICONTROL Paramètres], définissez ces paramètres, puis cliquez sur **[!UICONTROL Continuer]**.

| Élément | Description |
| --- |--- |
| Nom | Le nom de la suite de rapports virtuelle n’est pas hérité de la suite de rapports parente et doit être distinct. |
| Description | Ajoutez une description précise pour les utilisateurs d’entreprise. |
| Balises | Vous pouvez ajouter des balises pour organiser vos suites de rapports. |
| Source | Suite de rapports à partir de laquelle cette suite de rapports virtuelle hérite des paramètres suivants. La plupart des niveaux de service et des fonctionnalités (par exemple, les paramètres eVar, les règles de traitement, les classifications, etc.) sont hérités. Pour apporter des modifications à ces paramètres hérités sur une suite de rapports virtuelle, vous devez modifier la suite de rapports parente (Administration > Suites de rapports). |
| Fuseau horaire | Le choix d’un fuseau horaire est facultatif. Si vous choisissez un fuseau horaire, il est enregistré avec la suite de rapports virtuelle. Si aucun fuseau horaire n’est choisi, celui de la suite de rapports parente est utilisé.  Lors de la modification d’une suite de rapports virtuelle, le fuseau horaire enregistré avec la suite de rapports virtuelle apparaît dans le sélecteur déroulant. Si la suite de rapports virtuelle a été créée avant l’ajout de la prise en charge du fuseau horaire, le fuseau horaire de la suite de rapports parente s’affiche dans la liste de sélection déroulante. |
| Segments | Vous pouvez ajouter un seul segment ou empiler des segments.   Remarque : Lors de l’empilement de deux segments, ils sont associés par une instruction AND, qui ne peut pas être changée en instruction OR. Lorsque vous essayez de supprimer ou de modifier un segment qui est actuellement utilisé dans une suite de rapports virtuelle, un avertissement s’affiche. |

## Définir la définition de visite

Dans l&#39;onglet [!UICONTROL Définition de visite], définissez ces paramètres, puis cliquez sur **[!UICONTROL Continuer]**.

![](assets/visit-definition.png)

| Élément | Description |
| --- |--- |
| **Configurer la définition de visite** |  |
| Mettre en place le traitement de la période de rapport | Utilisez le traitement de la période de rapport pour modifier la longueur par défaut du délai d’expiration de la visite. Ces paramètres sont non destructifs et s’appliquent à Analysis Workspace uniquement. [En savoir plus](/help/components/vrs/vrs-report-time-processing.md) |
| Délai de visite | Définit la quantité d’inactivité qu’un visiteur unique doit atteindre avant qu’une nouvelle visite soit automatiquement démarrée. Cette option concerne la mesure des visites, le conteneur de segment de visite et les eVar qui expirent lors de la visite. |
| Commencer une nouvelle visite avec l’événement | Démarre une nouvelle session quand un des événements spécifiés est déclenché, qu’une session ait expiré ou non. |
| **Paramètres de visite des applications mobiles** | Modifiez la façon dont les visites sont définies pour les résultats d’applications mobiles collectés par les Mobile SDK d’Adobe. Ces paramètres ne sont pas destructifs et s’appliquent dans Analysis Workspace uniquement. |
| Empêcher les résultats d’arrière-plan de démarrer une nouvelle visite | Empêche les résultats d’arrière-plan de démarrer une nouvelle visite et de gonfler les visites et les mesures de visiteurs uniques. |
| Démarrer une nouvelle visite à chaque lancement d’application | Démarre une nouvelle session lorsqu’une application est lancée. [En savoir plus](/help/components/vrs/vrs-mobile-visit-processing.md) |

## Inclure et renommer des composants

![](assets/components.png)

1. Dans l&#39;onglet [!UICONTROL Composants], cochez la case pour appliquer la curation afin d&#39;inclure, d&#39;exclure et de renommer les composants de cette suite de rapports virtuelle en Analysis Workspace.
Pour plus d’informations sur la gestion des suites de rapports virtuelles, voir [Traitement des composants de suite de rapports virtuelle](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-components.html?lang=en#virtual-report-suites).

1. Faites glisser les composants (dimensions, mesures, segments ou plages de dates) que vous souhaitez inclure dans la suite de rapports virtuelle dans la section [!UICONTROL Composants inclus].

1. Lorsque vous avez terminé, cliquez sur **[!UICONTROL Enregistrer]**.

## Aperçu des données

Sur le côté droit de chaque onglet, vous pouvez prévisualisation le nombre total d’accès, le nombre total de visites et le nombre total de visiteurs dans cette suite de rapports virtuelle par rapport à la suite de rapports d’origine.

## Compatibilité des produits vue

Certaines fonctionnalités des suites de rapports virtuelles ne sont pas prises en charge par tous les produits Adobe Analytics. La liste de compatibilité des produits vous permet de savoir quels produits dans Adobe Analytics sont pris en charge en fonction des paramètres actuels de votre suite de rapports virtuelle.
