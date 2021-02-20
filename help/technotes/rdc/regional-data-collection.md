---
title: Collecte de données régionales
description: Informations sur la collecte de données régionales
translation-type: tm+mt
source-git-commit: 731209e28dab9f17e06948614149a4c99938fdae
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 57%

---


# Collecte de données régionales

Adobe Experience Cloud utilise la collecte de données régionales (RDC) afin que les interactions entre vos utilisateurs finaux et Adobe Experience Cloud se produisent le plus près possible de vos utilisateurs finaux. Cela améliore les performances du site ou de l’application et garantit que les données sont collectées le plus vite possible pour optimiser l’expérience de l’utilisateur final. Une fois que les données issues des propriétés numériques sont collectées au niveau régional dans un centre de collecte de données, elles sont transférées au moyen d’une connexion sécurisée à un centre de traitement de données, où elles sont traitées et mises à la disposition des produits dans Adobe Experience Cloud.

>[!IMPORTANT]
>
>Le package d’Ajoute-on China RDC (China Performance Optimization) est un module complémentaire payant pour Adobe Analytics. L&#39;optimisation des performances de l&#39;Adobe en Chine continentale permet aux clients en Chine d&#39;envoyer directement des données au noeud de périphérie de la Chine, plutôt qu&#39;à d&#39;autres emplacements à l&#39;échelle mondiale. Ceci améliore les temps de chargement des pages et la précision des données lors de l’envoi des données vers des noeuds en dehors de la Chine. Pour plus d&#39;informations, contactez votre représentant commercial d&#39;Adobe.

La collecte de données régionale inclut les emplacements suivants (sujets à modification) :

## Collecte de données HTTP et tierces

| Type de collecte de données régionale | Centres de collecte de données |
|---------------------|-------------------|
| Par défaut | Oregon, Virginie, Irlande, Paris, Mumbai, Singapour, Tokyo, Sydney, Chine* |

Remarque : Si votre demande d’image Analytics est envoyée aux points de terminaison `adobedc`, `2o7.net` ou `omtrdc.net`, vous disposez d’une collecte de données tierce. Vous pouvez le déterminer si vous voyez l’un des terminaux présents dans l’URL de vos requêtes.

*La collecte de données régionale pour la Chine nécessite le paquet Ajoute-On pour la Chine. Consultez la note &quot;Important&quot; ci-dessus.

## Collecte de données HTTPS propriétaires

| Type de collecte de données régionale | Centres de collecte de données |
|---------------------|-------------------|
| Mondiale (par défaut) | Oregon, Virginie, Irlande, Paris, Mumbai, Singapour, Tokyo, Sydney |
| Amériques uniquement | Oregon, Virginie |
| Europe uniquement | Irlande, Paris |
| Asie-Pacifique uniquement | Mumbai, Singapour, Tokyo, Sydney |
| Chine uniquement* | Pékin |

*La collecte de données régionale pour la Chine nécessite le paquet Ajoute-On pour la Chine. Consultez la note &quot;Important&quot; ci-dessus.

Remarque : Experience Edge Global offre les meilleures performances pour vos utilisateurs finaux.  Si vous souhaitez utiliser un autre type de CRD, contactez le service à la clientèle Adobe pour obtenir de l’aide.

## Avantages de la collecte de données régionale

| Avantage | Description |
| --- | --- |
| Performances | Avec la collecte de données régionale, vos visiteurs se connecteront au CDC le plus proche. Cela permet de disposer du temps de réponse le plus rapide, ce qui permet un suivi plus précis et des temps de chargement plus rapides. |
| Redondance | En cas de rupture de la communication avec un CDC, la collecte de données est automatiquement acheminée vers le CDC le plus proche, assurant ainsi la continuité de service. |
| Redondance | En cas de rupture de la communication entre le DCC et votre DPC, l’infrastructure de CRD de l’Adobe économise les données localement, puis les transfère au DPC lorsque les communications sont rétablies. |

## Fonctionnement de la collecte de données régionale

La liste suivante décrit le processus de collecte de données utilisé par Adobe :

1. Le DNS résout automatiquement le nom d’hôte de la collecte à l’adresse IP du centre de collecte de données le plus proche du visiteur.
1. Le visiteur envoie les données à cet emplacement.
1. Les données sont immédiatement transférées au moyen d’une connexion sécurisée à un centre de traitement de données, où elles sont traitées et mises à la disposition des produits dans Adobe Experience Cloud.
