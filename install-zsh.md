# Terminal customization

## Installing Zsh

Follow the tutorial provided by [Oh My Zsh organization](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH#install-and-set-up-zsh-as-default).

## Installing Oh My Zsh

To install Oh My Zsh, run the following command:

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

After running the command, restart your terminal and you should see it different.

From now on, every configuration like setting an environment variable or others,
use `~/.zshrc` instead of `~/.bash_profile` or similar.

## Using Dracula colors

First, install `dconf`, if you don't already have it.

```
sudo apt-get install dconf-cli
```

Now, clone the repository, and run the installation script.

```
git clone https://github.com/dracula/gnome-terminal
cd gnome-terminal
./install.sh
```

## Installing and applying FiraCode font

First, add the `universe` repository:

```
sudo add-apt-repository universe
```

If this command doesn't work, use this one instead:

```
sudo add-apt-repository "deb http://archive.ubuntu.com/ubuntu $(lsb_release -sc) universe"
```

Now, download the repository informations and install the font.

```
sudo apt update
sudo apt install fonts-firacode
```

Now, apply the font to your terminal by changing your terminal profile preferences.

## Installing Spaceship theme

First, clone the repository into Oh My Zsh `themes` folder:

```
git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt"
```

Now, create a symlink to the theme file in the Oh My Zsh themes folder:

```
ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"
```

Last but not least, open your `.zshrc` file:

```
sudo gedit ~/.zshrc
```

And change the `ZSH_THEME` variable, as follows:

```properties
ZSH_THEME="spaceship"
```

To apply the changes, restart your terminal.

## Beautify the prompt

Open your `.zshrc` file:

```
sudo gedit ~/.zshrc
```

Add the following lines to the end of the file:

```properties
SPACESHIP_PROMPT_ORDER=(
  user          # Username section
  dir           # Current directory section
  host          # Hostname section
  git           # Git section (git_branch + git_status)
  hg            # Mercurial section (hg_branch  + hg_status)
  exec_time     # Execution time
  line_sep      # Line break
  vi_mode       # Vi-mode indicator
  jobs          # Background jobs indicator
  exit_code     # Exit code section
  char          # Prompt character
)
SPACESHIP_USER_SHOW=always
SPACESHIP_PROMPT_ADD_NEWLINE=false
SPACESHIP_CHAR_SYMBOL="❯"
SPACESHIP_CHAR_SUFFIX=" "
```

## Add some plugins

First, install ZInit:

```
sh -c "$(curl -fsSL https://git.io/zinit-install)"
```

Update ZInit:

```
zinit self-update
```

Now, open your `.zshrc` file:

```
sudo gedit ~/.zshrc
```

And add the following lines under the `### End of ZInit's installer chunk`

```
zinit light zdharma-continuum/fast-syntax-highlighting
zinit light zsh-users/zsh-autosuggestions
zinit light zsh-users/zsh-completions
```
