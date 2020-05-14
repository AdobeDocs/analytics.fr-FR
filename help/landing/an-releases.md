---
description: Explique la nouvelle stratégie de mise à jour continue des fonctionnalités d’Adobe Analytics.
title: Versions des fonctionnalités d’Adobe Analytics
translation-type: tm+mt
source-git-commit: dcca8559c9e730c9e04981d69068786878062561
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 4%

---


# Versions des fonctionnalités d’Adobe Analytics

Historiquement, les versions des fonctionnalités d’Adobe Analytics suivaient un calendrier mensuel fixe. À compter d’avril 2020, Adobe Analytics a adopté un modèle de diffusion continu qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités.

## Stratégie de publication

[!UICONTROL Analyse Workspace] utilise des indicateurs de fonctionnalité (également appelés &quot;bascules&quot;) pour contrôler la visibilité des nouvelles fonctionnalités, ce qui permet des tests d’échelle contrôlés avant la version complète. Cette stratégie de mise à jour comprend les phases suivantes :

* **Mise en production (RTP)**: Le code est remis en production, la visibilité des fonctions étant désactivée dans l’espace de travail d’Analyse. **Remarque**: Dans RTP, la fonction peut être disponible dans l’API Analytics 2.0.

* **Tests** limités : Une version par étapes commence par un test effectué par les utilisateurs internes d’Adobe. La mise à jour est alors passée de 0 % à 100 % de disponibilité en quelques mois. Le déploiement par phases se produit au niveau de l’organisation Experience Cloud, de sorte que tous les utilisateurs autorisés d’une organisation bénéficient de la même expérience.

* **Disponibilité générale (GA)**: La fonctionnalité est disponible pour 100 % des organisations Experience Cloud autorisées et sa publication est terminée.

Pour chaque version de fonction, la chronologie entre RTP et GA peut varier. L&#39;objectif est de garder les versions courtes, de sorte que dans les 2 mois suivant le début de publication (RTP), une fonctionnalité sera GA.

## Avantages

Les versions par phases permettent à Adobe de mieux adapter le processus de déploiement des logiciels et de s’assurer que les fonctionnalités sont entièrement renforcées avant la disponibilité générale. Elle permet également la publication des fonctionnalités dès qu&#39;elles sont disponibles, plutôt que de respecter une fenêtre de publication mensuelle fixe.

## Questions fréquentes

| Question | Réponse |
|---|---|
| Puis-je demander un accès rapide à une fonction ? | Non. Un accès anticipé ne sera pas accordé.<br>Si vous souhaitez tester les premiers concepts d’Analytics, nous vous encourageons à essayer les laboratoires [](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/tech-previews/overview.html) Adobe Analytics pour fournir des commentaires sur nos innovations de pointe. |
| Cette stratégie de version affecte-t-elle mon accès aux fonctionnalités ? | Non. Une fois qu’une fonction a atteint la norme GA, vous aurez accès à la fonction si elle est incluse dans votre pack Analytics.<br>Vous pouvez vue les détails de votre module Analytics sous [!UICONTROL Administration] > Paramètres [!UICONTROL de] Société > Niveaux [d’accès aux](https://docs.adobe.com/content/help/en/analytics/admin/company-settings/feature-access-levels.html)fonctionnalités. |