---
title: Type de référent
description: Type de parrain, en fonction de la provenance du visiteur.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 0%

---


# Type de référent

La dimension &quot;type de Parrain&quot; signale les canaux génériques sur lesquels les visiteurs ont cliqué pour arriver sur votre site. Adobe conserve les règles pour chaque valeur de dimension, à la différence des canaux [](marketing-channel.md)marketing, où votre organisation conserve les règles pour chaque canal.

## Renseigner cette dimension avec des données

Cette dimension fait référence à plusieurs tables de recherche internes à Adobe. Chaque valeur est basée sur le [parrain](referrer.md) de l’accès, qui dépend des filtres [d’URL](/help/admin/admin/internal-url-filter-admin.md)internes. Assurez-vous que la dimension de parrain et les filtres d’URL internes sont correctement configurés.

## Valeurs de dimension

Les valeurs de dimension incluent le type de parrain de l’accès. Les valeurs spécifiques sont les suivantes :

* **Tapé/marqué**: Aucune donnée de parrain n&#39;existe pour l&#39;accès.
* **Moteurs** de recherche : Le parrain provient d&#39;un moteur de recherche reconnu qui inclut une chaîne de requête de mot-clé.
* **Réseaux sociaux:**: Les données de Parrain appartenaient à un réseau social reconnu par Adobe.
* **Autres sites** Web : Les données de Parrain n&#39;appartenaient pas à un moteur de recherche ou à un réseau social reconnu par Adobe.
* **Disque dur**: Le Parrain provient d&#39;une copie locale d&#39;une page Web sur le disque dur du visiteur.
* **Courriel**: Le Parrain provient d’une URL avec un protocole de `imap://` ou `mail://`. N’inclut pas les services de messagerie en ligne, car ils utilisent généralement `https://` le protocole.

### Réseaux sociaux

La liste suivante fait référence au tableau de recherche &quot;Réseaux sociaux&quot; utilisé par Adobe. Adobe fournit cette liste à titre de courtoisie aux clients de Adobe Analytics. Si vous souhaitez recommander à Adobe d’ajouter un domaine à cette liste, demandez à un délégué de l’assistance de votre entreprise de contacter le service d’assistance clientèle.

>[!NOTE]
>
>Cette liste est différente de la liste par défaut des réseaux sociaux dans les règles [de traitement des canaux](../c-marketing-channels/c-rules.md)marketing.

