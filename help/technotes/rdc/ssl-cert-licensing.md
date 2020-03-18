---
title: Licences de certificat SSL
description: Procédures de certificat pour les certificats gérés par le client
translation-type: ht
source-git-commit: 290838566b86f71902abd303b5c43dd2661d3ce1

---


# Licences de certificat SSL/TLS

Adobe vous conseille de gérer le certificat sans frais supplémentaires via le [programme de certificat géré Adobe](https://marketing.adobe.com/resources/help/fr_FR/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html).  Le programme de certificat géré Adobe est entièrement automatisé et garantit que les certificats sont renouvelés en temps voulu afin qu’il n’y ait pas d’incidence en raison de l’expiration des certificats.

Si vous choisissez de ne pas utiliser le [programme de certificat géré Adobe](https://marketing.adobe.com/resources/help/fr_FR/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html), vous devez fournir un certificat SSL/TLS à utiliser pour les cookies propriétaires.

Si vous fournissez vos propres certificats, il vous incombe de les acheter et de les gérer.  Votre certificat SSL/TLS doit inclure une licence de serveur illimitée.

Pour garantir la sécurité des certificats, obtenez une demande de signature de certificat [CSR] auprès d’Adobe et demandez à votre autorité de certification de signer le certificat.  Fournissez à Adobe le certificat signé à mettre en œuvre.  Ce processus permet de conserver la sécurité de la clé du certificat.  L’assistance clientèle d’Adobe vous aidera dans ce processus.

Dans le cadre de la maintenance des certificats, au moins un mois avant l’expiration de votre certificat, demandez à l’autorité de certification de votre choix de renouveler le certificat et fournissez-le à Adobe.  Ce certificat doit utiliser le même CSR que précédemment.  Contactez Adobe si vous avez besoin d’une copie du CSR ou si vous souhaitez générer un nouveau CSR avec une nouvelle clé.

Vous pouvez contacter l’assistance clientèle à customercare@adobe.com ou au 1-800-497-0335.

Les autorités de certificats couramment utilisées sont DigiCert, Comodo et GeoTrust.
