---
source-git-commit: ca1e86606454c2f906cef0cc1d1a9d1c67cedf0e
workflow-type: tm+mt
source-wordcount: '2360'
ht-degree: 36%

---
# Extraits

## Report Builder hérité {#legacy-arb}

>[!IMPORTANT]
>
>Un nouveau Report Builder simplifié de [](https://experienceleague.adobe.com/fr/docs/analytics/analyze/report-builder/report-buider-overview) a été publié le 16 octobre 2024. Il est pris en charge dans Mac, Windows et les navigateurs web.
>Cette version de complément de Report Builder héritée fonctionne toujours. Vous pouvez [convertir vos classeurs hérités](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/convert-workbooks) en nouveau Report Builder.

## Annonce de fin de vie de Reports &amp; Analytics {#ra-eol}

>[!IMPORTANT]
>
>À compter du **17 janvier 2024**, l’Adobe a arrêté Reports &amp; Analytics et les rapports et fonctionnalités qui l’accompagnent. À ce moment-là, Reports &amp; Analytics et l’ensemble de ses rapports et plannings ont cessé de fonctionner. Reports &amp; Analytics sʼappuie sur des rapports, des visualisations et des technologies sous-jacentes qui ne répondent plus aux normes technologiques dʼAdobe. La plupart des fonctionnalités de Reports &amp; Analytics sont disponibles dans Analysis Workspace. Pour plus d’informations sur l’utilisation des rapports dans Analysis Workspace, voir [ Utilisation de rapports préconfigurés ](/help/analyze/analysis-workspace/reports/use-reports.md).
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

Un modèle d’attribution détermine les éléments de dimension qui reçoivent du crédit pour une mesure lorsque plusieurs valeurs sont affichées dans l’intervalle de recherche en amont d’une mesure. Les modèles d’attribution ne s’appliquent que lorsque plusieurs éléments de dimension sont définis dans l’intervalle de recherche en amont. Si un seul élément de dimension est défini, il est crédité à 100 %, quel que soit le modèle d’attribution utilisé.

| Icône | Modèle d’attribution | Définition |
| :---: | :--- | --- |
| ![Dernière touche](/help/assets/icons/AttributeLastTouch.svg) | Dernière touche | Attribue un crédit de 100 % au point de contact le plus récent avant la conversion. Ce modèle d’attribution est généralement la valeur par défaut pour toute mesure pour laquelle aucun modèle d’attribution n’est spécifié autrement. Les entreprises utilisent généralement ce modèle lorsque le temps de conversion est relativement court, par exemple lors de l’analyse de mots-clés de recherche interne. |
| ![Première touche](/help/assets/icons/AttributeFirstTouch.svg) | Première touche | Attribue un crédit de 100 % au point de contact affiché pour la première fois dans l’intervalle de recherche en amont d’attribution. Les entreprises utilisent généralement ce modèle pour comprendre la notoriété de la marque ou l’acquisition de clients. |
| ![Linéaire](/help/assets/icons/AttributeLinear.svg) | Linéaire | Accorde le même crédit à chaque point de contact visible menant à une conversion. Cela s’avère utile lorsque les cycles de conversion sont plus longs ou nécessitent un engagement client plus fréquent. Les entreprises utilisent généralement ce modèle d’attribution pour mesurer l’efficacité des notifications des applications mobiles ou avec des produits basés sur les abonnements. |
| ![Participation](/help/assets/icons/AttributeParticipation.svg) | Participation | Attribue un crédit de 100 % à tous les points de contact uniques. Comme chaque point de contact reçoit un crédit de 100 %, les données de mesure s’additionnent généralement à plus de 100 %. Si un élément de dimension apparaît plusieurs fois distinct menant à une conversion, les valeurs sont dédupliquées à 100 %. Ce modèle d’attribution est idéal dans les situations où vous souhaitez comprendre les points de contact auxquels les clients sont le plus exposés. Les entreprises de médias utilisent généralement ce modèle pour calculer la vitesse du contenu. Les organisations de vente au détail utilisent généralement ce modèle pour comprendre les parties de leur site qui sont essentielles à la conversion. |
| ![Même touche](/help/assets/icons/AttributeSameTouch.svg) | Même touche | Attribue un crédit de 100 % à l’événement correspondant à celui où la conversion a eu lieu. Si un point de contact ne se produit pas sur le même événement qu’une conversion, il est regroupé sous « Aucun ». Ce modèle d’attribution équivaut parfois à n’avoir aucun modèle d’attribution. Elle s’avère utile dans les scénarios où vous ne souhaitez pas que les valeurs d’autres événements affectent la manière dont une mesure crédite les éléments de dimension. Les équipes de produit ou de conception peuvent utiliser ce modèle pour évaluer l’efficacité d’une page sur laquelle une conversion a lieu. |
| ![En U](/help/assets/icons/AttributeUShaped.svg) | En forme de U | Attribue 40 % de crédit à la première interaction, 40 % à la dernière interaction et divise les 20 % restants entre les autres points de contact. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les conversions avec deux points de contact, 50 % de crédit est attribué aux deux. Ce modèle d’attribution est idéal dans les scénarios où vous attribuez la plus grande valeur aux première et dernière interactions, mais où vous ne souhaitez pas ignorer entièrement les interactions supplémentaires entre les deux. |
| ![Courbe J](/help/assets/icons/AttributeJCurve.svg) | En forme de J | Attribue un crédit de 60 % à la dernière interaction, de 20 % à la première interaction et divise les 20 % restants entre les autres points de contact. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les conversions avec deux points de contact, 75 % de crédit est attribué à la dernière interaction et 25 % à la première. Semblable à la forme en U, ce modèle d’attribution favorise la première et la dernière interaction, mais privilégie plus fortement la dernière interaction. |
| ![Inverse J](/help/assets/icons/AttributeInverseJ.svg) | En forme de J inversé | Attribue un crédit de 60 % au premier point de contact, de 20 % au dernier point de contact et divise les 20 % restants entre les autres points de contact. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les conversions avec deux points de contact, 75 % de crédit est attribué à la première interaction et 25 % à la dernière. Semblable à la forme en J, ce modèle d’attribution favorise la première et la dernière interactions, mais favorise plus fortement la première interaction. |
| ![Décroissance temporelle](/help/assets/icons/AttributeTimeDecay.svg) | Décroissance temporelle | Suit une atténuation exponentielle avec un paramètre de demi-vie personnalisé, où la valeur par défaut est de sept jours. La pondération de chaque canal dépend de la durée écoulée entre l’initiation du point de contact et la conversion éventuelle. La formule utilisée pour déterminer le crédit est `2^(-t/halflife)`, où `t` correspond à la durée entre un point de contact et une conversion. Tous les points de contact sont ensuite normalisés à 100 %. Idéal pour les scénarios dans lesquels vous souhaitez mesurer l’attribution par rapport à un événement spécifique et significatif. Plus une conversion se produit après cet événement, moins le crédit est accordé. |
| ![Personnalisé](/help/assets/icons/AttributeCustom.svg) | Personnalisé | Vous permet de spécifier le poids que vous souhaitez donner au premier point de contact, au dernier point de contact et aux points de contact intermédiaires. Les valeurs spécifiées sont normalisées à 100 %, même si les nombres personnalisés saisis ne totalisent pas 100. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les interactions avec deux points de contact, le paramètre du milieu est ignoré. Les premier et dernier points de contact sont ensuite normalisés à 100 % et le crédit est attribué en conséquence. Ce modèle est idéal pour les analystes qui souhaitent exercer un contrôle total sur leur modèle d’attribution et qui ont des besoins spécifiques que d’autres modèles d’attribution ne répondent pas. |
| ![Algorithmique](/help/assets/icons/AttributeAlgorithmic.svg) | Algorithmique | Utilise des techniques statistiques pour déterminer de manière dynamique l’attribution optimale du crédit pour la mesure sélectionnée. L’algorithme utilisé pour l’attribution est basé sur le dividende d’Harsanyi de la théorie du jeu coopératif. Le dividende d’Harsanyi est une généralisation de la solution de valeur de Shapley (nommée en honneur de Lloyd Shapley, un lauréat du prix Nobel d’économie) pour distribuer le crédit entre les participants d’un jeu dont les contributions au résultat sont inégales.<br>À haut niveau, l’attribution se calcule comme une coalition d’acteurs à laquelle un excédent doit être équitablement réparti. La distribution des excédents de chaque coalition est déterminée en fonction de l&#39;excédent qui a été précédemment créé par chaque sous-coalition (ou les éléments de dimension précédemment participants) de manière récursive. Pour plus de détails, voir les documents originaux de John Harsanyi et de Lloyd Shapley : <br>Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.<br>Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220. |

{style="table-layout:auto"}

## Intervalle de recherche en amont d’attribution {#attribution-lookback-window}

Un intervalle de recherche en amont est la durée pendant laquelle une conversion doit faire une recherche en amont pour inclure des points de contact. Si un élément de dimension est défini en dehors de l’intervalle de recherche en amont, la valeur n’est incluse dans aucun calcul d’attribution.

* **14 jours** : recherche les 14 jours précédents à partir du moment où la conversion a eu lieu.
* **30 jours** : vérifie les 30 jours précédents à partir du moment où la conversion a eu lieu.
* **60 jours** : vérifie les 60 jours précédents à partir du moment où la conversion a eu lieu.
* **90 jours** : vérifie les 90 jours précédant la date de la conversion.
* **Visite** : remonte au début de la visite où une conversion s’est produite.
* **Visiteur (intervalle du compte rendu des performances)** : examine toutes les visites jusqu’au premier du mois de la période actuelle. Par exemple, si la période du rapport s’étend du 15 au 30 septembre, la période de recherche en amont des visiteurs comprend le 1er au 30 septembre. Si vous utilisez cet intervalle de recherche en amont, vous pouvez parfois voir que les éléments de dimension sont attribués à des dates en dehors de votre intervalle de compte rendu des performances.
* **Heure personnalisée :** vous permet de définir un intervalle de recherche en amont personnalisé à partir du moment où une conversion s’est produite. Vous pouvez spécifier le nombre de minutes, heures, jours, semaines, mois ou trimestres. Par exemple, si une conversion a eu lieu le 20 février, un intervalle de recherche en amont de cinq jours évalue tous les points de contact de dimension entre le 15 et le 20 février dans le modèle d’attribution.

## Exemple d’attribution {#attribution-example}

Examinez l’exemple suivant :

1. Le 15 septembre, une personne arrive sur votre site par le biais d’une publicité de référencement payant, puis quitte.
1. Le 18 septembre, la personne revient sur votre site via un lien de réseau social qu’elle a reçu d’un ami. Ils ajoutent plusieurs articles à leur panier, mais n’achètent rien.
1. Le 24 septembre, votre équipe marketing leur envoie un courrier électronique contenant un bon pour certains articles de leur panier. Ils appliquent le bon, mais se rendent sur plusieurs autres sites pour voir s’il existe d’autres bons. Ils en trouvent un autre par le biais d’une annonce d’affichage, puis effectuent un achat de 50 $.

Selon votre intervalle de recherche en amont et votre modèle d’attribution, les canaux reçoivent un crédit différent. Voici quelques exemples :

* En utilisant **première touche** et un **intervalle de recherche en amont de session**, l’attribution ne s’intéresse qu’à la troisième visite. Entre le courrier électronique et l’affichage, le courrier électronique était le premier. Dès lors, il reçoit 100 % du crédit pour l’achat de 50 $.

* À l’aide de **première touche** et d’un **intervalle de recherche en amont personne**, l’attribution examine les trois visites. Le référencement payant a été le premier. Il obtient donc un crédit de 100 % pour l’achat de 50 $.

* En utilisant **linéaire** et un **intervalle de recherche en amont de session**, le crédit est divisé entre l’e-mail et l’affichage. Ces deux chaînes ont chacune un crédit de 25 $.
En utilisant **linéaire** et un **intervalle de recherche en amont personne**, le crédit est divisé entre le référencement payant, les réseaux sociaux, les e-mails et l’affichage. Chaque canal reçoit un crédit de 12,50 $ pour cet achat.

* En utilisant la **en forme de J** et un **intervalle de recherche en amont personne**, le crédit est divisé entre le référencement payant, les réseaux sociaux, les e-mails et l’affichage.

   * Un crédit de 60 % est accordé à l’affichage, pour un montant de 30 $.
   * Un crédit de 20 % est accordé au référencement payant, pour un montant de 10 $.
   * Les 20 % restants sont répartis entre les réseaux sociaux et le courrier électronique, soit 5 $ à chacun.

* À l’aide de **Dégradation dans le temps** et d’un **intervalle de recherche en amont**, le crédit est divisé entre le référencement payant, les réseaux sociaux, les e-mails et l’affichage. Utilisation de la demi-vie de sept jours par défaut :

   * Intervalle de zéro jour entre le point de contact de l’affichage et la conversion. `2^(-0/7) = 1`
   * Intervalle de zéro jour entre le point de contact de l’e-mail et la conversion. `2^(-0/7) = 1`
   * Intervalle de six jours entre le point de contact social et la conversion. `2^(-6/7) = 0.552`
   * Intervalle de neuf jours entre le point de contact de référencement payant et la conversion. `2^(-9/7) = 0.41`
   * La normalisation de ces valeurs entraîne les résultats suivants :

      * Affichage : 33,8 %, gain de 16,88 $
      * Courrier électronique : 33,8 %, gain de 16,88 $
      * Réseaux sociaux : 18,6 %, gain de 9,32 $
      * Référencement payant : 13,8 %, gain de 6,92 $

Les événements de conversion qui comportent généralement des nombres entiers sont divisés si le crédit appartient à plusieurs canaux. Par exemple, si deux canaux contribuent à un ordre à l’aide d’un modèle d’attribution linéaire, les deux canaux obtiennent 0,5 de cet ordre. Ces mesures partielles sont additionnées pour toutes les personnes, puis arrondies à l’entier le plus proche pour la création de rapports.

## Comparaisons des visualisations de parcours {#journey-visualization-comparisons}

Diverses visualisations dans l’analyse des Parcours client sont conçues pour analyser les parcours que vous fournissez à vos clients.

Utilisez les informations suivantes pour choisir la visualisation qui répond le mieux à vos besoins.

| Fonction | Zone de travail du parcours | Abandon | Flux |
|---------|----------|---------|---------|
| **Ordre prédéfini des pages** | Oui</br>Combine une analyse prédéfinie et exploratoire. Le chemin d’accès final est utilisé lors de l’utilisation de nœuds prédéfinis sur le chemin d’accès (les visiteurs sont comptabilisés tant qu’ils passent finalement d’un nœud prédéfini à l’autre). Les nœuds immédiats (et non éventuels) suivants peuvent également être affichés. | Oui</br>le chemin peut être un chemin éventuel ou peut être limité au point de contact suivant | Non |
| **Séquence exploratoire des pages (analyse ad hoc)** | Oui</br>Combine une analyse prédéfinie et exploratoire. Le chemin d’accès final est utilisé lors de l’utilisation de nœuds prédéfinis sur le chemin d’accès (les visiteurs sont comptabilisés tant qu’ils passent finalement d’un nœud prédéfini à l’autre). Les nœuds immédiats (et non éventuels) suivants peuvent également être affichés. | Limité</br>Permet d’effectuer un clic droit et d’afficher les abandons immédiats dans un tableau à structure libre. | Oui</br>Analyse exploratoire uniquement. Toujours au sein d’une instance de dimension entre les nœuds. Cela signifie que chaque nœud affiche le point de contact suivant immédiat (et non éventuel) le long du chemin. |
| **Indique où les personnes sont parties (sont tombées) et ont continué à passer (sont tombées)** | Oui</br>affiche pour les parcours prédéfinis et exploratoires | Oui</br>affiche les parcours prédéfinis | Oui</br>Affichage pour les parcours exploratoires |
| **parcours linéaires** | Oui | Oui | Non |
| **parcours non linéaires avec plusieurs points d’entrée et trajectoires** | Oui | Non | Oui |
| **Mesure de Principal** | Toute mesure, y compris les mesures calculées | Session ou personne uniquement | Occurrences uniquement (vues de chemin) |
| **Deuxième mesure** | Oui<p>Toute mesure, y compris les mesures calculées</p> | Non | Non |
| **Prise en charge des composants dans les nœuds ou les points de contact** | Mesures, éléments de dimension, filtres et périodes. | Mesures, éléments de dimension, filtres et périodes. | Uniquement les éléments de dimension (à l’exception des points de contact de début et de fin) |
| **Comparer les filtres** | Non | Oui<p>Comparez en vis-à-vis deux filtres du même rapport.</p> | Non |
| **Interaction des composants par glisser-déposer** | Oui | Oui | Non |
| **parcours Adobe Journey Optimizer** | Oui</br>Ouvrir les parcours de Journey Optimizer pour une analyse et une personnalisation plus approfondies | Non | Non |

{style="table-layout:auto"}
