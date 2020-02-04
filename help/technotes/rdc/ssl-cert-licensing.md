---
title: Licences de certificat SSL
description: Procédures de certificat pour les certificats gérés par le client
translation-type: tm+mt
source-git-commit: 290838566b86f71902abd303b5c43dd2661d3ce1

---


# Licence de certificat SSL/TLS

Adobe recommande de gérer votre certificat sans frais supplémentaires via le programme [Adobe Managed Certificate Program](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html).  Le programme Adobe Managed Certificate est entièrement automatisé et garantit que les certificats sont renouvelés en temps voulu afin de ne pas avoir d’incidence en raison de certificats expirés.

Si vous choisissez de ne pas utiliser le programme [Adobe Managed Certificate Program](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html) , vous devez fournir un certificat SSL/TLS à utiliser pour les cookies propriétaires.

Si vous fournissez vos propres certificats SSL, il vous incombe de les acheter et de les gérer.  Votre certificat SSL/TLS doit inclure une licence serveur illimitée.

Pour garantir la sécurité des certificats, obtenez une demande de signature de certificat [CSR] auprès d’Adobe et demandez à votre autorité de certification de signer le certificat.  Fournissez à Adobe le certificat signé pour l’implémentation.  En suivant ce processus, la sécurité de la clé du certificat est conservée.  Le service à la clientèle Adobe vous aidera dans ce processus.

Dans le cadre de la maintenance des certificats, au moins un mois avant l’expiration de votre certificat, demandez à votre autorité de certification d’obtenir un certificat renouvelé et de le fournir à Adobe.  Ce certificat doit utiliser le même CSR utilisé précédemment.  Contactez Adobe si vous avez besoin d’une copie du fichier CSR ou si vous souhaitez qu’un nouveau fichier CSR soit généré avec une nouvelle clé.

Le service à la clientèle peut être contacté à l’adresse customercare@adobe.com ou au 1-800-497-0335.

Les autorités de certificats couramment utilisées sont DigiCert, Comodo et GeoTrust.
