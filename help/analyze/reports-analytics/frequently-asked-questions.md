---
description: Fournit des réponses et des suggestions en matière de dépannage pour certaines des questions d’analyses les plus fréquemment posées.
keywords: Dépannage d’Analytics
seo-description: Fournit des réponses et des suggestions en matière de dépannage pour certaines des questions d’analyses les plus fréquemment posées.
seo-title: Questions fréquentes
title: Questions fréquentes
uuid: 285b0ea4-aa07-4d39-a74f-37b1d02d19f1
translation-type: tm+mt
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# Questions fréquentes

Fournit des réponses et des suggestions de dépannage à certaines des questions Analytics les plus fréquentes pour les rapports et analyses. Pour les questions fréquentes sur l’implémentation, consultez la [FAQ](/help/implement/faq.md) dans le guide de l’utilisateur Mise en oeuvre.

**Mon compte a été verrouillé ; comment le déverrouiller ?**

Pour réactiver un compte, contactez un administrateur au sein de votre organisation. Voir aussi [Résolution des problèmes de connexion avec Adobe Analytics](/help/technotes/troubleshoot-login.md) dans le guide de l’utilisateur Technotes.

**Pourquoi est-ce que je vois un rapport vierge alors que je sais que des données sont collectées ?**

Il existe plusieurs éléments à vérifier pour résoudre les problèmes liés aux données de rapport :

* Vérifiez les mesures utilisées : Certains rapports prennent la valeur Recettes par défaut dans les rapports et analyses. Assurez-vous que la mesure que vous affichez est pertinente pour le rapport.
* Vérifiez la plage de dates : Les plages de dates, en particulier celles qui dépassent la stratégie de rétention des données de votre entreprise, ne peuvent renvoyer aucune donnée. Vérifiez que la plage de dates est correctement définie.
* Vérifier les filtres d’URL internes : Certains rapports de sources de trafic ne fonctionnent qu’une fois que vous avez correctement défini les filtres d’URL internes.

**Pourquoi certains rapports sont-ils manquants dans le menu de navigation ?**

Les rapports manquants dans un menu proviennent généralement des autorisations restreintes ou de la personnalisation des menus. Contactez un administrateur de produit au sein de votre entreprise pour vous assurer que vous avez accès à toutes les dimensions et mesures nécessaires et que la structure de menus d’une suite de rapports n’a pas été personnalisée.

**Pourquoi certaines valeurs longues sont-elles coupées ?**

Presque toutes les variables d’Adobe Analytics ont une limite de caractères. Le nom de page est limité à 100 caractères, tandis que les variables de conversion personnalisées (eVars) sont limitées à 255 caractères. Adobe recommande de s’assurer que les valeurs que vous envoyez à Adobe sont concises afin d’éviter toute troncature.

**Pourquoi vois-je un retard majeur dans la création de rapports ?**

La création de rapports en temps réel permet à certaines mesures de trafic d’être disponibles en quelques minutes, tandis que la conversion et d’autres données à fort traitement sont généralement disponibles en 30 à 90 minutes. Malgré la puissance de la plate-forme Experience Cloud, certaines situations peuvent donner lieu à des retards au niveau de la génération de rapports. Ce délai est appelé latence. Voir [Latence](/help/technotes/latency.md) dans le guide de l’utilisateur des notes techniques pour en savoir plus.

**Pourquoi est-ce que je ne vois pas la version du périphérique sur iPhone ?**

Les périphériques Apple signalent leur version du microprogramme dans la chaîne de l’agent utilisateur, et non la version du périphérique. Il est difficile de déterminer la version d’un périphérique iPhone à l’aide des informations disponibles pour Adobe Analytics. Pour plus d’informations, voir [Comparaison des versions](https://helpx.adobe.com/analytics/kb/comparing-iphone-device-versions.html) de périphériques iPhone dans la base de connaissances Analytics.

**Pourquoi les totaux au bas de mon rapport ne correspondent-ils pas lorsque je additionne les valeurs ?**

Les valeurs de dimension peuvent souvent s’appliquer à plusieurs endroits ; par exemple, les visites qui s’étendent sur minuit ou plusieurs produits appartenant à une seule commande. La valeur de dimension est reportée sur toutes les lignes applicables, mais elle est dédupliquée dans le total du rapport. Pour plus d’informations, voir [Comparaison de la somme des éléments de ligne pour rapporter le total](https://helpx.adobe.com/analytics/kb/sum-line-items-different-from-total.html) dans le Ko Analytics.

**Comment exclure des données d’une adresse IP particulière dans ma suite de rapports ?**

Vous pouvez éliminer les données provenant des activités de site Web internes (telles que les tests de site et l’utilisation des employés) de vos rapports Cette fonction vous permet (à vous ainsi qu’à vos collègues) de visiter votre site sans biaiser vos données de trafic. Pour plus d’informations, voir [Exclure par adresse](/help/admin/admin/exclude-ip.md) IP dans le guide de l’utilisateur administrateur.

**Puis-je supprimer une suite de rapports ?**

La suppression d’une suite de rapports n’est pas possible. Toutefois, une suite de rapports peut être masquée de toutes les vues dans Adobe Analytics. Notez que les appels serveur envoyés à une suite de rapports masquée sont toujours comptabilisés dans votre limite mensuelle de contrat. Voir [Masquer les suites](/help/admin/company/c-hide-report-suites.md) de rapports dans le guide de l’utilisateur Admin pour plus d’informations.

**Lors de l’utilisation de la segmentation, quel conteneur dois-je utiliser ? Page vue, visite ou visiteur ?**

Le conteneur de segments que vous utilisez dépend de la largeur de capture des données. Les conteneurs Page vue n’apportent que les accès qui correspondent aux critères de segment, ce qui s’avère utile pour filtrer les parties non pertinentes des visites. Les conteneurs de visites apportent tous les accès d’une visite pour laquelle un ou plusieurs accès correspondent à des critères de segment, utiles pour consulter les sessions en général. Les conteneurs de visiteurs apportent toutes les visites pour lesquelles un accès correspond à des critères de segment, ce qui est utile pour consulter les personnes. En tant qu’analyste, vous avez le choix de déterminer le conteneur de segments à utiliser le mieux. Pour plus d’informations, voir Présentation [de la](/help/components/c-segmentation/seg-overview.md) segmentation dans le guide de l’utilisateur Composants.

**Pourquoi mon segment ne s’affiche-t-il pas dans Data Warehouse ?**

En raison de l’architecture de traitement unique de Data Warehouse, la plateforme n’est pas optimisée pour gérer certains types de données, comme le cheminement. Pour plus d’informations, voir Compatibilité [des segments de l’entrepôt de](/help/components/c-segmentation/seg-reference/seg-compatibility.md) données dans le guide de l’utilisateur Composants.
