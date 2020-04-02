---
description: Dans la version 14, un visiteur unique se rapporte à un visiteur qui consulte un site pour la première fois au cours d’une période donnée. Par exemple, le visiteur unique peut visiter un site dix fois au cours d’une semaine ; si, toutefois, la période définie est Semaine, il est comptabilisé une seule fois au cours de cette semaine. Une fois la semaine terminée, ce visiteur unique peut être compté de nouveau pour une nouvelle période donnée.
title: Visiteurs uniques
topic: Metrics
uuid: ae210698-99f9-485e-a640-c7520807adc7
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Visiteurs uniques

Dans la version 14, un visiteur unique se rapporte à un visiteur qui consulte un site pour la première fois au cours d’une période donnée. Par exemple, le visiteur unique peut visiter un site dix fois au cours d’une semaine ; si, toutefois, la période définie est Semaine, il est comptabilisé une seule fois au cours de cette semaine. Une fois la semaine terminée, ce visiteur unique peut être compté de nouveau pour une nouvelle période donnée.

## Différences entre les versions 14 et 15

La version 14 ne supprime pas les mesures [!UICONTROL Visites] et [!UICONTROL Visiteurs uniques] en double des rapports basés sur les classifications. Si, par exemple, deux clips vidéo partageaient la même classification, un seul visiteur qui a visionné les deux clips générait deux [!UICONTROL Visites] et deux [!UICONTROL Visiteurs uniques] dans ce rapport.

La version 15 supprime les mesures [!UICONTROL Visites] et [!UICONTROL Visiteurs uniques] en double du rapport basé sur les classifications. Il s’agit d’une mesure plus précise pour [!UICONTROL Visites] et [!UICONTROL Visiteurs], mais cela se traduit généralement par une réduction du nombre de [!UICONTROL Visites] et de [!UICONTROL Visiteurs uniques] pour les rapports de classification, comparé aux données collectées avant la mise à niveau.

| Utilisations | Description |
|---|---|
| Trafic | Un visiteur est une personne qui se rend sur votre site web. Ne nécessite pas un cookie permanent. |
| Conversion | Un visiteur est une personne qui se rend sur votre site web. Est compté lorsqu’un événement lié à une conversion ou une action s’effectue. |
| Ad Hoc Analysis | Un visiteur est une personne qui se rend sur votre site web. Ne nécessite pas un cookie permanent. |

Voir [Rapport Visiteurs uniques - Version 15 et Ad Hoc Analysis](/help/components/c-variables/dimensionslist/reports-unique-visitors-v15-dsc.md).

>[!MORELIKETHIS]
>
>* [Visiteurs uniques par jour](/help/components/c-variables/c-metrics/metrics-daily-unique-visitors.md)

