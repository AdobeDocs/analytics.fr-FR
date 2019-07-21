---
description: Répertorie les mesures standard dans Adobe Analytics.
seo-description: Répertorie les mesures standard dans Adobe Analytics.
seo-title: Mesures référence rapide
solution: Analytics
title: Référence rapide des mesures
topic: Mesures
uuid: 34160 c 96-7 cb 3-4 e 2 f -9956-9 ffa 9 d 9 a 359 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Référence rapide des mesures

Répertorie les mesures standard dans Adobe Analytics.

>[!NOTE]
>
>Any metric (event) not listed below is a [custom metric](../../../components/c-variables/c-metrics/metrics-custom.md#concept_F44638FC95A44B06AEBA3A6F9D008D27) (event).

<table id="table_CF4480B640BD4C81B4B32121FED5C96A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nom de la mesure </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Profondeur moyenne de page </td> 
   <td colname="col2"> Affiche le stade auquel chaque valeur a été déclenchée, en moyenne, au sein d’une visite. Cette mesure se révèle particulièrement utile pour déterminer le niveau auquel votre audience a atteint une page ou une valeur de propriété donnée au cours d’une visite. Profondeur moyenne de page est disponible sur toute variable dans laquelle le cheminement est activé. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durée de consultation moyenne de la page </td> 
   <td colname="col2"> Représente la durée moyenne de consultation de la page au cours d’une visite. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durée moyenne de la visite du site </td> 
   <td colname="col2"> Représente la durée moyenne de consultation d’un site au cours d’une visite. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Taux de rebond </td> 
   <td colname="col2"> Affiche le pourcentage de visites qui contiennent un seul accès. Le taux de rebond applique la mesure des rebonds et est calculé comme suit : rebonds divisés par les entrées. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rebonds </td> 
   <td colname="col2"> Visite correspondant à un seul appel serveur. Par exemple, une visite de page unique est qualifiée de « rebond » si l’interaction d’un visiteur avec la page ne se traduit pas par l’envoi de données à Adobe ; comme un clic sur un lien ou le début d’une vidéo. Si plus d’un accès unique est reçu lors d’une visite, un rebond n’est pas comptabilisé. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clics publicitaires de campagne </td> 
   <td colname="col2"> Les clics publicitaires représentent le nombre de fois où le code de suivi d’une campagne donnée a été transmis dans le cadre de la création de rapports. Lorsqu’un visiteur clique sur un lien affilié balisé avec l’un de ces codes de suivi, il est amené sur votre page d’entrée et le code de suivi est capturé dans s.campaign. Ces données sont envoyées dans le cadre de la création de rapports et un clic publicitaire est enregistré. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ajouts au panier </td> 
   <td colname="col2"> Nombre de fois où un article a été ajouté à un panier. Cette valeur provient de l’événement scAdd. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ouverture de panier </td> 
   <td colname="col2"> Nombre de fois où un client a ouvert un panier en ajoutant un premier article. Se produit lorsqu’un élément est ajouté au panier pour la première fois. Cette valeur provient de l’événement scOpen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Retraits du panier </td> 
   <td colname="col2"> Nombre de fois où un article a été supprimé d’un panier. Cette valeur provient de l’événement scRemove. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Paniers </td> 
   <td colname="col2"> Nombre de fois où un panier a été ouvert ou initialisé. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Consultations du panier </td> 
   <td colname="col2"> Nombre de fois où le contenu du panier est consulté par le client. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Passage en caisse </td> 
   <td colname="col2"> Événement survenant lorsque des clients arrivent à l’étape du paiement. L’étape de paiement survient habituellement juste avant la finalisation d’un achat et suppose généralement la saisie d’informations personnelles par le client (tels que ses adresses de facturation et de livraison). Vous contrôlez les événements de votre site qui sont qualifiés de passages en caisse. Cette valeur provient de l’événement scCheckout. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clics publicitaires </td> 
   <td colname="col2">Les clics publicitaires représentent le nombre de fois où le code de suivi d’une campagne donnée a été transmis dans le cadre de la création de rapports. When a visitor clicks on an affiliate link that has been tagged with one of these tracking codes, the visitor is taken to your landing page and the tracking code is captured in <span class="varname"> s.campaign</span>. Ces données sont envoyées dans le cadre de la création de rapports et un clic publicitaire est enregistré. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Client (nouveaux, récurrents, fidélisés) </td> 
   <td colname="col2">Catégories du rapport Fidélisation des clients : <p>Nouveau client : client avec 0 achat. </p> <p>Client régulier : client avec 1 achat. </p> <p>Client loyal : client avec plus d’un achat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visites récurrentes quotidiennes </td> 
   <td colname="col2"> Présente le nombre de visiteurs ayant fréquenté votre site plusieurs fois en une journée. Un jour est défini comme la période des dernières 24 heures. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrées </td> 
   <td colname="col2"> Les entrées représentent le nombre de fois où une valeur donnée est capturée comme première valeur d’une visite. Une mesure Entrées peut survenir une seule fois par visite. Cependant, il ne s’agit pas nécessairement du premier accès si la variable n’est pas définie. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sorties </td> 
   <td colname="col2"> Le nombre de fois où une valeur donnée est capturée comme dernière valeur d’une visite. Les sorties ne peuvent se produire qu’une seule fois par visite. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Instances </td> 
   <td colname="col2"> Nombre de fois où une valeur a été définie pour une variable. Les instances sont comptabilisées pour tous les types d’accès mais ne sont pas comptabilisées lorsqu’une valeur est enregistrée pour une variable sur un accès suivant en raison de la persistance. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durée de vie </td> 
   <td colname="col2"> Montant total d’une mesure donnée, indicatrice de succès pour un utilisateur donné, par exemple, le nombre total de visites sur toute la durée de vie d’un utilisateur. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Affichage à partir d’un appareil mobile </td> 
   <td colname="col2"> Nombre de fois qu’une page est affichée ou qu’une dimension est définie lors d’un accès par l’intermédiaire d’un appareil mobile. Ad Hoc Analysis uniquement. À la place de la mesure des affichages à partir d’un appareil mobile, nous recommandons d’appliquer le segment « Visites issues de périphériques mobiles ». </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nouveaux engagements </td> 
   <td colname="col2"> « Nouveaux engagements » est le nom d’une mesure de création de rapports Canal marketing qui comptabilise les nouveaux visiteurs provenant d’un canal. Cette mesure comptabilise également les visiteurs qui n’ont pas accédé à votre site au cours des 30 derniers jours. Un nouvel engagement est une variable eVar définie au début de chaque visite (allocation initiale). Les canaux Première touche peuvent également être de nouveaux engagements, en fonction du paramètre d’expiration de l’engagement des visiteurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Occurrences </td> 
   <td colname="col2"> Nombre de captures d’une valeur spécifique, plus le nombre de pages vues pour lesquelles la valeur donnée était persistante. En d’autres termes, « Occurrences » fait référence à la somme des pages vues et des événements de page. Les occurrences sont disponibles uniquement dans les Ad Hoc Analysis. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commandes </td> 
   <td colname="col2"> Nombre de commandes passées sur votre site web au cours d’une période sélectionnée. Vous pouvez ventiler les périodes individuelles en fonction d’autres mesures afin d’afficher les éléments (produits ou campagnes) qui ont contribué à la majorité des commandes pendant cette période. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profondeur de page </td> 
   <td colname="col2"> Nombre moyen de clics dont les utilisateurs ont besoin pour atteindre une certaine page du site web. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Événements de pages </td> 
   <td colname="col2"> Les événements de pages se composent de données de requête d’image provenant de requêtes non standard. Le suivi de liens personnalisés, les liens de sortie et les liens personnalisés sont autant de sources de ces requêtes non standard. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pages vues </td> 
   <td colname="col2"> Une page vue est comptée pour chaque appel de serveur envoyé. Cette mesure représente le nombre total d’instances de page vue. Les appels TrackLink ne sont pas comptés comme des pages vues et n’incrémentent pas la mesure Pages vues. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vues chemins </td> 
   <td colname="col2"> <p>La mesure Vues chemins repose sur les données de cheminement, lesquelles font l’objet d’un suivi pour tous les utilisateurs qui ont accepté des cookies persistants. </p> <p>Le terme Vue chemin sert à indiquer le nombre de fois où une page est consultée, étant donné les contraintes du ou des chemins affichés. Cette mesure calcule le nombre de consultations d’une page donnée, survenues dans le chemin sélectionné. Cette mesure est disponible sur le rapport Chemins. Les vues de chemins indiquent le nombre de consultations d’une séquence particulière de pages. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Consultations produits </td> 
   <td colname="col2"> Instance de la vue de produit en cours de définition. Se produit lorsque la page des détails du produit est affichée. Cette valeur provient de l’événement prodView. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Actualisations </td> 
   <td colname="col2"> Comptées lorsque le même nom de page est chargé deux fois. Indique généralement que la page a été actualisée. Notez que le fait de se rendre deux fois sur la même page lors d’une même visite ne compte pas comme un rechargement, sauf si les deux visites se produisent à la suite. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visites récurrentes </td> 
   <td colname="col2"> Présente le nombre de visites lorsque cette valeur est supérieure à 1. Les visites récurrentes comprennent des visiteurs qui ne sont pas suivis par un cookie. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recettes </td> 
   <td colname="col2"> Les recettes sont capturées lors de l’événement d’achat et définies comme le montant total de la commande pour chaque article. Cette valeur provient de l’événement purchase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recherches </td> 
   <td colname="col2"> <p>Il ne s’agit pas d’une mesure par défaut. C’est toujours une mesure personnalisée. </p> <p>Il s’agit de la mesure par défaut conseillée pour les moteurs de recherche et les mots-clés. Cette mesure représente les instances d’un clic publicitaire et montre la page associée à un moteur ou à un mot-clé spécifique. Les données de la mesure Recherches peuvent faire l’objet d’un rapport rétroactivement depuis le début du jeu de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Accès unique </td> 
   <td colname="col2"> L’accès unique se définit par le nombre de visites sur votre site qui contiennent une seule valeur Nom de page unique. Si un utilisateur se rend sur votre site et clique sur un lien suivi, déclenche un événement (un affichage de vidéo, par exemple) ou recharge la page, la visite est toujours considérée comme une visite Accès unique. Tant que la valeur de la variable pageName reste inchangée, n’importe quel nombre de requêtes peut être envoyé et la visite est toujours considérée comme un accès unique. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durée de la visite </td> 
   <td colname="col2"> Mesures qui génèrent des rapports sur le temps passé par les visiteurs sur une page, sur un site ou par visite. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total </td> 
   <td colname="col2"> Les mesures totales génèrent un rapport sur la valeur de tous les éléments du rapport pour une période rapportée. Si un filtre est actuellement sélectionné, le total peut correspondre au total filtré plutôt qu’au total de la suite de rapports. Si aucun filtre n’est sélectionné, le total représente le total de la suite de rapports. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Client unique </td> 
   <td colname="col2"> <p>(par heure, par jour, par semaine, par mois, par trimestre, par an) </p> <p>Un client unique est comptabilisé une seule fois pour cette période, mais il ne peut plus être comptabilisé, quel que soit le nombre de ses retours sur le site pour faire un achat. Un visiteur unique est comptabilisé une fois lors de la première visite au cours d’une période spécifiée, puis n’est plus comptabilisé jusqu’à l’expiration de la période. Une fois la période écoulée, il est de nouveau comptabilisé. Les clients uniques sont toujours comptabilisés en tant que visiteurs uniques, dans la mesure où ils doivent visiter le site pour faire un achat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visiteurs uniques </td> 
   <td colname="col2"> Présente le nombre total de visiteurs uniques pour la période des rapports (peut être par jour, par semaine, par mois, par trimestre et par an). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Unités </td> 
   <td colname="col2"> Nombre total d’unités commandées au cours d’une période sélectionnée. Étant donné que plusieurs unités peuvent être achetées par commande, « Unités » constitue une mesure importante qui traduit l’évolution générale des stocks. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visiteurs </td> 
   <td colname="col2"> Nombre de visiteurs uniques de votre site pour une heure, un jour, une semaine, un mois, un trimestre ou une année sélectionné(e). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visites </td> 
   <td colname="col2"> <p>Séquence de pages vues lors d’une session unique. Cette mesure est généralement utilisée dans les rapports qui affichent le nombre de sessions utilisateurs au cours de la période sélectionnée. </p> <p>Cette mesure est toujours associée à une période afin que vous sachiez si vous comptabilisez ou non une nouvelle visite si le même visiteur revient sur votre site. </p> </td> 
  </tr> 
 </tbody> 
</table>