* `12seconds.tv`
* `t.163.com`
* `4travel.jp`
* `advogato.org`
* `ameba.jp`
* `anobii.com`
* `asmallworld.net`
* `avforums.com`
* `backtype.com`
* `badoo.com`
* `bebo.com`
* `bigadda.com`
* `bigtent.com`
* `biip.no`
* `blackplanet.com`
* `blogspot.com`
* `blogster.com`
* `blomotion.jp`
* `bolt.com`
* `brightkite.com`
* `buzznet.com`
* `cafemom.com`
* `care2.com`
* `classmates.com`
* `cloob.com`
* `collegeblender.com`
* `cyworld.co.kr`
* `cyworld.com.cn`
* `dailymotion.com`
* `yozm.daum.net`
* `delicious.com`
* `deviantart.com`
* `digg.com`
* `diigo.com`
* `disqus.com`
* `draugiem.lv`
* `facebook.com`
* `faceparty.com`
* `fc2.com`
* `flickr.com`
* `flixster.com`
* `fotolog.com`
* `foursquare.com`
* `friendfeed.com`
* `friendsreunited.com`
* `friendsreunited.co.uk`
* `friendster.com`
* `fubar.com`
* `gaiaonline.com`
* `geni.com`
* `goodreads.com`
* `plus.google.com`
* `plus.url.google.com`
* `grono.net`
* `habbo.com`
* `hatena.ne.jp`
* `t.hexun.com`
* `hi5.com`
* `hyves.nl`
* `ibibo.com`
* `identi.ca`
* `t.ifeng.com`
* `imeem.com`
* `hotnews.infoseek.co.jp`
* `instagram.com`
* `intensedebate.com`
* `irc-galleria.net`
* `iwiw.hu`
* `jaiku.com`
* `kaixin001.com`
* `kaixin002.com`
* `kakaku.com`
* `kanshin.com`
* `kozocom.com`
* `last.fm`
* `linkedin.com`
* `livejournal.com`
* `lnkd.in`
* `me2day.net`
* `meetup.com`
* `mister-wong.com`
* `mixi.jp`
* `mixx.com`
* `mouthshut.com`
* `multiply.com`
* `mumsnet.com`
* `myheritage.com`
* `mylife.com`
* `myspace.com`
* `myyearbook.com`
* `nasza-klasa.pl`
* `matome.naver.jp`
* `netlog.com`
* `nettby.no`
* `netvibes.com`
* `nextdoor.com`
* `nicovideo.jp`
* `ning.com`
* `odnoklassniki.ru`
* `ok.ru`
* `orkut.com`
* `pakila.jp`
* `t.people.com.cn`
* `photobucket.com`
* `pinterest.com (and all international domains)`
* `plaxo.com`
* `plurk.com`
* `po.st`
* `t.qq.com`
* `mp.weixin.qq.com`
* `boards.qwant.com`
* `reddit.com`
* `renren.com`
* `blog.seesaa.jp`
* `t.sina.com.cn`
* `skyrock.com`
* `slideshare.net`
* `smcb.jp`
* `smugmug.com`
* `t.sohu.com`
* `sonico.com`
* `studivz.net`
* `stumbleupon.com`
* `t.co`
* `tabelog.com`
* `tagged.com`
* `taringa.net`
* `thefancy.com`
* `toutiao.com`
* `tripit.com`
* `trombi.com`
* `trytrend.jp`
* `tuenti.com`
* `tumblr.com`
* `twine.com`
* `twitter.com`
* `uhuru.jp`
* `viadeo.com`
* `vimeo.com`
* `vk.com`
* `wayn.com`
* `weibo.com`
* `weourfamily.com`
* `wer-kennt-wen.de`
* `wordpress.com`
* `xanga.com`
* `xing.com`
* `answers.yahoo.com`
* `yammer.com`
* `yaplog.jp`
* `yelp.com`
* `yelp.co.uk`
* `youku.com`
* `youtube.com`
* `yuku.com`
* `zooomr.com`
* `zhihu.com`

### Moteurs de recherche dans la valeur de dimension &quot;Autres sites Web&quot;

Lorsque vous vue des domaines spécifiques dans la dimension &quot;type de Parrain&quot;, il peut y avoir des domaines auxquels vous vous attendez sous &quot;moteurs de recherche&quot; répertoriés à la place sous &quot;Autres sites Web&quot;. Par exemple, vous pouvez voir `'google.com'` sous &quot;Autres sites Web&quot;.

* **Domaines de moteurs de recherche dans la valeur** de dimension &quot;Moteurs de recherche&quot; : Le parrain répondait à tous les critères pour être classé comme moteur de recherche par Adobe. Le domaine référent est un moteur de recherche valide ** et l’URL référente contient un paramètre de chaîne de requête de mot-clé.
* **Domaines de moteurs de recherche dans la valeur** de dimension &quot;Autres sites Web&quot; : L&#39;URL référente ne répondait pas à tous les critères de classification en tant que moteur de recherche. Les exemples courants incluent les sous-domaines dédiés à d’autres fonctionnalités en plus de la recherche. Par exemple, `mail.google.com` ou `autos.yahoo.com` ne sont pas des moteurs de recherche, mais résident sur un domaine de niveau supérieur généralement associé à la recherche. Ces sous-domaines n&#39;incluent pas de chaîne de requête de mots-clés, c&#39;est pourquoi ils sont inclus dans &quot;Autres sites Web&quot; au lieu de &quot;Moteurs de recherche&quot;.
