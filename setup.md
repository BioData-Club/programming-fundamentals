---
layout: page
title: Setup
permalink: /setup/index.html
root: ..
---

## Overview

This lesson is designed to be run in a Python environment.
All of the software and data used in this lesson are freely available online,
and instructions on how to obtain them are provided below.

## Setting up Python with [repl.it][replit-website]

In this lesson, we will be using a Python 3 environment on [repl.it][replit-website] online.
We will use some of Python's most popular scientific libraries.
Guidance will be provided for use in [repl.it][replit-website].
[repl.it][replit-website] is a free online integrated development environment (IDE).
An IDE is a software application that provides comprehensive facilities for software development. 
[repl.it][replit-website] gives you an instant IDE to learn, build, and collaborate.

## Alternatively: Installing Python on your personal computer

If you don't want to use [repl.it][replit-website], you can install a Python environment on your computer instead.
We recommend installing [Anaconda][anaconda-website], a Python distribution that comes with everything we need for the lesson. Detailed installation instructions for various operating systems can be found on The Carpentries [template website for workshops][anaconda-instructions] and in the [Anaconda documentation][anaconda-install].

We recommend [Visual Studio Code][vscode-website] for a full-featured IDE.
[Visual Studio Code][vscode-website] is free and supports most code development needs.

## Start your repl.it environment

1. Go to [repl.it][replit-website].
2. In the top right corner click `+ new repl`.
3. Click the left `Create New Repl` tab.
4. Make sure `Python` is selected in the language list and click `Create Repl`.

After a short loading you should see three side-by-side panes
surrounded by a top menu bar and a left menu bar.

## Obtain lesson materials and upload them to repl.it (Optional)

In this workshop we're only covering the first four episodes of the lesson. You are free to continue working on the remaining episodes on your own after the workshop is over.  The remaining lessons require downloading some data files and uploading them to repl.it.

1. Download [python-novice-inflammation-data.zip][zipfile1] and [python-novice-inflammation-code.zip][zipfile2].
2. Create a folder called `bdc-python` on your Desktop.
3. Move the downloaded files to `bdc-python`.
4. Unzip the files.
5. Drag and drop `bdc-python` into the leftmost `Files` pane in your repl.it window to upload the files to repl.it.

## Know your interface

The following sentences detail the user interface of repl.it.
The leftmost pane contains the folder of all the repository files.
The middle pane contains the current open files.
The rightmost pane is an interactive terminal.
The top menu has a few options to customize this repl page and run open code.
The left menu allows you to expand or collapse active Files, Version Control,
or to customize Settings of this online IDE.

[anaconda-install]: https://docs.anaconda.com/anaconda/install
[anaconda-instructions]: https://carpentries.github.io/workshop-template/#python
[anaconda-website]: https://www.anaconda.com/
[gitbash]: https://gitforwindows.org
[replit-website]: https://repl.it/
[vscode-website]: https://code.visualstudio.com/
[zipfile1]: {{ page.root }}/data/python-novice-inflammation-data.zip
[zipfile2]: {{ page.root }}/code/python-novice-inflammation-code.zip
