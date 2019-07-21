---
source-git-commit: 71899840dd5b401c6892b6ad5088d4a32fd07042
translation-type: tm+mt

---
# Accès tardifs

Les données historiques peuvent arriver après le traitement d'une tâche de flux de données pendant une heure ou une journée donnée, par exemple par le biais d'accès horodatés ou de sources de données. Les accès tardifs sont une personnalisation dorsale fournie par Adobe pour inclure ces données dans les flux de données.

## Fonctionnement des accès tardifs

Lorsqu'un flux de données traite normalement les données, il recherche uniquement les données dans sa fenêtre de création de rapports (généralement l'heure ou la journée la plus récente). Si les données arrivent après le traitement du flux de traitement de la fenêtre de création de rapports, ces données ne sont jamais incluses dans un flux de données.

Lorsque les accès tardifs sont activés, la méthode de traitement change pour inclure ces données. Chaque fois qu'un flux de données traite des données, il recherche tous les accès tardifs qui sont arrivés et les lots dans le prochain fichier de flux de données envoyé à votre site FTP.

## Activation des accès tardifs

Les accès tardifs peuvent être activés manuellement par Adobe sur des flux de données individuels. Avant de procéder ainsi, tenez compte des points suivants :

* Les données des différents jours apparaissent fréquemment dans les flux de données lorsque les accès tardifs sont activés. Assurez-vous que la plate-forme utilisée pour assimiler les flux de données peut contenir des données de différents jours dans le même fichier.
* Les accès tardifs augmentent le temps de traitement. En règle générale, ce délai est inférieur à l'heure, mais il peut s'écouler plusieurs heures ou plus si votre suite de rapports reçoit un grand nombre d'accès tardifs. Adobe recommande d'activer ce paramètre si l'arrivée opportune des flux de données est impérative pour le flux de travail de votre entreprise.
* Si un fichier de flux de données est retraité, les accès tardifs inclus dans le fichier d'origine ne sont pas inclus dans le fichier retraité.

Si vous souhaitez activer les accès tardifs pour un flux de données récurrent existant, demandez à un utilisateur pris en charge de contacter le service d'assistance clientèle et d'inclure ce qui suit :

* Notez que vous souhaitez activer les accès tardifs pour un flux de données spécifique.
* Identifiant de suite de rapports
* Nom du flux de données
