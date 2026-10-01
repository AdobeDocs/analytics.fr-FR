---
description: La variable de conversion Custom Insight (ou eVar) est placée dans le code Adobe sur les pages web sélectionnées de votre site. Son principal objectif est de segmenter les mesures de succès de conversion dans les rapports marketing personnalisés. Une eVar peut être basée sur les visites et fonctionner comme un cookie. Les valeurs transmises dans des variables eVar suivent l’utilisateur pendant une période prédéfinie.
keywords: eVar
title: Variables de conversion (eVar)
feature: Admin Tools
role: Admin
exl-id: 822ecaff-a06c-42e1-aee8-ef4a43df4230
TQID: https://experienceleague.adobe.com/rYLxVYB1oDyfEk8gQyesTSRRPHid-6zJ8QaqFG2b0Kc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: ca917b867cd84b09b899ce7b72586f0b15003106
workflow-type: tm+mt
source-wordcount: '1726'
ht-degree: 44%
---
# Variables de conversion (eVars)

La variable de conversion Custom Insight (ou eVar) est placée dans le code Adobe sur les pages web sélectionnées de votre site. Son principal objectif est de segmenter les mesures de succès de conversion dans les rapports marketing personnalisés. Une eVar peut être basée sur les visites et fonctionner comme un cookie. Les valeurs transmises dans des variables eVar suivent l’utilisateur pendant une période prédéfinie.

**[!UICONTROL Analytics]** > **[!UICONTROL Administration]** > **[!UICONTROL Suites de rapports]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Conversion]** > **[!UICONTROL Variables de conversion]**

## Vue d’ensemble des variables de conversion (eVar)

