---
layout: single
title: Scam Hunting - Bancolombia
excerpt: #"This scam was funn to found"
date: 2025-05-03
classes: wide
header:
  teaser: /assets/images/scamhunting.png
  teaser_home_page: true
  icon: #/assets/images/hackthebox.webp
categories:
  - Infosec
tags:  
  - Scam Hunting
  - data leak
  - phishing
---

Hey!! After a long, long, long time without a post, it's time to let you know that I'm bringing up a new project named "Scam Hunting." The principal goal of this project is to understand how scams work, figure out the entire workflow, and identify scammers behind the scenes.


so ... say less...


In this case, I found a SMS scam with this content:

>BAN'C0L0M'BIA, 29/O4/2025, 
>H0Y, Se Activara tu PLAN SE-GUR0 DE VIDA por 211.300 C0P,
>Deseas Desactivarlo? Ingrese Aqui: https://maliciousurl.xxx

![](/assets/images/bancolombia-scam/SMS.jpeg)


Once we click it, we got a redirect to a new url with this:

![](/assets/images/bancolombia-scam/web.png)

The content of that website indicates that the victim activated life insurance, so he needs to deactivate or cancel it; otherwise, it will result in a charge on his bank account.

after a few minutes I found some requests to firestore.

>https://firestore.googleapis.com/v1/projects/xxxxx/databases/xxxx/documents/xxx/xxx

Due to bad security configurations like Public access was possible to get important information from the firestore of the scam.

From the information we found, like telegram tokens (admin bot and general bot, a few telegram channel IDs, API key), I started to enumerate information about those telegram bots.

![](/assets/images/bancolombia-scam/telegram_getme.png)


>#1 bot name @GpColombot

![](/assets/images/bancolombia-scam/telegram_getme_2.png)

>#2 bot name @ColomRes2Bot

>Apparently, Telegram has flagged the chat name as this_chat_is_scam

the next step was get information from the channel IDs

![](/assets/images/bancolombia-scam/infochats_token_bot.png)

> #1 Title Chat: Gp C.C Colombia

> #2 Title Chat: GPsucursal 2 bancolom

> #3 Title Chat: BankColomKeys

> #4 Title Chat: PhotoColomRes


![](/assets/images/bancolombia-scam/administrators1.png)

the first time that I take the evidence his username was "Donaldtrump_21" but few days later he changed it to "Bctc2" (premium telegram).

![](/assets/images/bancolombia-scam/bctc2.png)

After reviewing the posts from that profile, we were able to identify some data that could give us an indication of their possible location.

![](/assets/images/bancolombia-scam/waze%20ruta.png)

there is a few bulding names... so lets google it...

![](/assets/images/bancolombia-scam/googlemaps.png)

As you can see, they belong to the city of Barranquilla (Colombia).




## Conclusion

People still being victim of scams in general, no matters how unreal can be look those scams... We have to share the knowledge and explain to people how this kind of scam works. :D  



