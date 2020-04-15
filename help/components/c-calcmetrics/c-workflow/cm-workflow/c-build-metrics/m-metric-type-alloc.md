---
description: 'En savoir plus sur '
title: Type de mesure et attribution
uuid: 64649698-df2a-42c3-bb31-938f766e1d1f
translation-type: tm+mt
source-git-commit: 7a791dda238b04fbee2773c60668eb45db0a1fd0

---


# Type de mesure et attribution

La sélection de l’icône d’engrenage en regard d’une mesure vous permet de spécifier le type de mesure et le modèle d’attribution.

* [Type de mesure](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_34A86FB402F94E988724232283BF18B7)
* [Modèle d’attribution de colonnes](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_F9690FD1943B403AB28E2FAC54EFE032)
* [Fonctionnement de l’allocation linéaire (à partir du 19 juillet 2018)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1)

## Type de mesure

![](assets/cm_type_alloc.png)

| Type de mesure | Définition |
|---|---|
| Standard | Ces mesures sont les mêmes mesures que celles utilisées dans la création de rapports standard [!DNL Analytics]. Si une formule est composée d’une seule mesure standard, elle affiche des données identiques à sa contrepartie de mesure non calculée. Les mesures standard sont utiles pour créer des mesures calculées spécifiques à chaque élément de ligne. Par exemple, [Commandes] / [Visites] utilise des commandes pour cette ligne spécifique et la divise par le nombre de visites correspondant à cette ligne spécifique. |
| Total | Utilisez le total pour la période du  de chaque ligne. Si une formule est composée d’un nombre total de mesures unique, elle affiche le même nombre total sur chaque ligne. Les mesures totales sont utiles pour créer des mesures calculées qui se comparent aux données totales du site. Par exemple, [Commandes] / [Nombre total de visites] affiche la proportion des commandes par rapport à TOUTES les visites sur votre site, et non juste les visites sur la ligne spécifique objet. |

## Modèle d’attribution de colonnes

