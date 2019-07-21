---
description: Cette section vous explique en quoi l’activation de la fonction d’identification des visiteurs sur plusieurs périphériques affecte les données affichées dans les rapports.
keywords: Mise en œuvre d’Analytics
seo-description: Cette section vous explique en quoi l’activation de la fonction d’identification des visiteurs sur plusieurs périphériques affecte les données affichées dans les rapports.
seo-title: Impact des données sur l'identification des visiteurs sur plusieurs périphériques
solution: Analytics
subtopic: Visiteurs
title: Impact des données sur l'identification des visiteurs sur plusieurs périphériques
topic: Développeur et mise en œuvre
uuid: 1 db 4 d 149-cd 50-4 b 41-a 850-988901 f 25051
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Impact des données sur l'identification des visiteurs sur plusieurs périphériques

>[!IMPORTANT]
>
>Cette méthode d'identification des visiteurs sur l'ensemble des périphériques n'est plus recommandée. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Cette section vous explique en quoi l’activation de la fonction d’identification des visiteurs sur plusieurs périphériques affecte les données affichées dans les rapports.

Pour comprendre l’incidence de cette fonction sur la collecte de données, il convient de connaître les champs de données du visiteur dans un profil du visiteur :

| Champ de données | Description |
|---|---|
| Cookie identifiant visiteur | ID généré automatiquement lors de la première visite à partir d’un périphérique ou d’un navigateur et stocké dans le cookie `s_vi`. |
| Variable d’identifiant visiteur | [!UICONTROL Identifiant visiteur] facultatif défini lors de l’utilisation de la variable `s.visitorID`. Cette valeur est renseignée dès qu’un utilisateur s’est authentifié et peut correspondre à un ID que votre société utilise pour effectuer le suivi d’un utilisateur sur plusieurs canaux de marketing numérique. |
| Identifiant visiteur effectif | L’[!UICONTROL identifiant visiteur] est l’ID réel du profil utilisateur. Cette valeur est définie sur le cookie [!UICONTROL identifiant visiteur] ou sur la variable d’[!UICONTROL identifiant visiteur], si celle-ci est fournie. |

