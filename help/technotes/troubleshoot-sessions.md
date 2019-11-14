---
title: Dépannage des sessions dans Adobe Analytics
description: Découvrez comment résoudre les problèmes liés à la déconnexion d’Adobe Analytics.
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Dépannage des sessions dans Adobe Analytics

Cette page traite des sessions de dépannage, ce qui signifie que vous pouvez vous connecter mais que des problèmes restent connectés. Si vous rencontrez des problèmes lors de la connexion à Adobe Analytics, reportez-vous à la section [Dépannage de la connexion à Adobe Analytics](troubleshoot-login.md).

Presque tous les problèmes liés aux sessions proviennent du réseau d’entreprise personnalisé d’une entreprise. Si vous pouvez vous connecter à Adobe Analytics mais que vous rencontrez des difficultés pour rester connecté, utilisez cet article pour déterminer la cause.

## Déterminez si le problème est dû au réseau de votre entreprise.

De nombreuses entreprises déploient des fonctionnalités réseau supplémentaires pour améliorer la sécurité, telles que des serveurs proxy ou des pare-feu. Ces personnalisations peuvent parfois interférer avec la possibilité de conserver une session active dans Adobe Analytics.

Pour déterminer si le réseau d’entreprise auquel vous êtes connecté génère des problèmes lors de l’utilisation d’Adobe Analytics, utilisez vos informations de connexion Experience Cloud sur un périphérique extérieur au réseau de votre entreprise. Vous pouvez, par exemple, utiliser votre réseau domestique ou le plan de données d’un périphérique mobile. Si vous parvenez à passer d’une page à l’autre sans être déconnecté, c’est probablement le réseau de votre entreprise qui vous déconnecte d’Adobe Analytics.

## Problèmes dus au proxy

Adobe utilise un en-tête d’autorisation lors de l’envoi de requêtes à Adobe. Certains serveurs proxy, tels que Bluecoat (désormais détenu par Symantec), dépouillent les informations d’en-tête d’autorisation critiques utilisées par Adobe Analytics. Lorsqu’Adobe ne voit pas l’en-tête d’autorisation, la session expire.

Pour résoudre ce problème, Adobe conseille de travailler avec l’équipe informatique de votre entreprise afin d’autoriser l’en-tête d’autorisation via le proxy de votre entreprise.

> [!NOTE] Bien que les membres de la communauté Analytics aient trouvé les liens suivants utiles, ils ne sont pas la propriété d’Adobe. Tenez compte de cette remarque lorsque vous affichez leur contenu.

Vous trouverez des informations sur les serveurs proxy et les en-têtes d'authentification Symantec à l'adresse suivante :

* [Configuration de l'authentification proxy en amont dans un déploiement de chaîne de proxy sur une appliance ProxySG ou ASG](https://support.symantec.com/en_US/article.TECH246122.html)
* [Permettre à ProxySG de toujours transférer l'autorisation du serveur en amont](https://support.symantec.com/en_US/article.TECH244708.html)
