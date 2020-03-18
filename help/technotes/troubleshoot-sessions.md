---
title: Sessions de dépannage dans Adobe Analytics
description: Découvrez comment résoudre les problèmes liés à la déconnexion d’Adobe Analytics.
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Sessions de dépannage dans Adobe Analytics

Cette page traite des sessions de dépannage dans le cas où vous parvenez à vous connecter, mais ne réussissez pas à le rester. Si vous rencontrez des difficultés pour vous connecter à Adobe Analytics, voir [Dépannage de la connexion à Adobe Analytics](troubleshoot-login.md).

Presque tous les problèmes liés aux sessions sont liés à un réseau d’entreprise personnalisé. Si vous parvenez à vous connecter à Adobe Analytics mais pas à rester connecté, utilisez cet article pour déterminer la cause.

## Problèmes liés au réseau de votre entreprise

De nombreuses entreprises déploient des fonctionnalités réseau supplémentaires pour améliorer la sécurité, telles que des serveurs proxy ou des pare-feu. Ces personnalisations peuvent parfois interférer avec la possibilité de conserver une session active dans Adobe Analytics.

Pour déterminer si le réseau d’entreprise auquel vous êtes connecté engendre des problèmes lors de l’utilisation d’Adobe Analytics, utilisez vos informations de connexion Experience Cloud sur un appareil extérieur au réseau de votre entreprise. Vous pouvez par exemple utiliser votre réseau domestique ou le forfait de données d’un appareil mobile. Si vous parvenez à passer d’une page à l’autre sans être déconnecté, c’est probablement le réseau de votre entreprise qui vous déconnecte d’Adobe Analytics.

## Problèmes liés au proxy

Adobe utilise un en-tête d’autorisation lors de l’envoi de requêtes à Adobe. Certains serveurs proxy, tels que Bluecoat (désormais détenu par Symantec), dépouillent les informations critiques d’en-tête d’autorisation utilisées par Adobe Analytics. La session expire si Adobe ne voit pas l’en-tête d’autorisation.

Pour résoudre ce problème, Adobe conseille de travailler avec l’équipe informatique de votre entreprise afin d’autoriser l’en-tête d’autorisation via le proxy de votre entreprise.

> [!NOTE] Bien que les membres de la communauté Analytics aient trouvé les liens suivants utiles, ils ne sont pas la propriété d’Adobe. Tenez compte de cette remarque lorsque vous affichez leur contenu.

Vous trouverez des informations sur les serveurs proxy et les en-têtes d’authentification Symantec à l’adresse suivante :

* [Configurer l’authentification du proxy amont dans un déploiement de chaînes de proxy sur un appareil ProxySG ou ASG](https://support.symantec.com/en_US/article.TECH246122.html)
* [Autoriser un ProxySG à toujours transférer l’autorisation du serveur en amont](https://support.symantec.com/en_US/article.TECH244708.html)
