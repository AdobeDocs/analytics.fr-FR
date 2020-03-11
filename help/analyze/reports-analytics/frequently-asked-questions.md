---
description: Fournit des réponses et des suggestions en matière de dépannage pour certaines des questions d’analyses les plus fréquemment posées.
keywords: Troubleshooting Analytics
title: Questions fréquentes
uuid: 285b0ea4-aa07-4d39-a74f-37b1d02d19f1
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Questions fréquentes

Fournit des réponses et des suggestions en matière de dépannage pour certaines des questions d’analyses les plus fréquemment posées concernant la section Reports &amp; Analytics. Pour les questions les plus fréquemment posées relatives à l’implémentation, consultez la [FAQ](/help/implement/faq.md) dans le guide d’utilisation de l’implémentation.

**Mon compte a été verrouillé. Comment puis-je le déverrouiller ?**

Pour réactiver un compte, contactez un administrateur de votre entreprise. Vous pouvez également vous reporter à la section [Résolution des problèmes de connexion avec Adobe Analytics](/help/technotes/troubleshoot-login.md) dans le guide d’utilisation de Technotes.

**Pourquoi un rapport vierge s’affiche-t-il alors que je sais que des données ont été collectées ?**

Vous pouvez vérifier plusieurs éléments afin de dépanner les données du rapport :

* Vérifiez les mesures utilisées : certains rapports renvoient par défaut le chiffre d’affaires dans Reports &amp; Analytics. Assurez-vous que la mesure que vous consultez est pertinente pour le rapport.
* Vérifiez la période : les périodes, en particulier celles qui démarrent avant la politique de conservation des données de votre entreprise, peuvent ne pas renvoyer de données. Vérifiez que la période est définie correctement.
* Vérifiez les filtres URL internes : certains rapports sur les sources de trafic ne fonctionnent pas tant que vous n’avez pas défini correctement les filtres URL internes.

**Pourquoi manque-t-il certains rapports dans le menu de navigation ?**

Un rapport manquant dans un menu provient généralement soit d’autorisations restreintes soit de la personnalisation des menus. Contactez un administrateur produit de votre entreprise pour vous assurer que vous avez accès à toutes les dimensions et mesures nécessaires et qu’une structure de menus de la suite de rapports n’a pas été personnalisée.

**Pourquoi certaines valeurs longues sont-elles coupées ?**

La plupart des variables Adobe Analytics possèdent une limite de caractères. Le nom de page possède une limite de caractères de 100, tandis que les variables de conversion (eVar) possèdent une limite de caractères de 255. Adobe recommande de vous assurer que les valeurs que vous envoyez vers Adobe sont concises pour éviter la troncature.

**Pourquoi puis-je constater un retard majeur dans les rapports ?**

La création de rapport en temps réel permet à certaines mesures de trafic d’être disponibles quelques minutes, tandis la conversion et d’autres données de traitement intensif sont généralement disponibles entre 30 et 90 minutes. Malgré la puissance de la plateforme Experience Cloud, certaines situations peuvent donner lieu à des retards au niveau de la génération de rapports. On parle alors de latence. Pour en savoir plus, consultez la section [Latence](/help/technotes/latency.md) du guide d’utilisation de Technotes.

**Pourquoi la version de l’appareil n’apparaît-elle pas sur iPhone ?**

Les périphériques Apple renvoient leur version du microprogramme dans leur chaîne d’agent utilisateur au lieu de la version du périphérique. Il est difficile de déterminer la version d’un appareil iPhone à l’aide des informations disponibles dans Adobe Analytics. Pour en savoir plus, consultez la section [Comparer les versions d’appareils iPhone](https://helpx.adobe.com/fr/analytics/kb/comparing-iphone-device-versions.html) dans la base de connaissances Analytics.

**Pourquoi les totaux du bas de mon rapport ne correspondent-ils pas lorsque j’additionne les valeurs ?**

Les valeurs de dimension peuvent souvent s’appliquer à plusieurs endroits, par exemple pour des visites qui s’étendent au-delà de minuit ou pour des commandes de plusieurs produits. La valeur de dimension est reprise sur tous les éléments de ligne pour lesquels elle s’applique, mais elle est dédupliquée du total du rapport. Pour en savoir plus, consultez la section [Comparer la somme des éléments de ligne par rapport au total du rapport](https://helpx.adobe.com/fr/analytics/kb/sum-line-items-different-from-total.html) dans la base de connaissances Analytics.

**Comment exclure des données d’une adresse IP en particulier dans ma suite de rapports ?**

Vous pouvez éliminer les données provenant des activités de site web internes (telles que les tests de site et l’utilisation des employés) de vos rapports. Cette fonction vous permet (à vous ainsi qu’à vos collègues) de visiter votre site sans biaiser vos données de trafic. Pour en savoir plus, consultez la section [Exclure par adresse IP](/help/admin/admin/exclude-ip.md) du guide d’utilisation destiné à l’administrateur.

**Puis-je supprimer une suite de rapports ?**

Il n’est pas possible de supprimer une suite de rapports. Néanmoins, il est possible de masquer une suite de rapports de tous les affichages dans Adobe Analytics. Notez que les appels au serveur envoyés vers une suite de rapports masquée comptent toujours dans votre limite de contrat mensuelle. Pour en savoir plus, consultez la section [Masquer les suites de rapports](/help/admin/company/c-hide-report-suites.md) dans le guide d’utilisation destiné à l’administrateur.

**Quel conteneur dois-je utiliser lorsque j’utilise la segmentation ? Page vue, visite ou visiteur ?**

Le conteneur de segments que vous utilisez dépend de la largeur des données que vous souhaitez capturer. Les conteneurs Page vue ne contiennent que les accès correspondant à un critère de segment et sont utiles pour exclure les parties de visites que vous estimez peu pertinentes. Les conteneurs Visites incluent tous les accès d’une visite pour lesquels un ou plusieurs accès ont correspondu aux critères de segment et sont utiles pour examiner les sessions en général. Les conteneurs Visiteurs incluent toutes les visites pour lesquelles un accès a correspondu à un critère de segments et sont utiles pour étudier les personnes. En tant qu’analyste, le choix vous appartient de déterminer le conteneur de segments le mieux adapté à vos besoins. Pour plus d’informations, consultez la section [Aperçu de la segmentation](/help/components/c-segmentation/seg-overview.md) du guide d’utilisation des composants.

**Pourquoi mon segment ne s’affiche-t-il pas dans Data Warehouse ?**

En raison de l’architecture de traitement unique de Data Warehouse, la plateforme n’est pas optimisée pour traiter certains types de données, comme le cheminement. Pour en savoir plus, consultez la section [Compatibilité des segments Data Warehouse](/help/components/c-segmentation/seg-reference/seg-compatibility.md) dans le guide d’utilisation des composants.
