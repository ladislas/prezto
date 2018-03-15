# Prezto – Instantly Awesome Zsh

Prezto is the configuration framework for [Zsh](http://www.zsh.org); it enriches the command line interface environment with sane defaults, aliases, functions, auto completion, and prompt themes.

## Installation

Prezto will work with any recent release of Zsh, but the minimum required version is 4.3.11.

1.  Launch Zsh:

    ``` console
    zsh
    ```

2.  Clone the repository:

    ``` console
    git clone --recursive https://github.com/ladislas/prezto.git "${ZDOTDIR:-$HOME}/.zprezto"
    ```

3.  Create a new Zsh configuration by copying the Zsh configuration files provided:

    ``` sh
    setopt EXTENDED_GLOB
    for rcfile in "${ZDOTDIR:-$HOME}"/.zprezto/runcoms/^README.md(.N); do
      ln -s "$rcfile" "${ZDOTDIR:-$HOME}/.${rcfile:t}"
    done
    ```

    Note: If you already have any of the given config files, ln will error. In simple cases you can add `source "${ZDOTDIR:-$HOME}/.zprezto/init.zsh"` to the bottom of your `.zshrc` to load prezto but keep your config intact. For more complicated setups, it is recommended that you back up your original configs and replace them with the provided prezto runcoms.

4.  Set Zsh as your default shell:

    ``` console
    chsh -s /bin/zsh
    ```

5.  Open a new Zsh terminal window or tab.

### Troubleshooting

If you are not able to find certain commands after switching to *Prezto*, modify the `PATH` variable in *~/.zprofile* then open a new Zsh terminal window or tab.

## Updating

Run `zprezto-update` to automatically check if there is an update to zprezto. If there are no file conflicts, zprezto and its submodules will be automatically updated. If there are conflicts you will instructed to go into the `$ZPREZTODIR` directory and resolve them yourself.

To pull the latest changes and update submodules manually:

``` console
cd $ZPREZTODIR
git pull
git submodule update --init --recursive
```

## Usage

Prezto has many features disabled by default. Read the source code and accompanying README files to learn of what is available.

### Modules

1.  Browse */modules* to see what is available.
2.  Load the modules you need in *~/.zpreztorc* then open a new Zsh terminal window or tab.

### Themes

1.  For a list of themes, type `prompt -l`.

2.  To preview a theme, type `prompt -p name`.

3.  Load the theme you like in *~/.zpreztorc* then open a new Zsh terminal window or tab.

    ![sorin theme](http://i.imgur.com/nrGV6pg.png "sorin theme")

### External Modules

1.  By default modules will be loaded from */modules* and */contrib*.

2.  Additional module directories can be added to the `:prezto:load:pmodule-dirs` setting in *~/.zpreztorc*.

    Note that module names need to be unique or they will cause an error when loading.

    ``` console
    zstyle ':prezto:load' pmodule-dirs $HOME/.zprezto-contrib
    ```

## Customization

The project is managed via [Git](http://git-scm.com). It is highly recommended that you fork this project; so, that you can commit your changes and push them to [GitHub](https://github.com) to not lose them. If you do not know how to use Git, follow this [tutorial](http://gitimmersion.com) and bookmark this [reference](http://gitref.org).

## Resources

The [Zsh Reference Card](http://www.bash2zsh.com/zsh_refcard/refcard.pdf) and the [zsh-lovers](http://grml.org/zsh/zsh-lovers.html) man page are indispensable.

## License

This project is licensed under the MIT License.
