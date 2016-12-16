---
layout: post
title:  "Getting A Decent Shell for Windows"
date:   2016-12-15
---

In Linux or on a Mac, working in the terminal is usually a relatively pleasant experience. You boot up the terminal, do what you want with it, and that's the end of it. On Windows, however, using the terminal is *awful*; the shell is less powerful and it's a complete eye-sore. When I use the command line, I want a shell that *does* good and a terminal that *looks* good. With the release of the Linux Subsystem for Windows, anyone can now get a bash shell with their full Windows 10 installation. By default it's still really ugly, and so still not very usable. With the recent release of [Hyper](www.hyper.is), a beautiful cross-platform terminal emulator, we can fix the ugliness of the Windows terminal and natively get the power of Bash and all your favorite Linux utilities--even apt-get! For this tutorial, you'll need to be running Windows 10 Anniversary Update build 14393 or later.

Here's a screenshot of my shell:
![A Decent Windows Shell]({{ site.url }}/assets/terminal.png)

So how do we get there?

1. Install the Linux Subsystem for Windows.
2. Install a decent terminal font.
3. Install and configure Hyper.is

Step 1 is optional if you actually like the Windows command line. Step 2 is also optional if you don't mind the font and just want a more powerful shell.

A Truly *Power*ful Shell For Windows
---------------------------------------
Everything you need to know about installing the Linux Subsystem for Windows is in [this article](https://msdn.microsoft.com/en-us/commandline/wsl/install_guide) by Microsoft. In summary:
1. Go to Settings > Update and Security > For developers and click the Developer Mode button
2. Search for `Turn Windows features on or off`, click on that, check `Windows Subsystem for Linux (beta)`, and press OK
3. Restart your computer.
4. Open a terminal and type 'bash'. Follow the instructions.

Now you have a Linux system living inside your Windows machine. Awesome! Just don't try using windows programs to edit things in your Linux subsystem folder, or you could corrupt your linux installation.

Why Are All These Fonts So Ugly?
-----------------------------------
The default terminal fonts included with Windows are OK, but can strain your eyes, hurt your brain, and offend your modern sensibilities. If we're going to have a beautiful terminal, we might as well go all the way and get a decent font for it. For that, I like [DejaVu fonts](http://dejavu-fonts.org/wiki/Main_Page). They are a set of solid, free fonts. To install them, just download [this](http://sourceforge.net/projects/dejavu/files/dejavu/2.37/dejavu-fonts-ttf-2.37.zip) zip file and extract it. Install as many as you want by clicking them and hitting the install button, but we're specifically interested in **DejaVu Sans Mono**. This is in the `DejaVuSansMono.ttf` file. This font is intended for a terminal and Hyper will look to use it by default. 

A Terminal Emulator Built To Be Beautiful
--------------------------------------------
The point of [Hyper](www.hyper.is) is to allow you to use your favorite HTML, CSS and JavaScript tricks to make a really stunning terminal. However, even without any of that, it's a solid terminal that just looks great. To start, download and execute the terminal installer [here](https://hyper-updates.now.sh/download/win). If you want your terminal to use the windows shell, that's all you need to do. However, if you want to connect the terminal to our new Bash shell you'll need to do a little configuration. To do that,

1. Open the file explorer, double click the address bar, and type %userprofile%.
2. Open the .hyper.js file with a text editor. You can use notepad for this if you want, but a more powerful editor like [Sublime Text 3](https://www.sublimetext.com/3) would be better.
3. About halfway down the file, there's a key and value for shell and shellArgs. Change the default shell to our new bash shell, and add an argument so you start in your home directory. After this, your file should look like this:

```javascript
    // the shell to run when spawning a new session (i.e. /usr/local/bin/fish)
    // if left empty, your system's login shell will be used by default
    shell: 'C:\\Windows\\System32\\bash.exe',

    // for setting shell arguments (i.e. for using interactive shellArgs: ['-i'])
    // by default ['--login'] will be used
    shellArgs: ['~'],
```

Save that file, and you're done. Open your new shell and bask in its beauty and power!
