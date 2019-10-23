---
description: valeur nulle
seo-description: valeur nulle
seo-title: Présentation du panneau Attribution
title: Présentation du panneau Attribution
uuid: bb345642-4f45-4fb8-82d0-803248dd52ea
translation-type: tm+mt
source-git-commit: bfa8dbdae3c67ec441d18fa4dfa181fa057bd24d

---


# Présentation du panneau Attribution

>[!IMPORTANT] Le panneau Attribution est disponible pour tous les clients sur les SKU Adobe Analytics Ultimate, Prime, Select et Foundation.

Le panneau d’attribution est une fonction de QI [d’](../../attribution-iq.md) attribution qui vous permet d’ajouter de nombreux nouveaux types de modèles d’attribution aux tableaux à structure libre, aux visualisations et aux mesures calculées. Tous les modèles d’attribution ont deux composants :

* **** Modèle d’attribution : Le modèle décrit la distribution des conversions aux accès d’un groupe. Par exemple, Première touche ou Dernière touche.
* **** Fenêtre de recherche d’attribution : La fenêtre de recherche décrit les groupes d’accès pris en compte pour chaque modèle. Par exemple, visite ou visiteur.

## Modèles d’attribution

| Icône d’interface | Modèle d’attribution | Définition | Quand utiliser |
| --- | --- | --- | --- |
| ![Dernière touche](assets/last_touch1.png) | Dernière touche | Attribue un crédit de 100 % au point de contact le plus récent avant la conversion. | Le modèle d’attribution le plus élémentaire et le plus courant. Il est fréquemment utilisé pour les conversions avec un cycle de réflexion court. Le modèle Dernière touche est couramment utilisé par les équipes qui gèrent le marketing de moteur de recherche ou qui analysent les mots-clés de recherche interne. |
| ![Première touche](assets/first_touch.png) | Première touche | Attribue un crédit de 100 % au point de contact affiché pour la première fois dans la fenêtre de recherche d’attribution. | Un autre modèle d’attribution courant est utile pour analyser les canaux marketing destinés à sensibiliser la marque ou à acquérir des clients. Il est fréquemment utilisé par les équipes de marketing social ou d’affichage, mais il est également idéal pour évaluer l’efficacité des recommandations de produits sur site. |
| ![Même touche](assets/same_touch.png) | Même touche | Attribue un crédit de 100 % à l’accès même où la conversion a eu lieu. Si un point de contact ne se produit pas sur le même accès qu’une conversion, il est placé sous "Aucun". | Un modèle utile lors de l’évaluation du contenu ou de l’expérience utilisateur présenté immédiatement au moment de la conversion. Les équipes de produits ou de conception utilisent souvent ce modèle pour évaluer l’efficacité d’une page où une conversion se produit. |
| ![Linéaire](assets/linear.png) | Linéaire | Attribue le même crédit à chaque point de contact visible menant à une conversion. | Utile pour les conversions avec des cycles de réflexion plus longs ou les expériences utilisateur qui nécessitent un engagement plus fréquent de la part des clients. Il est souvent utilisé par des équipes qui mesurent l’efficacité des notifications d’application mobile ou avec des produits basés sur l’abonnement. |
| ![En forme de U](assets/u_shaped.png) | En forme de U | Attribue 40 % de crédit à la première interaction, 40 % à la dernière interaction et divise les 20 % restants entre les points de contact. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les conversions avec deux points de contact, un crédit de 50 % est accordé aux deux. | Un modèle idéal pour ceux qui valorisent les interactions qui ont introduit ou fermé une conversion, mais qui veulent tout de même reconnaître les interactions d’assistance. L’attribution en forme de U est couramment utilisée par les équipes qui adoptent une approche plus équilibrée mais souhaitent accorder plus de crédit aux canaux qui ont trouvé ou fermé une conversion. |
| ![En forme de J](assets/j_shaped.png) | En forme de J | Attribue un crédit de 60 % à la dernière interaction, de 20 % à la première interaction et divise les 20 % restants entre les points de contact. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les conversions avec deux points de contact, 75 % du crédit est attribué à la dernière interaction et 25 % au premier. | Ce modèle est idéal pour ceux qui donnent la priorité aux détecteurs et aux chiffonniers, mais qui veulent se concentrer sur les interactions de fermeture. L’attribution en forme de J est fréquemment utilisée par les équipes qui adoptent une approche plus équilibrée et veulent accorder plus de crédit aux canaux qui ont fermé une conversion. |
| ![Inverse en forme de J](assets/inverse_j.png) | En forme de J inversé | Donne 60 % de crédit au point de première touche, 20 % au point de dernière touche et divise les 20 % restants entre les points de contact. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les conversions avec deux points de contact, 75 % du crédit est attribué à la première interaction et 25 % au dernier. | Ce modèle est idéal pour ceux qui donnent la priorité aux détecteurs et aux chiffonniers, mais qui veulent se concentrer sur la recherche des interactions. L’attribution Inverse J est utilisée par les équipes qui adoptent une approche plus équilibrée et veulent accorder plus de crédit aux canaux qui ont initié une conversion. |
| ![Personnalisé](assets/custom.png) | Personnalisé | Permet de spécifier les pondérations à attribuer aux points de première touche, aux points de dernière touche et aux points de contact intermédiaires. Les valeurs spécifiées sont normalisées à 100 %, même si les nombres personnalisés saisis ne sont pas ajoutés à 100. Pour les conversions avec un point de contact unique, un crédit de 100 % est attribué. Pour les interactions avec deux points de contact, le paramètre du milieu est ignoré. Les points Première touche et Dernière touche sont ensuite normalisés à 100 % et le crédit est attribué en conséquence. | Ce modèle est parfait pour ceux qui veulent un contrôle total sur leur modèle d'attribution et qui ont des besoins spécifiques que d'autres modèles d'attribution ne remplissent pas. |
| ![Décroissance temporelle](assets/time_decay.png) | Décadrage temporel | Suit et diminue exponentielle avec un paramètre de demi-vie personnalisé, où la valeur par défaut est 7 jours. Le poids de chaque canal dépend de la durée écoulée entre l’initiation du point de contact et la conversion éventuelle. La formule utilisée pour déterminer le crédit est `2`<sup>`(-t/halflife)`</sup>, où `t` correspond à la durée entre un point de contact et une conversion. Tous les points de contact sont alors normalisés à 100 %. | Idéal pour les équipes qui gèrent régulièrement de la publicité vidéo ou qui font du marketing contre des événements avec une date prédéterminée. Plus une conversion se produit après un événement marketing, moins le crédit est attribué. |
| ![Participation](assets/participation.png) | Participation | Attribue un crédit de 100 % à tous les points de contact uniques. Le nombre total de conversions est gonflé par rapport aux autres modèles d’attribution. La participation déduplique les canaux qui sont vus plusieurs fois. | Excellent pour comprendre qui les clients sont souvent exposés à une interaction donnée. Les sociétés de médias utilisent fréquemment ce modèle pour calculer la vitesse du contenu. Les sociétés de vente au détail utilisent souvent ce modèle pour comprendre quelles parties de leur site sont essentielles à la conversion. |

