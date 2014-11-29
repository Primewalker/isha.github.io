---
layout: post
title: Pokemon battles with Viper and RIME
excerpt: "UBC ECE Capstone Pokemon Battles with Viper and RIME"
categories: articles
tags: [UBC,capstone,viper,RIME]
comments: true
share: true
---

This past week I finished the first term of my UBC Engineering capstone project - [Viper](http://ishakumaarr.com/Viper). This was an exciting project with only six weeks to develop a multi-channel realtime image and video performance system. We were able to deliver **most** of what we promised with some extras:

* *Sequencer mode*. This enables devices to send a list of timed instructions. This was an extension of our test mode which runs lists of test files with messages in JSON.

* *Record mode*. This records incoming instructions from various devices. Currently it doesn't save timing information, but the idea is that these recordings can be played back with the sequencer mode.

* *GUI*. We honestly weren't expecting to have time to work on a this, but in the end were able to come up with a very basic GUI.

<figure>
  <img src="/images/viper-gui.png" alt="Viper GUI">
  <figcaption>Initial Viper GUI</figcaption>
</figure>

* *Master controls*. These allow an instruction or an effect to be applied to all objects on the screen.

* *Multiple channels*. In this context, a channel refers to a unique device sending instructions and having its own collection or images and videos. In our project proposal, we chose the safe path and only promised single channel this term. However, we were able to run viper with more than one channel.   


> All these features come with a price and right now Viper noticeably lags with lots of videos playing. In the new year, we plan to improve CPU performance and optimize for memory amongst other things.  


Our partner project, [RIME](https://github.com/adamjberg/RIME), did a fantastic job with their Android and iOS apps that act as Viper controllers. In their capstone demo they simulated a pokemon battle, with gestures from their phones triggering attack events on Viper. They also had sensor data directly mapped to the red hue of their pokemon which would then be used to show reducing health.   

See Adam and David battle pikachu and weedle below:  
<p>
<video width="560" height="315" controls>
  <source src="/videos/rime-pokemon-battle.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>
</p>


It was a fun term and I can't wait to see what both the projects can achieve in the coming months.
