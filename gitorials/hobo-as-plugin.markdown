


<a name='hobo-as-plugin-sidebar'> </a>


Agility: Hobo as Plugin Sidebar
{: .document-title}

Contents
{: .contents-heading}

- contents
{:toc}

# Hobo as Plugin Sidebar

You may wish to run Hobo as a plugin rather than as a gem.

## Run rails generator

The first step is to run the standard rails generator:

    $ rails agility
    $ cd agility

## Install as a plugin

    $ git submodule add git://github.com/tablatom/hobo.git vendor/plugins/hobo

## Run hobo command

To run the hobo command when it's installed as a plugin instead of a gem:

    $ ./vendor/plugins/hobo/hobo/bin/hobo --no-rails

(This command will fail if you don't have the hobo gem install.  Don't worry about this and follow the next step).

## Comment out gem statement

The hobo command generates a setup designed to be used with the hobo gem.  If you wish to use the plugin, comment out `config.gem 'hobo'` in *config/environment.rb*.

## Run hobo command again

Now that we've fixed config/environment.rb, we can run `hobo` again, and it will run to completion.  This is only necessary if it failed previously.

    $ ./vendor/plugins/hobo/hobo/bin/hobo --no-rails

## Fix Rakefile

The hobo command sets up the Rakefile to use the gem.   Let's fix it so that it works with the plugin by removing the `require 'hobo/tasks/rails'` line.


gitorial-005: [view on github](http://github.com/bryanlarsen/agility-gitorial/commit/b1402c7896a5bf536da3d82c696da0737d26cf93), [download 05-hobo-as-plugin-sidebar.patch](/patches/agility/05-hobo-as-plugin-sidebar.patch)
{: .commit}