## Fenêtres de recherche

Une fenêtre de recherche est la durée pendant laquelle une conversion doit revenir en arrière pour inclure des points de contact. Les modèles d’attribution qui accordent plus de crédit aux premières interactions affichent des différences plus importantes lors de l’affichage de différentes fenêtres de recherche.

* **** Fenêtre de recherche de visites : Recherche le début d’une visite au cours de laquelle une conversion s’est produite. Les fenêtres de recherche des visites sont étroites, car elles ne regardent pas au-delà de la visite. Les fenêtres de recherche de visites respectent la définition de visite modifiée dans les suites de rapports virtuelles.
* **** Fenêtre de recherche du visiteur : Recherche toutes les visites jusqu’au 1er du mois de la période en cours. Les fenêtres de recherche des visiteurs sont larges, car elles peuvent s’étendre sur de nombreuses visites. Par exemple, si la période du rapport est comprise entre le 15 septembre et le 30 septembre, la période de consultation des visiteurs inclut la période du 1er au 30 septembre.

## Exemple

Examinez l’exemple suivant :

1. Le 15 septembre, un visiteur arrive sur votre site par le biais d’une annonce de recherche payante, puis le quitte.
2. Le 18 septembre, le visiteur arrive de nouveau sur votre site par le biais d’un lien sur les réseaux sociaux qu’il a obtenu d’un ami. Ils ajoutent plusieurs articles à leur panier, mais n’achètent rien.
3. Le 24 septembre, votre équipe marketing leur envoie un courrier électronique contenant un bon pour certains articles de leur panier. Ils appliquent le bon, mais se rendent sur plusieurs autres sites pour voir s'il existe d'autres bons. Ils en trouvent un autre par le biais d'une annonce publicitaire, puis effectuent un achat de 50 dollars.

Selon votre fenêtre de recherche et votre modèle d’attribution, les canaux reçoivent un crédit différent. Voici quelques exemples notables :

