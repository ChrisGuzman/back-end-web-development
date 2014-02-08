Course Materials for [Back-End Web Development](http://betamore.com/academy/back-end-web-development)

# Things to install

## Mac OS X Mavericks

On your Mac, click on the Apple icon in the top left (also called the Apple menu), and choose **About this Mac**. If the version is **10.9.0** or higher, you are running the latest version of OS X. If not, launch the Mac App Store (either from the icon in the doc or from the Apple menu), search for Mavericks and install. It is a free upgrade.

## Command-Line Tools

Launch the program called **Terminal**. At the command prompt, type the following command and press enter:

    xcode-select --install

You will see a dialog that says **Would you like to install the tools now?**. Press the install button and wait for the install to complete.

## iTerm 2

[http://www.iterm2.com](http://www.iterm2.com)

This program is a free alternative to Terminal that has some advantages. Install this and use it in place of Terminal. Make the following configuration changes:

Go to *iTerm > Preferences > Profiles > General*. Under **Working Directory**, choose **Advananced Configuration**. Press the edit button next to that. For **Working Directory for New Windows**, leave that as **Home directory**. For **Working Directory for New Tabs** and **Working Directory for New Split Panes**, choose **Reuse previous session's directory**.

Go to *iTerm > Preferences > Profiles > Terminal*. Under **Notifications**, check **Silence bell**.

## Homebrew

[Homebrew](http://brew.sh/) makes it easier to install command-line programs on a Mac. To install Homebrew, run this command from iTerm:

    ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"

## Sublime Text 3

[Sublime Text](http://www.sublimetext.com/3) is a text editor. It has lots of great features, works on Windows, Mac and Linux. It has an unlimited free trial, but does cost $70 to buy. You can use the trial indefinately, it will just occassionally bug you to go purchase it while you are using the free trial.

Once you have downloaded and installed Sublime Text, make it so that you can launch Sublime Text from command line. In iTerm, run these commands:

    cd /usr/local/bin
    ln -s /Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl

For the last command, don't try to type it all out or copy and paste it. Type `/` then the first few letters of the path "App", then press tab. It will complete the rest of the word. Do this for each part of the path. Doing it this way will verify that these directories actually exist on your computer and you have typed it correctly.

## RBENV

If using a Mac

Setup `PATH` and `subl` shortcut in `~/.bash_profile`

    export PATH=~/bin:/usr/local/bin:$PATH

Create the `bin` directory in your home:

    $ mkdir ~/bin

Create the `subl` shortcut

    $ ln -s /Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl ~/bin/

Install Command Line Tools from http://developer.apple.com/downloads

Install Homebrew from http://brew.sh

Then install git, rbenv, ruby-build, ruby 2.0 and postgres via homebrew:

    brew install git

Install GitX 0.7 from http://gitx.frim.nl

Install rbenv

    brew install rbenv

Add this to your `~/.bash_profile` to make rbenv load in each new shell

    eval "$(rbenv init -)"; fi

Install `ruby-build` so you can install ruby via rbenv

    brew install ruby-build

Install Ruby 2.0 via rbenv:

    rbenv install 2.0.0-p247

Install postgresql:

    brew install postgresql

Fix `unix_socket_directory` before loading plist into launchctl