>[!IMPORTANT]
>
>En juillet 2018, [!DNL Analytics] a ajouté la nouvelle fonctionnalité [Attribution IQ](https://marketing.adobe.com/resources/help/fr_FR/analytics/analysis-workspace/attribution.html), qui a revu la manière dont les modèles d’attribution dans les mesures calculées sont évalués. Dans le cadre de cette modification, les mesures calculées qui n’utilisent pas un modèle d’attribution par défaut ont été migrées vers des nouveaux modèles d’attribution améliorés :
>
>* Pour obtenir un complet des modèles d’attribution non par défaut et des fenêtres de recherche prises en charge, reportez-vous à la documentation [Attribution IQ](https://marketing.adobe.com/resources/help/fr_FR/analytics/analysis-workspace/attribution.html) .
>* Les modèles d’attribution « Dernière touche canal marketing » et « Première touche canal marketing » seront migrés vers les nouveaux modèles d’attribution « Dernière touche » et « Première touche », respectivement. (Remarque : les rapports « Canaux marketing » ne seront pas obsolètes, seuls les deux modèles d’attribution qui apparaissent dans les mesures calculées le seront.)
>* De plus, nous corrigerons la façon dont l’affectation linéaire est calculée. Pour les clients qui utilisent des mesures calculées avec des modèles d’attribution « linéaire », les rapports peuvent légèrement changer afin de tenir compte du nouveau modèle d’attribution corrigé. Cette modification des mesures calculées sera reflétée dans Analysis Workspace, Reports &amp; Analytics, l’API de création de rapports, Report Builder et Ad Hoc Analysis. For more information, see **How Linear Allocation works (as of July 19, 2018**, below.
>



## Fonctionnement de l’attribution linéaire (au 19 juillet 2018)

En juillet 2018, Adobe a modifié la manière de générer des rapports sur l’affectation linéaire pour les mesures calculées. Cette modification a un impact sur Analysis Workspace, sur l’Ad Hoc Analysis, sur les Reports &amp; Analytics, sur le Report Builder, sur Activity Map et sur les API de création de rapports. Le changement a principalement un impact sur les eVars et autres dimensions qui ont une persistance. Notez que ces modifications s’appliquent uniquement aux mesures calculées et n’affectent pas les autres rapports utilisant l’attribution linéaire (comme le rapport Pages dans les Rapports et analyses). D’autres rapports utilisant l’attribution linéaire continueront d’utiliser la méthode existante d’attribution linéaire.

L’exemple suivant illustre la manière dont les mesures calculées avec attribution linéaire changeront dans les  de :

|  | Accès 1 | Accès 2 | Accès 3 | Accès 4 | Accès 5 | Accès 6 | Accès 7 |
|--- |--- |--- |--- |--- |--- |--- |--- |
| Données envoyées dans | PROMO A | N/A | PROMO A | PROMO B | N/A | PROMO C | $10 |
| eVar Dernière touche | PROMO A | PROMO A | PROMO A | PROMO B | PROMO B | PROMO C | $10 |
| eVar Première touche | PROMO A | PROMO A | PROMO A | PROMO A | PROMO A | PROMO A | $10 |
| Exemple de prop | PROMO A | N/A | PROMO A | PROMO B | N/A | PROMO C | $10 |

Dans cet exemple, les valeurs A, B et C ont été envoyées dans une variable sur les accès 1, 3, 4 et 6 avant qu’un achat de 10 euros ne soit effectué sur l’accès 7. Sur la deuxième ligne, ces valeurs persistent sur l’ensemble des accès lors d’une visite Dernière touche. La troisième ligne illustre une persistance de visite Première touche. Enfin, la dernière ligne illustre comment les données seraient enregistrées pour une prop qui n’a pas de persistance.

## Différences entre le fonctionnement de l’attribution linéaire dans les rapports et analyses et l’espace de travail

Il existe des différences dans le fonctionnement de l’attribution linéaire entre ces deux outils :

* Dans les rapports et analyses, l’attribution linéaire (traitée) est toujours basée sur les visites, tandis que dans Workspace, elle peut être basée sur les visites ou les.
* Dans les rapports et analyses, si aucune valeur n’était transmise au premier accès d’une visite, la valeur (initiale) persistait à partir de la visite précédente. Ceci n’est PAS le cas dans Workspace (QI d’attribution). Si aucune valeur n’est transmise au premier accès d’une visite, &quot;Aucun&quot; est la valeur initiale.

## Fonctionnement de l&#39;attribution linéaire avant juillet 2018

Avant le 19 juillet 2018, l’attribution linéaire était calculée une fois que la persistance Première touche ou Dernière touche avait déjà eu lieu. Cela signifie que pour l’eVar Dernière touche ci-dessus, les 10 euros seraient distribués comme suit : A = 10 * (3/6) = 5 $, B = 10 * (2/6) = 3,33 $, C = 10 * (1/6) = 1,67 $.

Pour l’eVar Première touche ci-dessus, tous les 10 euros seraient donnés à A. Pour la prop : A = 10 * (2/4) = 5 $, B = 10 * (1/4) = 2,50 $ et C = 10 * (1/4) = 2,50 $. Pour résumer l’attribution linéaire telle qu’elle fonctionnait auparavant :

| Valeurs | eVar Dernière touche actuelle | eVar Première touche actuelle | Prop actuelle |
|---|---|---|---|
| PROMO A | $5.00 | $10.00 | $5.00 |
| PROMO B | $3.33 | $0 | $2.50 |
| PROMO C | $1.67 | $0 | $2.50 |
| Total | $10.00 | $10.00 | $10.00 |

**Résumé du fonctionnement de l’attribution linéaire à partir du 19 juillet 2018**

À compter du 19 juillet, nous avons corrigé ce comportement dans les mesures calculées. Au lieu d’utiliser les valeurs qui ont persisté sur la base de la dernière ou de la première touche, [!DNL Analytics] utilise maintenant uniquement les valeurs qui ont été passées (première ligne en haut du tableau). Les paramètres d’attribution de dimension n’ont donc plus d’incidence sur le mode de calcul de l’attribution linéaire (c’est-à-dire que les props et les eVars sont traités de la même manière). Les résultats reflètent ce qui a été transmis à l’origine plutôt que les valeurs Première touche ou Dernière touche qui ont pu persister. Ainsi, dans les trois cas, A = 10 * (2/4) = 5 $, B = 10 * (1/4) = 2,50 $ et C = 10 * (1/4) = 2,50 $.

| Valeurs | Nouvelle eVar Dernière touche | Nouvelle eVar Première touche | Nouvelle prop |
|---|---|---|---|
| PROMO A | $5.00 | $5.00 | $5.00 |
| PROMO B | $2.50 | $2.50 | $2.50 |
| PROMO C | $2.50 | $2.50 | $2.50 |
| Total | $10.00 | $10.00 | $10.00 |

