---
description: Importation des données de suivi à partir d’applications tierces dans Analytics.
title: Prise en main des connecteurs de données Analytics
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Présentation des connecteurs de données

Adobe fournit aux entreprises des renseignements pratiques en temps réel à propos de leurs stratégies numériques et de leurs initiatives marketing. Les connecteurs de données vous permettent d’importer dans Analytics des données de suivi à partir d’applications tierces, afin que vous puissiez les rassembler et les utiliser dans un emplacement central. Si vous utilisez l’un des produits partenaires, vous pouvez créer une intégration qui importe les données d’application dans les rapports marketing. Après l’intégration, vous pouvez générer des rapports qui incluent des données issues de votre application.

Par exemple, une intégration de courrier électronique peut vouloir utiliser un partenaire de courrier électronique pour distribuer une campagne par courrier électronique. Lorsque des visiteurs se rendent sur votre site Web, vous voulez savoir quels sont ceux qui sont venus en réponse à votre campagne par courrier électronique. Les connecteurs de données intègrent les données de votre partenaire de courrier électronique dans les rapports marketing afin que vous puissiez déterminer ces informations et mesurer l’efficacité de votre campagne par courrier électronique.

**Configuration requise**

Les connecteurs de données doivent s’intégrer de manière appropriée aux navigateurs Web les plus populaires. Toutefois, l’aspect et le fonctionnement des rapports sont meilleurs sur les systèmes ayant la configuration recommandée suivante :

* Navigateur : Microsoft Internet Explorer version 6 et ultérieure
* Cookies : obligatoires
* JavaScript : activé
* Système d’exploitation : Windows
* Macromedia Flash Player : version 6 ou ultérieure
* Résolution de l’écran : 1 024 x 768 (800 x 600 fonctionne aussi)
* Intensité de couleur : 16 bits ou plus

En outre, la collecte de données est plus performante lorsque JavaScript est activé dans le navigateur des utilisateurs.

**Conditions préalables**

Avant de configurer une intégration des connecteurs de données pour votre produit, vous devez vous assurer que les conditions suivantes sont réunies :

* Posséder les informations d’identification nécessaires pour accéder au compte de produit partenaire, avec les autorisations d’accès à toutes les données à intégrer aux rapports marketing. Vous pouvez créer un compte de messagerie spécial pour les distributeurs de rapports, ainsi que pour les notifications relatives aux opérations intégrées.
* Identifier les variables personnalisées qui contiennent les informations sur votre campagne. On parle généralement de code de suivi de campagne, mais une autre terminologie peut être utilisée.
* Déterminer les événements pour lesquels vous souhaitez recevoir des données d’impression et de clic. Vous pouvez renommer les événements en conséquence.
* Placer le code approprié sur votre page d’entrée, afin qu’Analytics puisse procéder à la modélisation appropriée avec les données issues du produit partenaire. Vous trouverez des instructions spécifiques à chaque produit partenaire dans la Présentation des Data Connectors sous l’onglet Ressources.

## Ajout d’une intégration

Vous devez disposer d’un compte actif pour accéder à la page d’entrée [!UICONTROL Data Connectors] (console). Il est également conseillé de connaître Adobe Analytics.

1. Connectez-vous à Adobe Experience Cloud.
1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Administration]** > **[!UICONTROL Data Connectors]**.
1. Cliquez sur **[!UICONTROL Ajouter nouveau]**.
1. Suivez l’interface **[!UICONTROL Ajouter une intégration]**.

   Selon l’intégration du produit individuel, il vous faudra peut-être fournir des informations spécifiques sur la configuration, dans le cadre du processus d’intégration.

   Une fois l’intégration terminée, l’icône du produit partenaire s’affiche sur la page du réseau des Data Connectors ; elle est alors accessible dans les menus.

## Console des Data Connectors

