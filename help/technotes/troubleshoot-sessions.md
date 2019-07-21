---
title: Dépannage des sessions dans Adobe Analytics
description: Découvrez comment résoudre les problèmes liés à la déconnexion d'Adobe Analytics.
seo-title: Dépannage des sessions dans Adobe Analytics
seo-description: Découvrez comment résoudre les problèmes liés à la déconnexion d'Adobe Analytics.
translation-type: tm+mt
source-git-commit: b5e3801454dafbcc47b93e65f8b5e7c59c3a8081

---


# Dépannage des sessions dans Adobe Analytics

Cette page traite de la résolution des problèmes, ce qui signifie que vous êtes en mesure de vous connecter avec succès, mais que vous êtes en mesure de rester connecté. If you are having issues logging in to Adobe Analytics, see [Troubleshoot logging in to Adobe Analytics](troubleshoot-login.md).

Presque tous les problèmes liés aux sessions proviennent du réseau d'entreprise personnalisé d'une organisation. Si vous pouvez vous connecter à Adobe Analytics mais que vous rencontrez des problèmes pour rester connecté, utilisez cet article pour vous aider à déterminer la cause.

## Déterminer si le problème est dû au réseau de votre entreprise

De nombreuses organisations déploient des fonctions réseau supplémentaires pour renforcer la sécurité, comme les serveurs proxy ou les pare-feu. Ces personnalisations peuvent parfois interférer avec la possibilité de conserver une session active dans Adobe Analytics.

Pour déterminer si le réseau d'entreprise auquel vous êtes connecté génère des problèmes lors de l'utilisation d'Adobe Analytics, utilisez vos identifiants de connexion Experience Cloud sur un périphérique en dehors de votre réseau d'entreprise. Les exemples d'appareils peuvent provenir de votre réseau domestique ou du plan de données d'un périphérique mobile. Si vous êtes en mesure de passer d'une page à une autre sans être déconnecté, le réseau de votre entreprise est probablement la raison pour laquelle vous êtes déconnecté d'Adobe Analytics.

## Problèmes dus au regroupement d'adresses IP

Certains réseaux utilisent une pratique appelée pool d'adresses IP, où l'adresse IP d'un périphérique peut fréquemment changer dans une plage utilisée par l'organisation. Dans le cadre des pratiques de sécurité d'Adobe, si une adresse IP change de mid-session, cette session est expirée.

Si votre organisation utilise le regroupement d'adresses IP, suivez les instructions ci-dessous pour que vos plages d'adresses IP soient ajoutées à la liste blanche d'Adobe :

1. Demandez à l'équipe informatique de votre organisation d'obtenir la liste des plages d'adresses IP utilisées dans votre organisation.
2. Demander à un délégué d'assistance clientèle de contacter le service à la clientèle Adobe et fournir à Adobe les plages d'adresses IP
3. L'agent saisit les plages d'adresses IP dans une liste blanche afin d'empêcher les sessions d'expirer si les deux adresses se trouvent dans les plages fournies.

## Problèmes dus à un proxy

Adobe utilise un en-tête d'autorisation lors de la création de requêtes à Adobe. Certains doublures, comme le Bluecoat (désormais détenu par Symantec), éliminent les informations essentielles d'en-tête d'autorisation utilisées par Adobe Analytics. Lorsqu'Adobe ne voit pas l'en-tête d'autorisation, la session expire.

Pour résoudre ce problème, Adobe conseille de travailler avec l'équipe informatique de votre organisation pour autoriser l'en-tête d'autorisation par le biais du proxy de votre organisation.

> [!NOTE] Remarque
>
> Bien que les membres de la communauté Analytics trouvent les liens suivants utiles, ils ne sont pas détenus par Adobe. Tenez compte de cette remarque lorsque vous consultez leur contenu.

Vous trouverez des informations sur les serveurs proxy et les en-têtes Symantec à l'adresse suivante :

* [Configuration de l'authentification par proxy en amont dans un déploiement en chaîne proxy sur un proxysg ou un appareil ASG](https://support.symantec.com/en_US/article.TECH246122.html)
* [Autoriser proxysg à transférer toujours l'autorisation du serveur en amont](https://support.symantec.com/en_US/article.TECH244708.html)
