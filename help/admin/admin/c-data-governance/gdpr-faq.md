---
description: FAQ sur la gouvernance des données Adobe Analytics
title: Questions fréquentes sur la gouvernance des données
feature: Data Governance
role: Admin
exl-id: 57399c1b-cf08-405b-8c1b-9d23e4c38716
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '2042'
ht-degree: 97%

---

# Questions fréquentes

+++ **Comment Adobe Analytics prend-il en charge les requêtes d’accès et de suppression pour les utilisateurs et utilisatrices finaux (Sujets de données) validées par les clientes et les clients (Contrôleurs de données) ?**

À compter de l’entrée en vigueur de plusieurs règles relatives à la Confidentialité des données (RGPD, CCPA), Adobe Analytics prendra en charge le traitement des demandes vérifiées soumises par les contrôleurs de données à l’API Data Privacy d’Experience Cloud pour favoriser l’automatisation du traitement. L’API relative à la Confidentialité des données d’Adobe Experience Cloud est conçue pour faciliter le traitement des requêtes individuelles de droits (par exemple, les requêtes d’accès et de suppression) pour les données de notre clientèle stockées dans les solutions Adobe Experience Cloud. Flexible, cette API s’adapte en fonction du nombre de demandes d’accès et de suppression de données que votre société reçoit des titulaires de données.

L’API Privacy Service permet également au client ou à la cliente de vérifier le statut du traitement des demandes d’accès et de suppression de données. Pour plus de détails, consultez la documentation de l’[API Privacy Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service/).

+++

+++ **Qui est la personne chargée de recevoir, d’accepter et de répondre aux requêtes relatives à la Confidentialité des données des utilisateurs et utilisatrices finaux ?**

Le contrôleur de données est seul responsable de la réception et de l’acceptation des demandes. Le contrôleur de données valide l’identité du ou de la titulaire de données, puis traite la demande. Une partie de cette responsabilité peut impliquer de contacter Adobe avec les identités des titulaires de données qui peuvent être associées aux données stockées dans Adobe Analytics.

En tant que responsable du traitement des données, Adobe doit fournir une assistance raisonnable au contrôleur pour traiter les demandes vérifiées dans un délai acceptable.

+++

+++ **Comment les clientes et clients d’Adobe (Contrôleurs de données) sauront-ils quelles requêtes relatives à la Confidentialité des données mappent à quels ID dans Adobe Analytics en vue du traitement en vertu de la Confidentialité des données ?**

Les contrôleurs de données détermineront comment résoudre la question de l’identité pour les demandes émanant des titulaires de données. Envisagez de déployer la balise de récupération des ID en vertu de la Confidentialité des données d’Adobe. Vos équipes de développement gagnent du temps en utilisant notre balise de récupération d’identifiant en vertu de la Confidentialité des données pour capturer les identifiants d’utilisateur ou d’utilisatrice (identifiants de cookie). Elles peuvent ensuite utiliser notre API de confidentialité des données pour envoyer ces identifiants d’utilisateur ou d’utilisatrice aux solutions appropriées dans Adobe Experience Cloud pour le traitement des demandes d’accès à des informations personnelles. L’API relative à la Confidentialité des données prend en charge un large éventail d’ID de clientes et clients dans de nombreuses solutions d’Adobe.

Si un titulaire de données soumet une demande avec un identifiant (variable personnalisée - prop ou eVar), Adobe Analytics effectue alors une recherche dans tout l’historique conservé des données collectées pour l’identifiant en question. Pour plus d’informations sur la configuration des identifiants personnalisés stockés dans les variables props ou eVars d’Analytics, reportez-vous à la [documentation d’Analytics sur les espaces de noms](/help/admin/admin/c-data-governance/data-labeling/gdpr-namespaces.md).

+++

+++ **Comment l’outil Gouvernance des données d’Adobe Analytics facilite-t-il le traitement des requêtes relatives à la Confidentialité des données ?**

Le nouvel outil Gouvernance des données d’Adobe Analytics permet aux contrôleurs de données d’appliquer des contrôles et des classifications de données à leurs données Analytics. Grâce à ce nouvel outil, les clients Adobe peuvent personnaliser le traitement de leurs demandes d’accès et de suppression des données en vertu de la Confidentialité des données. La console Gouvernance des données permet aux administrateurs de définir les paramètres à appliquer à différentes colonnes de données dans Adobe Analytics. Une fois ces étiquettes définies, Adobe traitera toutes les demandes d’accès ou de suppression en aval conformément aux paramètres d’étiquetage des clients. Le contrôleur de données est chargé de vérifier les paramètres d’étiquetage et de se concerter avec ses représentants et représentantes juridiques à ce sujet.

