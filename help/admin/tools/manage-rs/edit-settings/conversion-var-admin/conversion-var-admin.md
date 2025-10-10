---
description: La variable de conversion Custom Insight (ou eVar) est placée dans le code Adobe sur les pages web sélectionnées de votre site. Son principal objectif est de segmenter les mesures de succès de conversion dans les rapports marketing personnalisés. Une eVar peut être basée sur les visites et fonctionner comme un cookie. Les valeurs transmises dans des variables eVar suivent l’utilisateur pendant une période prédéfinie.
keywords: eVar
title: Variables de conversion (eVar)
feature: Admin Tools
role: Admin
exl-id: 822ecaff-a06c-42e1-aee8-ef4a43df4230
source-git-commit: 2d5348a4a6377313f5aab229214d97a02c826939
workflow-type: tm+mt
source-wordcount: '1722'
ht-degree: 93%

---

# Variables de conversion (eVars)

La variable de conversion Custom Insight (ou eVar) est placée dans le code Adobe sur les pages web sélectionnées de votre site. Son principal objectif est de segmenter les mesures de succès de conversion dans les rapports marketing personnalisés. Une eVar peut être basée sur les visites et fonctionner comme un cookie. Les valeurs transmises dans des variables eVar suivent l’utilisateur pendant une période prédéfinie.

**[!UICONTROL Analytics]** > **[!UICONTROL Administration]** > **[!UICONTROL Suites de rapports]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Conversion]** > **[!UICONTROL Variables de conversion]**

## Présentation des variables de conversion (eVars)

Pour obtenir un aperçu vidéo sur les variables de conversion, consultez [ Présentation des variables de conversion ](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/dimensions/introduction-to-conversion-variables-evars) dans le guide des tutoriels Analytics.

Lorsqu’une eVar est définie sur une valeur pour un visiteur, Adobe la mémorise automatiquement jusqu’à ce qu’elle arrive à expiration. Tout événement de succès auquel est associé un visiteur alors que la valeur eVar est active est comptabilisé dans cette dernière.

Les eVars sont parfaitement adaptées à la mesure des causes et des effets, comme par exemple :

* Quelles sont les campagnes internes qui ont eu une incidence sur le chiffre d&#39;affaires ?
* Quelles bannières publicitaires ont, au final, donné lieu à un enregistrement ?
* Combien de fois une recherche interne a-t-elle été utilisée avant de passer une commande ?

Il est conseillé d’utiliser des variables de trafic si vous souhaitez procéder à une mesure du trafic ou utiliser le cheminement.

>[!NOTE]
>
>Une seule valeur peut être stockée dans une eVar dans une demande d’image. Pour stocker plusieurs valeurs dans une eVar, il est recommandé d’utiliser des [variables de liste](/help/implement/vars/page-vars/page-variables.md).

### Variables de conversion - Descriptions {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

Description des champs utilisés lors de la [modification des variables de conversion](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md).

