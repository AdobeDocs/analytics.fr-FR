---
description: Cet exemple présente des appels au serveur émis dans le cadre d’une interaction client type.
keywords: Mise en œuvre d’Analytics
seo-description: Cet exemple présente des appels au serveur émis dans le cadre d’une interaction client type.
seo-title: Exemple de visite
solution: Analytics
subtopic: Visiteurs
title: Exemple de visite
topic: Développeur et mise en œuvre
uuid: bc5f8f56-52e3-42d8-af1a-7f5c7b9496c0
translation-type: ht
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Exemple de visite

>[!IMPORTANT]
>
>Cette méthode d’identification des visiteurs sur plusieurs appareils n’est plus recommandée. Reportez-vous à la [documentation d’Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/fr_FR/mcdc/).

Cet exemple présente des appels au serveur émis dans le cadre d’une interaction client type.

| Appel au serveur | Action | Cookie identifiant visiteur | Variable d’identifiant visiteur | Identifiant visiteur effectif | Numéro de page de la visite | Nombre de visites |
|--- |--- |--- |--- |--- |--- |--- |
| 1 | Un visiteur clique sur un lien contenu dans un courrier électronique marketing et consulte votre site à partir de son ordinateur personnel. Ce visiteur a déjà visité votre site 7 fois auparavant. | 1 | - | 1 | 1 | 8 |
| 2-8 | Consulte 7 autres pages de votre site. | 1 | - | 1 | 2-8 | 8 |
| 9 | Authentifie un ordinateur de bureau. | 1 | CID1 | CID1 | 9 <br>Il s’agit du tout premier accès de CID1, qui prend donc le contrôle et continue sur le profil du visiteur portant l’identifiant 1.</br> | 8 |
| 10 | Visite 1 page supplémentaire. | 1 | CID1 | CID1 | 10 | 8 |
| 11 | Ouvre un site à partir d’un ordinateur portable sur son lieu de travail. Ce visiteur n’a pas visité votre site avant d’utiliser ce périphérique. | 2 | - | 2 | 1 | 1 |
| 12 | Authentifie un ordinateur portable. | 2 | CID1 | CID1 | 1 | 9 |
| 13 | Affiche 1 page supplémentaire. | 2 | CID1 | CID1 | 2 | 9 |