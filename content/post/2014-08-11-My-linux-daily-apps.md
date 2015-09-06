---
layout: post
title: My linux daily apps
location: Bhubaneswar
tags:
- linux
- dotfiles
---

How do you maintain your projects with all the devices and application in a perfect sync? How do you work perfectly in a order that effectively makes your work smoother and easier .Well the answer could be *dropbox* but still I am talking about a more synchronized way of doing things on your linux machine. 


> The zen of workflow for your linux machine

## How should I do things then?

A few apps and settings that can boost your productivity on a daily basis.
But these are mostly ncurses apps ...
Before you use them... few things you need to learn art.


<!--excerpt-->


##Learn to confgure your linux

> Linux is kind of like a piece of open art. It only 
gets beautiful for you the way you paint it.

Without further ado...

Here's the list:

* tmux
* youtube-dl 
* cmus 
* mplayer 
* pyradio 

![advanced_terminal_photo](/images/2_1.png)

###Advantages:

* mplayer lets you play music through terminal.
* cmus is a ncurses music player
* youtube-dl as name suggests 
* tmux is the terminal multiplexer (it lets you create sessions and divides terminal to small screens as shown) 

Installation 

```
sudo apt-get install tmux
sudo apt-get install youtube-dl
sudo apt-get install cmus
sudo apt-get install mplayer

```




##youtube-dl hacks

It works great with videos and music files too.

You can use it to download music from soundcloud and myspace. Well the proper word will be called stream.

Right click on your song and copy link location and attach the url at the end of youtube-dl on your terminal.

![youtube...soundcloud](/images/2_2.png)  

![youtube...terminal](/images/2_3.png)  

![youtube...myspace](/images/2_4.png)  

It works on myspace too. Cool, no IDM shit any more... just copy and paste this sucker.


##Cmus

Cmus is one of the best ncurses music player you can have.
It comes with tons of functionality ranging from creating playlist, list names by artist to creating queue and music tagging.

Just hit 1 2 ... and so on, you will see all the views.

Just to help with to add all the music in a folder you just need the following command:
hit ```ctrl-C ``` then  ```:add ~/Music```.

###Usage:

```
Hit enter to play 
Hit c to stop
Hit e to add to queue
```

> This [tutorial](https://github.com/cmus/cmus/blob/master/Doc/cmus-tutorial.txt) will give you enough experience.

> Want to know [more about cmus](http://www.tuxarena.com/static/cmus_guide.php) about cmus ?
	

And yes _ cmus won't work without mplayer_.So don't forget to install mplayer.

```
sudo apt-get install mplayer
```

##Tmux 

Tmux is a longer topic like vim.It has really cool features with ssh and session sharing. I will soon update in another blog post.
