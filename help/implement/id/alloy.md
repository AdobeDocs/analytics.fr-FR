---
title: Identification des visiteurs à l'aide de la bibliothèque JavaScript Web SDK
description: Identifier correctement les visiteurs lors de l’implémentation de la bibliothèque JavaScript Web SDK.
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 0%

---

# Identification des visiteurs à l&#39;aide de la bibliothèque JavaScript Web SDK

La bibliothèque Adobe Experience Platform Web SDK JavaScript (`alloy.js`) offre une approche unifiée et moderne de la collecte de données pour toutes les applications Adobe Experience Cloud, y compris Adobe Analytics. Bien que la plupart des clients implémentent généralement l’extension de balises [Web SDK](web-sdk-extension.md), vous pouvez utiliser la bibliothèque JavaScript Web SDK seule ou dans un système de gestion des balises tiers. Voir [Alloy](https://github.com/adobe/alloy) sur GitHub pour télécharger la dernière version de la bibliothèque.

Les données d’identité peuvent être étendues pour prendre en charge les identifiants personnalisés et plusieurs espaces de noms à l’aide des `identityMap` XDM. Adobe recommande d’utiliser le service Adobe Experience Cloud ID en tant qu’identifiant principal pour Analytics et d’utiliser d’autres options de gestion des identités pour les scénarios avancés.

Si votre entreprise utilise la bibliothèque JavaScript Web SDK pour envoyer des données à Adobe Analytics, une configuration minimale est requise pour l’identification des visiteurs. Le service d’identification des visiteurs est intégré en mode natif à la bibliothèque, ce qui nécessite uniquement de définir le domaine **[!UICONTROL Edge]** dans la commande `configure`. Si ce champ est défini sur la valeur souhaitée, l’identification des visiteurs fonctionne sans configuration supplémentaire.
