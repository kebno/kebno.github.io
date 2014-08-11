---
layout: post
title: Weekly Catchup
---

## Thing 1

![view from my window]({{site.url}}/images/trees.jpg)

I see a lot of eucalyptus trees now. I've moved from sunny Portland to sunny
San Diego, CA.

## Thing 2

Xiph.Org is the group behind FLAC, Ogg Vorbis, Theora multimedia formats.
Recently they released two videos about the basics of digital media (from a
signal processing point of view).  I **highly** recommend watching both.

[Xiph.Org Video](https://www.xiph.org/video/)

## Thing 3

Over at windytan's blog,
[absorptions](http://www.windytan.com/2013/02/voice-over-laser.html), she wrote
about basic audio transmission with a laser. She used simple single-side-band
(SSB) modulated audio for transmission, and demodulated the received signal in
hardware.  I'm not too familiar with modulation and wanted to hear the modulated
signal (at 6kHz), but she didn't provide audio, nor code for demodulating the
same audio file.

Starting from [her script](https://gist.github.com/windytan/5021143), I added
modulation of a different file and demodulation using the same method.  I put
the code and an audio file up on Github in my one-off project collection
repository [`prac`](https://github.com/kebno/prac/tree/master/007) (as in
"practice").