| Élément | Description |
| --- | --- |
| [!UICONTROL Nom] | Nom convivial de la variable de conversion. Il s’agit du nom qui fait référence à l’eVar dans les rapports généraux, mais également du nom du rapport et de la dimension dans le menu de gauche. |
| [!UICONTROL Type] (eVar uniquement) | Type de valeur de la variable :<ul><li>**[!UICONTROL Chaîne de texte]** : capture les valeurs textuelles utilisées sur votre site. Il s’agit du type d’eVar le plus courant et du paramètre par défaut. Cette chaîne se comporte comme les autres variables, la valeur qu’elle contient étant une chaîne de texte statique. Si vous effectuez le suivi d’éléments tels que des campagnes internes ou des mots-clés de recherche interne, ce paramètre est recommandé.</li><li>**[!UICONTROL Compteur]** : compte le nombre d’occurrences d’une action avant l’événement de succès. Si, par exemple, vous utilisez une eVar pour suivre les recherches internes sur votre site, définissez cette valeur sur [!UICONTROL Chaîne de texte] pour suivre l’utilisation des termes de recherche. Définissez cette valeur sur [!UICONTROL Compteur] pour compter le nombre de recherches effectuées, quels que soient les termes de recherche utilisés. Vous pouvez, par exemple, utiliser une eVar de compteur pour suivre le nombre de fois où une personne a utilisé votre recherche interne avant d’effectuer un achat.</li></ul> |
| [!UICONTROL Attribution] | Détermine la manière dont Analytics attribue le crédit d’un événement de succès si une variable reçoit plusieurs valeurs avant l’événement. Les valeurs acceptables sont :<ul><li>**[!UICONTROL Le plus récent]** : la dernière valeur eVar reçoit le crédit des événements de succès jusqu’à l’expiration de l’eVar.</li><li>**[!UICONTROL Valeur d’origine]** : la première valeur eVar reçoit le crédit des événements de succès jusqu’à l’expiration de l’eVar.</li><li>**[!UICONTROL Linéaire]** : attribue uniformément les événements de succès sur toutes les valeurs eVar. Puisque l’affectation linéaire ne répartit précisément les valeurs que dans une visite, utilisez-la avec une expiration d’eVar de visite.</li></ul> **Remarque** : passer d’une allocation vers ou depuis Linéaire empêche l’affichage des données historiques. Mélanger divers types d’attribution dans l’interface de création de rapports peut se traduire par des données erronées dans les rapports. Il se peut, par exemple, qu’une attribution linéaire divise les recettes entre plusieurs valeurs eVar différentes. Après avoir rétabli le type d’attribution sur « Le plus récent », 100 % des recettes seront associées à la valeur unique la plus récente. Cette association peut mener à des conclusions incorrectes de la part des utilisateurs.<br><br>Pour éviter tout risque de confusion dans le compte rendu des performances, Adobe Analytics rend les données historiques inaccessibles à l’interface. Elles peuvent être visualisées si vous décidez de redéfinir l’eVar sur le paramètre d’attribution initial, même s’il est déconseillé de modifier les paramètres d’attribution de l’eVar aux seules fins d’accéder aux données historiques. Adobe recommande d’utiliser une nouvelle eVar lorsque de nouveaux paramètres d’attribution sont souhaités pour des données déjà en cours d’enregistrement, plutôt que de modifier les paramètres d’attribution sur une eVar qui a déjà accumulé une certaine quantité de données historiques. |
| [!UICONTROL Expire après] | Indique une période, ou un événement, à l’issue de laquelle (ou duquel) la valeur eVar arrive à expiration (elle le reçoit plus de crédit pour les événements de succès). Si un événement de succès se produit après l’expiration de l’eVar, la valeur Aucun reçoit le crédit pour l’événement (aucune valeur eVar n’était active). Si vous sélectionnez un événement comme valeur d’expiration, la variable arrive uniquement à expiration si l’événement a lieu. Dans le cas contraire, la variable n’expire jamais.  Les options d’expiration disponibles peuvent être classées dans quatre catégories principales :<ul><li>**Au niveau de la page vue ou de la visite.** Les événements de conversion situés au-delà de la page vue ou de la visite ne sont pas associés à l’eVar.</li><li>**Sur la base d’une période, telle qu’un jour, une semaine, un mois ou un an.** Les événements de conversion situés au-delà de la période spécifiée ne sont pas associés à l’eVar. La période d’expiration débute lorsque la variable est définie. Les eVar expirent selon la date définie exprimée en secondes (minute, heure, jour, mois, etc) : <ul><li>MINUTE=60 secondes</li><li>HEURE=3 600 secondes (60 minutes)</li><li>JOUR=86 400 secondes (24 heures)</li><li>SEMAINE=604 800 secondes (7 jours)</li><li>MOIS=2 678 400 secondes (31 jour)</li><li>TRIMESTRE=8 035 200 secondes (93 jours - 3 mois de 31 jours)</li><li>AN=31 536 000 secondes (365 jours)</li><br>Si une visite débute à 7 :00 un lundi et si une eVar est définie dans cette visite à 7 :15, l’expiration est la suivante :<li>Expiration du jour : eVar expire mardi à 7 :15.</li><li>Expiration de la semaine : eVar expire le lundi suivant à 7 :15.</li><li>Expiration mensuelle : eVar expire 31 jours à partir du lundi à 7:15h.</li></ul><li>**Evénements de conversion spécifiques.** Tout autre événement de conversion qui est déclenché après l’événement spécifique désigné est associé à l’eVar.</li><li>**Jamais.** Tant qu’un visiteur utilise le même identifiant, un laps de temps indéfini peut s’écouler entre l’eVar et l’événement.</li></ul> |
| [!UICONTROL Statut]   (eVar uniquement) | Définit le statut de la variable [!UICONTROL eVar] :<ul><li>**Désactivé** : désactive la variable [!UICONTROL eVar]. Supprime l’[!UICONTROL eVar] de la liste des variables de conversion.</li><li>**Aucune sous-relation** : vous empêche de répartir l’[!UICONTROL eVar] par une dimension.</li><li>**Sous-relations de base** : permet de ventiler une variable eVar en fonction de n’importe quelle sous-relation complète par exemple Produits ou Campagne.</li></ul> |
| [!UICONTROL Réinitialiser] | Réinitialise toute valeur dans la variable eVar. Utilisez ce paramètre lors de la réutilisation d’un eVar afin de ne pas mélanger une ancienne valeur dans un nouveau rapport. La réinitialisation n’efface pas les données historiques. |
| [!UICONTROL Marchandisage] (eVar uniquement) | Les variables de marchandisage peuvent se conformer à l’une des deux syntaxes suivantes :<ul><li>**[!UICONTROL Syntaxe Produits]** : associe la valeur eVar à un produit. **Remarque** : si [!UICONTROL Syntaxe Produits] est sélectionné, la section [!UICONTROL Événement de liaison de merchandising] est désactivée et ne peut pas être sélectionnée pour modification. Pour cette syntaxe, les [!UICONTROL Événements de liaison] ne sont pas applicables.</li><li>**[!UICONTROL Syntaxe de la variable de conversion]** : associe uniquement la valeur eVar à un produit si un [!UICONTROL événement de liaison] survient. Dans ce cas, sélectionnez les événements qui se comportent comme des [!UICONTROL Événements de liaison].  Si vous modifiez ce paramètre sans mettre à jour votre code JavaScript, vous perdrez des données. Voir [Variables de marchandisage](/help/components/dimensions/evar-merchandising.md).</li></ul> |
| [!UICONTROL Événement de liaison de marchandisage] (eVar uniquement) | Si le marchandisage est défini sur [!UICONTROL Syntaxe de la variable de conversion], les événements sélectionnés lieront la valeur de l’eVar active à un produit. Pour utiliser un [!UICONTROL Événement de liaison], définissez l’[!UICONTROL affectation] sur [!UICONTROL Le plus récent]. Si [!UICONTROL Affectation] est définie sur [!UICONTROL Valeur d’origine], la première liaison de produit eVar demeure jusqu’à l’expiration de l’eVar. Il est possible de sélectionner plusieurs événements en cliquant sur plusieurs éléments de la liste tout en maintenant la touche ctrl (Windows) ou cmd (Mac) enfoncée. Vous ne pouvez sélectionner un élément que lorsque le paramètre « [!UICONTROL Syntaxe de la variable de conversion] » est sélectionné. |

