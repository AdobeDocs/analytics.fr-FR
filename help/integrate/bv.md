---
title: Intégration de Brand Visibility
description: Intégration de Brand Visibility à Adobe Analytics
role: User
source-git-commit: 8a2a4637f21bbbe02ea88292d2ca503f4c667ebc
workflow-type: tm+mt
source-wordcount: '2637'
ht-degree: 1%
---

# Intégration de Adobe Brand Visibility

[&#128279;](https://experienceleague.adobe.com/fr/docs/llm-optimizer/using/home) est une application IA générative pour l&#39;optimisation du moteur de génération, conçue pour aider les marques à améliorer leur visibilité, leur précision et leur influence dans les environnements de recherche pilotés par l&#39;IA. Brand Visibility fournit des informations sur la présence des marques dans les réponses générées par l’IA, propose des recommandations de contenu prescriptives et automatise les correctifs d’optimisation.

L’IA est devenue un canal de découverte essentiel. Les agents de grands modèles linguistiques (LLM), tels que ChatGPT, Claude, Copilot et Perplexity, explorent le contenu de la marque.

>[!NOTE]
>
>Visibilité des marques était auparavant appelée **LLM Optimizer (LLMO)**. Il se peut que certains documents Adobe continuent à utiliser l’ancienne terminologie LLMO pendant la transition.


>[!PREREQUISITES]
>
>Vous devez disposer d’une offre de paiement par Visibilité des marques configurée et connectée à votre configuration Experience Platform par le biais du connecteur géré.


>[!IMPORTANT]
>
>Dans le cadre de cette intégration, certains traitements temporaires des données de Brand Visibility sont effectués aux États-Unis. Les données sont finalement stockées dans la région désignée comme configurée dans votre contrat Adobe Analytics.

Si vous utilisez Customer Parcours Analytics, une intégration entrante distincte et plus riche reçoit les mêmes données de trafic CDN sous-jacentes dans Customer Journey Analytics via Adobe Experience Platform. Cette intégration est désormais disponible. Voir Intégration de [Brand Visibility à Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/integrations/bv). Si vous disposez de Customer Journey Analytics, passez d’abord en revue cette intégration, car elle expose plus de champs et prend en charge la jonction des données Brand Visibility avec d’autres jeux de données. L’intégration d’Analytics décrite dans ce guide est conçue pour les clients qui utilisent Adobe Analytics sans avoir accès à ou disposer d’une licence pour Customer Journey Analytics.


## Cas d’utilisation

L’intégration entre Adobe Analytics et Brand Visibility peut vous être bénéfique de deux manières :

* **Intégration entrante** : utilisez les données Brand Visibility dans Adobe Analytics pour mesurer le trafic piloté par LLM (robots d&#39;exploration de robots, requêtes RAG, activité d’agent) avec les données web et mobiles existantes. Par exemple, vous pouvez effectuer les opérations suivantes :

  * Mesurez le trafic piloté par LLM par la source de l’agent avec les canaux traditionnels.

  * Identifier le contenu fortement consommé par les LLM, mais dont les performances sont insuffisantes pour la conversion humaine.

  * Détecter où les requêtes LLM-agent échouent sur les chemins critiques.

  * Comparez la demande des robots LLM pour une page aux conversions et au chiffre d’affaires de cette page dans vos données web, mappées au niveau de l’URL et de l’hôte.

* **Intégration sortante** : envoyez les données de performances Adobe Analytics dans Brand Visibility afin d’optimiser la visibilité de l’IA pour les sources LLM qui vous envoient un trafic important, comme le ChatGPT ou la Perplexité. Par exemple, vous pouvez effectuer les opérations suivantes :

  * Découvrez les sources LLM qui envoient des visiteurs humains qui convertissent ou génèrent des recettes. Adobe Analytics le mesure à partir du trafic web référencé, et non du jeu de données de robots.
  * Classez les sources LLM par la valeur en aval des visiteurs humains qu’elles envoient, puis concentrez votre travail de visibilité de l’IA sur les sources qui présentent les meilleures performances.


## Intégration entrante

Cette section décrit les conditions préalables et les étapes de configuration pour l&#39;intégration entrante **Adobe Brand Visibility → Adobe Analytics**.


Le connecteur Adobe Analytics entrant est configuré par suite de rapports via le **Gestionnaire de suites de rapports**, comme décrit dans la section 6.

>[!PREREQUISITES]
>
>Les journaux d’accès au réseau CDN doivent déjà être transférés et reçus par Adobe Brand Visibility pour chaque site Brand Visibility avant que le connecteur Brand Visibility → Adobe Analytics puisse être activé.
>
>Cette exigence s&#39;applique **par site de Visibilité des marques**. Une configuration de réseau CDN ou un flux de journal pour un site, un domaine ou un sous-domaine ne doit pas être supposé couvrir un autre site, sauf si Adobe confirme cette couverture.
>
>
>Avant d’activer le connecteur, vérifiez les points suivants :
>
>1. Le réseau CDN ou le pipeline de journal approprié est configuré pour transférer les journaux d’accès requis vers la destination fournie par Adobe.
>1. La visibilité des marques a confirmé que les journaux sont reçus et détectés pour le site concerné.
>1. Les données sont visibles dans le tableau de bord de trafic de Brand Visibility Agentic pour ce site.
>
>Le transfert de journal BYOCDN fournit les données de requête CDN côté serveur utilisées pour l’analyse du trafic de l’agent. Les données ne dépendent pas des balises JavaScript exécutées dans un navigateur. Sans le flux de journal CDN requis, le connecteur ne dispose d’aucune donnée de trafic à importer dans votre suite de rapports.
>
>Voir [Référence du transfert de journal BYOCDN](https://experienceleague.adobe.com/en/docs/brand-visibility/using/log-forwarding/log-forwarding-overview) pour plus d’informations.


>[!IMPORTANT]
>
>Dans le cadre de cette intégration, certains traitements temporaires des données de Brand Visibility sont effectués aux États-Unis. Les données sont finalement stockées dans la région désignée comme configurée dans votre contrat Adobe Analytics.


### Fonctionnement

La Visibilité des marques entrante → l’intégration d’Adobe Analytics ajoute un ensemble de **variables réservées** à votre suite de rapports. Ces variables contiennent des données de niveau résumé sur le trafic de robots et d’agents automatisés détecté sur votre site web, y compris le trafic basé sur LLM, provenant des mêmes journaux d’accès au réseau CDN que ceux décrits dans les [conditions préalables](#inbound-integration).

Ce trafic n’exécute généralement pas les balises JavaScript du navigateur et n’est pas capturé par le biais de votre implémentation Adobe Analytics existante. Les variables réservées vous permettent de voir ce trafic dans la même suite de rapports que celle que vous utilisez déjà pour votre site.

Les variables réservées suivantes sont ajoutées lorsque le connecteur est activé :

| Signalé comme | Type | Notes |
|---|---|---|
| URL | Dimension | URL de page associée à la requête. |
| Type de robot | Dimension | Type de robot ou d’agent automatisé qui a émis la requête (par exemple, un robot d&#39;exploration d’IA nommé). |
| Agent utilisateur | Dimension | Chaîne de l’agent utilisateur signalée par le robot ou l’agent. |
| État | Dimension | Code d’état HTTP renvoyé pour la requête. |
| Referer | Dimension | Valeur du référent HTTP de la requête, le cas échéant. |
| Demandes | Mesure | Le nombre de requêtes de réseau CDN à la fois électroniques et électroniques. |


#### Couverture par rapport à Customer Journey Analytics

L’intégration entrante de CJA repose sur un jeu de données Résumé des requêtes de réseau CDN plus large et prend en charge des champs supplémentaires (par exemple, hôte et fournisseur de réseau CDN) ainsi que la jointure avec d’autres jeux de données dans Customer Journey Analytics. L’intégration d’Adobe Analytics est un ensemble plus petit de variables réservées, natives dans la suite de rapports, conçu pour fonctionner dans le modèle de données existant d’Analytics. Si vos besoins de création de rapports dépassent les champs répertoriés ci-dessus, évaluez l’intégration de CJA.

#### Limites importantes

- Aucune donnée d’identifiant visiteur, d’ECID, de visites ou d’utilisateur unique n’est incluse. Il s’agit de données récapitulatives agrégées, non liées au visiteur.
- Les variables réservées ne prennent pas en charge les paramètres de type d’attribution ou de type d’expiration, puisqu’elles ne sont pas liées à un visiteur.
- Les données ne peuvent pas être jointes à d’autres jeux de données ou dimensions Analytics de la même manière que dans Customer Journey Analytics.
- Utilisez la mesure **Demandes** pour mesurer le volume de trafic des robots et des agents. Ne l’utilisez pas de manière interchangeable avec les mesures basées sur les visites ou les accès situées ailleurs dans votre suite de rapports.

L’ensemble exact de champs disponibles doit être confirmé par rapport à la configuration des variables de votre suite de rapports une fois que le connecteur est activé.

### Responsabilités

L’installation et la configuration du connecteur entrant s’accompagnent de responsabilités pour [&#128279;](#adobe-managed-responsibilities) et [vous en tant que client](#customer-owned-responsibilities).

#### Responsabilités gérées par Adobe

1. Détecte et confirme le transfert du journal CDN pour chaque site de Visibilité des marques intégré.
2. Rend les variables réservées disponibles pour l’approvisionnement une fois que le transfert du journal BYOCDN est confirmé.
3. Exécute le renvoi de 90 jours et la synchronisation horaire continue une fois que le connecteur est activé pour une suite de rapports.

#### Responsabilités détenues par le client

1. Réalisation de l’intégration à Brand Visibility et du transfert des journaux BYOCDN pour chaque site.
2. Les données de confirmation sont visibles dans le tableau de bord Trafic d’agent de Visibilité des marques avant d’activer le connecteur.
3. Choisir la suite de rapports à laquelle chaque site de Visibilité des marques de données se connecte (un site par suite de rapports).
4. Activation du connecteur via le Gestionnaire de suites de rapports.
5. Créer des rapports, des segments ou des vues de données (le cas échéant) qui utilisent les variables réservées répertoriées dans [Fonctionnement](#how-it-works).

### Avant de commencer

Confirmez les points suivants avant d’activer le connecteur :

- Vous avez terminé l’intégration à Adobe Brand Visibility pour le site auquel vous souhaitez vous connecter.
- Le transfert du journal BYOCDN est configuré et confirmé pour ce site (voir [conditions préalables](#inbound-integration)).
- Les données s’affichent dans le tableau de bord de trafic de Adobe Brand Visibility Agent pour ce site.
- Vous savez à quelle suite de rapports vous souhaitez connecter le site.

Chaque site Adobe Brand Visibility se connecte à une seule suite de rapports. Si vous souhaitez importer des données pour plusieurs sites de Visibilité des marques de données, connectez chaque site à une suite de rapports distincte.


### Activer le connecteur

Le connecteur est activé et désactivé à partir du menu **Modifier les paramètres** de la suite de rapports.

Pour ouvrir les paramètres Adobe Brand Visibility de votre suite de rapports :

1. Connectez-vous à Adobe Analytics.
1. Accédez à **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]**.
1. Sélectionnez la suite de rapports à laquelle vous souhaitez vous connecter.
1. Sélectionnez **[!UICONTROL Modifier les paramètres]**.
1. Dans le menu contextuel, sélectionnez **&#x200B;**.

Pour configurer le connecteur :

1. Sélectionnez **Configurer Adobe Brand Visibility Data Connector**.
1. Passez en revue les dimensions et les mesures qui seront ajoutées à cette suite de rapports (répertoriées dans [Fonctionnement](#how-it-works)).
1. Sous **Sélectionner le site Adobe Brand Visibility**, choisissez le site auquel se connecter à cette suite de rapports. Une fois connecté, le résumé des données du site se synchronise avec cette suite de rapports toutes les heures.
1. Sélectionnez **Activer**.

   Une fois activées, ces variables ne peuvent pas être supprimées de cette suite de rapports. L’activation du connecteur lance un renvoi de 90 jours, important les 90 derniers jours de données Adobe Brand Visibility dans cette suite de rapports.

   Avant d’activer le connecteur, vérifiez que vous avez terminé les étapes décrites dans [Avant de commencer](#before-you-start). Cela inclut la vérification que les données s’affichent déjà dans votre tableau de bord de trafic Adobe Brand Visibility Agentic.

Après avoir activé le connecteur, attendez que le renvoi initial et la première synchronisation horaire se terminent. Confirmez ensuite que les variables réservées mentionnées dans [Fonctionnement](#how-it-works) sont renseignées dans votre suite de rapports. voir la section 8, étape 3).

### Désactivation du connecteur

>[!WARNING]
>
>La désactivation du connecteur est **irréversible**. La désactivation arrête la synchronisation horaire et supprime les données Adobe Brand Visibility historiques de cette suite de rapports.

Pour désactiver le connecteur :

1. Accédez à **Admin → Report Suites → Edit Settings → Adobe Brand Visibility**.
1. Sélectionnez **Déconfigurer le connecteur de données Adobe Brand Visibility**.
1. Vérifiez que le site Adobe Brand Visibility répertorié est celui que vous avez l’intention de déconnecter.
1. Sélectionnez **Désactiver**.
1. Confirmez l’avertissement.

Si vous souhaitez uniquement suspendre temporairement la création de rapports, ne désactivez pas le connecteur. Contactez votre équipe de compte Adobe pour discuter des options permettant de suspendre la création de rapports avant de les désactiver.

### Paramétrer les critères d&#39;achèvement

L’intégration entrante est prête pour le compte rendu des performances lorsque tous les éléments suivants sont confirmés :

* Les journaux CDN sont transférés et reçus par Adobe Brand Visibility pour le site.
* Les données sont visibles dans le tableau de bord Trafic agent Adobe Brand Visibility pour le site.
* Le connecteur a été activé pour la suite de rapports prévue via le Gestionnaire de suites de rapports.
* Le renvoi initial et au moins une synchronisation horaire sont terminés.
* Les variables réservées de la section 4 renvoient les valeurs attendues dans les rapports.

### Procédure de vérification

La procédure de vérification comprend les étapes suivantes :

1. Confirmez la préparation du site de Visibilité des marques et du journal CDN :

   * Confirmez le site ou le domaine exact sur lequel vous souhaitez vous connecter.
   * Vérifiez que les journaux CDN sont transférés pour ce site et que la Visibilité des marques a confirmé leur réception.
   * Vérifiez que les données sont visibles dans le tableau de bord du trafic d’agent pour ce site.

1. Vérifiez que le connecteur est activé :

   1. Accédez à **Admin → Suites de rapports → Modifier les paramètres → Adobe Brand Visibility** pour la suite de rapports cible.
   1. Confirmez que la page affiche le connecteur comme activé et répertorie le site de Visibilité des marques connecté.

1. Confirmer les données dans les rapports :

   1. Ouvrez Analysis Workspace (ou votre workflow de création de rapports standard) par rapport à la suite de rapports connectée.
   1. Créez un tableau ou une visualisation à l’aide de la mesure **Demandes** répartie par **Type de robot**.
   1. Le volume Confirmer la demande s’affiche pour une période récente.
   1. Confirmez que les dimensions **URL**, **Agent utilisateur**, **Statut** et **Référent** renvoient les valeurs attendues.

   L’heure exacte de l’affichage des données dépend du planning de renvoi et de synchronisation décrit dans la section [&#x200B; Activer le connecteur &#x200B;](#enable-the-connector).



### Résolution des problèmes

Consultez les problèmes suivants et comment résoudre ces problèmes.

| Problème | Résoudre des problèmes |
|---|---|
| Le connecteur ne s’active pas ou la liste des sites est vide. | Vérifiez si :<ul><li>L’intégration de Adobe Brand Visibility est terminée pour le site.</li><li>Le transfert du journal BYOCDN est configuré et confirmé pour le site.</li><li>Vous travaillez dans la bonne suite de rapports.</li></ul> |
| Le connecteur est activé mais aucune donnée n’apparaît. | Vérifiez si : <ul><li>Les données sont visibles dans le tableau de bord Trafic agent pour le site connecté (si ce n’est pas le cas, le problème est en amont d’Analytics).</li><li>Un délai suffisant s’est écoulé pour le renvoi initial de 90 jours et au moins une synchronisation horaire.</li><li>- La période sélectionnée dans votre rapport comprend une période postérieure à l’activation du connecteur.</li></ul> |
| Les données semblent incomplètes ou inattendues. | Vérifiez si : <ul><li>La suite de rapports ne devrait pas non plus recevoir de données pour un site de Visibilité des marques de données différent (chaque suite de rapports se connecte à un site exactement).</li><li>Vous lisez la mesure **Demandes** plutôt que de compter les lignes ou les accès à un autre endroit de la suite de rapports.</li><li>Les dimensions que vous consultez correspondent à la liste de la section 4 ; les evars ou événements non liés dans la même suite de rapports ne font pas partie de cette intégration.</li></ul> |

>[!MORELIKETHIS]
>
>[Référence d&#39;intégration Visibilité des marques/LLMO](https://experienceleague.adobe.com/en/docs/analytics-platform/using/integrations/bv)
>[Référence du transfert du journal BYOCDN](https://experienceleague.adobe.com/en/docs/brand-visibility/using/log-forwarding/log-forwarding-overview)

## Notes de rédaction pour les documents (à ne pas publier)

Cette section est destinée à un examen interne et doit être supprimée avant publication.

- **Source de vérité utilisée :** les noms de champ, la liste de variables réservées et le workflow Gestionnaire de suites de rapports proviennent de [AN-468884](https://jira.corp.adobe.com/browse/AN-468884) (David Wardell, statut Nouveau à partir du 2026-08-28), qui est plus à jour et plus spécifique que la demande de documentation d’origine [AN-449989](https://jira.corp.adobe.com/browse/AN-449989) (Rob In der Maur, statut Nouveau). La copie de page pour les écrans de provisionnement/déprovisionnement incorpore les affinements du libellé de l&#39;examen interne 2026-08-28 (`2026-08-28-an468884-abv-report-suite-ui-review.md`), qui a remplacé l&#39;abréviation « ABV » du ticket brut par « Adobe Brand Visibility » dans le texte destiné aux clients.
- **Incohérence de l’ensemble de champs à réconcilier avant la publication :** la liste des dimensions d’origine d’AN-449989 était Hôte, URL/Chemin de page, Fournisseur de réseau CDN, Agent utilisateur et Type de robot LLM, avec une seule mesure Nombre de requêtes agents. La liste réelle de variables réservées d’AN-468884 est URL, type de robot, agent utilisateur, statut et référent, avec un seul événement Requests. L’hôte et le fournisseur de réseau CDN ne sont pas présents en tant que variables réservées distinctes dans AN-468884 ; le statut est nouveau. Ce brouillon suit AN-468884 comme faisant autorité selon le ticket fra, mais les deux doivent être réconciliés avec Aaron Kern / David Wardell avant que cela ne soit finalisé, car les noms de champ que les clients voient peuvent ne pas correspondre à ce que les équipes de compte ont décrit à l’aide de l’ancien langage AN-449989.
- **Pas encore confirmé, ne pas indiquer comme fait dans la version publiée :**
  - Date GA exacte. AN-431416 est compatible avec FixVersion H2 2026 (fenêtre de publication 2026-11-30) et possède le statut Exécuter à compter de 2026-09-01 ; AN-468884 (implémentation de la variable réservée) et AN-449989 (ce document) sont toujours nouveaux. Ne publiez pas tant que vous n’avez pas envoyé d’e-mail.
  - Indique si le type d’attribution/le type d’expiration sont entièrement supprimés sur les evars réservées en production. La révision 2026-08-28 a signalé qu’une suite de rapports de test affiche actuellement ces evars avec une affectation définie sur « Le dernier », qui peut être une valeur par défaut qui doit être effacée plutôt qu’un comportement final confirmé.
  - Le point d’entrée de l’API LLMO pour répertorier les sites ABV par organisation IMS (renseigne la liste déroulante de sélection de site) et l’API deprovision/disable étaient toujours en attente de la part de Joe Bass au moment du commentaire du ticket 2026-08-26.
  - Comparaison exacte entre le nombre de champs CJA. Le CJA des revendications de ticket d&#39;origine d&#39;AN-449989 a « 9 dimensions supplémentaires » et « 5 mesures supplémentaires », mais plusieurs d&#39;entre elles (compartiment de session LLM, nombre de sessions uniques LLM, nombre de doublons de demandes LLM) n&#39;ont pas été confirmées comme existant dans le groupe de champs `cdn-requests-summary` fourni au moment de la révision 2026-06-18. Pour cette raison, ce projet évite intentionnellement de citer des nombres spécifiques dans la comparaison CJA.
  - La cadence de synchronisation pour ce chemin d’accès AA est indiquée ici de manière horaire, en fonction de la langue du ticket d’AN-468884 (« exécuter des synchronisations horaires » / « processus de synchronisation horaire »). Cela n’a pas été validé indépendamment du comportement des sources de données AA de production tel que le rythme de CJA était.


## Intégration sortante

Ce guide ne couvre que l’intégration de la Visibilité des marques entrante, qui ajoute des données de trafic de robots et d’agents automatisés à une suite de rapports Analytics. La documentation d’intégration publiée décrit également une direction sortante, dans laquelle les données de performances Analytics sont mises à la disposition de Brand Visibility dans le produit Brand Visibility. Cette orientation n&#39;entre pas dans le cadre du présent guide. Consultez la documentation de la Visibilité des marques [&#128279;](https://experienceleague.adobe.com/en/docs/brand-visibility/using/resources/adobe-analytics-integration) pour plus d’informations sur l’intégration sortante.