---
description: Instructions sur l’exécution des analyses ad hoc avec Java 11.
seo-description: Instructions sur l’exécution des analyses ad hoc avec Java 11.
seo-title: Analyses ad hoc et Java 11
title: Exécution de l’Ad Hoc Analysis sur Java 11
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Exécution de l’Ad Hoc Analysis sur Java 11

Lors de l’exécution d’Ad Hoc Analysis avec Java 11, certaines étapes supplémentaires doivent être suivies par rapport à l’exécution avec Java 8.

## Conditions préalables

Travaillez avec votre équipe informatique pour vous assurer que les éléments suivants sont en place :

* Java 11 must be installed, with *JAVA_HOME* environment variable set
* JavaFX doit être installé, avec la variable d’environnement *PATH_TO_FX_SDK* pointée vers le répertoire du SDK JavaFX. Par exemple, *PATH_TO_TO_FX_SDK=/homedir/javafx-sdk-11.0.2* sur un Mac ou *PATH_TO_TO_FX_SDK=C:\Users\username\javafx-sdk-11.0.2* sur un PC.

## Installation d’Ad Hoc Analysis pour Java 11

1. Accédez à **[!UICONTROL Analytics &gt; Outils &gt; Ad Hoc Analysis]**.
1. Cliquez sur **[!UICONTROL Ad Hoc Analysis (Java 11)]**. Un fichier compressé est téléchargé.
1. Décompressez le fichier téléchargé.
1. **Sélectionnez le fichier .bat (PC) ou .sh (Mac)**. Sélectionnez le fichier du centre de données approprié en observant le numéro suivant "sc" dans l’URL d’Adobe Analytics. (3 = LON, 4 = SIN, 5 = PNW) Si vous utilisez un PC, vérifiez si vous exécutez un système d'exploitation Windows 32 bits ou 64 bits en accédant à "À propos de votre PC". Sélectionnez ensuite le fichier .bat approprié.
1. **Exécutez le fichier sélectionné**. Pour PC : double-cliquez sur le fichier .bat. Pour Mac : cliquez avec le bouton droit de la souris sur le fichier .sh, puis sélectionnez **[!UICONTROL Ouvrir avec &gt; Autre... &gt; Utilitaires &gt; (Activer toutes les applications) &gt; sélectionnez Terminal &gt; Ouvrir]**.
1. Connectez-vous à Ad Hoc Analysis.

> [!NOTE] Les méthodes d’authentification Federated et Enterprise ID ne sont pas compatibles avec la version Java 11 des analyses ad hoc.

## Fonctionnalités non prises en charge dans Ad Hoc Analysis (Java 11)

Il existe quelques limitations connues dans la version Java 11 compatibles avec les analyses ad hoc :

* Les méthodes d’authentification Federated et Enterprise ID ne sont pas prises en charge.
* Les systèmes d’exploitation Linux ne sont pas pris en charge.
* When using a Mac, do not use the Mac application menu (including *cmd + Q*). Ceci peut entraîner la fermeture d’Ad Hoc Analysis sans avertissement. Utilisez plutôt le menu d’Ad Hoc Analysis.
* La visualisation de site d’Ad Hoc Analysis n’est pas prise en charge lors de l’exécution d’Ad Hoc Analysis sous MacOS.

## FAQ

**Q : Je reçois une erreur "Impossible de trouver \bin\javaw" (exemple ci-dessous) - que dois-je faire ?**

![](/help/analyze/ad-hoc-analysis/assets/error-java.png)

R : Si cette erreur s’affiche, travaillez avec votre équipe informatique pour définir la variable d’environnement *JAVA_HOME* nécessaire pour exécuter Ad Hoc Analysis avec Java 11.
