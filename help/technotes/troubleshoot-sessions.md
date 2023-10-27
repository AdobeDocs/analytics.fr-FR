---
title: Sessions de dépannage dans Adobe Analytics
description: Découvrez comment résoudre les problèmes liés à la déconnexion d’Adobe Analytics.
feature: Analytics Basics
exl-id: 191250ef-8313-47be-9717-046cce870998
source-git-commit: d64f6687dd6e6f688d332926e6d90fa699cac968
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 97%

---

# Sessions de dépannage dans Adobe Analytics

Cette page traite des sessions de dépannage dans le cas où vous parvenez à vous connecter, mais ne réussissez pas à le rester. Si vous rencontrez des difficultés pour vous connecter à Adobe Analytics, voir [Dépannage de la connexion à Adobe Analytics](troubleshoot-login.md).

Presque tous les problèmes liés aux sessions sont liés à un réseau d’entreprise personnalisé. Si vous parvenez à vous connecter à Adobe Analytics mais pas à rester connecté, utilisez cet article pour déterminer la cause.

## Problèmes liés au réseau de votre entreprise

De nombreuses entreprises déploient des fonctionnalités réseau supplémentaires pour améliorer la sécurité, telles que des serveurs proxy ou des pare-feu. Ces personnalisations peuvent parfois interférer avec la possibilité de conserver une session active dans Adobe Analytics.

Pour déterminer si le réseau d’entreprise auquel vous êtes connecté engendre des problèmes lors de l’utilisation d’Adobe Analytics, utilisez vos informations de connexion Experience Cloud sur un appareil extérieur au réseau de votre entreprise. Vous pouvez par exemple utiliser votre réseau domestique ou le forfait de données d’un appareil mobile. Si vous parvenez à passer d’une page à l’autre sans être déconnecté, c’est probablement le réseau de votre entreprise qui vous déconnecte d’Adobe Analytics.

## Problèmes liés au proxy

Adobe utilise un en-tête d’autorisation lors de l’envoi de requêtes à Adobe. Certains proxys, tels que Edge Secure Web Gateway (anciennement Bluecoat), suppriment les informations dʼen-tête dʼautorisation importantes utilisées par Adobe Analytics. La session expire si Adobe ne voit pas l’en-tête d’autorisation.

Pour résoudre ce problème, Adobe conseille de travailler avec l’équipe informatique de votre entreprise afin d’autoriser l’en-tête d’autorisation via le proxy de votre entreprise.

>[!NOTE]
>
>Bien que les membres de la communauté Analytics aient trouvé les liens suivants utiles, ils ne sont pas la propriété d’Adobe. Tenez compte de cette remarque lorsque vous affichez leur contenu.

Vous trouverez des informations sur les serveurs proxy et les en-têtes d’authentification à l’adresse suivante :

* [Configurer l’authentification du proxy amont dans un déploiement de chaînes de proxy sur un appareil ProxySG ou ASG](https://techdocs.broadcom.com/us/en/symantec-security-software/web-and-network-security/edge-swg/7-3/authentication_co.html)
* [Comment transférer les informations dʼidentification utilisateur à un serveur situé derrière lʼappliance ProxySG](https://knowledge.broadcom.com/external/article/165859/how-to-forward-user-credentials-to-a-ser.html)
