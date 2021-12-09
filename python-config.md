# Configure python development environment

## Managing python versions with pyenv

Prepare the build environment:

```
sudo apt-get update; sudo apt-get install make build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm \
libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev
```

Install pyenv with the automatic installer

```
curl https://pyenv.run | bash
```

Open your `.zshrc` file or equivalent and add the following lines,
if they are not there:

```
export PATH="$HOME/.pyenv/bin:$PATH"
eval "$(pyenv init --path)"
eval "$(pyenv virtualenv-init -)"
```

Run the following command and restart your shell

```
exec $SHELL
```

## Managing virtual environments with poetry

Install poetry:

```
curl -sSL https://install.python-poetry.org | python3 -
```

Poetry should automatically detect your global pyenv version and
use it when creating a poetry project.
