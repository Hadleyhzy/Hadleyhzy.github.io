---
layout: post
title: Jekyll installation
key: 20180513
tags:
  - front end
  - jekyll
---

## Requirements

Before you start make sure your system has the following:
	* Ruby version 2.2.5 or above, including all development header(ruby installation can be checked by running `ruby -v`)
	* RubyGems(which you can check by running `gem -v`)
	* GCC and Make(in case your system doesn't have them installed, which you can check by running `gcc -v`, `g++ -v` and `make -v` in your system's command line interface)

## Install on macOS
We only cover macOS High Sierra 10.13 here, which comes with Ruby 2.3.3.

First, you need to install the command-line tools to be able to compile native extensions,open a terminal and run:
```terminal
xcode-select --install
```
## Install Homebrew

```terminal
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

## Install a newer Ruby version via Homebrew

If you wish to install the latest version of Ruby and get faster builds, we recommend to do it via Homebrew a handy package manager for macOS.

```terminal
brew install ruby
ruby -v
ruby 2.5.1p57 (2018-03-29 revision 63029) [x86_64-darwin16]
```
Now you have a shiny Ruby on your system!

Set up Ruby included with the OS
Check your Ruby version meet our requirements:
```terminal
ruby -v
ruby 2.5.1p57 (2018-03-29 revision 63029) [x86_64-darwin16]
```
Great, let's install Jekyll. We also need Bundler to help us handle plugins and themes:

```terminal
gem install bundler jekyll
```
Go to github.io directory:

```terminal
# Create a Gemfile
bundle init

# Add Jekyll
bundle add jekyll

# Install gems
bundle install
```