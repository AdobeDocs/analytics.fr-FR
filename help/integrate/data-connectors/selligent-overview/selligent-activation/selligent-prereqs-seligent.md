---
description: Répertorie les informations nécessaires à la fourniture de votre compte Selligent avant de pouvoir déployer l'intégration.
seo-description: Répertorie les informations nécessaires à la fourniture de votre compte Selligent avant de pouvoir déployer l'intégration.
seo-title: Conditions préalables pour Selligent
solution: Analytics
title: Conditions préalables pour Selligent
uuid: 3 a 43 a 1 c 0-5 f 51-4 bc 8-b 6 b 9-0 c 46 aa 00 ba 9 f
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Prerequisites for Selligent{#prerequisites-for-selligent}

Répertorie les informations nécessaires à la fourniture de votre compte Selligent avant de pouvoir déployer l'intégration.

**Compte Selligent valide**

Pour utiliser cette intégration de Connecteurs de données, vous devez disposer d'un compte Selligent valide.

**Informations du compte**

Vous aurez besoin des informations suivantes sur votre compte Selligent pendant cette configuration de l'intégration :

* **URL du service Adobe**:

   L'URL peut être dérivée de l'URL utilisée pour se connecter à la solution Selligent Marketing. Remplacez la partie « /simweb/login. aspx » de l'URL par « /automation/omniture. asmx ».

   Par exemple : http://<client-specific install url>/automation/omniture.asmx

* **Paramètres de chaîne de requête :** Elles sont ajoutées dans l'URL de la page d'entrée pour l'ID de message et l'ID de destinataire (identifiant visiteur). Il s'agit toujours de MID et de RID pour l'ID de message et l'ID de destinataire.

* **Jeton d'intégration** Lancez l'outil Gestionnaire depuis le Web et accédez **[!UICONTROL à Configuration]** &gt; Paramètres **[!UICONTROL système]** &gt; Onglet **[!UICONTROL Général]** &gt; **[!UICONTROL Système]**. Under **[!UICONTROL Security]**, you can find the Integration token.

   ![](assets/selligent-integration_token.png)

