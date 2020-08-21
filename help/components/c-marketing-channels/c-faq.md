---
title: FAQ sur les Canaux marketing
description: Questions fréquentes sur les canaux marketing.
translation-type: tm+mt
source-git-commit: 89c91aa7620eaba3d24e3d5de4055609c472f9f7
workflow-type: tm+mt
source-wordcount: '1465'
ht-degree: 59%

---


# FAQ sur les Canaux marketing

Questions fréquentes sur les canaux marketing.

## Mes codes de suivi ne suivent pas de schéma, et j&#39;en ai des milliers qui doivent être spécifiées pour mon canal Affiliés.

* Procédez par élimination. Si les canaux Courriel et Affilié utilisent le même paramètre de chaîne de requête, mais que vous n’avez que quelques codes de suivi, vous pouvez spécifier les codes de suivi par courriel dans un ensemble de règles définissant le courriel. Vous classez ensuite tous les autres codes de suivi avec  *`affiliates.`*
* Dans votre système de messagerie, ajoutez un paramètre de chaîne de requête à toutes les URL de page d’accueil, comme *`&ch=eml`*. Créez un ensemble de règles qui détectera si le paramètre de requête ch est égal à *`eml`*. S’il ne contient pas *`eml`*, il s’agit d’un affilié.

## Les domaines référents contiennent plus de données que prévu.

* Les domaines référents peuvent se trouver trop haut dans la liste des règles de traitement. Il doit s’agit de l’un des derniers ensembles de règles (ou du dernier), parce que l’ordre de traitement est important.

## J&#39;ai créé une règle qui correspond à un paramètre de chaîne de requête et elle ne fonctionne pas.

* Assurez-vous que le nom du paramètre est spécifié dans les champs de paramètre de chaîne de requête (généralement sous la forme d’une valeur alphanumérique). Vérifiez également que la valeur du paramètre est spécifiée après l’opérateur, comme indiqué dans l’exemple suivant illustrant une règle de courriel.

   ![](assets/example_email.png)

## Pourquoi tout mon trafic Dernière touche est-il attribué à un domaine interne ?

* Vous avez une règle qui correspond au trafic interne. N’oubliez pas que ces règles traitent chaque accès d’un visiteur à votre site, et pas seulement sa première visite. Dans le cas d’une règle telle que  *`Page URL exists`* sans aucun autre critère, une correspondance est établie avec ce canal lors de chaque visite successive sur votre site, car il existe toujours une URL de page.

## Comment déboguer le trafic qui s’affiche dans Aucun Canal identifié sur le rapport ?

* Les règles sont traitées dans l’ordre. Si aucun critère spécifique n’a de correspondance, les visites sont incluses dans l’une de trois catégories :

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

L’option Dernière touche interne (actualisation de la session) ne peut se produire que si elle était également la première touche - voir &quot;Relation entre la première et la dernière touche&quot; ci-dessus. Les scénarios ci-dessous expliquent comment l’actualisation de session peut être un canal Première touche.

* **Délai d’expiration** de la session : Un visiteur se rend sur le site Web, puis laisse l’onglet ouvert dans son navigateur pour l’utiliser ultérieurement. La période d’engagement du visiteur expire (ou bien il supprime volontairement ses cookies) et il utilise l’onglet ouvert pour se rendre à nouveau sur le site Web. L’URL de référence étant un domaine interne, la visite est classée comme Actualisation de session.

* **Toutes les pages du site ne sont pas balisées**: Un visiteur arrive à la page A qui n’est pas balisée, puis passe à la page B qui est balisée. La page A serait considérée comme le référent interne et la visite serait classée comme Actualisation de session.

* **Redirections**: Si une redirection n’est pas configurée pour transmettre des données de parrain au nouveau landing page, les véritables données du parrain d’entrée sont perdues et la page de redirection (probablement une page interne) s’affiche désormais comme domaine référent. La visite sera classée comme Actualisation de session.

* **Trafic** inter-domaines : Un visiteur passe d’un domaine qui se déclenche à la suite A, à un second domaine qui se déclenche à la suite B. Si, dans la Suite B, les filtres d’URL internes incluent le premier domaine, la visite dans la Suite B est enregistrée comme interne, puisque les Canaux marketing considèrent qu’il s’agit d’une nouvelle visite dans la deuxième suite. La visite sera classée comme Actualisation de session.

