---
title: Différences de traitement et d’architecture entre les plateformes Analytics
description: Découvrez les différentes façons dont certaines données sont collectées et affichées dans différentes plateformes, telles qu’Adobe Analytics et Google Analytics.
translation-type: tm+mt
source-git-commit: 6fc8145d9a94427ec942d55776b6029f7dd6f79c
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 66%

---


# Différences de traitement et d’architecture entre les plateformes Analytics

Bien qu’Adobe Analytics et Google Analytics soient deux outils d’analyse, la manière dont ces plateformes collectent et traitent les données est très différente. Grâce à cette page, vous comprendrez quelques-unes des principales différences dans la manière dont certaines dimensions et mesures sont collectées et pourquoi elles peuvent afficher des résultats différents dans des rapports similaires.

## [!UICONTROL Taux de rebond]

[!UICONTROL Le taux de rebond est un IPC courant qui permet de mesurer l’efficacité et la pertinence des pages d’entrée dans la plupart des outils d’analyse. ] Il est généralement défini comme étant le nombre de visiteurs qui accèdent au site web et le quittent sans cliquer sur une autre page.

* En Adobe Analytics, [!UICONTROL Le taux de rebond] est calculé à l&#39;aide de la formule **Rebonds divisée par les entrées**.
* En Google Analytics, [!UICONTROL Le taux de rebonds] est calculé à l’aide de la formule **Sessions d’une seule page divisées par Sessions**.

Sur les deux plateformes, si plusieurs accès sont envoyés au cours d’une même visite ou session, ce n’est pas considéré comme un rebond. Dans Adobe Analytics, des liens personnalisés sont disponibles et assez courants, ce qui peut empêcher une visite d’être comptée comme un rebond. Google Analytics envoie généralement une seule requête de données maximum sur la même page.

Pour obtenir une meilleure parité entre les outils de rapports, utilisez la mesure [!UICONTROL Visites mono-page] dans Adobe Analytics au lieu de [!UICONTROL Rebonds] dans le cadre d’une mesure calculée. La mesure [!UICONTROL Visites mono-page] comprend le nombre total de visites qui incluaient uniquement une vue d’une page ou de visites qui entrent sur le site Web mais n’incluent pas de clic sur une autre page.

Pour plus d’informations sur la mesure [Taux de rebond](/help/components/metrics/bounce-rate.md), voir le guide d’utilisation des composants.

## [!UICONTROL Visites et sessions]

[!UICONTROL Les visites]  (appelées sessions en Google Analytics) sont un groupe de vues de page créées par le même utilisateur en peu de temps. [!UICONTROL Sur les deux plateformes, une visite expire généralement après 30 minutes d’inactivité. ] Les deux plates-formes permettent la personnalisation à l&#39;expiration d&#39;une [!UICONTROL visite]. Plusieurs scénarios peuvent provoquer des différences entre les plateformes.

* **Fin de journée :** toutes les sessions de Google Analytics expirent après 23 h 59. Si l’utilisateur est toujours actif sur votre site après minuit, une nouvelle session est créée. Adobe Analytics compte une visite qui se poursuit sur le jour suivant comme une seule visite.
* **Campagnes différentes :** dans Google Analytics, une nouvelle session commence si la source de campagne d’un utilisateur change. Si une nouvelle valeur [!UICONTROL Code de suivi] est affichée en Adobe Analytics, elle est considérée comme faisant partie de la même visite.
* **Remplacement manuel de session :** dans Google Analytics, une nouvelle session commence si vous utilisez `sessionControl` pour démarrer ou terminer une session manuellement. [!UICONTROL Dans Adobe Analytics, ce n’est pas possible de terminer une visite manuellement.]
* **Détection des visites en amont dans Adobe Analytics :** une nouvelle instance   Visitin Adobe Analytics s’début automatiquement si un utilisateur atteint 12 heures d’activité continue, 2 500 accès ou 100 accès en 100 secondes. Ces comportements indiquent généralement l’activité de bots.

Pour plus d’informations sur la mesure [Visites](/help/components/metrics/visits.md), voir le guide d’utilisation des composants.
