---
description: Les rapports de source de trafic vous donnent une vue détaillée des visiteurs et de la façon dont ils interagissent avec votre site Web.
title: Rapports sur les sources de trafic
topic: Ad hoc analysis
uuid: 246afbdc-9f7b-4956-a44a-b7aad948f392
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Rapports sur les sources de trafic

Les rapports de source de trafic vous donnent une vue détaillée des visiteurs et de la façon dont ils interagissent avec votre site Web.

## Rapports sur les sources de trafic {#concept_0F1772141E1345C5BCF63BE7C544C0CB}

Les rapports de source de trafic vous donnent une vue détaillée des visiteurs et de la façon dont ils interagissent avec votre site Web.

Ils permettent :

* d’analyser les aspects critiques du comportement des visiteurs ;
* de surveiller et de comprendre les schémas de trafic ;
* de déterminer quel est le contenu le plus populaire du site ;
* de segmenter les visiteurs en fonction de critères mesurables.

**Persistance commune**

Dans [!UICONTROL Sources de trafic], toutes les valeurs de rapport sont persistantes et reçoivent du crédit jusqu’à ce qu’elles soient remplacées ou jusqu’à la fin de la visite, selon la condition qui se présente en premier. Auparavant, seuls les mots-clés et les domaines référents étaient persistants. Par exemple, si un visiteur recherche dans Google « DVD », qui l’amène sur votre site pour tout achat de 100 $, le rapport alloue un crédit de 100 $ au mot-clé « DVD » ainsi qu’au moteur de recherche Google. Cette fonctionnalité est inaltérable, quels que soient les paramètres d’[!DNL Admin Console].

## Mots-clés de recherche {#concept_071FDCBD0A3B4242BA00744786D1C59C}

Affiche une ventilation des mots-clés pour toutes les recherches, les recherches payantes et les recherches naturelles.

<!-- 

c_reports_search_keyword.xml

 -->

**[!UICONTROL Mots-clés de recherche – Tous]** : ce rapport répertorie chaque mot-clé de recherche qui a été utilisé pour trouver votre site. Vous pouvez trier cette liste par pages vues ou mots-clés de recherche en cliquant sur le titre de la colonne. Cliquez sur la loupe en regard d’un mot-clé de recherche afin d’afficher les écrans de résultats pour votre site.

**[!UICONTROL Mots-clés de recherche – Payée]** : répertorie les mots-clés de recherche payante qui ont été utilisés pour trouver votre site. Vous pouvez trier cette liste par pages vues ou mots-clés de recherche en cliquant sur le titre de la colonne. Cliquez sur la loupe en regard d’un mot-clé de recherche afin d’afficher les écrans de résultats pour votre site.

**[!UICONTROL Mots-clés de recherche – Naturelle]** : répertorie les mots-clés de recherche naturelle qui ont été utilisés pour trouver votre site. Vous pouvez trier cette liste par pages vues ou mots-clés de recherche en cliquant sur le titre de la colonne. Cliquez sur la loupe en regard d’un mot-clé de recherche afin d’afficher les écrans de résultats pour votre site.

## Moteurs de recherche {#concept_351CDE4F5FC44371B6B657064E125134}

Affiche les moteurs de recherche que les visiteurs ont utilisés pour effectuer tout type de recherche, des recherches payantes et des recherches naturelles.

<!-- 

c_reports_search_engines.xml

 -->

**[!UICONTROL Moteurs de recherche - Tous]** : répertorie les moteurs de recherche que les visiteurs utilisent pour trouver votre page Web. Le graphique présente la répartition en pourcentage des moteurs de recherche qui sont utilisés pour trouver votre site.

**[!UICONTROL Moteurs de recherche - Payés]** : répertorie les moteurs de recherche avec mots-clés payés que les visiteurs utilisent pour trouver votre page Web. Le graphique présente la répartition en pourcentage des moteurs de recherche qui sont utilisés pour trouver votre site.

**[!UICONTROL Moteurs de recherche - Naturelle]** : affiche les moteurs de recherche avec mots-clés naturels que les visiteurs utilisent pour trouver votre page Web. Le graphique présente la répartition en pourcentage des moteurs de recherche qui sont utilisés pour trouver votre site.

## Domaines référents {#concept_804614DF21C14C9FB542451B30F92788}

<!-- 

c_reports_ref_domains.xml

 -->

Indique les domaines de référence des clients qui ont eu le plus d’impact sur les mesures de succès de votre site. Les référents se répartissent en deux catégories principales : domaines et URL. Les domaines se réfèrent au nom de domaine et apparaissent comme le domaine de base sans la chaîne de requête ou les sous-répertoires attachés. Les URL incluent le nom de domaine de base, ainsi que les chaînes de requête ou sous-répertoires.

## Domaines référents d’origine {#concept_EB18251DF70343169B46BB59543A579A}

<!-- 

c_reports_original_ref_domains.xml

 -->

