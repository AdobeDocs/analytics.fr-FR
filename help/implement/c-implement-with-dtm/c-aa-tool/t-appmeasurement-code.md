---
description: Insérez du code AppMeasurement lors du déploiement manuel de Dynamic Tag Management dans Adobe Analytics.
keywords: Gestion dynamique des balises;comptes liés;liaison de comptes;modifier le code;appmeasurement;code appmeasurement
seo-description: Insérez du code AppMeasurement lors du déploiement manuel de Dynamic Tag Management dans Adobe Analytics.
seo-title: Insertion du code AppMeasurement de base
solution: Experience Cloud,Analytics,Target,Gestion dynamique des balises
title: Insertion du code AppMeasurement de base
uuid: 3f83fbb1-3ed5-4e45-888a-0a183aac1a90
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Insertion du code AppMeasurement de base

Insérez du code AppMeasurement lors du déploiement manuel de Dynamic Tag Management dans Adobe Analytics.

1. Dans la page d’outils [!DNL Adobe Analytics], développez la section **Général**, puis cliquez sur **[!UICONTROL Ouvrir l’éditeur]**.
1. Unzip the [!DNL AppMeasurement_JavaScript*.zip] file you downloaded in [deploy Adobe Analytics](../../../implement/c-implement-with-dtm/t-analytics-deploy.md#task_3A00639CADF14C9C844F962222077E4E).

   Si vous avez choisi l’option de bibliothèque personnalisée, la fenêtre contient déjà la version de code la plus récente lorsque vous l’ouvrez. Il n’est pas nécessaire de télécharger le fichier zip à partir d’Admin Console.
1. Open [!DNL AppMeasurement.js] in a text editor.
1. Copy and paste the contents into the **[!UICONTROL Edit Code]** window.

   ![](assets/edit-code.png)

1. Adobe recommande que vous ajoutiez le code suivant au-dessus de *`Do Not Alter Anything Below This Line`*:

   ```
   var s_account="INSERT-RSID-HERE"
   var s=s_gi(s_account)
   ```

   >[!IMPORTANT]
   >
   >If you add this code, it is recommended that you also select the **[!UICONTROL Set report suites using custom code below]** checkbox in the overall library settings.

1. Click **[!UICONTROL Save and Close]**.

   Si vous utilisez le mode Media, le module Integrate ou des plug-ins d’implémentation, vous pouvez également les copier dans la section de code. Dans Dynamic Tag Management, le code géré peut être configuré tout comme le fichier JavaScript dans une mise en œuvre standard.