L’outil Gouvernance des données contient les étiquettes de données suivantes :

* **Étiquettes de données d’identité** : utilisées pour classer les données qui peuvent être utilisées seules ou en combinaison avec d’autres données pour identifier un individu. (Aucune, I1, I2)

* **Étiquettes de données sensibles** : utilisées pour classer les données en tant que données pouvant être définies comme sensibles en vertu de la loi en vigueur. (Aucune, S1, S2) Notez que, actuellement, l’utilisation des données sensibles dans Adobe Analytics est généralement interdite, excepté pour les données de géolocalisation précise obtenues légitimement en vertu de la loi applicable, qui peuvent être considérées comme des données sensibles dans certaines juridictions.

* **Étiquettes de données relatives aux informations personnelles** : utilisées pour définir les champs pouvant contenir des identifiants personnels à utiliser dans des demandes relatives aux informations personnelles ou qui doivent être supprimés dans le cadre d’une demande de suppression relative aux informations personnelles. Dans certains cas, ces étiquettes peuvent se superposer aux étiquettes de données d’identification et de données sensibles.

Pour plus d’informations sur les étiquettes de gouvernance des données, voir [Étiquettes de Confidentialité des données pour les variables Analytics](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md).

+++

+++ **Comment puis-je vérifier que les demandes Privacy Service fonctionnent correctement pour supprimer des données d’Adobe Analytics ?**

Généralement, les clients et clientes Analytics configurent des suites de rapports de test pour vérifier ses fonctionnalités avant sa commercialisation. Les sites web ou applications de pré-production envoient des données à ces suites de rapports de test/dev/QA afin d’évaluer la façon dont les choses fonctionnent quand le code est communiqué avant que le trafic réel ne soit envoyé aux suites de rapport de production.

Toutefois, avec une configuration normale, le traitement des requêtes en vertu du RGPD ne peut pas être testé sur ces suites de rapports de test avant d’appliquer les requêtes aux suites de rapports de production. Cela s’explique par le fait qu’une demande d’accès aux infomations personnelles est automatiquement appliquée à toutes les suites de rapports dans l’organisation Experience Cloud, qui correspond souvent à toutes les suites de rapports pour votre entreprise.

Néanmoins, il existe certaines façons de tester votre traitement des informations personnelles avant de l’appliquer à toutes vos suites de rapports :

* Vous pouvez par exemple configurer une organisation Experience Cloud séparée contenant uniquement les suites de rapports de test. Ensuite, utilisez cette organisation Experience Cloud pour votre test relatif à la Confidentialité des données et votre organisation Experience Cloud classique pour effectuer le véritable traitement.

* Une autre option consiste à attribuer des espaces de noms différents aux ID dans vos suites de rapports de test par rapport à ceux qui figurent dans vos suites de rapports de production. Par exemple, vous pouvez ajouter le préfixe « qa- » à chaque espace de noms dans vos suites de rapports de test. Lorsque vous soumettez vos demandes relatives à la Confidentialité des données avec uniquement des espaces de noms comportant le préfixe qa, ces demandes ne sont exécutées que par rapport à vos suites de rapports de test. Ensuite, lorsque vous soumettez vos demandes sans le préfixe qa, elles seront appliquées à vos suites de rapports de production. **Il s’agit de l’approche recommandée, sauf si vous utilisez les espaces de noms visitorId, AAID, ECID ou customVisitorId. Ces espaces de noms sont codés en dur et vous ne pouvez pas spécifier d’autres noms dans vos suites de rapports de test.**

+++

+++ **Comment me préparer à la Confidentialité des données avec Adobe Analytics ?**

Pour une présentation détaillée sur la façon de se préparer aux règles de Confidentialité des données, reportez-vous à la section [Workflow relatif à la confidentialité des données d’Adobe Analytics](/help/admin/admin/c-data-governance/an-gdpr-workflow.md).

+++

