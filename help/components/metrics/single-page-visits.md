---
title: Visites sur une seule page (mesures)
description: Le nombre de fois que l’élément de dimension « Page » n’a pas changé au cours d’une visite.
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
TQID: https://experienceleague.adobe.com/iDXuwf-Ls1N7VzmtZiMRISLbSEtHOtDTeoddfDEiAwA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 239
ht-degree: 33%

---

# Visites de page unique

*Cette page d’aide décrit le fonctionnement de la mesure « Visites de page unique ». Pour plus d’informations, consultez la dimension [Visites de page unique](../dimensions/single-page-visits.md).*

La **[!UICONTROL Visites sur une seule page]** [mesure](overview.md) indique le nombre de visites pour lesquelles l’élément de dimension [Page](../dimensions/page.md) ne contenait qu’une seule valeur pour l’ensemble de la visite. Cette mesure est utile pour les dimensions dans lesquelles vous souhaitez consulter des visites de courte durée, mais qui ne comportent pas de règle aussi stricte que les [[!UICONTROL Rebonds]](bounces.md).

## Méthode de calcul de cette mesure

La définition de cette mesure dépend du paramètre du projet [[!UICONTROL Compter les instances répétées]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings) :

* **[!UICONTROL Compter les instances répétées] activé** : compte le nombre de visites pour lesquelles la dimension [!UICONTROL Page] contenait une seule valeur pour la visite. Si un visiteur recharge la page, elle est disqualifiée en tant que visite sur une seule page.
* **[!UICONTROL Compter les instances répétées] désactivé** : compte le nombre de visites pour lesquelles la dimension [!UICONTROL Page] contenait une valeur unique pour l’ensemble de la visite.

Quel que soit le paramètre de projet « [!UICONTROL Compter les instances répétées] », cette mesure respecte les règles suivantes :

* Une visite est toujours considérée comme une visite sur une seule page si un visiteur déclenche des appels de suivi des liens (la dimension [!UICONTROL Page] est supprimée de tous les appels de suivi des liens).
* Dès que la dimension [!UICONTROL Page] est remplacée par une seconde valeur unique, la visite n’est plus considérée comme une visite sur une seule page.

Consultez [Accès unique](single-access.md) pour une comparaison des mesures.
