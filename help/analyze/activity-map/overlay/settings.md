---
description: Modifiez les paramètres et les propriétés de tous les types de visualisations de recouvrement dans Activity Map.
title: Paramétrage d’Activity Map
uuid: 42a0309e-3efc-4506-989b-09b6fe419423
feature: Activity Map
role: User, Admin
exl-id: 65c9c690-81e0-4f0f-989d-586d247ed380
source-git-commit: 13ad9d40ad74a8dffe05d899db54f4d77cbcc34c
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 4%

---

# Paramétrage d’Activity Map

Le panneau des paramètres d’Activity Map vous permet de modifier les paramètres et les propriétés de tous les types de visualisations de recouvrement.

**[!UICONTROL Superposition Activity Map]** > **Afficher les paramètres (icône d’engrenage)** > **[!UICONTROL Paramètres]**

## Paramètres généraux

Modifiez les paramètres généraux de l’extension et des recouvrements.

* **[!UICONTROL Entreprises]** : affiche l’organisation Analytics actuelle à laquelle vous êtes connecté.
* **[!UICONTROL Nom de la page]** : affiche le nom de la page active.
* **[!UICONTROL Langue]** : modifie la langue des libellés d’extension Activity Map. Ce paramètre ne modifie pas le contenu de votre site web ni les noms de liens dans les rapports. Les langues prises en charge sont l’anglais, le français, le chinois (simplifié), le chinois (traditionnel), l’allemand, le japonais, le coréen, l’espagnol et le portugais.
* **[!UICONTROL Recouvrements de libellés avec]** : détermine ce qu’est le texte de bulle ou de gradient. Le paramètre par défaut est [!UICONTROL Rang]. Les options incluent ce qui suit :
   * **[!UICONTROL Pas de libellé]** : pas de texte dans les libellés, ce qui en fait des zones colorées
   * **[!UICONTROL Valeur]** : affiche le nombre de clics sur les liens ([Occurrences](/help/components/metrics/occurrences.md))
   * **[!UICONTROL Pourcentage]** : affiche la proportion de clics sur les liens par rapport au nombre total de clics sur les liens de la page.
   * **[!UICONTROL Classement]** : classement numérique du lien par nombre de clics sur le lien.
* **[!UICONTROL Taille de police des libellés]** : détermine la taille du texte dans la bulle ou le gradient.
* **[!UICONTROL Couleur de dégradé]** : permet de modifier la couleur du dégradé lorsque le type de visualisation est [!UICONTROL Dégradé].
* **[!UICONTROL Couleur de bulle]** : permet de modifier la couleur de la bulle lorsque le type de visualisation est [!UICONTROL Bulle].
* **[!UICONTROL Dégradé de couleurs basé sur]** : détermine la mesure sur laquelle l’intensité de couleur d’un lien est basée lorsque le type de visualisation est [!UICONTROL Dégradé].
   * **[!UICONTROL Classements des 30 premiers]** : l’intensité des couleurs est normalisée pour les 30 premiers liens.
   * **[!UICONTROL Valeur de mesure absolue]** : l’intensité de la couleur est une fonction de la valeur de mesure absolue.
* **[!UICONTROL Transparence des dégradés]** : détermine la transparence des superpositions de dégradés lorsque le type de visualisation est [!UICONTROL Dégradés]. Ce curseur vous permet de rendre la superposition de couleurs complètement transparente, complètement opaque ou n’importe où entre les deux.

## Paramètres standard

Ajustez les paramètres de la vue standard.

* **[!UICONTROL Filtrage dynamique des données]** : permet de modifier les liens affichés.
   * **[!UICONTROL Haut]** : affiche les liens les plus populaires. Utilisez la liste déroulante numérique à droite pour déterminer le nombre de liens principaux à afficher. Les options incluent 1, 10, 50 et 100.
   * **[!UICONTROL Bas]** : affiche les liens les moins populaires en fonction de la liste déroulante des nombres. Utilisez la liste déroulante numérique à droite pour déterminer le nombre de liens inférieurs à afficher. Les options incluent 1, 10, 50 et 100.
   * **[!UICONTROL Tous les liens]** : ne pas appliquer de filtrage dynamique des données. La liste déroulante numérique ne s’applique pas lorsque cette option est sélectionnée.
* **[!UICONTROL Masquer les recouvrements pour les liens qui n’ont reçu aucun accès]** : les liens sur la page ne comportant aucun clic sur les liens n’affichent pas de recouvrement. Ces liens sont exclus du filtrage dynamique des données.

## Paramètres en direct

* **[!UICONTROL Afficher en haut]** : affichez le nombre supérieur de gagnants ou de perdants en fonction de la liste déroulante numérique sur la gauche.
* **[!UICONTROL Exclure le bas (%)]** : filtrez le pourcentage inférieur des modifications de lien pour n’afficher que les liens contenant suffisamment de données pour afficher les gains ou pertes pertinents. Le pourcentage est calculé en fonction du nombre de liens sur la page. Par exemple, le filtrage des 10 % inférieurs d’une liste de 200 liens filtre les 20 liens inférieurs.
* **[!UICONTROL Mise à jour automatique des données]** : détermine si les données Analytics affichées dans le recouvrement sont automatiquement mises à jour lorsqu’une nouvelle période est calculée.
* **[!UICONTROL Période de mise à jour automatique]** : lorsque cette case est cochée, actualise la page à chaque nouvelle récupération de données afin que les liens de la page soient plus étroitement synchronisés avec les données collectées.
