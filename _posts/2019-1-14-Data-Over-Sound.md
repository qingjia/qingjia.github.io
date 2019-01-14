---
layout: post
title: Data Over Sound
categories: [Python,Chirp]
tags: [Python, dtmf,chirp,data over sound,audio jack]
---
![background]({{ site.baseurl }}/images/DOS/background.jpg)

When I saw LAKALA, I was confused how it communicate with Phone by Audio Jack. It's like a magic. it's digital signal or analog signal?

After investigation, I found it use Data over Sound technology, just like Chirp

Audio Jack can be treated as a modem in the case. the Data is encoded into sound  by different frequency combination (even left and right) from the Phone. At the same time the device can send data throught sound by MIC channel
![background]({{ site.baseurl }}/images/DOS/aux_headphone_jack_diagram.jpg)

For example, 300HZ may map to '0', 450 HZ may map to '1'. 
then last weekend, I decide to write one with python on PC to verify it.
First question how to encode the sound, I decide to use DTMF to encode the HEX.
![dtmf]({{ site.baseurl }}/images/DOS/dtmf.jpg)

One byte divided into two HEX values, the sender encode the byte array to a sound frame, the frame is begin with dialing sound. The receiver receive the sound and decode the DTMF to hex and recombine into chars.

Now with my demo program it can transfer 20 - 30  bytes per second.
