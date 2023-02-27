---
description: FAQ sur la gouvernance des données Adobe Analytics
title: Questions fréquentes sur la gouvernance des données
feature: Data Governance
exl-id: 57399c1b-cf08-405b-8c1b-9d23e4c38716
source-git-commit: c774d05ca3b1f9f45ec118b0e7b8a839a03b87e3
workflow-type: tm+mt
source-wordcount: '2076'
ht-degree: 52%

---

# Questions fréquentes

+++ **Comment Adobe Analytics prend-il en charge les demandes d’accès et de suppression pour les utilisateurs finaux (Sujets de données) validées par les clients (Contrôleurs de données) ?**

À compter de l’entrée en vigueur de diverses règles relatives à la Confidentialité des données (RGPD, CCPA), Adobe Analytics prendra en charge le traitement des demandes vérifiées soumises par les contrôleurs de données à l’API relative à la Confidentialité des données Experience Cloud afin de permettre un processus plus automatisé. L’API relative à la Confidentialité des données d’Adobe Experience Cloud est conçue pour faciliter le traitement des demandes individuelles de droits (p. ex., demandes d’accès et de suppression) pour les données de nos clients stockées dans les solutions Adobe Experience Cloud. Elle est flexible et évolue en fonction du nombre de demandes d’accès et de suppression de données que votre entreprise reçoit des titulaires de données.

