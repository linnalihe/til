## Homebrew
[Homebrew official install documentation](https://docs.brew.sh/Installation "https://docs.brew.sh/Installation")
```bash
which brew # to check if it's installed
brew doctor # to diagnose any errors
```
## Terminal Upgrade
Consider installing  [iTerm2](https://iterm2.com/ "https://iterm2.com/") + Oh My Zsh (https://ohmyz.sh/#install)
More detail can be found at https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH

iTerm2 is a better version of the default MacOS terminal, here are the [list of features for iterm2](https://iterm2.com/features.html) and Oh My Zsh is a power-up from the default bash controls
Another value add is https://github.com/junegunn/fzf

Check which shell you're running with `echo $0`

General alias to add to `~/.zshrc`
```bash
alias cls='printf "\ec"' # clear terminal
```
## Git
This is a free open source version control tool, separate from GitHub which is a prioprietary company that manages a interface tool that visualizes/augements the git experience
```bash
brew install git
```

## GitHub
Create a GitHub account so to work with the git tool installed on your machine. GitHub profile ideally has first and last name so that it's easy to identify you. GitLab or GitBucket are also ok.

## Docker Desktop
Docker is a tool for running applications in a container in a repeatable way. Docker Desktop is a tool that makes using Docker easier on OSX
Instructions for installation of [Docker Desktop](https://www.docker.com/products/docker-desktop)
Sign in or create an account on [Docker Hub]( https://hub.docker.com/signup)

## NVM
https://github.com/nvm-sh/nvm#usage
This is a tool that lets you installing an switch between different versions of NodeJS.

```bash
brew update
brew install nvm
mkdir ~/.nvm
```
Follow the instrucitons after installing nvm, likely involves `mkdir` command and adding something to profile (`~/.bash_profile` , `~/.zshrc`, `~/.profile`, or `~/.bashrc`)
Then run `command -v nvm`  to verify that it's installed. 

## Pyenv
[Getting Started With pyenv to Manage Multiple Python Versions](https://www.youtube.com/watch?v=ikKpWM4_3g4)
1. Install multiple version of python on your machine
2. Install the latest development version of Python
3. Switch between installed versions
4. Use virtual environment with pyenv
5. Activate different python version and virtual environments automatically

Pyenv is a tool that allows you to install and switch between different versions of Python. Makes Python development much easier. 
```bash
brew install pyenv pyenv-virtualenv
```

Add to ~/.zshrc for directory to be able to switch to python environment
```bash
export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
if which pyenv > /dev/null; then eval "$(pyenv init -)"; fi
if which pyenv > /dev/null; then eval "$(pyenv init --path)"; fi
if which pyenv > /dev/null; then eval "$(pyenv virtualenv-init -)"; fi

alias pip=pip3
```

https://github.com/pyenv/pyenv#simple-python-version-management-pyenv on how to use pyenv.
To upgrading pyenv there a few different options.
If you installed via pyenv installer: `pyenv update`
If you installed via Homebrew (recommended): `brew upgrade pyenv`
If you installed via Git: `cd $(pyenv root) && git pull`

Create virtual environments for each Python project you work on by following these steps

1.  `cd` to your codebase’s folder
2. Figure out what version of python you want to install. Check the `README` or the `Dockerfile`, if the app has them. For the sake of these instructions, we’re going to assume you want to run python **3.8.1.**
3. Ensure `pyenv` has that version of python installed
	3.1.  `pyenv install 3.8.1`
	3.2.  If your version of `pyenv` does not support the version you want, try upgrading `pyenv` either using `brew` or by following these instructions: https://github.com/pyenv/pyenv#upgrading
	3.3.  You can list what versions of python are available to install by executing `pyenv install --list`
	3.4.  If the exact version of python you want is not available, try using one that has a different minor version (in our example, that could be using 3.8.0 instead of 3.8.1)
4.  Create a `virtualenv` using `pyenv` and the version of python you just installed
	4.1.  `pyenv virtualenv 3.8.1 <codebase name>`
5.  Tell `pyenv` to use your `virtualenv` automatically from now
	5.1.  `pyenv local <codebase name>`
	5.2.  This creates a file named `.python-version` - you likely will NOT want to commit that to your codebase.

## Virtualenv
`pip install virtualenv`
create named virtual environments to install pip packages in isolated environments
create environment for web dev and data science and don't co-mingle

## Python Poetry
`pip install poetry`

and then add `export PATH=$PATH:$HOME/.poetry/bin`
and start project with `poetry init`
Decide on dependencies and it will generate a pyproject.toml with dependencies; then use `poetry install` to install them
Poetry does things asychronously
It created a virtual environment, you can check with 
```bash
poetry env info --path
poetry env info
```

In VSCode, under the python interpreter (python extension and linter has to be installed), paste in the poetry env path

Can be in the virtual environment and run commands but can be outside the virtual env and use poetry to run the commands in the virtual env



