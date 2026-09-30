---
description: Pour vérifier que le transfert côté serveur est correctement activé, vous devez examiner la réponse HTTP provenant de la demande de suivi Analytics. Ces instructions indiquent les indicateurs qui doivent être présents pour s’assurer que le transfert côté serveur est correctement activé.
solution: Analytics
title: Comment vérifier la mise en œuvre du transfert côté serveur
feature: Report Suite Settings
exl-id: 21db4572-da3c-43aa-a774-86a089656695
role: Admin
TQID: 'https://experienceleague.adobe.com/FpB4dk9D87gc24t5KG6WRJ-r8GFOvOEUlRTTjc6XFYI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
subfeature_v2:
  - id: c354699e-6555-4397-8706-1a9a89984069
    internal-label: Server side forwarding
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
    internal-label: Report Suite settings
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 86%
---
# Comment vérifier la mise en œuvre du transfert côté serveur

Pour vérifier que le transfert côté serveur est correctement activé, vous devez examiner la réponse HTTP provenant de la demande de suivi Analytics. Pour ce faire, utilisez les outils de développement d’un navigateur ou un outil de proxy tel que Charles Web Debugger. Les instructions suivantes indiquent les indicateurs qui doivent être présents pour que le transfert côté serveur soit correctement activé.

Pour vérifier le statut du transfert côté serveur :

1. Chargez une page de test contenant le code AppMeasurement mis à jour.
1. Dans les outils de débogage de votre navigateur ou en utilisant un logiciel de proxy, examinez la réponse HTTP provenant de la demande de suivi d’Analytics (vous pouvez facilement la filtrer en sélectionnant un chemin d’accès contenant &quot;b/ss&quot;).
1. Examinez la réponse HTTP. Si la réponse contient des données Audience Manager (comme illustré ci-dessous), le transfert côté serveur fonctionne.

![](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/assets/ssf-succeed.png)

>[!CAUTION]
>
>Si la réponse contient la paire valeur/clé `"status":"SUCCESS"` ou une image 2 x 2, le transfert côté serveur * n’est pas* configuré correctement. Assurez-vous que le Service d’identités est correctement déployé, que vous avez déployé le module App Measurement, que la suite de rapports applicable a été mappée à l’ID dʼorganisation appropriée et que le transfert côté serveur a été activé dans les outils d’administration Analytics.

>[!MORELIKETHIS]
>
>* [Charles Web Debugger](https://www.charlesproxy.com/)
