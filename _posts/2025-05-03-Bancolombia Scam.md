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

Hey!! After a long, long time without a post, it's time to let you know that I'm bringing up a new project named "Scam Hunting." The principal goal of this project is to understand how scams work, figure out the entire workflow, and identify scammers behind the scenes.


In this case, I found a SMS scam with this content:

>BAN'C0L0M'BIA, 29/O4/2025, 
>H0Y, Se Activara tu PLAN SE-GUR0 DE VIDA por 211.300 C0P,
>Deseas Desactivarlo? Ingrese Aqui: https://maliciousurl.xxx

![](/assets/images/bancolombia-scam/SMS.jpeg)


Once we click it, we got a redirect to a new url with this:

![](/assets/images/bancolombia-scam/web.png)

The content of that website indicates that the victim activated life insurance, so he needs to deactivate or cancel it; otherwise, it will result in a charge on his bank account.

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

the first time that I take the evidence his username was "Donaldtrump_21" but few days later he changed it.

![](/assets/images/bancolombia-scam/username.png)

After reviewing the posts from that profile, we were able to identify some data that could give us an indication of their possible location.

![](/assets/images/bancolombia-scam/waze%20ruta.png)

there is a few bulding names... so lets google it...

![](/assets/images/bancolombia-scam/googlemaps.png)

As you can see, they belong to the city of Barranquilla (Colombia).

and some tattoos...

![](/assets/images/bancolombia-scam/tattoo%20brazo.png)


Ok ... Ok... 

We identified some information from the bots and the administrator account, but what about the information they got from the victims?

lets see...

I was able to forward all the information from their group chats to my Telegram account.

![](/assets/images/bancolombia-scam/chat_is_scam.png)

> 810 pictures (I had to stop at this point forwarding the data from this bot because there is more than 8000 data, IDs (pictures), user and passwords).

![](/assets/images/bancolombia-scam/cedulas1.png)

now the admin bot ...

![](/assets/images/bancolombia-scam/GpColombiaBot.png)

> 3926 registers (I had to stop at this point forwarding the data from this bot because there is more than 16000 data, IDs, user and passwords, credit card numbers).

![](/assets/images/bancolombia-scam/datos_tarjetas.png)

And ... That's it, guys !! ... I hope you enjoyed this post.


## Conclusion

- People still being victim of scams in general, no matters how unreal can be look those scams... We have to share the knowledge and explain to people how this kind of scam works. :D  

- This scam was reported to Bancolombia, and they are taking action on the case.