En outre, l’API du Privacy Service permet au client de vérifier l’état du traitement des demandes d’accès et de suppression des données en cours de traitement. Pour plus de détails, consultez la [](https://developer.adobe.com/experience-platform-apis/references/privacy-service/)documentation de lʼAPI Privacy Service.

+++

+++ **Qui est chargé de recevoir, d’accepter et de répondre aux demandes relatives à la Confidentialité des données des utilisateurs finaux ?**

Le contrôleur de données est seul responsable de la réception et de l’acceptation des demandes. Le contrôleur de données valide l’identité du titulaire de données, puis répond à la demande. Une partie de cette responsabilité peut impliquer de contacter l’Adobe avec les ID des titulaires de données qui peuvent être associés aux données stockées dans Adobe Analytics.

En tant qu&#39;entité de traitement des données, l&#39;Adobe doit fournir une assistance raisonnable au contrôleur pour traiter les demandes vérifiées dans un délai acceptable.

+++

+++ **Comment les clients Adobe (Contrôleurs de données) sauront-ils quelles demandes relatives à la Confidentialité des données mappent à quels ID dans Adobe Analytics en vue du traitement en vertu de la Confidentialité des données ?**

Les contrôleurs de données déterminent comment résoudre l’identité des demandes provenant des titulaires de données. Envisagez de déployer la balise de récupération des ID en vertu de la Confidentialité des données d’Adobe. Vos équipes de développement gagnent du temps en utilisant notre balise de récupération des ID en vertu de la Confidentialité des données pour capturer les ID d’utilisateur (ID de cookie). Ils peuvent ensuite utiliser notre API relative à la Confidentialité des données pour envoyer ces ID utilisateur aux solutions appropriées dans Adobe Experience Cloud pour le traitement des demandes relatives à la Confidentialité des données. L’API relative à la Confidentialité des données prend en charge un large éventail d’ID de clients dans de nombreuses solutions Adobe.

Si un titulaire de données envoie une demande avec un identifiant (variable personnalisée - prop ou eVar), Adobe Analytics analyse alors l’historique conservé complet des données collectées pour l’identifiant donné. Pour plus d’informations sur la configuration des ID personnalisés stockés dans les variables props ou eVars d’Analytics, reportez-vous à la section [Documentation d’Analytics sur les espaces de noms](/help/admin/admin/c-data-governance/data-labeling/gdpr-namespaces.md).

+++

+++ **Comment l’outil Gouvernance des données d’Adobe Analytics facilite-t-il le traitement des demandes relatives à la Confidentialité des données ?**

La gouvernance des données est un nouvel outil d’Adobe Analytics qui permet aux contrôleurs de données d’appliquer des contrôles de données et des classifications à leurs données Analytics. Grâce à ce nouvel outil, les clients Adobe peuvent personnaliser le traitement de leurs demandes d’accès et de suppression des données en vertu de la Confidentialité des données. La console Gouvernance des données permet aux administrateurs de définir les paramètres à appliquer à différentes colonnes de données dans Adobe Analytics. Une fois ces étiquettes définies, Adobe traitera toutes les demandes d’accès ou de suppression en aval conformément aux paramètres d’étiquetage des clients. Il est de la responsabilité du contrôleur de données d’examiner ces paramètres d’étiquette et de se concerter avec ses représentants juridiques.

L’outil Gouvernance des données contient les étiquettes de données suivantes :

* **Étiquettes de données d’identification**: Utilisé pour classer les données qui peuvent identifier un individu directement ou en combinaison avec d’autres données. (Aucune, I1, I2)

* **Étiquettes de données sensibles**: Utilisé pour classer les données en tant que données pouvant être définies comme sensibles en vertu de la loi en vigueur. (Aucune, S1, S2) Notez que, actuellement, l’utilisation des données sensibles dans Adobe Analytics est généralement interdite, excepté pour les données de géolocalisation précise obtenues légitimement en vertu de la loi applicable, qui peuvent être considérées comme des données sensibles dans certaines juridictions.

* **Étiquettes de données relatives à la confidentialité des données**: Utilisé pour définir les champs qui peuvent contenir des identifiants personnels à utiliser dans les demandes relatives à la Confidentialité des données ou qui doivent être supprimés dans le cadre d’une demande de suppression relative à la Confidentialité des données. Dans certains cas, ces étiquettes peuvent se superposer aux étiquettes de données d’identification et de données sensibles.

Pour plus d’informations sur les étiquettes de gouvernance des données, voir [Étiquettes de Confidentialité des données pour les variables Analytics](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md).

+++

+++ **Comment puis-je vérifier que les demandes du Privacy Service fonctionnent correctement pour supprimer des données d’Adobe Analytics ?**

En règle générale, les clients Analytics configurent certaines suites de rapports de test pour vérifier les fonctionnalités avant qu’elles ne soient publiées pour le grand public. Les sites web ou applications de pré-production envoient des données dans ces suites de rapports test/dev/QA afin d’évaluer le fonctionnement des éléments lorsque le code est publié avant que le trafic réel ne soit envoyé aux suites de rapports de production.

Toutefois, avec une configuration normale, le traitement des demandes en vertu du RGPD ne peut pas être testé sur ces suites de rapports de test avant d’appliquer les demandes aux suites de rapports de production. En effet, une demande relative à la Confidentialité des données est automatiquement appliquée à toutes les suites de rapports de l’organisation Experience Cloud, qui correspond souvent à toutes les suites de rapports de votre entreprise.

Vous pouvez toutefois tester le traitement en vertu de la Confidentialité des données de plusieurs façons avant de l’appliquer à toutes vos suites de rapports :

* Vous pouvez par exemple configurer une organisation Experience Cloud séparée contenant uniquement les suites de rapports de test. Ensuite, utilisez cette organisation Experience Cloud pour votre test relatif à la Confidentialité des données et votre organisation Experience Cloud classique pour effectuer le véritable traitement.

* Une autre option consiste à attribuer des espaces de noms différents aux ID dans vos suites de rapports de test par rapport à ceux qui figurent dans vos suites de rapports de production. Par exemple, vous pouvez ajouter le préfixe « qa- » à chaque espace de noms dans vos suites de rapports de test. Lorsque vous soumettez vos demandes relatives à la Confidentialité des données avec uniquement des espaces de noms comportant le préfixe qa, ces demandes ne sont exécutées que par rapport à vos suites de rapports de test. Ensuite, lorsque vous soumettez vos demandes sans le préfixe qa, elles seront appliquées à vos suites de rapports de production. **Il s’agit de l’approche recommandée, sauf si vous utilisez les espaces de noms visitorId, AAID, ECID ou customVisitorId. Ces espaces de noms sont codés en dur et vous ne pouvez pas spécifier d’autres noms dans vos suites de rapports de test.**

+++

+++ **Comment me préparer à la Confidentialité des données avec Adobe Analytics ?**

Pour une présentation détaillée sur la façon de se préparer aux règles de Confidentialité des données, reportez-vous à la section [Processus relatif à la confidentialité des données Adobe Analytics](/help/admin/admin/c-data-governance/an-gdpr-workflow.md).

+++

+++ **Comment les contrôleurs de données doivent-ils envisager le consentement dans le cadre de l’interaction client ?**

Le RGPD et le CCPA sont de bonnes occasions de réexaminer votre stratégie et vos pratiques de gestion du consentement. Cela inclut la détermination du moment où le consentement est nécessaire et la réflexion sur la proposition de valeur pour l’utilisateur. Tenir compte de la proposition de valeur pour la confidentialité des consommateurs peut favoriser la conversion et la fidélisation. L’espace de gestion du consentement (p. ex., outils, normes, bonnes pratiques) est un domaine en rapide évolution à ne pas perdre de vue. Afin de minimiser l’impact sur l’engagement des utilisateurs, les contrôleurs doivent collaborer avec les fournisseurs de cet espace ainsi qu’avec leur service juridique, pour s’assurer qu’ils suivent les nouvelles lois et les conseils sur le consentement et les cookies. Envisager une « confidentialité empirique » par la mise en place d’une expérience de la marque pertinente sur le plan contextuel, qui définit la proposition de valeur de vos activités de collecte de données constitue une bonne stratégie.

En tant que contrôleur de données, c’est à vous qu’il revient d’obtenir le consentement explicite de vos titulaires de données avant de collecter des données à leur sujet (comprenant éventuellement des données Adobe Analytics) et d’implémenter une [mécanisme d&#39;exclusion](https://www.adobe.com/fr/privacy/opt-out.html#customeruse) sur votre site web. Cela permet aux sujets des données de se désabonner de la future collecte de données Adobe Experience Cloud.

+++

+++ **Comment les contrôleurs de données doivent-ils envisager la conservation des données dans le cadre de la Confidentialité des données ?**

En règle générale, les données personnelles ne doivent pas être conservées plus longtemps que nécessaire pour atteindre l’objectif pour lequel elles ont été collectées. Les conditions générales de l’Adobe appliquent un plan de conservation des données de 25 mois par défaut, sauf si un autre terme de conservation des données est convenu contractuellement. Les clients doivent définir leur politique de conservation des données avant qu’Adobe puisse traiter une demande relative à la Confidentialité des données.

La politique actuelle de conservation des données de chaque suite de rapports figure dans la nouvelle interface utilisateur d’administration de la Gouvernance des données. Les clients doivent contacter leur représentant d’Adobe s’ils ont besoin d’ajuster leur politique de conservation des données. Reportez-vous à la section [FAQ sur la rétention des données Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=en).

+++

+++ **Un client peut-il réduire ou prolonger la période de conservation des données par défaut ?**

Les clients peuvent demander que leurs données soient supprimées avant 25 mois en contactant l’assistance clientèle. Les clients ont également la possibilité de prolonger la période de conservation des données au-delà de 25 mois en achetant une extension. Les extensions sont disponibles par incréments d’une année supplémentaire, jusqu’à 8 années supplémentaires au maximum (10 années au total). Ces extensions nécessiteront une mise à jour des termes du contrat et des frais supplémentaires.

+++

+++ **De quelles considérations en matière de protection de la vie privée un contrôleur de données doit-il tenir compte lors de l’exportation de données personnelles depuis Adobe Analytics ?**

Si un client utilise des flux de données Adobe Analytics pour exporter les données d’Analytics vers son entrepôt de données d’entreprise ou d’autres systèmes en dehors d’Adobe, il incombe au client (Contrôleur de données) de s’assurer que les demandes de suppression sont appliquées aux données. Cela s’applique également aux implémentations on-premise d’Adobe Data Workbench, où un flux de données Adobe Analytics en cours renseigne les données du Data Workbench. Adobe peut vous fournir des outils qui vous aideront à rechercher et à supprimer les enregistrements de certains types de flux de données, y compris ceux utilisés pour Data Workbench, mais c’est au client (Contrôleur de données) qu’il revient de s’assurer que les données sont supprimées, conformément à ses propres politiques internes en matière de suppression et de conservation des données.

Veuillez également tenir compte des cas où les employés ont téléchargé des rapports Adobe Analytics contenant des données personnelles. Il se peut que ces rapports doivent être mis à jour ou supprimés si une demande de suppression relative à la Confidentialité des données est reçue impliquant un ID présent dans le rapport. Les clients doivent collaborer avec le service juridique de leur propre entreprise pour déterminer les périodes de conservation, ainsi que les exigences de confidentialité et de sécurité qui doivent être appliquées à ces types de documents.

+++

+++ **Certaines données que nous n’étions pas censés recueillir ont été accidentellement envoyées à Adobe Analytics. Pouvons-nous utiliser l’API relative à la Confidentialité des données pour nettoyer ces données ?**

Le [API du Privacy Service de données](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) a été fourni pour vous aider à répondre aux demandes relatives à la Confidentialité des données, qui sont urgentes. L’utilisation de cette API à d’autres fins n’est pas prise en charge par Adobe et peut avoir une incidence sur la capacité d’Adobe à traiter en temps voulu des demandes relatives à la Confidentialité des données pour d’autres clients Adobe.

Nous vous demandons de ne pas utiliser l’API relative à la Confidentialité des données à d’autres fins, par exemple pour effacer des données qui ont été soumises accidentellement à de grands groupes de visiteurs. Vous devez également savoir que tout visiteur ayant un accès supprimé (mis à jour ou rendu anonyme) à la suite d’une demande de suppression relative à la Confidentialité des données verra ses informations publiques réinitialisées. La prochaine fois que le visiteur reviendra sur votre site Web, il sera considéré comme un nouveau visiteur. Toutes les attributions d’eVar seront réinitialisées, tout comme les informations telles que le nombre de visites, les référents, la première page visitée, etc. Cet inconvénient n’est pas souhaitable dans les situations où vous voulez effacer des champs de données et met en évidence une des raisons pour lesquelles l’API relative à la Confidentialité des données ne convient pas à cet usage.

Veuillez contacter votre gestionnaire de compte (CSM) afin qu’il vous mette en relation avec notre équipe de conseillers en architecture et ingénierie de données dans le but d’effectuer un examen plus approfondi et de fournir le niveau d’effort nécessaire pour pallier tout problème de PII ou de données.

+++

+++ **Notre équipe juridique a déterminé que les valeurs que nous recueillons dans une variable depuis des années ne sont plus conformes à notre politique de confidentialité mise à jour. Pouvons-nous utiliser l’API relative à la Confidentialité des données pour supprimer toutes les valeurs de cette variable ?**

Le [API du Privacy Service de données](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) a été fourni pour vous aider à répondre aux demandes relatives à la Confidentialité des données, qui sont urgentes. L’utilisation de cette API à d’autres fins n’est pas prise en charge par Adobe et peut avoir une incidence sur la capacité d’Adobe à traiter en temps voulu des demandes relatives à la Confidentialité des données pour d’autres clients Adobe. Nous vous demandons de ne pas utiliser l’API relative à la Confidentialité des données à d’autres fins, par exemple pour effacer des données qui ont été soumises accidentellement à de grands groupes de visiteurs.

Vous devez également savoir que tout visiteur ayant un accès supprimé (mis à jour ou rendu anonyme) à la suite d’une demande de suppression relative à la Confidentialité des données verra ses informations publiques réinitialisées. La prochaine fois que le visiteur reviendra sur votre site Web, il sera considéré comme un nouveau visiteur. Toutes les attributions d’eVar seront réinitialisées, tout comme les informations telles que le nombre de visites, les référents, la première page visitée, etc. Cet inconvénient n’est pas souhaitable dans les situations où vous voulez effacer des champs de données et met en évidence une des raisons pour lesquelles l’API relative à la Confidentialité des données ne convient pas à cet usage.

Veuillez contacter votre gestionnaire de compte (CSM) afin qu’il vous mette en relation avec notre équipe de conseillers en architecture et ingénierie de données afin d’effectuer un examen plus approfondi et de fournir le niveau d’effort nécessaire pour pallier tout problème de PII ou de données.

+++

Autres ressources relatives à la confidentialité des données :

* [Termes communs relatifs au RGPD](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf)
* [Package de prise en charge](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf) de la Confidentialité des données Experience Cloud
* [Article de blog](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/) sur la confidentialité empirique
