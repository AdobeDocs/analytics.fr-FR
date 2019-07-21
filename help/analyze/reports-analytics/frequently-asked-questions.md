---
description: Fournit des réponses et des suggestions en matière de dépannage pour certaines des questions d’analyses les plus fréquemment posées.
keywords: Dépannage d’Analytics
seo-description: Fournit des réponses et des suggestions en matière de dépannage pour certaines des questions d’analyses les plus fréquemment posées.
seo-title: Questions fréquentes
title: Questions fréquentes
uuid: 285 b 0 ea 4-aa 07-4 d 39-a 74 f -37 b 1 d 02 d 19 f 1
translation-type: tm+mt
source-git-commit: fd1e2f1789ed9c8c31c89f0e7b6b7b2dd3ee114d

---


# Questions fréquentes

Fournit des réponses et des suggestions de dépannage à certaines des questions Analytics les plus fréquemment posées pour les rapports et analyses. For frequently asked implementation questions, see the [FAQ](../../implement/faq.md) in the Implement user guide.

**Mon compte a été verrouillé ; comment puis-je le déverrouiller ?**

Pour réactiver un compte, contactez un administrateur au sein de votre organisation. See also [Troubleshoot login issues with Adobe Analytics](../../technotes/troubleshoot-login.md) in the Technotes user guide.

**Pourquoi vois-je un rapport vide même si je sais que les données sont collectées ?**

Il existe plusieurs éléments à vérifier pour résoudre les problèmes liés aux données de rapport :

* Vérifiez les mesures utilisées : Certains rapports par défaut sont Recettes dans les rapports et analyses. Assurez-vous que la mesure que vous visualisez est pertinente pour le rapport.
* Vérifiez la plage de dates : Les plages de dates, notamment celles qui dépassent la politique de rétention des données de votre organisation, ne peuvent renvoyer aucune donnée. Vérifiez que la plage de dates est correctement définie.
* Vérifier les filtres d'URL internes : Certains rapports de sources de trafic ne fonctionnent pas tant que vous n'avez pas défini correctement les filtres d'URL internes.

**Pourquoi certains rapports sont-ils absents du menu de navigation ?**

Les rapports manquants d'un menu proviennent le plus souvent d'autorisations restreintes ou de personnalisation des menus. Contactez un administrateur du produit au sein de votre organisation pour vous assurer que vous avez accès à toutes les dimensions et mesures requises et que la structure de menus d'une suite de rapports n'a pas été personnalisée.

**Pourquoi certaines valeurs longues sont-elles coupées ?**

Presque toutes les variables d'Adobe Analytics ont une limite de caractères. Le nom de page est limité à 100 caractères, tandis que les variables de conversion personnalisées (evars) ont une limite de 255 caractères. Adobe recommande de s'assurer que les valeurs envoyées à Adobe sont concises afin d'éviter la troncature.

**Pourquoi le rapport contient-il un retard majeur ?**

La création de rapports en temps réel permet la disponibilité de certaines mesures de trafic en quelques minutes, tandis que la conversion et d'autres données gourmandes en traitement sont généralement disponibles dans les 30 à 90 minutes. Malgré la puissance de la plate-forme Experience Cloud, certaines situations peuvent donner lieu à des retards au niveau de la génération de rapports. Ce délai est appelé latence. See [Latency](../../technotes/latency.md) in the Technotes user guide for more information.

**Pourquoi ne puis-je pas voir la version du périphérique sur les iphones ?**

Les périphériques Apple signalent leur version du microprogramme dans la chaîne de l'agent utilisateur, et non dans la version du périphérique. Il est difficile de déterminer la version du périphérique iphone à l'aide d'informations disponibles pour Adobe Analytics. See [Comparing iPhone device versions](https://helpx.adobe.com/analytics/kb/comparing-iphone-device-versions.html) in the Analytics KB for more information.

**Pourquoi les totaux au bas de mon rapport ne correspondent-ils pas lorsque je additionne les valeurs ?**

Les valeurs de dimension peuvent souvent s'appliquer à plusieurs emplacements ; par exemple, les visites qui couvrent minuit ou plusieurs produits appartenant à une seule commande. La valeur de dimension est rapportée sur tous les éléments de ligne applicables, mais elle est dédupliquée dans le total du rapport. See [Compare sum of line items to report total](https://helpx.adobe.com/analytics/kb/sum-line-items-different-from-total.html) in the Analytics KB for more information.

**Comment exclure les données d'une adresse IP particulière dans ma suite de rapports ?**

Vous pouvez éliminer les données provenant des activités de site Web internes (telles que les tests de site et l’utilisation des employés) de vos rapports Cette fonction vous permet (à vous ainsi qu’à vos collègues) de visiter votre site sans biaiser vos données de trafic. See [Exclude by IP Address](../../admin/admin/exclude-ip.md) in the Admin user guide for more information.

**Puis-je supprimer une suite de rapports ?**

Il n'est pas possible de supprimer une suite de rapports. Toutefois, une suite de rapports peut être masquée dans toutes les vues d'Adobe Analytics. Notez que les appels serveur envoyés à une suite de rapports masquée sont toujours comptabilisés dans votre limite mensuelle. See [Hide report suites](../../admin/company/c-hide-report-suites.md) in the Admin user guide for more information.

**Lors de l'utilisation de la segmentation, quel conteneur dois-je utiliser ? Page view, visit, or visitor?**

Le conteneur de segments que vous utilisez dépend de la largeur de capture des données. Les conteneurs Page vue ne génèrent que des accès qui correspondent aux critères de segment, ce qui est utile pour filtrer les parties inappropriées de visites. Conteneurs de visites l'affichent tous les accès d'une visite où un ou plusieurs accès correspondent aux critères de segment, utiles pour consulter les sessions en général. Les conteneurs de visiteurs génèrent toutes les visites où un accès correspond aux critères de segment, utiles pour étudier les personnes. Il s'agit de votre choix en tant qu'analyste pour déterminer quel conteneur de segments est le mieux utilisé. See [Segmentation overview](../../components/c-segmentation/seg-overview.md) in the Components user guide for more information.

**Pourquoi mon segment ne s'affiche-t-il pas dans l'entrepôt de données ?**

En raison de l'architecture de traitement unique de l'entrepôt de données, la plate-forme n'est pas optimisée pour gérer certains types de données, tels que le cheminement. See [Data Warehouse segment compatibility](../../components/c-segmentation/seg-reference/seg-compatibility.md) in the Components user guide for more information.
