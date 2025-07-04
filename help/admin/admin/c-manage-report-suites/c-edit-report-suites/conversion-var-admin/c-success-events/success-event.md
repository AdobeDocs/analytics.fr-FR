---
description: Les événements de succès sont des actions dont le suivi peut être effectué. Il vous appartient de déterminer ce qu’est un événement de succès. Par exemple, si une personne achète un article, l’achat peut être considéré comme un événement de succès.
keywords: événement
title: Événements de succès - Présentation
feature: Metrics
role: Admin
exl-id: d52a691a-8124-4601-932f-d6d2d0a7842b
source-git-commit: 1281bdc569c9ebc5d8daa151b19dc21710633eab
workflow-type: tm+mt
source-wordcount: '938'
ht-degree: 54%

---

# Événements de succès

Les événements de succès (également appelés événements de conversion ou événements personnalisés) sont des actions dont le suivi peut être effectué. Il vous appartient de déterminer ce qu’est un événement de succès. Par exemple, si une personne achète un article, l’achat peut être considéré comme un événement de succès.

Pour obtenir un aperçu vidéo des événements de succès, voir [Présentation des événements de conversion](https://experienceleague.adobe.com/fr/docs/analytics-learn/tutorials/analysis-workspace/metrics/introduction-to-conversion-events) dans le guide des tutoriels Analytics.

## Exemples d’événements de succès

Il existe de nombreux types d’événements de succès en fonction du type de votre site web. En voici quelques exemples :

* **Vente au détail** : consultation produit, passage en caisse, achat
* **Média** : inscription, inscription à des concours, pages vues, affichage de vidéos
* **Finance** : envoi d’applications, connexion, utilisation d’outils en libre-service
* **Voyage** : réservation (achat), campagne interne (clic publicitaire), recherche (prix, itinéraires)
* **Télécommunications** : achat, pistes, utilisation d’outils en libre-service
* **Haute technologie** : téléchargement de livres blancs, appels d’offres, remplissage de formulaires, demandes d’assistance
* **Automobile** : envoi de pistes, demande de devis, téléchargement de brochures

La variable [s.events](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=fr) définit un événement de succès.

## Configurer des événements de succès

Vous pouvez configurer les variables d’événement utilisées sur votre site. Vous pouvez ajouter jusqu’à 1 000 événements de succès. Les événements 81 à 1 000 ne fonctionnent que si vous utilisez un code H22 ou supérieur.

Pour configurer des événements de succès :

1. Dans Adobe Analytics, sélectionnez **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]**.
1. Sélectionnez la suite de rapports dans laquelle vous souhaitez configurer les événements de succès.
1. Sélectionnez **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Conversion]** > **[!UICONTROL Événements de succès]**.

   ![Résultat de l’étape](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/assets/success_event_page.png)

1. Dans la colonne [!UICONTROL **Événement**], identifiez le nom de l’événement que vous souhaitez utiliser comme événement de succès.

1. Dans la colonne **[!UICONTROL Nom]**, cochez la case en regard de l’élément pour activer la modification, puis spécifiez le nom souhaité.

   Attribuez des noms explicites aux événements de succès utilisés sur votre site. Par exemple, si événement1 est utilisé pour effectuer le suivi des inscriptions, renommez-le pour qu’il apparaisse en tant que mesure « Inscriptions » dans tous les rapports de conversion.

1. Dans la colonne **[!UICONTROL Type]**, cochez la case en regard de l’élément pour activer la liste déroulante, puis sélectionnez le type souhaité.

   >[!IMPORTANT]
   >
   >Tenez compte des points suivants lors de la modification du type d’événement :<ul><li>Vous pouvez changer le type d’événement entre compteur et numérique sans perdre l’accès aux données capturées précédemment.</li><li>Lorsque vous modifiez les types d’événement en devise ou à partir d’un événement de devise, un message s’affiche indiquant que les données historiques ne sont pas disponibles dans les rapports. Les différents types d’événement utilisent des tableaux de données distincts, et ne peuvent pas être utilisés simultanément. Certaines données historiques peuvent être restaurées si l’utilisateur rétablit le type d’événement. Toutefois, les données collectées après la modification initiale ne sont pas disponibles.</li></ul>

   Le type que vous sélectionnez détermine s’il s’agit d’un événement de compteur (standard), numérique ou monétaire. <p>Les événements de compteur sont utilisés pour enregistrer un événement dans le temps.</p><p>Les événements numériques servent à générer des rapports sur les numéros qui ne sont pas des numéros de devise, tels que le nombre de coupons utilisés dans une commande.</p> <p>Les événements de devise enregistrent un nombre décimal, comme les taxes ou les frais d’expédition. La valeur transmise aux événements de devise est convertie depuis la devise de la page vers la devise de base de la suite de rapports dès réception. Les événements monétaires sont utilisés pour le suivi des impôts et des frais d’expédition. Pour plus d’informations sur l’utilisation d’événements de devise, contactez un représentant Adobe.<p>Les événements numériques et monétaires vous permettent d’incrémenter les mesures de plus d’une unité.</p><p>Les événements utilisés dans le type standard de Sources de données doivent être numériques ou monétaires.</p>

