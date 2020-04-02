---
description: Les suites de rapports virtuelles segmentent les données Adobe Analytics afin que vous puissiez contrôler l’accès à chaque segment.
title: Suites de rapports virtuelles - Aperçu
uuid: 51c63c56-dd58-4c23-a997-ea6942480d22
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Suites de rapports virtuelles - Aperçu

Les suites de rapports virtuelles segmentent les données Adobe Analytics afin que vous puissiez contrôler l’accès à chaque segment.

De nombreux clients disposent de données qui circulent dans une suite de rapports globale, mais également de données qui circulent dans des suites de rapports plus petites. Ils définissent une variable sur plusieurs suites de rapports et envoient leurs données à plusieurs suites de rapports. Ceci est appelé *balisage multisuite* ou *suites de rapports de base/parentes*.

Par exemple, toutes les données peuvent être collectées dans une suite de rapports, mais, ensuite, vous pouvez configurer des suites de rapports secondaires de sorte que le personnel de l’entreprise ait accès à une partie des données, mais pas à toutes. Les données peuvent être divisées par région. Vous pouvez avoir différents sites web pour différents pays. Autres exemples : des marques spécifiques appartenant à une plus grande entreprise, mais ayant chacune leurs propres équipes de marketing.

Une *suite de rapports virtuelle* permet de reproduire ce concept d’embranchement en utilisant des segments au lieu de plusieurs suites de rapports. Les données sont envoyées à une suite de rapports, puis divisées selon les segments. En utilisant l’exemple des marques multiples, vous pouvez définir une prop pour la marque à laquelle appartient un article. En utilisant des segments, vous pouvez créer des rapports pour les éléments assignés à chaque prop. Chacun de ces segments devient sa propre vue, créant ainsi une suite de rapports. Vous n’envoyez pas de données spécifiquement à ce segment, uniquement à la suite de rapports globale, mais elle fonctionne dans les rapports comme s’il s’agissait d’une suite de rapports différente.

Une suite de rapports virtuelle hérite de la plupart des niveaux de service de la suite de rapports de base (parente) tels que les paramètres d’eVar, les règles de traitement, les classifications, etc. Les paramètres suivants NE sont PAS hérités :

* Identifiant de la suite de rapports (RSID)
* Nom de la suite de rapports
* Groupes d’autorisations (les suites de rapports virtuelles peuvent être affectées à leurs propres groupes d’autorisations)

## Avantages des suites de rapports virtuelles  {#section_3420422FE6DF46EAB151FD9442AAFDC4}

Les clients paient pour les appels au serveur secondaire. L’élimination de ces appels peut donc entraîner des économies importantes. Une suite de rapports virtuelle est également complètement rétroactive. Si la suite de rapports globale contient déjà des données, les données pertinentes sont automatiquement incluses dans une nouvelle suite de rapports virtuelle. Une nouvelle suite de rapports secondaire ne commence à collecter des données qu’après sa création, de sorte qu’elle n’inclut aucune donnée historique. Lorsque vous implémentez Analytics, il vous suffit d’envoyer des données à une seule suite de rapports plutôt que de devoir créer des implémentations pour la suite de rapports globale et chaque suite de rapports secondaire.

Les suites de rapports virtuelles bénéficient des avantages suivants :

* Elles permettent de simplifier l’implémentation en autorisant l’utilisation d’un seul identifiant de suite de rapports dans tous les sites/domaines. Le regroupement de toutes les données dans une seule suite de rapports permet l’analyse des clients à mesure que nous migrons vers la prochaine génération d’Adobe Analytics.
* Les utilisateurs de votre entreprise n’affichent toujours que les segments de données dont ils ont besoin.
* Elles renforcent la sécurité en permettant aux utilisateurs administrateurs de contrôler plus facilement et plus précisément l’accès aux données après l’implémentation.
* Elles fournissent la possibilité de participer à la fonctionnalité Device Co-op.
* Mesure Personnes.
* Une vue client unique des données (à l’avenir).
* La possibilité de créer des suites de rapports virtuelles illimitées pour segmenter les données.

## Limites des suites de rapports virtuelles  {#section_F22A6DEBDC9848429E446F4CC2C4EEDE}

Les suites de rapports virtuelles comportent les limites suivantes :

* Les limites de segments s’appliquent aux suites de rapports virtuelles

   Une suite de rapports virtuelle n’est rien de plus qu’un segment appliqué à une suite de rapports. Comme chaque suite de rapports possède son propre entrepôt de données et son propre flux de données, l’utilisation de plusieurs suites de rapports offre des avantages que les segments n’offrent pas.
* Rapport en temps réel
* Les paramètres et noms de variables ne peuvent pas être personnalisés comme dans une suite de rapports complète

## Suites de rapports virtuelles par rapport au balisage multi-suite  {#section_317E4D21CCD74BC38166D2F57D214F78}

| Fonctionnalité | Suite de rapports virtuelle | Balisage multi-suite |
|--- |--- |--- |
| Offre des rapports en temps réel ou de données actives | Non | Oui |
| Fonctionne dans tous les outils d’Analytics (Analysis Workspace, Report Builder, Ad Hoc Analysis, etc.) | Oui.   Remarque : Vous pouvez modifier et identifier une suite de rapports virtuelle en tant que telle dans les Reports &amp; Analytics uniquement. Vous pouvez toutefois sélectionner des suites de rapports virtuelles dans les menus déroulants des suites de rapports dans d’autres outils. | Oui |
| Peut télécharger des données vers celle-ci (par le biais des classifications, des flux de données, etc.) | Non | Oui |
| Prend en charge la création de rapports, de signets, de tableaux de bord, de cibles, d’alertes, de segments, de mesures calculées, etc. | Oui | Oui |
| Peut être séparément ajoutée à des groupes d’autorisations | Oui | Oui |
| Peut utiliser les fonctions d’administration pour modifier des paramètres spécifiques de cette suite de rapports (Admin > Suites de rapports) | Non (les paramètres sont hérités du parent) | Oui |

## Combiner les suites de rapports virtuelles et le balisage multi-suite {#section_026FA3FCD7314DD18220E73EC5702AFF}

Dans certains cas, il est avantageux d’utiliser à la fois les suites de rapports virtuelles et le balisage multi-suite.

Par exemple, un détaillant peut utiliser une suite de rapports pour chaque marque et des suites de rapports virtuelles pour chaque marque afin de ventiler les données par région. De même, une organisation sportive peut utiliser une suite de rapports pour chaque équipe, puis des suites de rapports virtuelles pour diviser les fans entre ceux qui se trouvent dans la région de l’équipe et ceux qui se trouvent en dehors de la région.