* **Délais** de chargement des pages d&#39;entrée longs : Un visiteur arrive sur la page A, qui contient beaucoup de contenu, et le code Adobe Analytics se trouve au bas de la page. Avant que tout le contenu (y compris la demande d’images Adobe Analytics) puisse être chargé, le visiteur clique sur la page B. La page B déclenche sa demande d’images Adobe Analytics. Comme la demande d’images de la page A n’a jamais abouti, la deuxième page apparaît comme le premier accès de la visite dans Adobe Analytics, avec la page A comme référent. La visite est classée comme Actualisation de session.

* **Effacement des cookies au milieu du site**: Un visiteur se rend sur le site et efface les cookies en milieu de session. Les canaux Première touche et Dernière touche seront réinitialisés et la visite sera classée comme Actualisation de session (car le référent est interne).

Voici un exemple de canal interne (actualisation de session) défini comme premier et dernier  tactile :

* Jour 1 : l’utilisateur accède au site par le biais de l’Affichage. Les canaux Première touche et Dernière touche seront définis sur Affichage.
* Jour 2 : l’utilisateur se rend sur le site par le biais d’une Recherche naturelle. La première touche reste sur Affichage et la dernière touche est définie sur Recherche naturelle.
* Jour 35 : l’utilisateur ne s’est pas rendu sur le site depuis 33 jours et y retourne en utilisant l’onglet qu’il a ouvert dans son navigateur. En supposant une fenêtre d’engagement de 30 jours, la fenêtre se serait fermée et les cookies Marketing Channel auraient expiré. Les canaux Première touche et Dernière touche seront réinitialisés et seront définis sur Actualisation de session puisque l’utilisateur provient d’une URL interne.

## Pourquoi certains canaux restent-ils inchangés après avoir modifié les règles de traitement du canal marketing ?

Parfois, les règles de traitement du Canal marketing sont mal configurées, ce qui rend nécessaire de modifier les règles de traitement. Après avoir appliqué les modifications, vous pouvez voir que certaines mesures attribuent toujours des données à un canal incorrect. Il y a plusieurs points à prendre en compte :

* **Les données du Canal marketing sont collectées en temps** réel : Les données du canal marketing sont traitées lors de la collecte des données et sont permanentes à 100 %. La modification des règles de traitement n’affecte pas les données rétroactivement.
* **La modification des règles de traitement n’affecte pas immédiatement les données** Première touche : Par exemple :
   1. Un utilisateur arrive par l’intermédiaire de votre canal électronique, car il a été configuré de manière incorrecte, puis quitte votre site.
   2. Le lendemain, vous modifiez la règle de traitement du courrier électronique pour la corriger.
   3. Cet utilisateur revient plusieurs jours plus tard par la recherche naturelle et fait un achat.
   4. Le canal de messagerie reçoit le crédit Première touche et la recherche naturelle reçoit le crédit Dernière touche.

   Même plusieurs jours après avoir modifié vos règles de traitement, les données peuvent toujours être collectées dans le mauvais canal Première touche. Les données Première touche sont continuellement collectées dans un canal incorrect jusqu’à l’expiration de l’engagement visiteur de tous les utilisateurs.

La meilleure façon de remédier à ces écarts est de procéder à l&#39;une des actions suivantes, ou aux deux :

* **expirer manuellement toutes les périodes** d’engagement des visiteurs : Ce paramètre expire instantanément tous les canaux Première touche et Dernière touche de tous les visiteurs :
   1. Accédez à Outils d’administration > Report Suites.
   2. Placez le pointeur de la souris sur Paramètres de modification de l’image > Canaux marketing > Expiration de l’engagement des Visiteurs
   3. Cliquez sur Expire tout.
   4. Cliquez sur OK dans la fenêtre contextuelle d’avertissement, en reconnaissant que vous comprenez ce qu’elle va faire.

* **Seules les mesures Dernière touche de vue à partir du moment où vous avez redéfini** vos règles : Les mesures Dernière touche suivent toujours l’ensemble de règles actuel. L’affichage de l’heure à partir de laquelle vous avez modifié les règles de traitement reflète correctement les règles de traitement les plus récentes.
