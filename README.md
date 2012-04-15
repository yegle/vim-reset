# vim-reset

A reset script so you can customize your very own VIM configurations

*WARNING*: `vim-reset` doesn't come with any default `.vimrc` file / syntax file / plugins.

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

## how to use it?

1. `git clone https://github.com/yegle/vim-reset`
2. `export VIMCONFIG_DIR="${HOME}/myvimconfigdir"`
3. `source vim-reset/activate`

You can put your `~/.vimrc` files and all your plugins/syntax files into `$VIMCONFIG_DIR` now.

You can also add these commands to your `~/.bashrc` file and run `vim-reset` each time you invoke an interactive shell.

NOTE: `vim-reset` will do a _soft_ reset. That means the vim variable `runtimepath` will contain `$VIMCONFIG_DIR` along with your old `runtimepath`.

NOTE AGAIN: `vim-reset` uses `$VIMCONFIG_DIR/_vimrc` as your main VIM configuration file by default, not `$VIMCONFIG_DIR/.vimrc`.
