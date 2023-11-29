---
title: FAQ sur les canaux marketing
description: Forum aux questions sur les canaux marketing.
feature: Marketing Channels
exl-id: 6698ef7e-bdac-4b1a-a723-4984e12ce70a
source-git-commit: 2eff7656741bdba3d5d7d1f33e9261b59f8e6083
workflow-type: tm+mt
source-wordcount: '1500'
ht-degree: 100%

---

# FAQ sur les canaux marketing

>[!NOTE]
>
>Afin d’optimiser l’efficacité des canaux marketing pour Attribution  et Customer Journey Analytics, nous avons publié quelques [bonnes pratiques révisées](/help/components/c-marketing-channels/mchannel-best-practices.md).
>
>Les administrateurs et administratrices d’Analytics peuvent gérer les canaux marketing pour leurs organisations, tel que décrit dans la section [Gestion des canaux marketing](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md).

Forum aux questions sur les canaux marketing.

## Mes codes de suivi ne suivent pas de schéma et j’en ai des milliers à spécifier pour mon canal Affilié.

* Procédez par élimination. Si les canaux Courriel et Affilié utilisent le même paramètre de chaîne de requête, mais que vous n’avez que quelques codes de suivi, vous pouvez spécifier les codes de suivi par courriel dans un ensemble de règles définissant le courriel. Vous classez ensuite tous les autres codes de suivi avec   *`affiliates.`*
* Dans votre système de messagerie, ajoutez un paramètre de chaîne de requête à toutes les URL de page de destination, comme *`&ch=eml`*. Créez un ensemble de règles qui détectera si le paramètre de requête ch est égal à *`eml`*. S’il ne contient pas *`eml`*, il s’agit d’un affilié.

## Les domaines référents contiennent plus de données que prévu.

Les domaines référents peuvent se trouver trop haut dans la liste des règles de traitement. Il doit s’agit de l’un des derniers ensembles de règles (ou du dernier), parce que l’ordre de traitement est important.

## J’ai créé une règle correspondant à un paramètre de chaîne de requête, mais elle ne fonctionne pas.

Assurez-vous que le nom du paramètre est spécifié dans les champs de paramètre de chaîne de requête (généralement sous la forme d’une valeur alphanumérique). Vérifiez également que la valeur du paramètre est spécifiée après l’opérateur, comme indiqué dans l’exemple suivant illustrant une règle de courriel.

![](assets/example_email.png)

## Pourquoi la totalité du trafic Dernière touche est-elle attribuée à un domaine interne ?

Vous avez une règle qui correspond au trafic interne. N’oubliez pas que ces règles traitent chaque accès d’un visiteur à votre site, et pas seulement sa première visite. Dans le cas d’une règle telle que   *`Page URL exists`* sans aucun autre critère, une correspondance est établie avec ce canal lors de chaque visite successive sur votre site, car il existe toujours une URL de page.

## Comment déboguer le trafic qui s’affiche dans Aucun canal identifié sur le rapport ?

Les règles sont traitées dans l’ordre. Si aucun critère spécifique n’a de correspondance, les visites sont incluses dans l’une de trois catégories :

1. Aucun référent (visite directe).

2. Référent interne, sur la première page de la visite.

3. Défaut de traitement sur la page.

Vérifiez que vous disposez d’un canal pour ces trois possibilités. Créez, par exemple, des règles indiquant ce qui suit :

1. **[!UICONTROL Référent]** et **[!UICONTROL N’existe pas]** et **[!UICONTROL Est la première page de la visite]**. (Voir [Direct.](/help/components/c-marketing-channels/c-faq.md))

2. **[!UICONTROL Le référent correspond aux filtres d’URL internes]** et **[!UICONTROL Est la première page de la visite]**. (Voir [Interne](/help/components/c-marketing-channels/c-faq.md).)

3. **[!UICONTROL Domaine référent]** et **[!UICONTROL Existe]** et **[!UICONTROL Le référent ne correspond pas aux filtres d’URL internes]**.

