# Zim-Gollum

Workflow tools and eventual integration between the [Zim Desktop Wiki](http://zim-wiki.org/) and the [Gollum](https://github.com/gollum/gollum) simple Git-powered wiki server.

The idea here is to make it easier to use Zim as a personal interface to a wiki served by Gollum. Zim's formatting is unfamiliar to Gollum, but Zim does support exporting its own formats into Markdown. That feature is used to automatically create a new branch that you can point Gollum at with its `--ref` option.

Further, this process offers the chance to enhance Gollum's features, such as by providing an RSS feed at `/latest_changes.rss` to go along with Gollum's own `/latest_changes` URL endpoint showing the repository log.

# Prerequisites

* Zim
* Ruby
* [Gitfeed](https://github.com/scotchi/gitfeed)

# Installation

In brief, with Gem installation under the `git` user account, and be sure to change `/path/to/git/project/repository` to your `$GIT_DIR` repository root:

```sh
sudo apt install zim ruby
sudo -u git gem install --user-install gitfeed # You may also want to install `gollum`
sudo -u git cp hooks/post-receive /path/to/git/project/repository.git/hooks/post-receive
sudo -u git chmod a+x !$
```
