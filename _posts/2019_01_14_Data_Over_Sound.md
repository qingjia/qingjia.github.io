---
layout: post
title: Data over Sound 
categories: [Python,Chirp]
tags: [Python, dtmf,chirp]

---
![background]({{ site.baseurl }}\images\DOS\background.jpg)

When I saw Lakala, I was confused how it communicate with Phone by Audio Jack. It's like a magic. it's digital signal or analog signal?
After google, I figure out it should use encoded analog signal like Chirp.   Different frequency may be map to different code. For example, 300HZ may map to '0', 450 HZ may map to '1'. 
then last weekend, I decide to write one with python on PC to verify it.
First question how to encode the sound, I decide to use DTMF to encode the HEX.
![dtmf]({{ site.baseurl }}\images\DOS\dtmf.jpg)
one byte divided into to HEX values, the sender encode the byte array to a sound frame, the receiver receive the sound and decode the DTMF to hex and recombine into chars.

Now with my demo program it can transfer 20 - 30  bytes per second.