+++ **Comment les contrôleurs de données doivent-ils envisager le consentement dans le cadre de l’interaction client et cliente ?**

Le RGPD et le CCPA sont l’occasion de réexaminer votre stratégie et vos pratiques de gestion du consentement. Cela inclut la détermination du moment où le consentement est nécessaire et la réflexion sur la proposition de valeur pour l’utilisateur ou l’utilisatrice. Tenez compte de la proposition de valeur pour la confidentialité des consommateurs et consommatrices afin de favoriser la conversion et la fidélisation. L’espace de gestion du consentement (par exemple les outils, les normes ou les bonnes pratiques) est un domaine en rapide évolution à ne pas perdre de vue. Afin de minimiser l’impact sur l’interaction client et cliente, les contrôleurs doivent collaborer avec les fournisseurs et fournisseuses dans cet espace ainsi qu’avec leur service juridique, pour s’assurer de leur conformité avec les nouvelles lois et recommandations sur le consentement et les cookies. Envisager une « confidentialité expérimentale » par la mise en place d’une expérience de la marque pertinente sur le plan contextuel, qui définit la proposition de valeur de vos activités de collecte de données, constitue une bonne stratégie.

En tant que contrôleur des données, c’est à vous qu’il revient d’obtenir le consentement explicite de vos titulaires de données avant de collecter des données à leur sujet (comprenant éventuellement des données Adobe Analytics) et d’implémenter un [mécanisme de désinscription](https://www.adobe.com/fr/privacy/opt-out.html#customeruse) sur votre site web. Cela permet à vos titulaires de données de ne plus participer à la future collecte de données d’Adobe Experience Cloud.

+++

+++ **Comment les contrôleurs de données doivent-ils envisager la conservation des données dans le cadre de la Confidentialité des données ?**

Les données personnelles ne doivent généralement pas être conservées plus longtemps que la durée nécessaire pour atteindre l’objectif pour lequel elles ont été collectées. Les conditions générales d’Adobe appliquent un plan de conservation des données de 25 mois par défaut, sauf si une autre condition de conservation des données est convenue contractuellement. Il sera demandé aux clientes et clients de définir leur politique de conservation des données avant qu’Adobe puisse traiter les demandes relatives aux informations personnelles.

La politique actuelle de conservation des données de chaque suite de rapports figure dans la nouvelle interface d’utilisation d’administration de la Gouvernance des données. Les clientes et clients doivent contacter leur représentant Adobe pour modifier leur politique de conservation des données, le cas échéant. Reportez-vous à la section [FAQ sur la conservation des données d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=fr).

+++

+++ **Est-ce qu’un client ou une cliente peut réduire ou prolonger la période de conservation des données par défaut ?**

Les clientes et clients peuvent demander que leurs données soient supprimées avant le délai de 25 mois en contactant le service d’assistance clientèle. Les clientes et clients ont également la possibilité de prolonger la période de conservation des données au-delà de 25 mois en achetant une extension. Les extensions sont disponibles par incréments d’1 année supplémentaire, dans la limite de 8 années supplémentaires (10 années au total). Ces extensions nécessiteront la mise à jour des termes du contrat et impliqueront des frais supplémentaires.

+++

+++ **De quelles considérations en matière de protection de la vie privée une personne chargée du contrôle des données doit-elle tenir compte lors de l’exportation de données personnelles depuis Adobe Analytics ?**

Si un client ou une cliente utilise des flux de données d’Adobe Analytics pour exporter des données d’Analytics vers son entrepôt de données d’entreprise ou d’autres systèmes en dehors d’Adobe, il lui incombe (en tant que personne chargée du contrôle des données) de s’assurer que les requêtes de suppression sont appliquées aux données. Ceci vaut également pour les implémentations On-Premise d’Adobe Data Workbench, où un flux de données Adobe Analytics en cours renseigne les données Data Workbench. Adobe peut vous fournir des outils qui vous aideront à rechercher et à supprimer les enregistrements de certains types de flux de données, y compris ceux utilisés pour Data Workbench, mais c’est au client ou à la cliente (en tant que personne chargée du contrôle des données) qu’il revient de s’assurer que les données sont supprimées, conformément à ses propres stratégies internes en matière de suppression et de conservation des données.

N’oubliez pas de tenir compte des cas où le personnel a téléchargé des rapports Adobe Analytics contenant des données personnelles. Il se peut que ces rapports doivent être mis à jour ou être supprimés en cas de réception d’une demande de suppression relative à la Confidentialité des données impliquant un identifiant présent dans le rapport. Les clientes et clients doivent collaborer avec le service juridique de leur entreprise afin de déterminer les périodes de conservation, ainsi que les exigences en matière de confidentialité et de sécurité à appliquer à ces types de documents.

+++

+++ **Certaines données dont la collecte n’était pas censée être effectuée ont été accidentellement envoyées à Adobe Analytics. Pouvons-nous utiliser l’API de confidentialité des données pour nettoyer ces données ?**

L’[API Data Privacy Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) a été fournie pour vous aider à répondre aux demandes relatives à la Confidentialité des données, qui sont urgentes. L’utilisation de cette API à d’autres fins n’est pas prise en charge par Adobe et peut avoir une incidence sur la capacité d’Adobe à traiter en temps voulu des requêtes relatives à la Confidentialité des données pour d’autres clientes et clients d’Adobe.

Nous vous demandons de ne pas utiliser l’API relative à la Confidentialité des données à d’autres fins, par exemple pour effacer des données qui ont été soumises accidentellement à de grands groupes de visiteurs et visiteuses. Vous devez également savoir que tout visiteur ayant un accès supprimé (mis à jour ou rendu anonyme) à la suite d’une demande de suppression relative à la Confidentialité des données verra ses informations publiques réinitialisées. La prochaine fois que le visiteur reviendra sur votre site Web, il sera considéré comme un nouveau visiteur. Toutes les attributions d’eVar seront réinitialisées, tout comme les informations telles que le nombre de visites, les référents, la première page visitée, etc. Cet inconvénient n’est pas souhaitable dans les situations où vous voulez effacer des champs de données et met en évidence une des raisons pour lesquelles l’API relative à la Confidentialité des données ne convient pas à cet usage.

Veuillez contacter votre équipe de compte d’Adobe pour qu’elle se mette en relation avec notre équipe de conseillers en architecture et ingénierie de données afin d’effectuer un examen plus approfondi et de fournir le niveau d’effort nécessaire pour supprimer les informations d’identification personnelles ou les problèmes de données.

+++

+++ **Notre équipe juridique a déterminé que les valeurs que nous recueillons dans une variable depuis des années ne sont plus conformes à notre politique de confidentialité mise à jour. Pouvons-nous utiliser l’API relative à la Confidentialité des données pour supprimer toutes les valeurs de cette variable ?**

L’[API Data Privacy Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) a été fournie pour vous aider à répondre aux demandes relatives à la Confidentialité des données, qui sont urgentes. L’utilisation de cette API à d’autres fins n’est pas prise en charge par Adobe et peut avoir une incidence sur la capacité d’Adobe à traiter en temps voulu des requêtes relatives à la Confidentialité des données pour d’autres clientes et clients d’Adobe. Nous vous demandons de ne pas utiliser l’API relative à la Confidentialité des données à d’autres fins, par exemple pour effacer des données qui ont été soumises accidentellement à de grands groupes de visiteurs et visiteuses.

Vous devez également savoir que tout visiteur ayant un accès supprimé (mis à jour ou rendu anonyme) à la suite d’une demande de suppression relative à la Confidentialité des données verra ses informations publiques réinitialisées. La prochaine fois que le visiteur reviendra sur votre site Web, il sera considéré comme un nouveau visiteur. Toutes les attributions d’eVar seront réinitialisées, tout comme les informations telles que le nombre de visites, les référents, la première page visitée, etc. Cet inconvénient n’est pas souhaitable dans les situations où vous voulez effacer des champs de données et met en évidence une des raisons pour lesquelles l’API relative à la Confidentialité des données ne convient pas à cet usage.

Veuillez contacter votre équipe de compte d’Adobe pour qu’elle se mette en relation avec notre équipe de conseillers en architecture et ingénierie de données afin d’effectuer un examen plus approfondi et de fournir le niveau d’effort nécessaire pour supprimer les informations d’identification personnelles ou les problèmes de données.

+++

Autres ressources relatives à la confidentialité des données :

* [Termes communs relatifs au RGPD](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf)
* [Package de prise en charge](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf) de la Confidentialité des données Experience Cloud
* [Article de blog](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/) sur la confidentialité empirique
