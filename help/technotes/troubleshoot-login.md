---
title: Dépannage de la connexion à Adobe Analytics
description: Etapes à suivre lorsque vous ne pouvez pas vous connecter à Adobe Analytics.
exl-id: e670a043-c55b-4717-9b60-613ea4d04382
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 2%

---

# Dépannage de la connexion à Adobe Analytics

Adobe Analytics utilise plusieurs méthodes d’authentification pour se connecter :

* Adobe ID par l&#39;Experience Cloud
* Identifiant Analytics hérité
* Authentification unique

**Si vous accédez régulièrement à Analytics et que vous rencontrez des problèmes de connexion de manière aléatoire, effacer les cookies et le cache de votre navigateur résout la plupart des problèmes.**

Parfois, des problèmes de disponibilité peuvent affecter la capacité de se connecter. Consultez [status.adobe.com](https://status.adobe.com) pour connaître les incidents en cours. Sinon, utilisez la section appropriée en fonction de la méthode d’authentification de votre entreprise.

## Adobe ID

Résolvez les problèmes liés à la connexion à Adobe Analytics à l’aide de l’Experience Cloud.

1. Accédez à [experience.adobe.com](https://experience.adobe.com). Si vous ne parvenez pas à accéder à ce site, votre entreprise peut ne pas autoriser ce domaine par le biais de votre pare-feu. Contactez l’équipe informatique de votre entreprise pour l’autoriser. Voir [IP et domaines utilisés dans le Adobe Experience Cloud](https://helpx.adobe.com/fr/analytics/kb/adobe-ip-addresses.html) pour obtenir des informations utiles à votre équipe informatique.

2. Authentifier à l’aide de Adobe ID : Cliquez sur **[!UICONTROL Se connecter avec une Adobe ID]**. Si vous ne parvenez pas à vous connecter, doublon vérifiez que votre adresse électronique est correctement saisie. Sinon, cliquez sur **[!UICONTROL Réinitialiser le mot de passe]** et suivez les invites pour réinitialiser votre mot de passe Adobe ID.

3. Accédez à Analytics après l’authentification : Cliquez sur l’icône en forme de 9 grilles en haut à droite, puis sur Analytics. Si vous ne disposez pas de cette option ou si elle est grisée, demandez à un administrateur de produit de votre entreprise de vous assurer que vous disposez des autorisations appropriées pour accéder à Analytics.

## Identifiant Analytics hérité

Un utilisateur de votre organisation peut recevoir l’erreur suivante lorsqu’il tente de se connecter :

*Par mesure de sécurité, ce compte a été verrouillé en raison d’un trop grand nombre d’échecs de connexion.*

Si l’effacement des cookies/du cache du navigateur ne résout pas le problème, demandez à un administrateur Analytics de votre entreprise de réinitialiser le mot de passe de l’utilisateur.

>[!IMPORTANT]
>
>Les étapes suivantes pour réinitialiser le mot de passe d’un utilisateur s’appliquent uniquement aux identifiants Analytics hérités, et non à Adobe ID. Si votre entreprise utilise Adobe ID, vous pouvez gérer les comptes d’utilisateurs à l’adresse [adminconsole.adobe.com](https://adminconsole.adobe.com).

1. Connectez-vous à Adobe Analytics avec un compte doté de droits d’administration.
2. Accédez à **[!UICONTROL Admin]** > **[!UICONTROL Tous les admin]** > **[!UICONTROL Gestion utilisateur]**.
3. Cliquez sur l’onglet **[!UICONTROL Utilisateurs]**, puis sur **[!UICONTROL Modifier]** en regard de l’utilisateur concerné.
4. Remplacez le mot de passe par n’importe quelle valeur et cochez la case **[!UICONTROL Obliger l’utilisateur à changer de mot de passe lors de la prochaine connexion]**.
5. Informer l’utilisateur du nouveau mot de passe.

## Authentification unique

Contactez un administrateur de votre entreprise pour résoudre les problèmes de connexion unique.

## Connexions expirées

Un utilisateur de votre organisation peut recevoir l’erreur suivante lorsqu’il tente de se connecter :

*Erreur : Cette connexion a expiré.*

Cette erreur fonctionne comme prévu. Adobe Analytics permet aux administrateurs de définir une plage de dates valide pour un compte d’utilisateur. Si la date actuelle se trouve en dehors de la plage de dates valide du compte, il n’est pas possible de se connecter. Adressez-vous à un administrateur Analytics de votre entreprise pour étendre la plage de dates valide de la connexion. Le service à la clientèle d’Adobe n’est pas autorisé à modifier les plages de dates de connexion valides pour les comptes d’utilisateurs.

## Autres problèmes de connexion

Si aucune des étapes ci-dessus ne fonctionne, déterminez l’étendue du problème de connexion :

* Le problème se produit-il lors de l’utilisation d’un autre navigateur ou est-il présent dans tous les navigateurs ?
* Le problème se produit-il sur un autre ordinateur du réseau ou sur plusieurs ordinateurs ?
* Essayez de vous connecter en utilisant un autre réseau, tel qu&#39;une connexion aux données mobiles, une bibliothèque ou un réseau domestique. Le problème est-il présent dans tous les réseaux ?

Si le problème est isolé dans votre réseau, demandez à l’équipe informatique de votre entreprise de le résoudre. S’il ne se limite pas à un seul réseau, contactez le service à la clientèle Adobe.
