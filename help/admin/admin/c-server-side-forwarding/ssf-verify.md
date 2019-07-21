---
description: Pour vérifier que le transfert côté serveur est correctement activé, vous devez examiner la réponse HTTP provenant de la demande de suivi Analytics. Pour ce faire, utilisez les outils de développement d’un navigateur ou un outil de proxy tel que Charles Web Debugger. Les instructions suivantes illustrent les indicateurs qui doivent être présents pour garantir que le transfert côté serveur est correctement activé.
seo-description: Pour vérifier que le transfert côté serveur est correctement activé, vous devez examiner la réponse HTTP provenant de la demande de suivi Analytics. Pour ce faire, utilisez les outils de développement d’un navigateur ou un outil de proxy tel que Charles Web Debugger. Les instructions suivantes illustrent les indicateurs qui doivent être présents pour garantir que le transfert côté serveur est correctement activé.
seo-title: Vérification de la mise en œuvre du transfert côté serveur
solution: Audience Manager
title: Vérification de la mise en œuvre du transfert côté serveur
uuid: e 37296 cc -0120-486 a-a 4 ca -78 d 648 cf 6 a 11
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Vérification de la mise en œuvre du transfert côté serveur

Pour vérifier que le transfert côté serveur est correctement activé, vous devez examiner la réponse HTTP provenant de la demande de suivi Analytics. Pour ce faire, utilisez les outils de développement d’un navigateur ou un outil de proxy tel que Charles Web Debugger. Les instructions suivantes illustrent les indicateurs qui doivent être présents pour garantir que le transfert côté serveur est correctement activé.

Pour vérifier l’état du transfert côté serveur :

1. Chargez une page de test contenant le code AppMeasurement mis à jour.
1. Dans les outils de débogage de votre navigateur ou en utilisant un logiciel de proxy, examinez la réponse HTTP provenant de la demande de suivi d’Analytics (vous pouvez facilement la filtrer en sélectionnant un chemin d’accès contenant "b/ss").
1. Examinez la réponse HTTP. Si la réponse contient des données Audience Manager (comme illustré ci-dessous), le transfert côté serveur fonctionne.

![](assets/ssf-succeed.png)

>[!CAUTION]
>
>If the response contains the key value pair `"status":"SUCCESS"` or a 2 x 2 image, then server-side forwarding * is not* configured correctly. Assurez-vous que le service d'identité est correctement déployé, que vous avez déployé le module App Measurement, que la suite de rapports appropriée a été mappée à l'organisation IMS correcte et que le transfert côté serveur a été activé dans la console d'administration Analytics.

>[!MORE_LIKE_THIS]
>
>* [Charles Web Debugger](https://www.charlesproxy.com/)

