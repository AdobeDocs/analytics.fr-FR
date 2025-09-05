---
description: Pour vérifier que le transfert côté serveur est correctement activé, vous devez examiner la réponse HTTP provenant de la demande de suivi Analytics. Ces instructions indiquent les indicateurs qui doivent être présents pour s’assurer que le transfert côté serveur est correctement activé.
solution: Analytics
title: Comment vérifier l’implémentation du transfert côté serveur
feature: Report Suite Settings
exl-id: 21db4572-da3c-43aa-a774-86a089656695
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 86%

---

# Comment vérifier l’implémentation du transfert côté serveur

Pour vérifier que le transfert côté serveur est correctement activé, vous devez examiner la réponse HTTP provenant de la demande de suivi Analytics. Pour ce faire, utilisez les outils de développement d’un navigateur ou un outil de proxy tel que Charles Web Debugger. Les instructions suivantes indiquent les indicateurs qui doivent être présents pour que le transfert côté serveur soit correctement activé.

Pour vérifier l’état du transfert côté serveur :

1. Chargez une page de test contenant le code AppMeasurement mis à jour.
1. Dans les outils de débogage de votre navigateur ou en utilisant un logiciel de proxy, examinez la réponse HTTP provenant de la demande de suivi d’Analytics (vous pouvez facilement la filtrer en sélectionnant un chemin d’accès contenant &quot;b/ss&quot;).
1. Examinez la réponse HTTP. Si la réponse contient des données Audience Manager (comme illustré ci-dessous), le transfert côté serveur fonctionne.

![](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/assets/ssf-succeed.png)

>[!CAUTION]
>
>Si la réponse contient la paire valeur/clé `"status":"SUCCESS"` ou une image 2 x 2, le transfert côté serveur * n’est pas* configuré correctement. Assurez-vous que le service d’identité est correctement déployé, que vous avez déployé le module App Measurement, que la suite de rapports applicable a été mappée à l’ID dʼorganisation appropriée et que le transfert côté serveur a été activé dans les outils d’administration Analytics.

>[!MORELIKETHIS]
>
>* [Charles Web Debugger](https://www.charlesproxy.com/)