* En utilisant la **première touche** et une fenêtre **de recherche de** visite, l’attribution ne regarde que la troisième visite. Entre le courrier électronique et l’affichage, le courrier électronique était le premier, de sorte que le courrier électronique reçoive 100 % du crédit pour l’achat de 50 euros.
* En utilisant **Première touche** et une fenêtre **de recherche** du visiteur, l’attribution examine les trois visites. La recherche payante a été la première, elle obtient donc un crédit de 100 % pour l’achat de 50 $.
* À l’aide d’une fenêtre **de recherche** linéaire **et** de visite, le crédit est divisé entre le courrier électronique et l’affichage. Ces deux canaux reçoivent chacun un crédit de 25 euros.
* À l’aide d’une fenêtre **** linéaire **et d’une fenêtre** de recherche devisiteurs, le crédit est divisé entre la recherche payante, le réseau social, le courrier électronique et l’affichage. Chaque canal reçoit un crédit de 12,50 $ pour cet achat.
* En utilisant la forme **** J et une fenêtre **de recherche** du visiteur, le crédit est divisé entre la recherche payée, le réseau social, le courrier électronique et l’affichage.
   * Un crédit de 60 % est accordé pour l’affichage, pour 30 $.
   * Un crédit de 20 % est accordé à la recherche payante, pour 10 $.
   * Les 20 % restants sont répartis entre les réseaux sociaux et le courrier électronique, ce qui donne 5 $ à chacun.
* À l’aide de la **période de désintégration** et d’une fenêtre **de recherche de** visiteurs, le crédit est divisé entre la recherche payante, le réseau social, le courrier électronique et l’affichage. Utilisation de la demi-vie de 7 jours par défaut :
   * Intervalle de 0 jour entre le point tactile d’affichage et la conversion. `2`<sup>`(-0/7)`</sup> `= 1`
   * Intervalle de 0 jour entre le point de contact du courrier électronique et la conversion. `2`<sup>`(-0/7)`</sup> `= 1`
   * Intervalle de 6 jours entre le point de contact social et la conversion. `2`<sup>`(-6/7)`</sup> `= 0.552`
   * Intervalle de 9 jours entre le point de contact de recherche payante et la conversion. `2`<sup>`(-9/7)`</sup> `= 0.41`
   * La normalisation de ces valeurs génère les résultats suivants :
      * Afficher : 33,8 %, avec 16,88 $
      * Courriel : 33,8 % obtenant 16,88 $
      * Social : 18,6 %, avec 9,32 $
      * Recherche payante : 13,8 %, avec 6,92 $

> [!TIP] D’autres événements de conversion, tels que des commandes ou des événements personnalisés, sont également divisés si le crédit appartient à plusieurs canaux. Par exemple, si deux canaux contribuent à un événement personnalisé à l’aide d’un modèle d’attribution linéaire, les deux canaux obtiennent 0,5 de l’événement personnalisé. Ces fractions d’événement sont additionnées pour toutes les visites, puis arrondies à l’entier le plus proche pour la création de rapports.

## Utilisation de l’attribution avec les canaux marketing

Lorsque les canaux marketing ont été introduits pour la première fois, ils n’étaient dotés que des dimensions Première touche et Dernière touche. Avec ces modèles d’attribution supplémentaires, les dimensions Première touche/Dernière touche explicites ne sont plus nécessaires. Adobe fournit des dimensions de canal **** marketing génériques qui peuvent être utilisées avec votre modèle d’attribution de choix. Ces dimensions de canaux marketing génériques se comportent de la même manière que les dimensions de canal Dernière touche, mais sont étiquetées différemment pour éviter toute confusion lors de l’utilisation de canaux marketing avec un modèle d’attribution différent.

Etant donné que les dimensions des canaux marketing dépendent d’une définition de visite traditionnelle (définie par leurs règles de traitement), la définition de visite ne peut pas être modifiée à l’aide de suites de rapports virtuelles.

## Utilisation de l’attribution avec des variables à plusieurs valeurs

Certaines dimensions d’Analytics peuvent contenir plusieurs valeurs sur un seul accès. Les variables de liste et la variable products sont des exemples courants.

Lorsque l’attribution est appliquée aux accès à plusieurs valeurs, toutes les valeurs d’un même accès reçoivent le même crédit. Comme de nombreuses valeurs peuvent recevoir ce crédit, le total du rapport peut être différent de celui de chaque élément de ligne. Le total du rapport est dédupliqué, tandis que chaque valeur de dimension individuelle reçoit le crédit approprié.

## Utilisation de l’attribution avec segmentation

L’attribution s’exécute toujours avant la segmentation et la segmentation s’exécute avant l’application des filtres de rapport. Ce concept s’applique également aux suites de rapports virtuelles utilisant des segments.

Par exemple, si vous créez une suite de rapports virtuelle avec un segment "Accès à l’affichage" appliqué, vous pouvez voir d’autres canaux dans un tableau à l’aide de certains modèles d’attribution.

![Suite de rapports virtuelle affichée uniquement](assets/vrs-aiq-example.png)
