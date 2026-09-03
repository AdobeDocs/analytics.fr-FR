---
title: Sessions de dépannage dans Adobe Analytics
description: Découvrez comment résoudre les problèmes liés à la déconnexion d’Adobe Analytics.
feature: Analytics Basics
exl-id: 191250ef-8313-47be-9717-046cce870998
TQID: https://experienceleague.adobe.com/b8dTBhP3a6FZSmABKtQKTp9XkmYIjfS5--Vbzl6xRGE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: a421fb65-2c82-457a-921c-28c46b697a39
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 367
ht-degree: 80%

---

# Sessions de dépannage dans Adobe Analytics

Cette page traite des sessions de dépannage dans le cas où vous parvenez à vous connecter, mais ne réussissez pas à le rester. Si vous rencontrez des difficultés pour vous connecter à Adobe Analytics, voir [Dépannage de la connexion à Adobe Analytics](troubleshoot-login.md).

Presque tous les problèmes liés aux sessions sont liés à un réseau d’entreprise personnalisé. Si vous parvenez à vous connecter à Adobe Analytics mais pas à rester connecté, utilisez cet article pour déterminer la cause.

## Problèmes liés au réseau de votre entreprise {#network}

De nombreuses entreprises déploient des fonctionnalités réseau supplémentaires pour améliorer la sécurité, telles que des serveurs proxy ou des pare-feu. Ces personnalisations peuvent parfois interférer avec la possibilité de conserver une session active dans Adobe Analytics.

Pour déterminer si le réseau d’entreprise auquel vous êtes connecté pose des problèmes d’utilisation d’Adobe Analytics, utilisez vos identifiants de connexion CX Enterprise sur un appareil situé en dehors du réseau de votre entreprise. Vous pouvez par exemple utiliser votre réseau domestique ou le forfait de données d’un appareil mobile. Si vous parvenez à passer d’une page à l’autre sans être déconnecté, c’est probablement le réseau de votre entreprise qui vous déconnecte d’Adobe Analytics.

## Problèmes liés au proxy {#proxy}

Adobe utilise un en-tête d’autorisation lors de l’envoi de requêtes à Adobe. Certains proxys, tels que Edge Secure Web Gateway (anciennement Bluecoat), suppriment les informations dʼen-tête dʼautorisation importantes utilisées par Adobe Analytics. La session expire si Adobe ne voit pas l’en-tête d’autorisation.

Pour résoudre ce problème, Adobe conseille de travailler avec l’équipe informatique de votre entreprise afin d’autoriser l’en-tête d’autorisation via le proxy de votre entreprise.

>[!NOTE]
>
>Bien que les membres de la communauté Analytics aient trouvé les liens suivants utiles, ils ne sont pas la propriété d’Adobe. Tenez compte de cette remarque lorsque vous affichez leur contenu.

Vous trouverez des informations sur les serveurs proxy et les en-têtes d’authentification à l’adresse suivante :

* [Configuration de l’authentification du proxy amont dans un déploiement de chaînes de proxy sur un appareil ProxySG ou ASG](https://techdocs.broadcom.com/us/en/symantec-security-software/web-and-network-security/edge-swg/7-3/authentication_co.html)
* [Comment transférer les informations d&#39;identification utilisateur vers un serveur derrière l&#39;appliance ProxySG](https://knowledge.broadcom.com/external/article/165859/how-to-forward-user-credentials-to-a-ser.html)
