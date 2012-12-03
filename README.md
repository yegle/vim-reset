# vim-reset

A bash script so you can customize your very own VIM configurations.

`vim-reset` is in [Public Domain]( http://en.wikipedia.org/wiki/Public_Domain ), feel free to re-use it and distribute it.

*WARNING*:
`vim-reset` doesn't come with any default `.vimrc` file / syntax file / plugins etc. You can refer to [yegle-vimrc]( https://github.com/yegle/yegle-vimrc ) as a start point.

## what's reset?

The `reset` concept was borrowed from web front-end engineers.
It's a good idea to first reset all browser-specific default settings before front-end engineers adding any customization.

So is `vim-reset`. It is intended to `reset` default VIM settings between different Linux distributions.
As a system administrator, I have to deal with different distros, each comes with different default VIM settings. That's really annoying.

## anything else?

Besides the `reset` process, `vim-reset` also provides a way to maintain your very own VIM configuration files in a different directory other than `~/.vim` directory.
You can put all syntax file, plugins in a dedicated directory without any modification to `~/.vim` directory.

If you are familiar to `python`, `vim-reset` is like the `virtualenv` for VIM.

## it's a dirty hack!

After reading the source code you may think that this is really a dirty hack. Yes, but this is *the only way*.

Vim hardcoded `~/.vim` directory and `~/.vimrc` file in their source code which makes it hard to customize where you can load your VIM configurations.

## do I need this?

You may find `vim-reset` similar to [pathogen.vim]( https://github.com/tpope/vim-pathogen ). But they are different. `pathogen.vim` manages files _inside_ `runtimepath`, while `vim-reset` take care of your `runtimepath` directory.

`vim-reset` is very useful if you need to maintain many different sets of vim configuration files, or you are using a shared account on a server with someone else.

`vim-reset` makes it possible to share a complete `vimrc` directory to someone else with all plugins / syntax, not just `~/.vimrc`.

## how to use it?

1. `git clone https://github.com/yegle/vim-reset`
2. `export VIMCONFIG_DIR="${HOME}/myvimconfigdir"`
3. `source vim-reset/activate`

You can put your `~/.vimrc` files and all your plugins/syntax files into `$VIMCONFIG_DIR` now.

You can also add these commands to your `~/.bashrc` file and run `vim-reset` each time you invoke an interactive shell.

NOTE: `vim-reset` will do a _soft_ reset. That means the vim variable `runtimepath` will contain `$VIMCONFIG_DIR` along with your old `runtimepath`.

NOTE AGAIN: `vim-reset` uses `$VIMCONFIG_DIR/_vimrc` as your main VIM configuration file by default, not `$VIMCONFIG_DIR/.vimrc`.
