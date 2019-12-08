---
description: Permet de contrôler l’accès aux données de création de rapports. Les options incluent les mots de passe difficiles à deviner, l’expiration du mot de passe, ainsi que les restrictions d’adresses IP et de domaines de courriel.
title: Gestionnaire de sécurité
topic: Admin tools
uuid: b3fbdba0-e2bf-4d67-92e3-ef05711141d4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Gestionnaire de sécurité

Le Gestionnaire de sécurité vous permet de contrôler l’accès aux données de création de rapports. Les options incluent les mots de passe difficiles à deviner, l’expiration du mot de passe, ainsi que les restrictions d’adresses IP et de domaines de courriel.

## Paramètres

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Paramètres de la société]** &gt; **[!UICONTROL Sécurité]**

| Paramètre | Description |
|--- |--- |
| Requiert des mots de passe difficiles à deviner | Force l’utilisateur à créer des mots de passe plus sécurisés qui satisfont aux règles suivantes : <ul><li>Comporter au moins huit caractères.</li><li>Doit comporter au moins un symbole/caractère numérique entre le premier et le dernier caractères.</li><li>Doit comporter au moins un caractère alphabétique.</li><li>Ne pas figurer dans un dictionnaire ou ne contenir aucun mot du dictionnaire (anglais).</li><li>Ne pas inclure trois (3) caractères consécutifs figurant dans le nom de connexion de l’utilisateur.</li><li>Être différent des 10 mots de passe précédents.</li></ul>**Remarque**: Cette fonctionnalité est appliquée aux nouveaux mots de passe. Elle ne vérifie pas les mots de passe existants, ni ne force les utilisateurs à les modifier. C’est pourquoi il est conseillé d’activer l’expiration du mot de passe pour forcer les utilisateurs à modifier leurs mots de passe et à se conformer aux nouvelles règles en matière de mots de passe renforcés. |
| Expiration du mot de passe | Force les utilisateurs à changer régulièrement le mot de passe de leur compte utilisateur. Vous pouvez indiquer l’intervalle d’expiration des mots de passe et les forcer à expirer immédiatement. |
| Exiger des restrictions d’identification par IP | (Cette fonctionnalité ne peut pas être utilisée conjointement avec la connexion à Experience Cloud. Notez que cette fonctionnalité ne sera plus disponible à compter d’octobre 2020. [Plus..](/help/admin/company/login-restrictions-eol.md).<br> Limite l’accès aux rapports à des adresses IP ou des plages d’adresses IP spécifiques. Vous pouvez ajouter jusqu’à 100 entrées dans la liste Filtre d’adresses IP ; chaque entrée peut être une adresse spécifique ou une plage d’adresses. L’option Exiger des restrictions d’identification par IP n’est pas appliquée tant que la liste Filtre d’adresses IP ne comporte pas au moins une entrée. Adresse IP acceptée : pour spécifier une plage d’adresses IP, placez celle-ci entre crochets (par exemple :       `192.168.10.[20-240]`). You can also use wildcards to specify any number from 0 to 255 (for example, `192.168.[10-14].*8) Failed logins are logged and viewable from the [Usage and Access Log](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/logs.html#section_6FBAF92D9EA244809C45A78A2F0A7232). |
| Mettre en place les restrictions de domaine de courriel | Filtre les adresses et domaines de courriel auxquels Analytics envoie des signets, des rapports téléchargeables et des alertes. La liste Filtre de courriel prend en charge jusqu’à 100 entrées ; chacune d’elles pouvant être une adresse ou un domaine de courriel complet. Si un rapport planifié contient une destination de courriel non approuvée, Analytics envoie une notification par courriel du problème, ainsi qu’un lien pour annuler la planification du rapport. **[!UICONTROL L’option Mettre en place les restrictions de domaine de courriel]** n’est pas appliquée tant que la liste Filtre de domaine de courriel accepté ne comporte pas au moins une entrée. **[!UICONTROL Adresse électronique et domaines]** acceptés : Pour spécifier une plage d’adresses IP, placez-la entre crochets (par exemple, 192.168.10.[20-240]). You can also use wildcards to specify any number from 0 to 255 (for example, 192.168.[10-14].*) |
| Notification de récupération de mot de passe | Avertit les administrateurs spécifiés lorsqu’un utilisateur tente de réinitialiser un mot de passe de compte utilisateur. **[!UICONTROL Admins disponibles]** : affiche tous les administrateurs. Vous pouvez utiliser les combinaisons Ctrl + clic et Maj + clic pour sélectionner plusieurs administrateurs. **[!UICONTROL Membres de la messagerie]** : affiche le groupe de messagerie défini actuellement. |
