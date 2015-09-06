---
layout: post
title: Introduction to Vim
location: Bhubaneswar
tags:
- vim
- dotfiles
---
Well if you are new to vim or linux or a wannabe programmer this post is surely for you. If you google about vim you will get hell of a lot of answers which gets more and more complicated. So, just read the wiki article to get the story. And the moment you start using it you will realize it's not your cup of tea and cannot be jot up in one day.


First thing first, if you are using windows then don't try to install vim on it because it's more than a Install and an I agree box. It will get way more tougher than you think:

* Vim is a primarily a terminal based application.
* Vim works best on linux and unix based systems.
* What I meant is, you should use ubuntu or mac osx. Fedora works great too.


<!--excerpt-->

So go to your terminal and type:
```sudo apt-get install vim```  

```apt-get``` is for ubuntu  
replace it with ```yum``` if you are using fedora.

So let me explain you the file structure of vim:


First of all, after installing you have to manually create a folder called .vim and a file called .vimrc on the Home directory of your machine. 

```

.	Home
	├── .vim(folder)
	│   └── I keep all the subfolders and important files.
	│   
	└── .vimrc(file)
		└── I am the monster you must understand before using vim
	    
```

These are dotfiles begins with dot so are hidden in linux. To see them, type "Ctrl-h". 

Both the ``.vimrc`` file and the **.vim** folder are used to configure vim editor. Initially you will get a version of vim which will be nothing cooler than a terminal :P.

In this post I will talk about .vimrc .

Well vim is a very powerful text editor. So, to maintain it or configure it uses a Language called VimL and can also use other scripting languages too.

So, copy the following and paste it on your .vimrc.


```
set number
colorscheme darkblue
abbr teh the
abbr email <your_email@gamil.com>
```

Now open up your vim editor.

You will see the line numbers in vim and background changed. And type "teh" a common spelling mistake.You will see them automaticaly get corrected.

If you don't see them, that probably means vim may not be opening .vimrc at startup and you need to manually configure it.
TO check hit  &ltESC&gt :scriptnames.
See if ``vimrc`` is mentioned. If not google about how can you configure vim startups to point to .vimrc. You will probably find a lot of commands and solution online.

Lets get started with ``vimrc``.

##Modes

Vim works in **three modes** insert ,visual and normal.

You can map any command  to the keystrokes in the three modes:
`imap,vmap & nmap `

and combo mapping like nnoremap,inoremap and bunch of others.



> This shows you the [list](http://vim.wikia.com/wiki/Displaying_the_current_Vim_environment) of all the mappings.

The commands you type in the vim panel are the same thing you can write in your vimrc file.

Actually the only thing vim does is runs the file vimrc at the startup.
Hence you see the command above in vimrc can be written through your vim terminal hitting escape like:

```
:colorscheme blue
:set number
```
Lets change a few more things in .vimrc and restart vim.
```
nnoremap <C-h> :tabprevious<CR>
nnoremap <C-l> :tabnext<CR>
nnoremap <C-t> :tabnew<CR>
```

In your vim terminal
hit ESC  and write ```:tabnew```

Now in vim hit ```ctrl-t , ctrl-h , ctrl-l.```


Check some vimrc [vimrc](http://www.dotfiles.org/.vimrc).

Now lets source [one](http://www.dotfiles.org/~omab/.vimrc) to your .vim. Name it ``test.vim``

go to your vimrc:
and add:

```
"source files
source ~/.vim/test.vim
```

```
The structure:

.	Home
	├── .vim(folder)
	│   ├── test.vim
	│   └── other files and folders you don't need to bother.
	└── .vimrc(file)
		└──
```

###Hacks you should try
Check your new vim. Try other configuration too and don't source them all together.