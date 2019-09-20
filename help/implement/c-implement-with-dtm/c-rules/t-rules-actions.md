---
description: Configuration des actions que la condition doit déclencher.
keywords: Gestion dynamique des balises;règle;créer une règle;nouvelle règle;balises JavaScript/tierces;configurer des actions pour la condition;ajouter un nouveau script;javascript non séquentiel;javascript séquentiel;html non séquentiel
seo-description: Configuration des actions que la condition doit déclencher.
seo-title: Configuration des actions que la condition doit déclencher
solution: Experience Cloud,Analytics,Target,Gestion dynamique des balises
title: Configuration des actions que la condition doit déclencher
uuid: 2e892f0b-7261-41ee-b849-6e3054a38de0
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Configuration des actions que la condition doit déclencher

Configurez les actions de votre choix que la condition doit déclencher.

Une fois la condition configurée, vous devez définir les actions qui doivent être déclenchées par celle-ci. Ces actions peuvent comprendre des événements [!DNL Analytics], des balises ces et des scripts personnalisés. Cet exemple illustre comment configurer des scripts ou des balises ces.

Outre les outils intégrés tels qu’[!DNL Adobe Analytics] et Google Analytics, Dynamic Tag Management peut déclencher tout type de script JavaScript ou injecter du code HTML dans votre site, dans les pages sélectionnées ou des scénarios spécifiques.

Chaque règle peut déclencher autant de scripts ou d’injections HTML que vous le souhaitez.

>[!NOTE]
>
>Because DTM allows you to inject custom code into your page, please take care not to create cross-site scripting (XSS) vulnerabilities (see [OWASP’s guide](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS)) for more info). L’utilisation d’éléments de données dans un script demande une attention toute particulière. Vous devez toujours supposer que les valeurs des éléments de données proviennent d’une source non fiable.

**Pour configurer les actions que la condition doit déclencher**

1. Click **[!UICONTROL JavaScript / Third Party Tags]** to add a new script to your rule.

   ![](assets/scripts-actions.png)

1. Cliquez sur **[!UICONTROL Ajouter un nouveau script]**.

   ![](assets/scripts-actions2.png)

1. Attribuez un nom au script.
1. Indiquez le mode de déclenchement du script, puis collez le contenu souhaité dans la zone de texte. ![](assets/scripts-actions3.png)

1. Click **[!UICONTROL Save Code]**, and the script will be added to the queue for the rule. ![](assets/scripts-actions4.png)

