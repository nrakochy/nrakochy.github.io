---
layout:     post
title:      Idempotent
date:       2015-04-14 12:00:00
summary:    What does idempotent mean in HTTP-speak?
categories: http idempotent
---


Idempotent

What does idempotent mean in HTTP-speak? In a recent pairing session, my counterpart kept affirming idempotency for the functionality that we were building out. This was all fine and good, because the function was idempotent.
The problem is that, while the task was strictly idempotent, there was some murkiness that could lead to confusion down the road.

[Wikipedia](http://en.wikipedia.org/wiki/Idempotence) would tell us that idempotency is native to algebra, and I would refer to that article if you want to get into the nitty gritty. For this post, let's stick to HTTP methods.

So what is idempotent mean in practical terms? According to [RFC 2616 9.1.2]](http://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html), "methods can also have the property of 'idempotence' in that (aside from error or expiration issues) the side-effects of N > 0 identical requests is the same as for a single request."

Here's my attempt to translate that into English- a method is idempotent when it can be executed as many times as needed, and the outcome will always be the same regardless of how many times it is called. The result on execution #100 or execution #5000 will be the same as execution #1.

For an HTTP example, it is helpful to think about the difference between a POST request and a GET request. When you post a form to the server, you are sending new information over to be processed every time that you hit submit. Even duplicate information will be submitted as a new set of data each time.
With a GET request, you can get google.com as many times as you want, and you always get the same homepage.

Back to the pairing session. The function that we laid down could be executed as many times as needed, without side effects. It was indeed idempotent.

What I thought needed clarification is that there is more to idempotency than just update. `DELETE` is an [idempotent http method](http://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html). So long as everything is properly configured, and the server allows the method, you should be able to DELETE the User record with the id of 1 as many times as you would like.
There should be no difference in deleting that record 10 times or 100 times. The outcome should always be the same: the user record should be gone.

There is nothing wrong with creating a method that only updates. The confusion came where my counterpart was not interested in deleting anything in the functionality, because he wanted it to be idempotent. Alas, `delete` and `find_or_create_by` can both be idempotent and the terminology needs to be tightened up a bit.

