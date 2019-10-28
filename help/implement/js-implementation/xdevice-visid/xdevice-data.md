---
description: Cette section vous explique en quoi l’activation de la fonction d’identification des visiteurs sur plusieurs périphériques affecte les données affichées dans les rapports.
keywords: Mise en œuvre d’Analytics
seo-description: Cette section vous explique en quoi l’activation de la fonction d’identification des visiteurs sur plusieurs périphériques affecte les données affichées dans les rapports.
seo-title: Incidence sur les données de l’identification des visiteurs sur plusieurs appareils
solution: Analytics
subtopic: Visiteurs
title: Incidence sur les données de l’identification des visiteurs sur plusieurs appareils
topic: Développeur et mise en œuvre
uuid: 1db4d149-cd50-4b41-a850-988901f25051
translation-type: ht
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Incidence sur les données de l’identification des visiteurs sur plusieurs appareils

>[!IMPORTANT]
>
>Cette méthode d’identification des visiteurs sur plusieurs appareils n’est plus recommandée. Reportez-vous à la [documentation d’Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/fr_FR/mcdc/).

Cette section vous explique en quoi l’activation de la fonction d’identification des visiteurs sur plusieurs périphériques affecte les données affichées dans les rapports.

Pour comprendre l’incidence de cette fonction sur la collecte de données, il convient de connaître les champs de données du visiteur dans un profil du visiteur :

| Champ de données | Description |
|---|---|
| Cookie identifiant visiteur | ID généré automatiquement lors de la première visite à partir d’un périphérique ou d’un navigateur et stocké dans le cookie `s_vi`. |
| Variable d’identifiant visiteur | [!UICONTROL Identifiant visiteur] facultatif défini lors de l’utilisation de la variable `s.visitorID`. Cette valeur est renseignée dès qu’un utilisateur s’est authentifié et peut correspondre à un ID que votre société utilise pour effectuer le suivi d’un utilisateur sur plusieurs canaux de marketing numérique. |
| Identifiant visiteur effectif | L’[!UICONTROL identifiant visiteur] est l’ID réel du profil utilisateur. Cette valeur est définie sur le cookie [!UICONTROL identifiant visiteur] ou sur la variable d’[!UICONTROL identifiant visiteur], si celle-ci est fournie. |