### Expiration

Les `eVars` arrivent à expiration après une période que vous avez spécifiée. Une fois arrivées à expiration, elles ne reçoivent plus de crédit pour les événements de succès. Vous pouvez également configurer les eVars pour qu’elles arrivent à expiration lors d’un événement de succès. Ainsi, dans le cas d’une promotion interne qui arrive à expiration à la fin de la visite, celle-ci ne reçoit du crédit que pour les achats ou inscriptions qui ont lieu au cours de la visite pendant laquelle ils ont été activés.

Il existe deux méthodes pour faire expirer une eVar :

* Vous pouvez la configurer de manière à ce qu’elle arrive à expiration après une période ou un événement spécifique.
* Vous pouvez forcer l’expiration d’une eVar en la réinitialisant, ce qui se révèle utile pour redéfinir son objectif.

Par exemple, si vous faites passer de 30 à 90 jours l’expiration d’une eVar, les valeurs d’eVar collectées continueront à persister pendant la durée du nouveau jeu d’expiration (dans ce cas, 90 jours). Le système examine simplement le paramètre d’expiration actuel et le dernier horodatage défini de la valeur eVar collectée pour déterminer l’expiration. Seule l’option **[!UICONTROL Réinitialiser]** expire les valeurs et le fait immédiatement.

Autre exemple : Une eVar, d’une durée de validité de 21 jours, est utilisée en mai pour faire état de promotions internes, et en juin, est utilisée pour capturer des mots-clés de recherche interne. Dans ce cas, le 1er juin, vous devez forcer l’expiration de cette variable ou la réinitialiser. De cette manière, les valeurs de promotion interne ne figureront pas dans les rapports du mois de juin.

### Respect de la casse

Les eVars ne sont pas sensibles à la casse. La majuscule ou la minuscule utilisée dans le rapport est basée sur la première valeur enregistrée par le système principal. Cette valeur peut être la première instance jamais vue ou varier en fonction d’une période (par exemple, mensuelle), selon la variété et la quantité des données associées à la suite de rapports.

### Compteurs

Bien que les eVars soient généralement utilisées pour contenir des valeurs de chaîne, elles peuvent également être configurées pour faire office de compteurs. Elles s’avèrent particulièrement utiles sous cette forme lorsque vous essayez de comptabiliser le nombre d’actions qu’un utilisateur effectue avant un événement. Vous pouvez, par exemple, utiliser une eVar pour capturer le nombre de recherches internes avant un achat. Chaque fois qu’un visiteur effectue une recherche, l’eVar doit contenir une valeur « +1 ». Si un utilisateur effectue quatre recherches avant un achat, une instance est affichée pour chaque compte total : 1.00, 2.00, 3.00 et 4.00. Cependant, seule la valeur 4.00 reçoit du crédit pour l’événement d’achat (mesures Commandes et Recettes). Seuls les nombres positifs sont autorisés comme valeurs d’un compteur eVar.

## Ajouter ou modifier des variables de conversion

1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]**.
1. Sélectionnez une suite de rapports.
1. Cliquez sur **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Conversion]** > **[!UICONTROL Variables de conversion]**.
1. Sur la page [!UICONTROL Variables de conversion], cliquez sur l’icône **[!UICONTROL Développer]** [+] en regard de la variable de conversion à modifier.

   OU

   Cliquez sur **[!UICONTROL Ajouter nouveau]** pour ajouter une eVar inutilisée à la suite de rapports.
1. Sélectionnez les champs de variable de conversion à modifier.

   Voir [Variables de conversion - Descriptions](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md#section_7C317BB0287A4B8EB0A1A4ECC40627BF). Vous pouvez saisir directement une valeur dans certains champs. D’autres champs permettent de sélectionner une valeur dans une liste déroulante.
1. Cliquez sur **[!UICONTROL Enregistrer]**.