Pour obtenir un aperçu vidéo sur les variables de conversion, consultez [&#x200B; Présentation des variables de conversion &#x200B;](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/dimensions/introduction-to-conversion-variables-evars) dans le guide des tutoriels Analytics.

Lorsqu’une eVar est définie sur une valeur pour un visiteur, Adobe la mémorise automatiquement jusqu’à ce qu’elle arrive à expiration. Tout événement de succès rencontré par un visiteur alors que la valeur eVar est active est comptabilisé pour cette valeur.

Les eVars sont parfaitement adaptées à la mesure des relations de cause à effet, par exemple :

* Quelles campagnes internes ont influencé le chiffre d’affaires ?
* Quelles bannières publicitaires ont, au final, donné lieu à un enregistrement ?
* Combien de fois une recherche interne a-t-elle été utilisée avant de passer une commande ?

Il est conseillé d’utiliser des variables de trafic si vous souhaitez procéder à une mesure du trafic ou utiliser le cheminement.

>[!NOTE]
>
>Une seule valeur peut être stockée dans une eVar dans une demande d’image. Si plusieurs valeurs sont souhaitées dans une valeur eVar, utilisez [&#x200B; Variables de liste &#x200B;](/help/implement/vars/page-vars/page-variables.md).

### Variables de conversion - Descriptions {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

| Élément | Description |
| --- | --- |
| [!UICONTROL Statut] | Détermine si l’eVar est active :<ul><li>**[!UICONTROL Activé]** : eVar est actif.</li><li>**[!UICONTROL Désactivé]** : désactive l’eVar et la supprime de la liste des variables de conversion.</li></ul> |
| [!UICONTROL Description] | Description facultative de l’eVar. Utilisez-le pour documenter ce que capture eVar et comment il est implémenté. |
| [!UICONTROL Nom] | Nom de dimension convivial de la variable de conversion. Il s’agit de la manière dont l’eVar est référencée dans les rapports généraux. |
| [!UICONTROL Attribution] | Détermine la manière dont Analytics attribue le crédit d’un événement de succès si une variable reçoit plusieurs valeurs avant l’événement. Les valeurs acceptables sont :<ul><li>**[!UICONTROL Le dernier)]** : la dernière valeur eVar est toujours créditée pour les événements de succès jusqu’à l’expiration de cette eVar.</li><li>**[!UICONTROL Valeur d’origine (première)]** : la première eVar est toujours créditée pour les événements de succès jusqu’à l’expiration de cette eVar.</li><li>**[!UICONTROL Linéaire]** : attribue uniformément les événements de succès sur toutes les valeurs eVar. Puisque l’affectation linéaire ne répartit les valeurs que dans une visite, utilisez-la avec une expiration eVar de visite ou plus courte. Cette option n’est pas disponible pour les eVars de marchandisage.</li></ul>**Important** : Adobe déconseille de passer à ou depuis une allocation [!UICONTROL linéaire], car elle masque les données historiques dans les rapports jusqu’à ce que vous reveniez en arrière. Pour modifier l’affectation sur une eVar avec un historique significatif, Adobe recommande d’utiliser une nouvelle eVar à la place. |
| [!UICONTROL Expire après] | Indique le moment où la valeur eVar expire (ne reçoit plus de crédit pour les événements de succès). Si un événement de succès se produit après l’expiration de l’eVar, la valeur Aucun reçoit le crédit pour l’événement (aucune valeur eVar n’était active). Les valeurs acceptables sont :<ul><li>**[!UICONTROL Visite]** : la valeur expire à la fin de la visite.</li><li>**[!UICONTROL Accès]** : la valeur s’applique uniquement à l’accès pour lequel elle est définie.</li><li>**[!UICONTROL Minute]**, **[!UICONTROL Heure]**, **[!UICONTROL Jour]**, **[!UICONTROL Semaine]**, **[!UICONTROL Mois]**, **[!UICONTROL Trimestre]** ou **[!UICONTROL Year]** : la valeur expire à la seconde près, après un délai fixe :<ul><li>Minute = 60 secondes</li><li>Heure = 3 600 secondes (60 minutes)</li><li>Jour = 86400 secondes (24 heures)</li><li>Semaine = 604800 secondes (7 jours)</li><li>Mois = 2678400 secondes (31 jours)</li><li>Trimestre = 8035200 secondes (93 jours - 3 mois de 31 jours)</li><li>Année = 31536000 secondes (365 jours)</li></ul>Par exemple, si une eVar est définie à 7 h 15 le lundi, l’expiration [!UICONTROL Jour] se termine à 7 h 15 le mardi, l’expiration [!UICONTROL Semaine] se termine à 7 h 15 le lundi suivant et l’expiration [!UICONTROL Mois] se termine 31 jours plus tard, à 7 h 15.</li><li>**[!UICONTROL Personnalisé]** : la valeur expire après le nombre de jours que vous saisissez (86400 secondes par jour).</li><li>**Un événement** ([!UICONTROL Achat], [!UICONTROL Affichage du produit], [!UICONTROL Ouverture du panier], [!UICONTROL Passage en caisse du panier], [!UICONTROL Cart Ajouter], [!UICONTROL Cart Supprimer], [!UICONTROL Affichage du panier] ou un événement personnalisé) : la valeur expire lorsque l’événement sélectionné se produit. Si l’événement ne se produit jamais, la valeur n’expire jamais.</li><li>**[!UICONTROL Jamais]** : tant qu’un visiteur utilise le même identifiant, un laps de temps indéfini peut s’écouler entre l’eVar et l’événement.</li></ul> |
| [!UICONTROL Type] | Type de valeur de la variable :<ul><li>**[!UICONTROL Chaîne de texte]** : capture les valeurs textuelles. Il s’agit du type d’eVar le plus courant et du paramètre par défaut. Cette chaîne se comporte comme les autres variables, la valeur qu’elle contient étant une chaîne de texte statique. Si vous effectuez le suivi d’éléments tels que des campagnes internes ou des mots-clés de recherche interne, ce paramètre est recommandé.</li><li>**[!UICONTROL Compteur]** : compte le nombre d’occurrences d’une action avant l’événement de succès. Par exemple, vous pouvez compter le nombre de recherches effectuées, quels que soient les termes utilisés, avant un événement de succès.</li></ul> |
| [!UICONTROL Réinitialiser] | Lors de l’enregistrement, fait immédiatement expirer toutes les valeurs persistantes côté serveur pour cette variable parmi tous les visiteurs, y compris les liaisons de produit de marchandisage. Utilisez [!UICONTROL Réinitialiser] lors de la réutilisation d’un eVar afin de ne pas mélanger une ancienne valeur dans un nouveau rapport. **La réinitialisation n’efface pas les données historiques.** |
| [!UICONTROL Activer le marchandisage] | Les valeurs acceptables sont :<ul><li>**[!UICONTROL Désactivé]** : l’eVar attribue les événements de succès à la valeur qui persiste pour le visiteur.</li><li>**[!UICONTROL Activé]** : eVar devient une eVar de marchandisage, qui lie les valeurs aux produits individuels. Les événements de succès pour chaque produit sont crédités à la valeur liée à ce produit. L’activation du marchandisage affiche les paramètres [!UICONTROL Marchandisage] et [!UICONTROL Événement de liaison de marchandisage] et supprime l’affectation [!UICONTROL Linéaire].</li></ul>Activez le marchandisage uniquement pour les eVars qui décrivent la manière dont les produits sont trouvés ou achetés. Une eVar de marchandisage ne crédite plus les événements de succès qui ne sont pas liés à un produit. Voir [eVar (Marchandisage)](/help/components/dimensions/evar-merchandising.md). |
| [!UICONTROL Marchandisage] | Détermine d’où provient la valeur à lier aux produits :<ul><li>**[!UICONTROL Syntaxe du produit]** : la valeur est définie sur chaque produit dans la variable `products` et est liée à ce produit sur cet accès. Chaque produit peut avoir une valeur différente. Les événements de liaison ne sont pas utilisés. Par conséquent, la fonction [!UICONTROL Événement de liaison de marchandisage] est désactivée.</li><li>**[!UICONTROL Syntaxe de la variable de conversion]** : la valeur est définie dans l’eVar lui-même et persiste en tant que valeur intermédiaire, reflétant toujours la valeur la plus récente envoyée, quelle que soit [!UICONTROL Affectation]. La valeur se lie aux produits sur un accès uniquement si cet accès contient un [!UICONTROL événement de liaison de marchandisage] sélectionné. Chaque produit de cet accès reçoit la même valeur.</li></ul>Si vous modifiez ce paramètre sans mettre à jour votre implémentation, vous perdrez des données. Voir [eVar (variable de marchandisage)](/help/implement/vars/page-vars/evar-merchandising.md) pour les détails d’implémentation. |
| [!UICONTROL Événement de liaison de marchandisage] | Disponible uniquement lorsque [!UICONTROL Marchandisage] est défini sur [!UICONTROL Syntaxe de la variable de conversion]. Détermine quels événements ou eVars lient la valeur intermédiaire d’eVar aux produits sur le même accès. Si vous ne sélectionnez pas d’événement de liaison, [!UICONTROL Tous] est utilisé. Les valeurs acceptables sont :<ul><li>**[!UICONTROL Tous]** : tout autre événement ou eVar sur l’accès déclenche la liaison. Ce paramètre est le paramètre par défaut.</li><li>**[!UICONTROL Événement d’achat]**, **[!UICONTROL Événement d’affichage du produit]**, **[!UICONTROL Événement d’ouverture du panier]**, **[!UICONTROL Événement de passage en caisse du panier]**, **[!UICONTROL Événement d’ajout au panier]**, **[!UICONTROL Événement de suppression du panier]** ou **[!UICONTROL Événement d’affichage du panier]** : la liaison se produit sur les accès qui contiennent l’événement sélectionné.</li><li>**[!UICONTROL Événement de campagne]** : la liaison se produit sur les accès contenant une instance de la dimension [Code de suivi](/help/components/dimensions/tracking-code.md) (variable [`campaign`](/help/implement/vars/page-vars/campaign.md)).</li><li>**Événement personnalisé** : la liaison se produit sur les accès qui contiennent l’événement personnalisé sélectionné.</li><li>**Une eVar personnalisée** : la liaison se produit sur les accès qui définissent l’eVar sélectionnée.</li></ul>Les props ne peuvent pas déclencher de liaison. Sélectionnez plusieurs valeurs en maintenant la touche ctrl (Windows) ou cmd (Mac) enfoncée, puis en cliquant sur plusieurs éléments de la liste. Lorsqu’un produit spécifique déjà lié à une eVar reçoit une autre liaison avec cette même eVar, [!UICONTROL Attribution] détermine la valeur conservée. |

### Expiration

Les `eVars` arrivent à expiration après une période que vous avez spécifiée. Une fois arrivées à expiration, les eVars ne reçoivent plus de crédit pour les événements de succès. Vous pouvez également configurer les eVars pour qu’elles arrivent à expiration lors d’un événement de succès. Ainsi, dans le cas d’une promotion interne qui arrive à expiration à la fin de la visite, celle-ci ne reçoit du crédit que pour les achats ou inscriptions qui ont lieu au cours de la visite pendant laquelle ils ont été activés.

Il existe deux méthodes pour faire expirer une eVar :

* Vous pouvez définir l’expiration de l’eVar après une période spécifiée ou lors d’un événement donné.
* Vous pouvez forcer l’expiration d’une eVar en la réinitialisant, ce qui est utile lors de la réutilisation d’une variable.

Par exemple, si vous faites passer l’expiration d’une eVar de 30 à 90 jours, les valeurs d’eVar collectées continueront à être conservées pendant toute la nouvelle période d’expiration (dans ce cas, 90 jours). Le système se base simplement sur le paramètre d’expiration actuel et sur la date et l’heure de la dernière définition de la valeur d’eVar collectée pour déterminer son expiration. Seule l’option **[!UICONTROL Réinitialiser]** expire les valeurs et le fait immédiatement.

Autre exemple : si une eVar est utilisée en mai pour refléter les promotions internes et qu’elle expire après 21 jours, puis qu’elle est utilisée en juin pour collecter les mots-clés de recherche interne, vous devez, le 1er juin, forcer l’expiration de la variable ou réinitialiser cette dernière. De cette manière, les valeurs de promotion interne ne figureront pas dans les rapports du mois de juin.

### Respect de la casse

Les eVars ne respectent pas la casse. La majuscule ou la minuscule utilisée dans le reporting est basée sur la première valeur enregistrée par le système backe-nd. Cette valeur peut être la première instance jamais vue ou varier en fonction d’une période (par exemple, mensuelle), selon la variété et la quantité des données associées à la suite de rapports.

### Compteurs

Bien que les eVars soient généralement utilisées pour contenir des valeurs de chaîne, elles peuvent également être configurées pour faire office de compteurs. Elles s’avèrent particulièrement utiles sous cette forme lorsque vous essayez de comptabiliser le nombre d’actions qu’un utilisateur effectue avant un événement. Vous pouvez, par exemple, utiliser une eVar pour capturer le nombre de recherches internes avant un achat. Chaque fois qu’un visiteur effectue une recherche, l’eVar doit contenir une valeur de « +1 ». Si un visiteur effectue quatre recherches avant un achat, vous verrez une instance pour chaque nombre total : 1,00, 2,00, 3,00 et 4,00. Cependant, seule la version 4.00 reçoit un crédit pour l’événement d’achat (mesures Commandes et Revenus). Seuls les nombres positifs sont autorisés comme valeurs d’un compteur eVar.

## Ajouter ou modifier des variables de conversion

1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]**.
1. Sélectionnez une suite de rapports.
1. Cliquez sur **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Conversion]** > **[!UICONTROL Variables de conversion]**.
1. Sur la page [!UICONTROL Variables de conversion], cliquez sur l’icône **[!UICONTROL Développer]** [+] en regard de la variable de conversion à modifier.

   OU

   Cliquez sur **[!UICONTROL Ajouter nouveau]** pour ajouter une eVar inutilisée à la suite de rapports.
1. Sélectionnez les champs de variable de conversion à modifier.

   Voir [Variables de conversion - Descriptions](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md#section_7C317BB0287A4B8EB0A1A4ECC40627BF). Certains champs vous permettent de saisir directement une valeur. D’autres champs permettent de sélectionner une valeur dans une liste déroulante.
1. Cliquez sur **[!UICONTROL Enregistrer]**.
