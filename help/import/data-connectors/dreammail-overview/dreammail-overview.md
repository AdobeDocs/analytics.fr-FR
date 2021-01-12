---
description: Cette intégration des courriers électroniques d’Adobe® Data Connectors™ combine des informations comportementales d’Analytics® avec la solution de marketing par courrier électronique afin de créer un outil puissant permettant de redéfinir la mesure de succès et de cibler les audiences avec des messages plus pertinents.
title: Connecteur de données DreamMail pour Adobe Analytics
uuid: f6c01bf8-4e6a-4163-9d41-f24fb5f06bdc
translation-type: tm+mt
source-git-commit: 3850dc3503ca57ba4f13f0de63e8420e484db501
workflow-type: tm+mt
source-wordcount: '805'
ht-degree: 98%

---


# Connecteur de données DreamMail pour Adobe Analytics {#dreammail-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>Nous mettrons fin à la mise en service de la technologie Adobe Data Connector le 1er août 2021. [En savoir plus...](/help/import/data-connectors/data-connectors-eol.md)

Cette intégration des courriers électroniques d’Adobe® Data Connectors™ combine des informations comportementales d’Analytics® avec la solution de marketing par courrier électronique afin de créer un outil puissant permettant de redéfinir la mesure de succès et de cibler les audiences avec des messages plus pertinents.

La diffusion de messages électroniques pertinents à ces segments de marché peut déboucher sur de nouvelles opportunités de chiffre d’affaires, ce qui entraîne une augmentation des conversions et du chiffre d’affaires parmi les campagnes par e-mail existantes et nouvelles. Par exemple, il a été démontré que la diffusion de messages électroniques pertinents basés sur les produits consultés au cours d’une visite ou laissés dans un panier d’achats abandonné a un impact considérable sur le chiffre d’affaires et un impact minimal sur les coûts, puisque ce procédé tire parti des visiteurs déjà présents sur votre site.

Cette augmentation de l’efficacité marketing est l’un des principaux avantages de l’intégration [!DNL Analytics] avec [!DNL ~Partner~]. En outre, cette intégration synchronise automatiquement les mesures de courrier électronique avec les données [!DNL Analytics] de manière fréquente, chaque heure, pour la création de rapports en boucle fermée.

## Principaux avantages et fonctionnalités {#key-benefits-and-features}

Cette intégration présente les principaux avantages suivants :

* Consolidation des données d’analyse et de marketing par e-mail dans une interface de création de rapports.
* Optimisation des campagnes par e-mail par le biais de conversions et de contributions au chiffre d’affaires et au succès du site.
* Re-commercialisation auprès des segments de marché et visiteurs clés en fonction des segments de marketing dynamique.

## Segments de marketing dynamique {#dynamic-marketing-segments}

Cette intégration comprend les segments de marketing dynamique suivants :

* **Profils d’achat :** augmentez les commandes répétées et la valeur moyenne des commandes grâce à des campagnes ciblées en fonction des habitudes d’achat des visiteurs.
* **Profil comportemental basé sur la consultation de produits/contenu :** atteignez des clients potentiels par le biais de segments marketing basés sur les consultations de produits et la création de profils utilisateur relative à l’accès au contenu.
* **Profil d’abandon de panier :** aidez les visiteurs à devenir des clients grâce à des campagnes ciblées spécialement conçues pour les visiteurs qui hésitent à valider leur panier.
* Les clients peuvent également créer et planifier des segments de remarketing personnalisés spécifiques aux besoins de leurs utilisateurs.

## Avant l’activation {#before-you-activate}

Avant de démarrer l’intégration des Data Connectors pour , remplissez les exigences suivantes :

## Exigences d’Adobe Analytics {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **Spécifique à une suite de rapports :** notez que cette intégration est spécifique à une suite de rapports. Vérifiez que vous avez sélectionné la suite de rapports de votre choix avant d’activer l’intégration.
* **Variables Analytics disponibles et configurées :** cette intégration requiert des événements personnalisés et des eVars personnalisées, ainsi qu’éventuellement des événements supplémentaires et des eVars supplémentaires.

* **Représentant autorisé :** notez que l’activation de cette intégration peut entraîner des frais pour votre entreprise, conformément à votre contrat de service avec Adobe, Inc. ou votre contrat de service avec l’un des partenaires de confiance d’Adobe, le cas échéant. En activant cette intégration, vous déclarez être un représentant autorisé de votre entreprise. À ce titre, votre entreprise accepte de payer les frais, le cas échéant, prévus dans le contrat de service décrit ci-dessus.
* **Data Warehouse™ :** cette intégration requiert l’activation de Data Warehouse pour générer des segments de remarketing. Si vous n’avez pas activé Data Warehouse, contactez Adobe pour plus d’informations.
* **[!DNL ~Partner~] :** l’intégration requiert que nous capturions et stockions une adresse électronique dans une variable Analytics (eVar). Le « [!DNL ~Partner~] » est associé au comportement des visiteurs en aval sur le site (abandons de panier, achats, etc.) qui est transmis au système [!DNL ~Partner~] et peut être utilisé à des fins de remarketing. Dans le cadre du processus de configuration, vous devez identifier une eVar à cet effet lorsque l’assistant vous y invite.
* **Suivi externe :** si vous ne respectez pas actuellement la bonne pratique consistant à activer le suivi externe pour chaque campagne par e-mail envoyée, vous devez le faire pour garantir le succès de l’intégration. Consultez la section [!DNL ~Partner~] ci-dessous pour plus d’informations.
* **Respect de la confidentialité :** vous devez comprendre qu’en activant le suivi des identifiants destinataires ou visiteurs, cette fonctionnalité peut effectuer le suivi des informations d’identification personnelle des visiteurs de votre site. Cela entraîne des répercussions en matière de confidentialité qui nécessitent la mise en œuvre de procédures appropriées par votre organisation, comme la notification et la demande de consentement auprès des visiteurs de votre site.

## Tarifs {#pricing}

Notez que l’activation de cette intégration peut entraîner des frais pour votre entreprise, conformément à votre contrat de service avec Adobe, Inc. ou votre contrat de service avec l’un des partenaires de confiance d’Adobe, selon le cas.

En activant cette intégration, vous déclarez être un représentant autorisé de votre entreprise. À ce titre, votre entreprise accepte de payer les frais, le cas échéant, prévus dans le contrat de service décrit ci-dessus.

### Informations sur les tarifs des prestations d’Adobe {#section-1f4f46c0d969435db57d38c1c310a05a}

Cette intégration peut engendrer des frais récurrents et de mise en œuvre, notamment un coût provenant d’un nombre accru d’appels au serveur générés par cette intégration. Pour de plus amples informations concernant les tarifs, contactez votre gestionnaire de compte Adobe.

### Informations sur les tarifs des prestations ~Partner~ {#section-f8ca71df32224412a5101efb6e356529}

Cette intégration peut engendrer des frais récurrents et de mise en œuvre. Veuillez contacter [!DNL DreamMail] pour plus d’informations sur les tarifs.

## Variables d’intégration Analytics {#analytics-integration-variables}

Cette intégration nécessite que les variables Analytics effectuent le suivi des mesures.

Après avoir identifié l’événement et les eVars à utiliser avec cette intégration, ils doivent être activés dans Analytics Admin Console (voir [Suites de rapports](https://docs.adobe.com/content/help/fr-FR/analytics/admin/manage-report-suites/report-suites-admin.html) pour obtenir des instructions).