1. Dans la colonne **[!UICONTROL Polarité]**, cochez la case, puis choisissez dans le menu déroulant si une tendance à la hausse de cette mesure est bonne ou mauvaise.

   vous pouvez ainsi indiquer si Adobe Analytics doit le considérer comme positif ou négatif si un événement personnalisé (mesure) donné monte. Il active des indicateurs directionnels (flèches) pour diverses mesures afin d’ajouter du contexte (par exemple, des comparaisons de semaines à semaines).  Exemple : si l’événement « Bogues envoyés » augmente d’une semaine à l’autre, Adobe Analytics doit-il considérer cela comme un facteur positif ou négatif ? Une augmentation des inscriptions au publipostage est probablement bénéfique. En revanche, une augmentation des erreurs de soumission de formulaire est probablement mauvais signe.  Dans Analysis Workspace, la polarité est appliquée à : mise en forme conditionnelle de table de forme libre, visualisations de changement récapitulatives et modèle de couleur positif / négatif de la visualisation de mappage.

1. Dans la colonne **[!UICONTROL Visibilité]**, cochez la case, puis choisissez dans le menu déroulant s’il faut masquer les mesures standard (intégrées), les événements personnalisés et les événements intégrés dans le menu, les sélecteurs de mesure, le créateur de mesures calculées et le créateur de segments.

   Ce paramètre n’a aucun impact sur la collecte des données pour cette mesure ou cet événement ; il affecte uniquement sa visibilité dans l’interface utilisateur, comme suit :

   Les paramètres suivants sont disponibles :

   | Paramètre | Visible dans | Masqué dans |
   |---------|----------|---------|
   | [!UICONTROL **Visible partout**] | <ul><li>Analysis Workspace</li><li>Créateur de segments</li><li>Créateur de mesures calculées</li></ul> | S.O. |
   | [!UICONTROL **Créateurs**] | <ul><li>Créateur de segments</li><li>Créateur de mesures calculées</li><li>Analysis Workspace</li></ul> |
   | [!UICONTROL **Masqué partout**] | S.O. | <ul><li>Analysis Workspace</li><li>Créateur de segments</li><li>Créateur de mesures calculées</li></ul> |

1. Dans la colonne [!UICONTROL **Description**], cochez la case, puis fournissez une description.
1. Dans la colonne [!UICONTROL **Enregistrement d’événement unique**], cochez la case, puis choisissez dans le menu déroulant s’il faut toujours enregistrer l’événement.

   Les options disponibles sont les suivantes :

   | Option | Fonction |
   |---------|----------|
   | [!UICONTROL **Enregistrer Une Fois Par Visite**] | Associe l’événement donné à la session du visiteur. Les comptes suivants effectués sur un événement donné au cours d’une même visite sont ignorés. Ce type de sérialisation d’événement ne nécessite aucune modification de l’implémentation. |
   | [!UICONTROL **Utiliser l’identifiant d’événement**] | Associe l’événement donné à un identifiant personnalisé. Les comptes suivants effectués sur un événement donné avec le même ID d’événement sont ignorés. Ce type de sérialisation d’événement nécessite un identifiant personnalisé dans les accès pour dédupliquer les valeurs. Voir [Sérialisation des ID d’événements](/help/implement/vars/page-vars/events/event-serialization.md) dans le guide d’utilisation de la mise en œuvre. |

1. Dans la colonne [!UICONTROL **Participation**], cochez la case, puis choisissez d’activer ou de désactiver la participation. Lorsqu’elle est activée, elle attribue un crédit d’attribution complet à tous les éléments de dimension de la visite.

   >[!NOTE]
   >
   >Vous pouvez activer la participation pour 100 événements personnalisés au maximum. De plus, vous pouvez créer des mesures de participation dans le créateur de [mesures calculées](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/participation-metric.md).

1. Sélectionnez **[!UICONTROL Enregistrer]**.
