---
description: Découvrez comment définir l’expiration de l’engagement des visiteurs dans les canaux marketing.
subtopic: Marketing channels
title: Expiration du canal marketing
topic: Reports and analytics
uuid: 47f1ccaf-3ce7-494d-b456-956a3a3c6c9a
translation-type: tm+mt
source-git-commit: 46dae8ee28b202578f5ad0c2446b1fd63e5144cc
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 81%

---


# Expiration du canal marketing

Découvrez comment spécifier l’expiration, ou la période d’engagement du visiteur, pour les Canaux marketing.

L’engagement des visiteurs est le délai que vous souhaitez allouer pour que l’activité précédente du visiteur sur votre site soit attribuée au canal Première touche. Le paramètre d’expiration par défaut est réglé sur 30 jours.

Si le visiteur utilise fréquemment le site, la fenêtre d’engagement s’adaptera en fonction. Ils doivent être inactifs pendant 30 jours pour que la période arrive à expiration et que les canaux soient réinitialisés. Les canaux Première touche et Dernière touche d’un visiteur se réinitialisent après 30 jours d’inactivité sur ce navigateur.

Exemple :

* Jour 1 : l’utilisateur accède au site par le biais de l’Affichage. Les canaux Première touche et Dernière touche seront définis sur Affichage.
* Jour 2 : l’utilisateur se rend sur le site par le biais d’une Recherche naturelle. La première touche reste sur Affichage et la dernière touche est définie sur Recherche naturelle.
* Jour 35 : l’utilisateur ne s’est pas rendu sur le site depuis 33 jours et y retourne en utilisant l’onglet qu’il a ouvert dans son navigateur. En supposant une fenêtre d’engagement de 30 jours, la fenêtre se serait fermée et les cookies Marketing Channel auraient expiré. Les canaux Première touche et Dernière touche seront réinitialisés et seront définis sur Actualisation de session puisque l’utilisateur provient d’une URL interne.

## Paramètres d’expiration du canal marketing

Les paramètres d’expiration sont les suivants :

| Champ | Définition |
|--- |--- |
| Jours d’inactivité | Le nombre de jours qui doivent s’écouler avant l’expiration de l’engagement Première touche d’un visiteur. La valeur par défaut est 30. |
| Jamais | La période d’engagement du visiteur n’expire jamais. |
| Réinitialisation de canal | Fait expirer toutes les périodes d’engagement des visiteurs.  Si vous devez réinitialiser toutes les données de canal marketing, vous pouvez mettre fin à toutes les périodes d’activité des visiteurs. Vous devrez peut-être réinitialiser les données si vos règles de traitement étaient incorrectement configurées. Toutes les valeurs de canal Première touche et Dernière touche vont immédiatement expirer et seront réinitialisées au retour des visiteurs. |

## Définir l’expiration du canal marketing {#define-expiration}

Spécifiez la période d’engagement du visiteur.

1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]**.
2. Dans le [!UICONTROL Gestionnaire de suites de rapports], cliquez sur **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Canaux marketing]** > **[!UICONTROL Expiration du canal marketing]**.

   ![](assets/mchannel_expiration.png)

3. Configurez les champs de la période d’engagement du visiteur.
4. Cliquez sur **[!UICONTROL Enregistrer]**.

