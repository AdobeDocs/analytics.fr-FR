---
source-git-commit: d6e51ae2668bc25edea76640cdd97abef184fa3e
workflow-type: tm+mt
source-wordcount: '2997'
ht-degree: 87%

---
# Extraits

## Report Builder hérité {#legacy-arb}

>[!IMPORTANT]
>
>Un nouveau [Report Builder](/help/analyze/report-builder/rb-overview.md) simplifié a été publié le 16 octobre 2024. Il est pris en charge dans Mac, Windows et les navigateurs web.
>&#x200B;>Cette version héritée du complément Report Builder fonctionne toujours. Vous pouvez [convertir vos classeurs hérités](/help/analyze/report-builder/convert-workbooks.md) dans le nouveau Report Builder.

## Annonce de fin de vie de Reports & Analytics {#ra-eol}

>[!IMPORTANT]
>
>À compter du **17 janvier 2024** Adobe a arrêté Reports &amp; Analytics et les rapports et fonctionnalités qui l’accompagnent. À ce moment-là, Reports &amp; Analytics et l’ensemble de ses rapports et plannings ont cessé de fonctionner. Reports &amp; Analytics sʼappuie sur des rapports, des visualisations et des technologies sous-jacentes qui ne répondent plus aux normes technologiques dʼAdobe. La plupart des fonctionnalités de Reports &amp; Analytics sont disponibles dans Analysis Workspace. Pour plus d’informations, voir [Utiliser des modèles](/help/analyze/analysis-workspace/templates/use-templates.md).
> 
>Depuis la publication d’Analysis Workspace en 2015, les fonctionnalités de Reports &amp; Analytics ont migré vers Analysis Workspace, de telle sorte quʼun seuil de parité en matière de workflow a été atteint. Cet avis décrit le processus de fin de vie.
>
>En savoir plus sur l’[annonce de fin de vie](https://www.adobe.com/go/analytics_rnaeol_fr) de Reports &amp; Analytics.

## Options de tri des composants {#components-sort-options}

| Option | Fonction |
|---------|----------|
| [!UICONTROL **Recommandé**] | Trie les composants avec ceux qui sont recommandés en haut de la liste. Les composants utilisés le plus souvent et le plus récemment par vous ou par d’autres membres de votre organisation sont répertoriés plus haut dans la liste. |
| [!UICONTROL **Alphabétique**] | Trie les composants par ordre alphabétique. |
| [!UICONTROL **Catégorique**] | Trie les composants en fonction du type de composant (dimension, mesure, segment, période). |

{style="table-layout:auto"}

## Tests limités de la phase de publication {#release-limited-testing}

>[!AVAILABILITY]
>
>La fonctionnalité décrite dans cet article se trouve dans la phase de test limité de la publication et peut ne pas encore être disponible dans votre environnement. Cette note sera supprimée lorsque la fonctionnalité sera disponible. Pour plus d’informations sur le processus de publication d’Analytics, consultez [Versions des fonctionnalités Adobe Analytics](/help/release-notes/releases.md).

## Section Phase de tests limités de publication {#release-limited-testing-section}

>[!AVAILABILITY]
>
>La fonctionnalité décrite dans cette section se trouve dans la phase de test limité de la publication et peut ne pas encore être disponible dans votre environnement. Cette note sera supprimée lorsque la fonctionnalité sera disponible. Pour plus d’informations sur le processus de publication d’Analytics, consultez [Versions des fonctionnalités Adobe Analytics](/help/release-notes/releases.md).


## Clause de non-responsabilité du plug-in {#plug-in}

>[!IMPORTANT]
>
>Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez l’équipe de compte Adobe de votre organisation. Elle peut organiser une réunion avec un consultant ou une consultante pour obtenir de l’aide.


## Disponible uniquement pour les clients existants {#available-existing-customers}

>[!AVAILABILITY]
>
>La fonctionnalité décrite dans cette section n’est disponible que pour les clients existants qui disposent déjà d’une licence pour cette fonctionnalité. Cette fonctionnalité n’est plus proposée en tant que module complémentaire aux clients existants ou nouveaux.
>



## Modèles d’attribution {#attribution-models-details}

Un modèle d’attribution détermine les éléments de dimension crédités pour une mesure lorsque plusieurs valeurs sont affichées dans l’intervalle de recherche en amont d’une mesure. Les modèles d’attribution ne s’appliquent que lorsque plusieurs éléments de dimension sont définis dans l’intervalle de recherche en amont. Si un seul élément de dimension est défini, il est crédité à 100 %, quel que soit le modèle d’attribution utilisé.

| Icône | Modèle d’attribution | Définition |
| :---: | :--- | --- |
| ![Dernière touche](/help/assets/icons/AttributeLastTouch.svg) | Dernière touche | Attribue un crédit de 100 % au point de contact le plus récent avant la conversion. Ce modèle d’attribution est généralement la valeur par défaut de toute mesure pour laquelle aucun modèle d’attribution n’est spécifié. Les entreprises utilisent généralement ce modèle lorsque le temps de conversion est relativement court, par exemple lors de l’analyse de mots-clés de recherche interne. |
| ![Première touche](/help/assets/icons/AttributeFirstTouch.svg) | Première touche | Attribue un crédit de 100 % au point de contact affiché pour la première fois dans l’intervalle de recherche en amont d’attribution. Les entreprises utilisent généralement ce modèle pour comprendre la notoriété de la marque ou l’acquisition client. |
| ![Linéaire](/help/assets/icons/AttributeLinear.svg) | Linéaire | Attribue le même crédit à chaque point de contact visible menant à une conversion. Cela s’avère utile lorsque les cycles de conversion sont plus longs ou nécessitent un engagement client plus fréquent. Les entreprises utilisent généralement ce modèle d’attribution pour mesurer l’efficacité des notifications des applications mobiles ou avec des produits basés sur les abonnements. |
| ![Participation](/help/assets/icons/AttributeParticipation.svg) | Participation | Attribue un crédit de 100 % à tous les points de contact uniques. Comme chaque point de contact reçoit un crédit de 100 %, le total des données de mesure est généralement supérieur à 100 %. Si un élément de dimension apparaît plusieurs fois avant une conversion, les valeurs sont dédupliquées à 100 %. Ce modèle d’attribution est idéal dans les situations où vous souhaitez comprendre les points de contact auxquels les clientes et clients sont le plus exposés. Les sociétés de médias utilisent généralement ce modèle pour calculer la vitesse du contenu. Les sociétés de vente au détail utilisent généralement ce modèle pour comprendre les parties de leur site qui sont essentielles à la conversion. |
| ![Même touche](/help/assets/icons/AttributeSameTouch.svg) | Même touche | Attribue un crédit de 100 % à l’événement même où la conversion a eu lieu. Si un point de contact ne se produit pas sur le même événément qu’une conversion, il est placé sous « Aucun ». Ce modèle d’attribution équivaut parfois à n’avoir aucun modèle d’attribution. Il s’avère utile dans les scénarios où vous ne souhaitez pas que les valeurs d’autres événements affectent la manière dont une mesure crédite les éléments de dimension. Les équipes produit ou de conception peuvent utiliser ce modèle pour évaluer l’efficacité d’une page où a lieu une conversion. |
| ![En forme de U](/help/assets/icons/AttributeUShaped.svg) | En forme de U | Attribue 40 % de crédit à la première interaction, 40 % à la dernière interaction et divise les 20 % restants entre les autres points de contact. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les conversions avec deux points de contact, un crédit de 50 % est attribué aux deux. Ce modèle d’attribution est idéal dans les scénarios où vous attribuez la plus grande valeur aux première et dernière interactions, mais où vous ne souhaitez pas ignorer entièrement les interactions supplémentaires entre les deux. |
| ![En forme de J](/help/assets/icons/AttributeJCurve.svg) | Courbe en J | Attribue un crédit de 60 % à la dernière interaction, de 20 % à la première interaction et divise les 20 % restants entre les autres points de contact. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les conversions avec deux points de contact, un crédit de 75 % est attribué à la dernière interaction et 25 % à la première. Semblable à la forme en U, ce modèle d’attribution privilégie la première et la dernière interaction, mais plus fortement la dernière interaction. |
| ![Inverse J](/help/assets/icons/AttributeInverseJ.svg) | En forme de J inversé | Attribue un crédit de 60 % au premier point de contact, de 20 % au dernier point de contact et divise les 20 % restants entre les autres points de contact. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les conversions avec deux points de contact, un crédit de 75 % est attribué à la première interaction et 25 % à la dernière. Semblable à la forme en J, ce modèle d’attribution privilégie la première et la dernière interaction, mais plus fortement la première interaction. |
| ![Atténuation temporelle](/help/assets/icons/AttributeTimeDecay.svg) | Atténuation temporelle | Suit une atténuation exponentielle avec un paramètre de demi-vie personnalisé, où la valeur par défaut est de sept jours. La pondération de chaque canal dépend de la durée écoulée entre l’initiation du point de contact et la conversion éventuelle. La formule utilisée pour déterminer le crédit est `2^(-t/halflife)`, où `t` correspond à la durée entre un point de contact et une conversion. Tous les points de contact sont alors normalisés à 100 %. Idéal pour les scénarios dans lesquels vous souhaitez mesurer l’attribution par rapport à un événement spécifique et significatif. Plus une conversion se produit longtemps après un événement marketing, plus faible sera le crédit attribué. |
| ![Personnalisé](/help/assets/icons/AttributeCustom.svg) | Personnalisé | Permet de spécifier les pondérations à attribuer au premier et au dernier point de contact, et à tous les points de contact intermédiaires. Les valeurs spécifiées sont normalisées à 100 %, même si les nombres personnalisés saisis ne totalisent pas 100. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les interactions avec deux points de contact, le paramètre du milieu est ignoré. Les premiers et derniers points de contact sont ensuite normalisés à 100 % et le crédit est attribué en conséquence. Ce modèle est idéal pour les analystes qui souhaitent un contrôle total sur leur modèle d’attribution et qui ont des besoins spécifiques que d’autres modèles d’attribution ne remplissent pas. |
| ![Algorithmique](/help/assets/icons/AttributeAlgorithmic.svg) | Algorithmique | Utilise des techniques statistiques pour déterminer de manière dynamique l’allocation optimale de crédit pour la mesure sélectionnée. L’algorithme utilisé pour l’attribution est basé sur le dividende d’Harsanyi de la théorie du jeu coopératif. Le dividende d’Harsanyi est une généralisation de la solution de valeur de Shapley (nommée en honneur de Lloyd Shapley, un lauréat du prix Nobel d’économie) pour distribuer le crédit entre les participants d’un jeu dont les contributions au résultat sont inégales.<br>À haut niveau, l’attribution se calcule comme une coalition d’acteurs à laquelle un excédent doit être équitablement réparti. La répartition de l’excédent de chaque coalition est déterminée en fonction de l’excédent précédemment créé par chaque sous-coalition (ou des éléments de dimension ayant participé précédemment) de façon récurrente. Pour plus de détails, voir les articles originaux de John Harsanyi et de Lloyd Shapley : <br>Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.<br>Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220. |

{style="table-layout:auto"}

## Conteneur d’attribution {#attribution-container}

Un conteneur d’attribution définit la portée souhaitée pour l’attribution. Les options possibles sont les suivantes :

* **Visite** : examine les conversions à partir de la portée du conteneur de visites. Lorsque **[!UICONTROL Visite]** est sélectionné, l’intervalle de recherche en amont [Attribution](#atribution-lookback-window) est automatiquement défini sur **[!UICONTROL Intervalle de création de rapports]** et ne peut pas être modifié.
* **Visiteur** : examine les conversions à partir de la portée du conteneur de visiteurs.

## Intervalle de recherche en amont des attributions {#attribution-lookback-window}

Un intervalle de recherche en amont est la durée pendant laquelle une conversion doit faire une recherche en amont pour inclure des points de contact. Si un élément de dimension est défini en dehors de l’intervalle de recherche en amont, la valeur n’est incluse dans aucun calcul d’attribution.

* **[!UICONTROL Intervalle de création de rapports]** : remonte au début de l’intervalle de création de rapports à partir du moment où la conversion a eu lieu.
* **14 jours** : remonte jusqu’à 14 jours en arrière à partir du moment où la conversion a eu lieu.
* **30 jours** : remonte jusqu’à 30 jours en arrière à partir du moment où la conversion a eu lieu.
* **60 jours** : remonte jusqu’à 60 jours en arrière à partir du moment où la conversion a eu lieu.
* **90 jours** : remonte jusqu’à 90 jours en arrière à partir du moment où la conversion a eu lieu.
* **Heure personnalisée :** vous permet de définir un intervalle de recherche en amont personnalisé à partir du moment où une conversion s’est produite. Vous pouvez spécifier le nombre de minutes, heures, jours, semaines, mois ou trimestres. Par exemple, si une conversion a eu lieu le 20 février, un intervalle de recherche en amont de cinq jours évalue tous les points de contact de dimension du 15 au 20 février dans le modèle d’attribution.

## Exemple d’attribution {#attribution-example}

Examinez l’exemple suivant :

1. Le 15 septembre, un visiteur arrive sur votre site par le biais d’une annonce de référencement payant, puis le quitte.
1. Le 18 septembre, le visiteur arrive de nouveau sur votre site par le biais d’un lien sur les médias sociaux qu’un ami lui a envoyé. Ils ajoutent plusieurs articles à leur panier, mais n’achètent rien.
1. Le 24 septembre, votre équipe marketing leur envoie un courrier électronique contenant un bon pour certains articles de leur panier. Ils appliquent le bon, mais se rendent sur plusieurs autres sites pour voir s’il existe d’autres bons. Ils en trouvent un autre par le biais d’une annonce d’affichage, puis effectuent un achat de 50 $.

Selon votre modèle d’attribution, le conteneur et les canaux reçoivent un crédit différent. Voir le tableau ci-dessous pour obtenir des exemples :

| Modèle | Conteneur | Intervalle de recherche en amont | Explication |
|---|---|---|---|
| Première touche | Visite | Intervalle de rapport | L’attribution ne s’intéresse qu’à la troisième visite. Entre l’e-mail et l’affichage, l’e-mail était le premier. Dès lors, il reçoit 100 % du crédit pour l’achat de 50 $. |
| Première touche | Visiteur | 30 jours | L’attribution examine les trois visites. Le référencement payant a été le premier. Il obtient donc un crédit de 100 % pour l’achat de 50 $. |
| Linéaire | Visite | Intervalle de rapport | Le crédit est divisé entre l’e-mail et l’affichage. Ces deux canaux reçoivent chacun un crédit de 25 $. |
| Linéaire | Visiteur | 30 jours | Le crédit est divisé entre le référencement payant, les réseaux sociaux, les e-mails et l’affichage. Chaque canal reçoit un crédit de 12,50 $ pour cet achat. |
| En forme de J | Visiteur | 30 jours | Le crédit est divisé entre le référencement payant, les réseaux sociaux, les e-mails et l’affichage.<ul><li>Un crédit de 60 % est accordé à l’affichage, pour un montant de 30 $.</li><li>Un crédit de 20 % est accordé au référencement payant, pour un montant de 10 $.</li><li>Les 20 % restants sont répartis entre les réseaux sociaux et le courrier électronique, soit 5 $ à chacun.</li></ul> |
| Atténuation temporelle | Visiteur | 30 jours | <ul><li>Intervalle de zéro jour entre le point de contact de l’affichage et la conversion. `2^(-0/7) = 1`</li><li>Intervalle de zéro jour entre le point de contact de l’e-mail et la conversion. `2^(-0/7) = 1`</li><li>Intervalle de six jours entre le point de contact de réseaux sociaux et la conversion. `2^(-6/7) = 0.552`</li><li>Intervalle de neuf jours entre le point de contact du référencement payant et la conversion. `2^(-9/7) = 0.41`</li>La normalisation de ces valeurs entraîne les résultats suivants :<ul><li>Affichage : 33,8 %, gain de 16,88 $</li><li>Courrier électronique : 33,8 %, gain de 16,88 $</li><li>Réseaux sociaux : 18,6 %, gain de 9,32 $</li><li>Référencement payant : 13,8 %, gain de 6,92 $</li></ul></li></ul> |

Les événements de conversion qui comportent généralement des nombres entiers sont divisés si le crédit revient à plusieurs canaux. Par exemple, si deux canaux contribuent à un événement personnalisé à l’aide d’un modèle d’attribution linéaire, les deux canaux obtiennent 0,5 de cette commande. Ces mesures partielles sont additionnées pour toutes les personnes, puis arrondies à l’entier le plus proche à des fins de création de rapports.

## Comparaisons des visualisations de Journey {#journey-visualization-comparisons}

Diverses visualisations dans Customer Journey Analytics sont conçues pour analyser les parcours que vous fournissez à votre clientèle.

Utilisez les informations suivantes pour choisir la visualisation qui répond le mieux à vos besoins.

| Fonction | Zone de travail de parcours | Abandon | Flux |
|---------|----------|---------|---------|
| **Séquence prédéfinie de pages** | Oui</br>Combine l’analyse prédéfinie et l’analyse exploratoire. Le chemin d’accès définitif est utilisé lors de l’utilisation de nœuds prédéfinis sur le chemin d’accès (les visiteurs sont comptabilisés tant qu’ils passent finalement d’un nœud prédéfini à un autre). Les nœuds immédiats (et non éventuels) suivants peuvent également être affichés. | Oui</br>Le chemin d’accès peut être un chemin d’accès définitif ou peut être limité au point de contact suivant. | Non |
| **Séquence exploratoire des pages (analyse ad hoc)** | Oui</br>Combine l’analyse prédéfinie et l’analyse exploratoire. Le chemin d’accès définitif est utilisé lors de l’utilisation de nœuds prédéfinis sur le chemin d’accès (les visiteurs sont comptabilisés tant qu’ils passent finalement d’un nœud prédéfini à un autre). Les nœuds immédiats (et non éventuels) suivants peuvent également être affichés. | Limité</br>Vous permet de cliquer avec le bouton droit et d’afficher les abandons immédiats dans un tableau à structure libre. | Oui</br>Analyse exploratoire uniquement. Toujours dans une seule instance de dimension entre les nœuds. Cela signifie que chaque nœud affiche le point de contact suivant immédiat (non définitif) du chemin. |
| **Affiche où les personnes sont parties (ont abandonné) et ont continué leur visite (sont passées par l’emplacement)** | Oui</br>affiche pour les parcours prédéfinis et exploratoires | Oui</br>Affiche les parcours prédéfinis | Oui</br>S’affiche pour les parcours exploratoires |
| **Parcours linéaires** | Oui | Oui | Non |
| **Parcours non linéaires avec plusieurs points d’entrée et chemins** | Oui | Non | Oui |
| **Mesure principale** | Toute mesure, y compris les mesures calculées | Uniquement une session ou une personne | Uniquement les occurrences (vues des chemins) |
| **Mesure secondaire** | Oui<p>Toute mesure, y compris les mesures calculées</p> | Non | Non |
| **Prise en charge des composants dans les nœuds ou les points de contact** | Mesures, éléments de dimension, filtres et périodes. | Mesures, éléments de dimension, filtres et périodes. | Uniquement les éléments de dimension (à l’exception des points de contact de début et de fin) |
| **Comparer les filtres** | Non | Oui<p>Comparez en vis-à-vis deux filtres du même rapport.</p> | Non |
| **Interaction avec les composants par glisser-déposer** | Oui | Oui | Non |
| **Parcours Adobe Journey Optimizer** | Oui</br>Ouvrir les parcours de Journey Optimizer pour une analyse et une personnalisation plus approfondies | Non | Non |

{style="table-layout:auto"}



## Section de filtre de balise {#tagfiltersection}

| Balises | Description |
|---|---|
| ![Étiquettes](/help/assets/filter-tag.png){width="300"} | La section **[!UICONTROL Balises]** permet de filtrer par balise. <ul><li>Vous pouvez utiliser ![Rechercher](/help/assets/icons/Search.svg) *Rechercher des balises* pour rechercher les balises que vous souhaitez utiliser pour filtrer.</li><li>Vous pouvez sélectionnez plusieurs balises. Les balises disponibles dépendent des sélections effectuées dans d’autres sections du panneau Filtrer.</li><li>Les chiffres indiquent ce qui suit :<ul><li>**(1)** : nombre de balises sélectionnées (si une ou plusieurs balises sont sélectionnées).</li><li>**2︎⃣** : nombre de balises disponibles pour les éléments résultant du filtre actuel.</li><li>7︎⃣ : nombre d’éléments associés à la balise spécifique.</li></ul></li></ul> |


## Section Filtre de suite de rapports {#reportsuitefiltersection}

| Suite de rapports | Description |
|---|---|
| ![Suite de publications](/help/assets/filter-reportsuite.png){width="300"} | La section **[!UICONTROL Suite de rapports]** vous permet de filtrer les suites de rapports. <ul><li>Vous pouvez ![Rechercher](/help/assets/icons/Search.svg) *Rechercher des suites de rapports* pour rechercher des suites de rapports que vous pouvez utiliser pour filtrer.</li><li>Vous pouvez sélectionner plusieurs suites de rapports. Les suites de rapports disponibles dépendent des sélections effectuées dans d’autres sections du panneau de filtrage.</li><li>Les chiffres indiquent ce qui suit :<ul><li>**(2)** : nombre de suites de rapports sélectionnées (si une ou plusieurs suites de rapports sont sélectionnées).</li><li>**3︎⃣** : nombre de suites de rapports disponibles pour les éléments résultant du filtre actuel.</li><li>4︎⃣ : nombre d’éléments associés à la suite de rapports spécifique.</li></ul></li></ul> |

## Section Filtre de statut activé {#enabledstatusfiltersection}

| Statut Activé | Description |
|---|---|
| ![Statut activé](/help/assets/filter-enabledstatus.png){width="300"} | La section **[!UICONTROL Statut activé]** vous permet de filtrer par statut activé. <ul><li>Vous pouvez sélectionner plusieurs statuts.</li><li>Les chiffres indiquent ce qui suit :<ul><li>**(2)** : nombre de statuts sélectionnés (si un ou plusieurs statuts sont sélectionnés).</li><li>**2⃣** : nombre de statuts disponibles pour les éléments résultant du filtre actuel.</li><li>1︎⃣ : nombre d’éléments associés au statut spécifique.</li></ul></li></ul> |

## Section de filtre de type {#typefiltersection}

| Type | Description |
|---|---|
| ![Type](/help/assets/filter-type.png){width="300"} | La section **[!UICONTROL Type]** vous permet de filtrer par type. <ul><li>Vous pouvez sélectionner plusieurs types.</li><li>Les chiffres indiquent ce qui suit :<ul><li>**(2)** : nombre de types sélectionnés (si un ou plusieurs types sont sélectionnés).</li><li>**1︎⃣** : nombre de types disponibles pour les éléments résultant du filtre actuel.</li><li>3︎⃣ : nombre d’éléments associés au type spécifique.</li></ul></li></ul> |

## Section de filtre de propriétaire {#ownerfiltersection}

| Propriétaire | Description |
|---|---|
| ![Propriétaires](/help/assets/filter-owners.png){width="300"} | La section **[!UICONTROL Propriétaire]** vous permet de filtrer les propriétaires. <ul><li>Vous pouvez utiliser ![Rechercher](/help/assets/icons/Search.svg) *Rechercher des propriétaires* pour rechercher les propriétaires que vous souhaitez utiliser pour filtrer.</li><li>Vous pouvez sélectionner plusieurs propriétaires. Les propriétaires disponibles dépendent des sélections effectuées dans d’autres sections du panneau Filtrer.</li><li>Les chiffres indiquent ce qui suit :<ul><li>**(2)** : nombre de propriétaires sélectionnés (si une ou plusieurs personnes propriétaires sont sélectionnées).</li><li>**3︎⃣** : nombre de propriétaires disponibles pour les éléments résultant du filtre actuel.</li><li>4︎⃣ : nombre d’éléments associés à la personne propriétaire spécifique.</li></ul></li></ul> |

## Section des autres filtres {#otherfiltersfiltersection}

| Autres filtres | Description |
|---|---|
| ![Autres filtres](/help/assets/filter-other.png){width="300"} | La section **[!UICONTROL Autres filtres]** vous permet de filtrer selon un autre filtre prédéfini.<ul><li>Vous pouvez sélectionner l’une ou plusieurs des options suivantes :<ul><li> **[!UICONTROL Tout afficher]**</li><li>**[!UICONTROL Partagé avec moi]**</li><li>**[!UICONTROL À moi]**</li><li>**[!UICONTROL Approuvés]**</li><li>**[!UICONTROL Favoris]**</li></ul> Ce que vous pouvez sélectionner dépend de votre rôle et de vos autorisations.</li><li>Vous pouvez sélectionner plusieurs filtres. Les autres filtres disponibles dépendent des sélections effectuées dans d’autres sections du panneau Filtrer.</li><li>Les chiffres indiquent ce qui suit :<ul><li>**(1)** : nombre d’autres filtres sélectionnés (si un ou plusieurs autres filtres sont sélectionnés).</li><li>**5︎⃣** : nombre d’autres filtres disponibles pour les éléments résultant du filtre actuel.</li><li>4︎⃣ : nombre d’éléments associés à l’autre filtre spécifique.</li></ul></li></ul> |

## Section de filtre de période  {#daterangefiltersection}

| Période appliquée | Description |
|---|---|
| ![Période](/help/assets/filter-daterange.png){width="300"} | La section Période appliquée vous permet de filtrer par période applicable aux éléments.<ol><li>Sélectionnez une période.</li><li>Dans la fenêtre contextuelle du calendrier, définissez une période ou sélectionnez l’un des paramètres prédéfinis disponibles.<br>Vous pouvez également spécifier une période directement dans la section Période du panneau Filtre.</li></ol><ul><li>Les chiffres indiquent ce qui suit :<ul><li>**(1)** : nombre de périodes modifiées à partir des paramètres prédéfinis par défaut.</li><li>**5︎⃣** : nombre de périodes disponibles pour les éléments résultant du filtre actuel.</li></ul> |


## Obsolescence de l’importateur de classifications {#classification-importer-deprecation}

>[!WARNING]
>
>L’importateur de classifications est obsolète et ne sera plus accessible après le **31 août 2026**. Passez à l’expérience [Ensembles de classifications](/help/components/classifications/sets/overview.md) pour garantir la continuité des fonctionnalités.
>



## Obsolescence du Créateur de règles de classification {#classification-rulebuilder-deprecation}

>[!WARNING]
>
>Le créateur de règles de classification est obsolète et ne sera plus accessible après le **31 août 2026**. Passez à l’expérience [Ensembles de classifications](/help/components/classifications/sets/overview.md) pour garantir la continuité des fonctionnalités.
>

