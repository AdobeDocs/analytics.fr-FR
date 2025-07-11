---
title: Type de référent
description: Le type de référent en fonction de la provenance du visiteur.
feature: Dimensions
exl-id: a6cfcbf4-cd08-4e7f-8e86-47488ceb0ea3
source-git-commit: 825cded49c0ff456925e522ae2d0660b09ea6edd
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 96%

---

# Type de référent

La [dimension](overview.md) « Type de référent » indique les canaux génériques sur lesquels les visiteurs et visiteuses ont cliqué pour accéder à votre site. Adobe conserve les règles pour chaque élément de dimension, à la différence des [canaux marketing](marketing-channel.md), où votre entreprise conserve les règles pour chaque canal.

## Renseignement de cette dimension avec des données

Cette dimension fait référence à plusieurs tables de recherche internes à Adobe. Chaque valeur est basée sur le [référent](referrer.md) de l’accès, qui dépend des [filtres d’URL internes](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md). Veillez à configurer correctement la dimension Référent et les filtres d’URL internes.

## Éléments de dimension

Les éléments de dimension comprennent le type de référent de l’accès. Les valeurs spécifiques incluent les éléments suivants :

* **Tapé/Marqué d’un signet** : l’accès ne contient aucune donnée de référent.
* **Moteurs de recherche** : le référent provient d’un moteur de recherche reconnu comprenant une chaîne de requête de mot-clé.
* **Réseaux sociaux** : les données de référent appartiennent à un réseau social reconnu par Adobe.
* **Autres sites Web** : les données de référent n’appartiennent pas à un moteur de recherche ou à un réseau social reconnu par Adobe.
* **Disque dur** : le référent est issu d’une copie locale d’une page Web sur le disque dur du visiteur.
* **E-mail** : le référent est issu d’une URL avec un protocole `imap://` ou `mail://`. Ne comprend pas les services de messagerie en ligne, car ils utilisent généralement le protocole `https://`.

### Réseaux sociaux

La liste suivante fait référence à la table de recherche « Réseaux sociaux » utilisée par Adobe. Adobe fournit cette liste aux clients d’Adobe Analytics. Si vous souhaitez recommander à Adobe d’ajouter un domaine à cette liste, demandez à un délégué d’assistance de votre entreprise de contacter l’assistance clientèle.

>[!NOTE]
>
>Cette liste est différente de la liste par défaut des réseaux sociaux des [règles de traitement des canaux marketing](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md).

* `12seconds.tv`
* `4travel.jp`
* `advogato.org`
* `ameba.jp`
* `anobii.com`
* `answers.yahoo.com`
* `asmallworld.net`
* `avforums.com`
* `backtype.com`
* `badoo.com`
* `bebo.com`
* `bigadda.com`
* `bigtent.com`
* `biip.no`
* `blackplanet.com`
* `blog.seesaa.jp`
* `blogspot.com`
* `blogster.com`
* `blomotion.jp`
* `bolt.com`
* `brightkite.com`
* `bsky.app`
* `buzznet.com`
* `cafemom.com`
* `care2.com`
* `classmates.com`
* `cloob.com`
* `collegeblender.com`
* `cyworld.co.kr`
* `cyworld.com.cn`
* `dailymotion.com`
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
* `go.bsky.app`
* `goodreads.com`
* `plus.google.com`
* `plus.url.google.com`
* `grono.net`
* `habbo.com`
* `hatena.ne.jp`
* `hi5.com`
* `hotnews.infoseek.co.jp`
* `hyves.nl`
* `ibibo.com`
* `identi.ca`
* `t.ifeng.com`
* `imeem.com`
* `instagram.com`
* `intensedebate.com`
* `irc-galleria.net`
* `iwiw.hu`
* `jaiku.com`
* `jp.myspace.com`
* `kaixin001.com`
* `kakaku.com`
* `kanshin.com`
* `kozocom.com`
* `last.fm`
* `likeshop.me`
* `linkedin.com`
* `linkin.bio`
* `livejournal.com`
* `lnkd.in`
* `meetup.com`
* `me2day.net`
* `mister-wong.com`
* `mixi.jp`
* `mixx.com`
* `mouthshut.com`
* `mp.weixin.qq.com`
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
* `photobucket.com`
* `pinterest.com`
* `pinterest.co.uk`
* `plaxo.com`
* `plurk.com`
* `po.st`
* `reddit.com`
* `renren.com`
* `skyrock.com`
* `slideshare.net`
* `smcb.jp`
* `smugmug.com`
* `snapchat.com`
* `sonico.com`
* `studivz.net`
* `stumbleupon.com`
* `t.163.com`
* `t.co`
* `t.hexun.com`
* `t.people.com.cn`
* `t.qq.com`
* `t.sina.com.cn`
* `t.sohu.com`
* `tabelog.com`
* `tagged.com`
* `taringa.net`
* `thefancy.com`
* `threads.com`
* `threads.net`
* `tiktok.com`
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
* `web-cdn.bsky.app`
* `weibo.com`
* `weourfamily.com`
* `wer-kennt-wen.de`
* `wordpress.com`
* `x.com`
* `xanga.com`
* `xing.com`
* `yammer.com`
* `yaplog.jp`
* `yelp.com`
* `yelp.co.uk`
* `youku.com`
* `youtube.com`
* `yozm.daum.net`
* `yuku.com`
* `zooomr.com`
* `zhihu.com`

### Moteurs de recherche dans l’élément de dimension « Autres sites Web »

Lorsque vous consultez des domaines spécifiques dans la dimension « Type de référent », il se peut que certains domaines soient répertoriés sous « Autres sites Web » et non sous « Moteurs de recherche ». Par exemple, `'google.com'` pourrait se trouver sous « Autres sites Web ».

* **Domaines de moteur de recherche dans l’élément de dimension « Moteurs de recherche »** : le référent répond à tous les critères pour être classé comme moteur de recherche par Adobe. Le domaine référent est un moteur de recherche valide *et* l’URL de référence contient un paramètre de chaîne de requête de mot-clé.
* **Domaines de moteur de recherche dans l’élément de dimension « Autres sites Web »** : l’URL de référence ne répond pas à tous les critères pour être classés comme moteur de recherche. Les exemples courants comprennent les sous-domaines dédiés à d’autres fonctionnalités que la recherche. Par exemple, `mail.google.com` ou `autos.yahoo.com` ne sont pas des moteurs de recherche, mais résident sur un domaine de niveau supérieur généralement associé à la recherche. Ces sous-domaines ne comprennent pas de chaîne de requête de mot-clé, c’est pourquoi ils se trouvent dans « Autres sites Web » au lieu de « Moteurs de recherche ».