Affiche les référents initiaux qui ont produit les clients de votre site. Les clients peuvent se rendre sur votre site à plusieurs reprises et disposent d’un référent différent à chaque visite. Ce rapport présente la manière dont ils ont été référés la première fois qu’ils sont arrivés sur le site. Vous pouvez ainsi savoir s’ils ont continué à utiliser le même domaine référent et déterminer leurs schémas de renvoi à votre site. Vous pouvez afficher le nombre de visiteurs générés par un référent initial ou découvrir le montant des recettes générées par chaque référent initial. Les rapports Référent peuvent être créés chaque fois qu’un visiteur arrive sur le site, même s’il le fait à plusieurs reprises lors d’une même session (avant l’expiration de la visite).

## Référents {#concept_40CF9C2D10B94E82819BC65A232F05C3}

Affiche le domaine ou l’URL de provenance des visiteurs avant qu’ils arrivent sur votre site, les méthodes utilisées par les visiteurs pour trouver votre site web et le nombre de visites sur votre site qui proviennent de ces référents.

<!-- 

c_reports_referrers.xml

 -->

Si, par exemple, un visiteur clique sur un lien du Site A et arrive sur votre site, le Site A est le référent s’il n’est pas défini comme faisant partie de votre domaine. Lors de la mise en œuvre des Reports and Analytics marketing, votre conseiller peut vous aider à définir les domaines et adresses URL qui font partie de votre site Web. (Notez que cette modification peut être effectuée après la mise en œuvre.)

Les domaines ou URL ne faisant pas partie de ces domaines et URL définis sont considérés comme des référents. Par exemple, les pages Web A et Web B sont ajoutées au filtre URL interne, mais la page web C ne l’est pas. Dans ce cas, la page web C est considérée comme un référent.

Pour plus d’informations, voir la rubrique [Filtres URL internes](https://marketing.adobe.com/resources/help/fr_FR/reference/internal_URL_filter_admin.html) dans l’aide d’[!DNL Admin Console].

> [!NOTE] Les rapports et analyses marketing considèrent un domaine référent comme adresse e-mail lorsque les visiteurs cliquent sur un lien de message envoyé par e-mail contenant le protocole [!DNL imap://] ou [!DNL mail://] et arrivent sur votre site. Par exemple, les messages provenant de [!DNL https://mail.yahoo.com] ne sont pas considérés comme des référents « courriel », car le protocole est [!DNL https://]. Les courriels d’Outlook sont signalés dans la ligne Tapé/Marqué, alors que les référents avec un protocole HTTP où le domaine est un moteur de recherche connu sont signalés dans la ligne Moteur de recherche.

## Type de référent {#concept_689E42D8F96C450DA41C7167C7388198}

En suivant et en enregistrant les sites de référence des visiteurs pour chaque visite, vous pouvez déterminer de quelle façon les visiteurs sont parvenus sur votre site pour chaque visite.

<!-- 

c_reports_ref_types.xml

 -->

La liste ci-dessous définit les divers types de référents :

* *D’autres référents de site Web* sont enregistrés lorsque les visiteurs cliquent sur un lien figurant sur la page d’un autre site (non défini comme faisant partie de votre site) et arrivent sur votre site.
* Les référents de *moteur de recherche* sont enregistrés lorsque les visiteurs utilisent un moteur de recherche pour accéder à votre site.
* Les référents *tapés/marqués* sont enregistrés :

   * si un visiteur accède à votre site par le biais d’un lien hors navigateur (par exemple, dans un courriel) ;
   * si un visiteur saisit directement l’URL de votre site dans son navigateur ;
   * si un visiteur clique sur un lien HTML sur son disque dur personnel ;
   * si un visiteur accède à votre site en le sélectionnant parmi les signets de son navigateur.

**Définitions**

Les options suivantes peuvent s’afficher lors de l’exécution de ce rapport :

**Dans votre site** : ces éléments sont des URL balisées par les filtres URL internes. Ces éléments ne sont pas comptabilisées comme instances de référence, mais elles sont visibles lors de la génération de rapports sur d’autres mesures.

**Pas de JavaScript** : le type n’était pas identifiable (connu) en l’absence de code JavaScript. Cela signifie que le client n’a fourni aucune information de référence sur un navigateur, lequel ne fait pas état de son aptitude à prendre en charge JavaScript. Ces instances ne sont pas comptabilisées comme « instances de référence », mais elles sont visibles lors de la génération de rapports sur d’autres mesures.

**USENET (groupes de discussion)** : cela signifie que l’URL d’un référent commençait par `news://`. Dès lors, le lien de référence a été publié sur un groupe de discussion Usenet plutôt que sur une page Web.

> [!NOTE] La logique Type de référent correspond à d’autres rapports de sources de trafic (tels que [!UICONTROL Référents] et [!UICONTROL Domaines référents]). Cela devrait réduire, voire éliminer, les occurrences d’éléments Dans votre site et Pas de JavaScript dans le rapport [!UICONTROL Type de référent].

