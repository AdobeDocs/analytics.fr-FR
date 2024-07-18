---
title: Résolution des problèmes de connexion à Adobe Analytics
description: Étapes à suivre lorsque vous ne pouvez pas vous connecter à Adobe Analytics.
feature: Analytics Basics
exl-id: e670a043-c55b-4717-9b60-613ea4d04382
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 100%

---

# Résolution des problèmes de connexion à Adobe Analytics

Adobe Analytics utilise plusieurs méthodes d’authentification pour la connexion :

* Adobe ID par le biais d’Experience Cloud
* Identifiant Analytics hérité
* Authentification unique

**Si vous accédez régulièrement à Analytics et que vous rencontrez soudain des problèmes de connexion de manière aléatoire, effacer les cookies et vider le cache de votre navigateur résout la plupart des problèmes.**

Parfois, des problèmes de disponibilité peuvent affecter les capacités de connexion. Consultez [status.adobe.com](https://status.adobe.com) pour connaître les incidents en cours. Sinon, utilisez la section correspond à la méthode d’authentification de votre organisation.

## Adobe ID

Résolvez les problèmes de connexion à Adobe Analytics à l’aide d’Experience Cloud.

1. Accédez à [experience.adobe.com](https://experience.adobe.com). Si vous ne parvenez pas à accéder à ce site, c’est peut-être parce que votre organisation n’autorise pas ce domaine à traverser votre pare-feu. Contactez l’équipe informatique de votre organisation pour l’autoriser. Voir [IP et domaines utilisés dans Adobe Experience Cloud](https://helpx.adobe.com/fr/analytics/kb/adobe-ip-addresses.html) pour obtenir des informations qui seront utiles à votre équipe informatique.

2. Authentification à l’aide d’Adobe ID : cliquez sur **[!UICONTROL Se connecter à l’aide d’un Adobe ID]**. Si vous ne parvenez pas à vous connecter, vérifiez à nouveau que votre adresse e-mail est saisie correctement. Sinon, cliquez sur **[!UICONTROL Réinitialiser le mot de passe]** et suivez les invites pour réinitialiser votre mot de passe Adobe ID.

3. Accès à Analytics après l’authentification : cliquez sur l’icône en forme de grille à 9 cases en haut à droite, puis sur Analytics. Si cette option n’apparaît pas ou si elle est grisée, contactez l’administrateur produit de votre organisation pour vous assurer que vous disposez des autorisations nécessaires pour accéder à Analytics.

## Identifiant Analytics hérité

Un utilisateur de votre organisation peut recevoir l’erreur suivante lorsqu’il tente de se connecter :

*Pour des questions de sécurité, ce compte a été verrouillé en raison d’un trop grand nombre d’échecs de tentatives de connexion.*

Si le problème n’est pas résolu après avoir effacé les cookies et vidé le cache du navigateur, demandez à un administrateur Analytics de votre organisation de réinitialiser le mot de passe de l’utilisateur.

>[!IMPORTANT]
>
>Les étapes suivantes de réinitialisation du mot de passe d’un utilisateur s’appliquent uniquement aux identifiants Analytics hérités, et non aux Adobe ID. Si votre organisation utilise des Adobe ID, vous pouvez gérer les comptes d’utilisateurs à l’adresse [adminconsole.adobe.com](https://adminconsole.adobe.com).

1. Connectez-vous à Adobe Analytics avec un compte doté de droits d’administration.
2. Accédez à **[!UICONTROL Admin]** > **[!UICONTROL Tous les administrateurs]** > **[!UICONTROL Gestion des utilisateurs]**.
3. Cliquez sur l’onglet **[!UICONTROL Utilisateurs]**, puis sur **[!UICONTROL Modifier]** en regard de l’utilisateur concerné.
4. Modifiez le mot de passe en le remplaçant par n’importe quelle valeur, puiss cochez la case **[!UICONTROL L’utilisateur devra changer de mot de passe lors de sa prochaine identification]**.
5. Communiquez le nouveau mot de passe à l’utilisateur.

## Authentification unique

Contactez un administrateur au sein de votre organisation pour résoudre les problèmes d’authentification unique.

## Connexions expirées

Un utilisateur de votre organisation peut recevoir l’erreur suivante lorsqu’il tente de se connecter :

*Erreur : cette connexion a expiré.*

Cette erreur fonctionne comme prévu. Adobe Analytics permet aux administrateurs de définir une période valide pour un compte d’utilisateur. Si la date actuelle se trouve en dehors de la période valide du compte, la connexion s’avère impossible. Demandez à un administrateur Analytics de votre organisation d’étendre la période de connexion valide. L’Assistance clientèle d’Adobe n’est pas autorisée à modifier les périodes de connexion valides pour les comptes d’utilisateurs.

## Autres problèmes de connexion

Si aucune des étapes ci-dessus ne fonctionne, déterminez l’ampleur du problème de connexion :

* Le problème se produit-il lors de l’utilisation d’un autre navigateur ou le rencontrez-vous sur tous les navigateurs ?
* Le problème se produit-il sur un autre ordinateur du réseau ou sur plusieurs ordinateurs ?
* Essayez de vous connecter à l’aide d’un autre réseau, par exemple une connexion aux données mobiles, une bibliothèque ou un réseau domestique. Le problème est-il présent sur tous les réseaux ?

Si le problème est isolé au sein de votre réseau, demandez à l’équipe informatique de votre organisation de le résoudre. S’il ne se limite pas à un seul réseau, contactez l’Assistance clientèle d’Adobe.
