---
description: Après avoir effectué toutes les mises à jour de site web nécessaires, utilisez une visionneuse de trafic réseau, telle que Charles*, Chrome Developer Tools ou Firebug*, pour confirmer que DFA communique avec les serveurs de collecte Adobe.
keywords: DFA
seo-description: Après avoir effectué toutes les mises à jour de site web nécessaires, utilisez une visionneuse de trafic réseau, telle que Charles*, Chrome Developer Tools ou Firebug*, pour confirmer que DFA communique avec les serveurs de collecte Adobe.
seo-title: Confirmation d’une intégration DFA réussie
solution: Analytics
title: Confirmation d’une intégration DFA réussie
topic: Connecteurs de données
uuid: d 658 cd 7 c -6377-439 a -850 c-ecea 8 c 41 f 970
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Confirmation d’une intégration DFA réussie{#confirming-a-successful-dfa-integration}

Après avoir effectué toutes les mises à jour de site web nécessaires, utilisez une visionneuse de trafic réseau, telle que Charles*, Chrome Developer Tools ou Firebug*, pour confirmer que DFA communique avec les serveurs de collecte Adobe.

Après avoir déployé le fichier DFA `s_code.js`, utilisez la visionneuse de trafic réseau pour afficher les demandes entre DFA et les serveurs de collecte de données Adobe, en recherchant ce qui suit :

* A request to DFA's `fls.doubleclick.net/json` service. Ce service peut répondre différemment selon la version de DFA que vous utilisez. Avec l’intégration de DFA version 1.5 :

   * Une redirection HTTP 302 vers [!DNL ad.doubleclick.net]. Envoie une balise d’emplacement dans la réponse qui contient des informations sur le visiteur de la publicité.
   * This Location tag causes a redirect to [!DNL integrate.112.2o7.net/dfa_echo]. Ce service traduit les informations au sujet du visiteur de la publicité dans la chaîne codée JSON (JavaScript Object Notati on). Ces données sont renvoyées avec une réponse HTTP 200 OK.

* Avec l’intégration de DFA version 2.0 (fonction AdServing avancée activée) :

   * [!DNL fls.doubleclick.net] répond directement avec une réponse 200 OK.

Dans les deux cas, une demande réussie engendre une demande aux serveurs de collecte de données Adobe qui contient le paramètre vX, où X est votre numéro d’eVar d’affichage publicitaire. Cette valeur de paramètre prend la forme : DFA-XXXX-XXXX- XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX. Cette chaîne contient les données au sujet du dernier clic et de la dernière impression pour le visiteur actuel.