Une fois une intégration activée, elle s’affiche sur la page [!UICONTROL Data Connectors]. Vous pouvez afficher les détails et modifier la configuration sur la console. Vous pouvez afficher les intégrations actives et celles liées à toutes les suites de rapports de votre société. Vous pouvez également afficher un rapport des activités, définir une intégration comme tableau de bord, configurer une intégration et demander de l’aide.

![Console des Data Connectors](assets/data-connectors-console.png)

## Segments de remarketing dans les connecteurs de données

Les segments de remarketing sont des fichiers de données crées selon les variables utilisées dans une intégration des connecteurs de données.

Adobe Analytics vous les envoie via Data Warehouse dans des fichiers quotidiens distincts à un serveur FTP créé par Adobe pour le tiers. Le tiers distribue ensuite ces fichiers au client. Les entreprises utilisent couramment ces fichiers pour les revendre à des personnes qui ont peut-être visité leur site et regardé un produit sans l’acheter. (Vous touchez par exemple un client en offrant une remise sur un produit qu’il a regardé mais qu’il n’a pas acheté).

**Segments**

* [!UICONTROL Abandon de panier] : pourcentage de visiteurs ayant ajouté un article dans le panier sans l’acheter. D’un point de vue technique, il s’agit d’une mesure calculée composée des commandes divisées par les ajouts de panier.
* [!UICONTROL Achats] : identifiants des destinataires (ou identifiants visiteur) ayant effectué des achats selon l’ID de message dans un produit spécifique.
* [!UICONTROL Consultations produits] : il s’agit également d’une mesure calculée similaire aux [!UICONTROL abandons de panier]. Elle indique les [!UICONTROL Consultations produits] divisées par les commandes, puisque les clients qui ont regardé le produit ont manifesté de l’intérêt.

**Exemples de mise en œuvre**

Pour mettre correctement en œuvre les segments de remarketing, les conditions suivantes doivent être remplies :

* Un contrat concernant les connecteurs de données a été établi et votre entreprise a terminé la phase de mise en œuvre avec un consultant Adobe.
* L’événement correspond est déclenché au même moment que la variable des produits :
   * Abandon du panier : événement `scAdd`
   * Achats : événement `purchase`
   * Consultations produits : événement `prodView`

> [!NOTE] Si le produit est défini sans événement associé, l’événement prodView se déclenche automatiquement. Si les conditions ci-dessus ne sont pas remplies, les segments de remarketing correspondant ne sont pas signalés correctement.

[!UICONTROL Abandon de panier] : se déclenche après l’ajout par l’utilisateur d’un produit au panier :

```
s.products=";cat";
s.events="scAdd";
```

[!UICONTROL Achats] : se déclenche sur la page de confirmation d’achat :

```
s.products=";
cat;1;50";
s.events="purchase";
//Note: Though optional, adding the purchaseID variable increases accuracy by preventing duplicate purchases
```

**Problèmes courants**

| Problème | Description |
| -----------| ---------- |  
| Le fichier de segment de remarketing ne contient aucune information d’ID de produit. | Ce problème se produit lorsque l’événement correct se déclenche et qu’aucune variable de produit ne figure dans la même demande d’image. Pour corriger ce problème, vérifiez que la variable de produits et l’événement correspondant se déclenchent sur la même page, comme illustré dans les exemples de mise en œuvre ci-dessus. |
| Les fichiers de segment de remarketing n’ont pas été reçus. | Si vous ne recevez pas les fichiers, demandez à l’un des membre de l’assistance utilisateurs de contacter ClientCare pour rechercher la cause du problème. |


> [!IMPORTANT] Les consultants configurent couramment une demande Data Warehouse en tant que rapport planifié quotidien, en plus du fichier de segment de remarketing de l’intégration des connecteurs de données. Cette demande d’entrepôt de données contient les variables des connecteurs de données ainsi que des variables de connecteurs autres que de données. La demande peut être planifiée selon les besoins spécifiques de votre entreprise. Pour éviter toute confusion lors du dépannage, indiquez si le fichier en question est un fichier de segment de remarketing ou une demande d’entrepôt de données contenant des variables autres que Genesis.
