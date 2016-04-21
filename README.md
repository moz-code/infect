# Moz Infect

Moz `infect` is a bash tool that allows you to quickly deploy your favorite Linux
environment configuration from a git repository.

## Installation

Simply clone the git repository:

	git clone https://github.com/moz-code/infect.git

## Usage

Without any option, `infect` only shows the modification without applying them:

	moz_infect/infect path/to/env.conf

Use `-x` option to actually deploy the files:

	moz_infect/infect path/to/env.conf -x

## Config profile

Simply store all the file you want to backup in a directory:

	 my-config/
	 `
	  | .bash_aliases
	  | .bashrc
	  | .gitconfig
	  | .profile
	  | .ssh/
	  |  `- config
	  | .vimrc
	  ` my-config.conf

The `my-config.conf` contains the list of files or directories to deploy:

	.bashrc ~/.bashrc
	.bash_aliases ~/.bash_aliases
	.gitconfig ~/.gitconfig
	.profile ~/.profile
	.vimrc ~/.vimrc
	.ssh/config ~/.ssh/config

You can then version and backup all your config files using git very easily:

	cd my-config
	git init
	git add -A
	git commit -m "initial config import"
