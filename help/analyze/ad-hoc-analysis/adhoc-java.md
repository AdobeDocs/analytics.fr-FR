---
description: Instructions sur l’exécution d’Ad Hoc Analysis avec Java 11.
title: Exécution de l’Ad Hoc Analysis sur Java 11
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Exécution de l’Ad Hoc Analysis sur Java 11

Vous devez suivre d’autres étapes lors de l’exécution des  ad hoc  avec Java 11 par rapport à Java 8.

## Conditions préalables

Collaborez avec votre équipe informatique pour vous assurer que les éléments suivants sont en place :

* Java 11 doit être installé, avec la variable d’environnement *JAVA_HOME*
* JavaFX doit être installé, avec la variable *PATH_TO_FX_SDK*  pointée vers le répertoire du SDK JavaFX. Par exemple, *PATH_TO_FX_SDK=/homedir/javafx-sdk-11.0.2* sur un Mac ou *PATH_TO_FX_SDK=C:\Users\username\javafx-sdk-11.0.2* sur un PC.

## Installation du ad hoc   pour Java 11

1. Accédez à **[!UICONTROL Analytics > Tools > Ad Hoc Analysis]**.
1. Cliquez sur **[!UICONTROL Ad Hoc Analysis (Java 11)]**. Un fichier zip est alors téléchargé.
1. Décompressez le fichier téléchargé.
1. **Sélectionnez le fichier**.bat (PC) ou .sh (Mac). Sélectionnez le fichier de centre de données approprié en regardant le numéro qui suit « sc » dans l’URL Adobe Analytics. (3 = LON, 4 = SIN, 5 = PNW) Si vous utilisez un PC, vérifiez s’il s’agit d’un système d’exploitation Windows 32 bits ou 64 bits en sélectionnant « À propos de votre PC ». Sélectionnez ensuite le fichier .bat approprié.
1. **Exécutez le fichier** sélectionné. Pour PC : Cliquez deux fois sur le fichier .bat. Pour Mac : Cliquez avec le bouton droit sur le fichier .sh, puis sélectionnez **[!UICONTROL Open With > Other... > Utilities > (Enable all applications) > select Terminal > Open]**.
1. Connectez-vous à Ad Hoc Analysis.

>[!NOTE] Les méthodes d’authentification Federated et Enterprise ID ne sont pas compatibles avec la version Java 11 d’Ad Hoc Analysis.

## Fonctionnalités non prises en charge dans Ad Hoc Analysis (Java 11)

Il existe quelques limitations connues dans la version de Java 11 compatible avec Ad Hoc Analysis :

* Les méthodes d’authentification Federated &amp; Enterprise ID ne sont pas prises en charge.
* Les systèmes d’exploitation Linux ne sont pas pris en charge.
* Lorsque vous utilisez un Mac, n’utilisez pas le menu d’application Mac (y compris *cmd + Q*). Cela peut entraîner la fermeture des  ad hoc  sans avertissement. Utilisez plutôt le menu dans les  ad hoc .
* La visualisation de l’ du site  n’est pas prise en charge lors de l’exécution d’un de  ad hoc sous Mac OS.

## FAQ

**Q : J’obtiens une erreur « Cannot find \bin\javaw » (exemple ci-dessous), que dois-je faire ?**

![](/help/analyze/ad-hoc-analysis/assets/error-java.png)

R : Si cette erreur s’affiche, travaillez avec votre équipe informatique pour définir la variable d’environnement *JAVA_HOME* nécessaire pour exécuter Ad Hoc Analysis avec Java 11.
