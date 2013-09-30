Course Materials for [Back-end Web Development](http://betamore.com/academy/back-end-web-development)

## Things to install

* A text editor, preferably Sublime Text Beta 3 from http://www.sublimetext.com/3

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
    

