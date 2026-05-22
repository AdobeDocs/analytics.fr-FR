---
description: Comment afficher l’utilisation actuelle des appels au serveur dans Adobe Analytics.
title: Affichage de l’utilisation actuelle des appels au serveur
feature: Server Call Usage
exl-id: 07eac732-b9d6-41ab-be34-5688eaa8166e
role: Admin
TQID: 'https://experienceleague.adobe.com/5DgWR4QWklOEMK1Ato17-lcpMdnRgaIrMfds9ATXUpE'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: c9d85838-8d05-4bc7-9f18-30ec779251bc
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 293
ht-degree: 100%

---

# Affichage de l’utilisation actuelle des appels au serveur

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Utilisation de l’appel au serveur]** > **[!UICONTROL Utilisation actuelle]**

>[!IMPORTANT]
>
>L’ensemble des chiffres affichés relatifs à l’utilisation et à l’engagement regroupent toutes vos sociétés de connexion et vos suites de rapports.

Le tableau de bord de l’utilisation actuelle :

* affiche une répartition de votre consommation d’appels au serveur et de votre engagement pour chaque type d’appels au serveur. Cet affichage peut différer en fonction des clients et correspond aux inclusions de votre contrat. Par exemple, vous avez peut-être sélectionné quatre affichages différents : appel au serveur principal et secondaire web et appels au serveur principal et secondaire mobile. Dans ce cas, cet affichage sera composé de quatre onglets, un pour chaque type. Dans chacun de ces onglets, vous pourrez voir la consommation pour la période d’utilisation actuelle ;
* compare l’utilisation actuelle (ligne verte) à votre limite d’utilisation contractuelle (ligne rouge) ;

  ![](/help/admin/tools/server-call-usage/assets/current_period.png)

* compare la période d’utilisation actuelle à celle de l’année précédente (ligne bleue) ; Bien entendu, la ligne bleue n’apparaitra que si votre société possède les données d’utilisation de l’appel au serveur de l’année précédente.

  >[!NOTE]
  >
  >Si vous souhaitez afficher l’utilisation d’une période précédente, vous devez accéder à l’onglet [Suite de rapports d’utilisation](/help/admin/tools/server-call-usage/report-suite-usage.md) et télécharger les données d’utilisation d’une période précédente.

* répertorie le pourcentage d’appels utilisé (en pourcentage et données brutes) et le pourcentage de la période d’utilisation passée (en pourcentage et données brutes) ;
* est, par défaut, mis à jour quotidiennement, avec une latence de traitement de 5 jours ;
* vous permet de réduire et d’étendre tous les rapports.

![](/help/admin/tools/server-call-usage/assets/server_call_dashboard.png)

| Terme de l’interface utilisateur | Définition |
| --- | --- |
| Période d’utilisation actuelle (vert) | La période actuelle est basée sur la [période d’utilisation](/help/admin/tools/server-call-usage/overage-overview.md). |
| Période d’utilisation précédente (bleu) | La période précédente est définie comme la période d’utilisation actuelle moins un an. |
| Limite d’utilisation (rouge) | Votre limite d’utilisation contractuelle pour la période d’utilisation en question. |
