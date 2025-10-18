---
title: Identification des visiteurs à l'aide de la bibliothèque JavaScript Web SDK
description: Identifier correctement les visiteurs lors de l’implémentation de la bibliothèque JavaScript Web SDK.
source-git-commit: 3055a76f797438be71e82ea8f73800dc82ff4805
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 0%

---

# Identification des visiteurs à l&#39;aide de la bibliothèque JavaScript Web SDK

Adobe Experience Platform Web SDK (`alloy.js`) offre une approche unifiée et moderne de la collecte de données pour toutes les applications Adobe Experience Cloud, y compris Analytics. Les données d’identité peuvent être étendues pour prendre en charge les identifiants personnalisés et plusieurs espaces de noms à l’aide des `identityMap` XDM. Adobe recommande d’utiliser le service Adobe Experience Cloud ID en tant qu’identifiant principal pour Analytics et d’utiliser d’autres options de gestion des identités pour les scénarios avancés.

Si votre entreprise utilise la bibliothèque JavaScript Web SDK pour envoyer des données à Adobe Analytics, une configuration minimale est requise pour l’identification des visiteurs. Le service d’identification des visiteurs est intégré en mode natif à la bibliothèque, ce qui nécessite uniquement de définir le domaine **[!UICONTROL Edge]** dans la commande `configure`. Si ce champ est défini sur la valeur souhaitée, l’identification des visiteurs fonctionne sans configuration supplémentaire.
