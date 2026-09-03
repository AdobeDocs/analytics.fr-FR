---
title: Création d’un document de conception de solution
description: Découvrez ce qu’est un document de conception de solution et comment l’utiliser dans votre entreprise.
feature: Implementation Basics
exl-id: 0b5c5ddd-5f53-4790-a649-1381135dacda
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/OLSxdEz9--Xe8bCRH6-TimsPloUUdesg4-wrBNL3uPU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 698
ht-degree: 76%

---

# Création d’un document de conception de solution

Un document de conception de solution (également connu sous le nom de document de référence de conception de solution ou de document d’exigences opérationnelles) est essentiellement le plan directeur de votre mise en œuvre d’Analytics. Il définit les critères identifiés par les parties prenantes à l’échelle de votre organisation et les traduit en variables dans Adobe Analytics. Sans lui, les organisations ont du mal à coordonner les besoins en matière de rapports et ont tendance à ne pas collecter certaines données importantes.

## Conditions préalables

[Validez votre mise en œuvre Analytics et publiez-la en production](../launch/validate-publish-prod.md) - Bien qu’elle ne soit pas directement requise, Adobe conseille de mettre en place une mise en œuvre de base afin de collecter des données importantes, tout en définissant et en implémentant d’autres besoins opérationnels.

## Propriété et emplacement du document de conception

* **Déterminez qui, dans votre entreprise, sera responsable de la maintenance du document de conception de solution.** Ce rôle peut être soit une personne, soit une équipe. Assurez-vous que la gestion de la conception de solution est préservée, même après des changements de fonction ou des restructurations de l’organisation. Il s’agit d’un document évolutif qui doit être correctement géré.
* **Déterminez l’emplacement de votre document de solution.** Il n’existe pas d’emplacement idéal pour héberger les documents de conception de solution, mais ils se trouvent généralement dans un emplacement interne largement accessible. Par exemple, une feuille de calcul partagée ou un espace de travail collaboratif comme SharePoint ou un wiki interne. Il n’est pas nécessaire qu’il soit modifiable par tout le monde, mais il est préférable que les personnes qui peuvent accéder à la création de rapports soient au moins autorisées à le consulter.

## Définition des besoins opérationnels

Lors de la détermination des données à collecter, il est facile de dire « tout ». Cependant, cela peut rapidement devenir difficile à gérer, et même être moins bénéfique que de collecter des quantités de données plus raisonnables.

1. **Déterminez vos indicateurs clés de performance.** Que voulez-vous que les visiteurs fassent au bout du compte ? La réponse à cette question varie en fonction du secteur d’activité vertical et peut comporter divers éléments. À titre d’exemple, citons les achats, les enregistrements ou les clics publicitaires.
1. **Identifiez les données les plus importantes à collecter.** Posez les questions commerciales auxquelles vous souhaitez obtenir des réponses spécifiques. Les réponses à ces questions vous donneraient des informations sur la manière d’améliorer vos indicateurs de performances clés.
1. **Répondez à ces questions et déterminez vos besoins en matière de suivi.** Regroupez-les dans des dimensions et des mesures.
   * Les dimensions sont des variables qui contiennent du texte. À titre d’exemple, citons un terme de recherche interne, une catégorie de produit ou le nom d’une section sur laquelle a cliqué un visiteur.
   * Les mesures sont des événements spécifiques que vous souhaitez voir réalisés par un visiteur. Par exemple, lorsqu’il effectue l’action que vous souhaitez, le nombre augmente d’un. À titre d’exemple, citons l’envoi d’une commande, l’inscription à un bulletin d’information ou l’envoi d’une réponse à une enquête.
1. **Mapper des dimensions et des mesures dans une page ou une feuille de calcul.** Cette page ou ce tableau devient finalement votre document de conception de solution. Certaines colonnes ou puces utiles à inclure :
   * Statut d’implémentation : prévu, actif, inactif, problèmes, etc. Cela informerait les observateurs du document sur le statut de la variable, si elle a été implémentée, ou s’il existe des problèmes avec la collecte de données.
   * Nom de la variable : par exemple, « Termes de recherche internes ». Cette valeur correspond à ce que voient les analystes lorsqu’ils travaillent dans Analytics.
   * Variable Analytics associée à : à quelle variable Analytics par défaut ou personnalisée vous choisissez d’affecter des valeurs. Les dimensions dépendent généralement des eVars, tandis que les mesures dépendant des événements.
   * Logique : description de la définition de la variable et de ce qui détermine sa valeur. Par exemple, « Définir uniquement sur des pages de recherche interne. Prend la valeur du paramètre de chaîne de requête q. »
   * Toute autre remarque que vous souhaitez inclure au sujet de la variable.

## Ressources supplémentaires

La définition d’un document de conception de solution est un projet assez complexe, surtout pour les organisations qui n’en avaient pas encore créé. Si vous avez besoin d’une assistance supplémentaire, Adobe fournit des services de conseil spécialisés pour aider votre organisation à exécuter Adobe Analytics. Contactez l’équipe chargée de votre compte Adobe si vous souhaitez faire appel aux services professionnels d’Adobe. Vous pouvez remplir un [questionnaire technique préalable à la mise en œuvre](assets/technical-pre-implementation-questionnaire.pdf) afin qu’Adobe sache exactement comment vous aider en fonction des besoins de votre organisation.

Plusieurs partenaires Adobe se spécialisent également dans la création d’un document de conception de solution, ainsi que dans la mise en œuvre d’Adobe Analytics sur votre site.

## Étapes suivantes

Mettez en œuvre les variables dans votre document de conception de solution.

[Créer une couche de données](data-layer.md) : Traduisez les variables de votre document de conception en variables JavaScript sur votre site.
