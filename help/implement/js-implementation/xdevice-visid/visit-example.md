---
description: Cet exemple présente des appels au serveur émis dans le cadre d’une interaction client type.
keywords: Mise en œuvre d’Analytics
seo-description: Cet exemple présente des appels au serveur émis dans le cadre d’une interaction client type.
seo-title: Exemple de visite
solution: Analytics
subtopic: Visiteurs
title: Exemple de visite
topic: Développeur et mise en œuvre
uuid: bc 5 f 8 f 56-52 e 3-42 d 8-af 1 a -7 f 5 c 7 b 9496 c 0
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Exemple de visite

>[!IMPORTANT]
>
>Cette méthode d&#39;identification des visiteurs sur l&#39;ensemble des périphériques n&#39;est plus recommandée. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Cet exemple présente des appels au serveur émis dans le cadre d’une interaction client type.

| Appel au serveur | Action | Cookie identifiant visiteur | Variable identifiant visiteur | Identifiant visiteur effectif | Numéro de page de la visite | Nombre de visites |
|--- |--- |--- |--- |--- |--- |--- |
| 1 | Un visiteur clique sur un lien contenu dans un courrier électronique marketing et consulte votre site à partir de son ordinateur personnel. Ce visiteur a déjà visité votre site 7 fois auparavant. | 1 | - | 1 | 1 | 8 |
| 2-8 | Consulte 7 autres pages de votre site. | 1 | - | 1 | 2-8 | 8 |
| 9 | Authentifie un ordinateur de bureau. | 1 | CID1 | CID1 | 9 <br>This is CID1&#39;s first hit ever, so it takes over and continues on the visitor profile from Visitor ID 1.</br> | 8 |
| 10 | Visite 1 page supplémentaire. | 1 | CID1 | CID1 | 10 | 8 |
| 11 | Ouvre un site à partir d’un ordinateur portable sur son lieu de travail. Ce visiteur n’a pas visité votre site avant d’utiliser ce périphérique. | 2 | - | 2 | 1 | 1 |
| 12 | Authentifie un ordinateur portable. | 2 | CID1 | CID1 | 1 | 9 |
| 13 | Affiche 1 page supplémentaire. | 2 | CID1 | CID1 | 2 | 9 |