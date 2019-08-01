---
description: Après avoir exécuté l'assistant d'intégration, vous devez déployer le code d'intégration dans votre code de déploiement Adobe Analytics (s_ code).
seo-description: Après avoir exécuté l'assistant d'intégration, vous devez déployer le code d'intégration dans votre code de déploiement Adobe Analytics (s_ code).
seo-title: Déploiement du code d'intégration
title: Déploiement du code d'intégration
uuid: b 3 fbda 0 b -4 ed 3-4967-84 ee -6 c 66564606 e 7
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Deploying the Integration Code{#deploying-the-integration-code}

Après avoir exécuté l'assistant d'intégration, vous devez déployer le code d'intégration dans votre code de déploiement Adobe Analytics (s_ code).

>[!NOTE]
>
>Si vous avez utilisé Adobe tagmanager ou la gestion dynamique des balises pour déployer Adobe Analytics, vous pouvez facilement ajouter le code d'intégration à l'aide de l'un de ces outils.

1. Go to the **[!UICONTROL Support]** tab and download and save the `integration code v2_0_1` resource from the Resources area of the integration.

1. If applicable, make any necessary modifications to the code For more information, see [Modifying the Integration Code](../../demandbase-home/demandbase-deploying/demandbase-deploying-integration-code.md#concept-2e9e56282c9940d78e879aa45f70d855).
1. Incluez le module Integrate si celui-ci n'est pas déjà présent dans votre code de déploiement Adobe Analytics. For more information, see [Including the Integrate Module](../../demandbase-home/demandbase-deploying/demandbase-including-integrate-module.md#concept-2cc81dff010a4da89b097a59476f8b6e).
1. Déployez le code à l'aide de l'une des méthodes suivantes :

   * Utilisez Adobe tagmanager ou la gestion dynamique des balises pour ajouter le code.
   * Vous pouvez également diffuser le code à la ressource organisationnelle responsable de la mise à jour du code de déploiement Adobe Analytics.

>[!IMPORTANT]
>
>Assurez-vous de tester le déploiement pour cette intégration dans un environnement de développement/évaluation avant de le déployer dans un environnement de production.