Enfin, créez un canal *Other* qui capture les autres accès, comme indiqué dans la section [Aucun canal identifié](/help/components/c-marketing-channels/c-faq.md#no-channel-identified).

## Relation entre Première touche et Dernière touche

Pour comprendre l’interaction entre les dimensions héritées de première et de dernière touche et confirmer que les remplacements fonctionnent comme prévu, vous pouvez extraire un rapport du canal Première touche, sous-lié à un rapport du canal Dernière touche, en ajoutant votre mesure de succès clé (voir l’exemple ci-dessous). Cet exemple illustre l’interaction entre les canaux Première touche et Dernière touche.

![](assets/int-channel3.png)

L’intersection où la première touche équivaut à la dernière touche correspond à la diagonale du tableau. Les canaux Direct et Actualisation de session n’obtiennent le crédit Dernière touche que s’ils étaient également les canaux Première touche, car ils ne peuvent pas obtenir de crédit d’autres canaux persistants (lignes surlignées).

## Raisons pour lesquelles aucun canal n’est identifié {#no-channel-identified}

Lorsque les règles ne capturent pas de données, ou si les règles ne sont pas configurées correctement, le rapport affiche les données sur la ligne [!UICONTROL Aucun canal identifié] du rapport. Vous pouvez créer un ensemble de règles nommé *Autre*, par exemple, à la fin de l’ordre de traitement, pour identifier également le trafic interne.

![](assets/example_other.png)

Ce type de règle « fourre-tout » permet de s’assurer que le trafic des canaux corresponde toujours au trafic externe et ne figure pas dans la catégorie **[!UICONTROL Aucun canal identifié]**. Veillez à ne pas créer de règles identifiant également le trafic interne. La définition de la valeur du canal comme **[!UICONTROL Domaine référent]** ou **[!UICONTROL URL de la page]** est le moyen le plus courant et le plus utile de créer une règle « Other » efficace.

>[!NOTE]
>
>Il est possible qu’une certaine partie du trafic de canaux soit classée dans la catégorie Aucun canal identifié. Par exemple : un visiteur sur le site marque une page comme favori puis, au cours de la même visite, revient sur cette page en passant par les favoris. Puisqu’il ne s’agit pas de la première page de la visite, le trafic ne sera pas inclus dans la catégorie des canaux directs ni dans celle des autres canaux, puisqu’il n’y a aucun domaine référent.

## Raisons d’utiliser le canal interne (actualisation de session) {#internal}

La Dernière touche interne (actualisation de session) ne peut avoir lieu que si elle a également été la Première touche. Consultez « Relation entre Première touche et Dernière touche » ci-dessus. Les scénarios ci-dessous expliquent comment l’actualisation de session peut être un canal Première touche.

* **Délai d’expiration de la session** : un visiteur se rend sur un site Web, puis laisse l’onglet ouvert dans son navigateur pour y retourner ultérieurement. La période d’engagement du visiteur ou de la visiteuse expire (ou bien il ou elle supprime volontairement ses cookies) et il ou elle utilise l’onglet ouvert pour se rendre à nouveau sur le site Web. L’URL de référence étant un domaine interne, la visite est classée comme Actualisation de session.

* **Toutes les pages du site ne sont pas balisées** : un visiteur arrive sur la page A qui n’est pas balisée, puis passe à la page B qui est balisée. La page A serait considérée comme le référent interne et la visite serait classée comme Actualisation de session.

* **Redirections** : si une redirection n’est pas configurée pour transmettre les données du référent à la nouvelle page de destination, les données d’entrée réelle du référent sont perdues et la page de redirection (probablement une page interne) apparaît désormais comme domaine référent. La visite sera classée comme Actualisation de session.

* **Trafic interdomaines** : un visiteur passe d’un domaine qui se déclenche vers la suite A à un autre domaine qui se déclenche vers la suite B. Si, dans la suite B, les filtres d’URL internes incluent le premier domaine, la visite dans la suite B est enregistrée comme interne, puisque les canaux marketing la considèrent comme une nouvelle visite dans la deuxième suite. La visite sera classée comme Actualisation de session.

* **Longs délais de chargement de la page d’accès** : un visiteur accède à la page A, qui contient beaucoup de contenu, et le code Adobe Analytics se trouve au bas de la page. Avant que tout le contenu (y compris la demande d’images Adobe Analytics) puisse être chargé, le visiteur clique sur la page B. La page B déclenche sa demande d’images Adobe Analytics. Comme la demande d’images de la page A n’a jamais abouti, la deuxième page apparaît comme le premier accès de la visite dans Adobe Analytics, avec la page A comme référent. La visite est classée comme Actualisation de session.

* **Effacement des cookies pendant la visite** : un visiteur se rend sur le site et efface ses cookies durant la visite. Les canaux Première touche et Dernière touche seront réinitialisés et la visite sera classée comme Actualisation de session (car le référent est interne).

Voici un exemple de canal interne (actualisation de session) défini comme canaux Première touche et Dernière touche :

* Jour 1 : l’utilisateur accède au site par le biais de l’Affichage. Les canaux Première touche et Dernière touche seront définis sur Affichage.
* Jour 2 : l’utilisateur se rend sur le site par le biais d’une Recherche naturelle. La première touche reste sur Affichage et la dernière touche est définie sur Recherche naturelle.
* Jour 35 : l’utilisateur ne s’est pas rendu sur le site depuis 33 jours et y retourne en utilisant l’onglet qu’il a ouvert dans son navigateur. En supposant une fenêtre d’engagement de 30 jours, la fenêtre se serait fermée et les cookies Marketing Channel auraient expiré. Les canaux Première touche et Dernière touche seront réinitialisés et seront définis sur Actualisation de session puisque l’utilisateur provient d’une URL interne.

## Pourquoi certains canaux restent-ils inchangés après la modification des règles de traitement des canaux marketing ?

Parfois, les règles de traitement des canaux marketing sont mal configurées. Il est alors nécessaire de modifier les règles de traitement. Après avoir appliqué les modifications, vous pouvez voir que certaines mesures attribuent toujours des données à un canal incorrect. Il faut tenir compte de plusieurs points :

* **Les données du canal marketing sont collectées en temps réel** : les données du canal marketing sont traitées lors de la collecte des données et totalement permanentes. La modification des règles de traitement n’affecte pas les données rétroactivement.
* **La modification des règles de traitement n’affecte pas immédiatement les données Première touche**. Par exemple :
   1. Un utilisateur arrive par le biais de votre canal de courrier électronique, car il a été configuré de manière incorrecte, puis quitte votre site.
   2. Le lendemain, vous modifiez la règle de traitement du courrier électronique pour la corriger.
   3. Cet utilisateur revient plusieurs jours plus tard par le biais du référencement naturel et effectue un achat.
   4. Le canal de courrier électronique obtient le crédit Première touche et le référencement naturel obtient le crédit Dernière touche.

  Même plusieurs jours après avoir modifié les règles de traitement, les données peuvent encore être collectées dans le mauvais canal Première touche. Les données Première touche sont continuellement collectées dans un canal incorrect jusqu’à l’expiration de l’engagement des visiteurs de tous les utilisateurs.

La meilleure façon de remédier à ces divergences consiste à prendre l’une des mesures suivantes, ou les deux :

* **Faire expirer manuellement toutes les périodes d’engagement des visiteurs** : ce paramètre fait expirer instantanément tous les canaux Première touche et Dernière touche de tous les visiteurs :
   1. Accédez à Outils d’administration > Suites de rapports.
   2. Passez la souris sur Modifier les paramètres > Canaux marketing > Expiration de l’engagement des visiteurs.
   3. Cliquez sur Tout faire expirer.
   4. Dans la fenêtre pop-up d’avertissement, cliquez sur OK et confirmez que vous comprenez ce que cela implique.

* **Afficher uniquement les mesures Dernière touche à partir du moment où vous avez corrigé les règles** : les mesures Dernière touche suivent toujours l’ensemble de règles actuelles. L’affichage du moment à partir duquel vous avez modifié les règles de traitement reflète les règles de traitement les plus récentes.
