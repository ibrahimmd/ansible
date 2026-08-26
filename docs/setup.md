# Setup

## Supported Control Node OS
- macOS
- Linux

## Prerequisites

- [macOS](#macos)
- [Linux](#linux)

---

### macOS

#### Install Homebrew
If not already installed:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

#### Install  pyenv

[pyenv](https://github.com/pyenv/pyenv)

```bash
brew install pyenv
```

#### Install pyenv-virtualenv

[pyenv-virtualenv](https://github.com/pyenv/pyenv-virtualenv)

```bash
brew install pyenv-virtualenv
```

#### Install direnv

[direnv](https://direnv.net/)

```bash
brew install direnv
```

Configure `direnv` by following the installation steps.

#### Shell Configuration

Add to your shell config (`~/.zshrc` or `~/.bashrc`):

```bash
export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```


---

### Linux

#### Install pyenv
```bash
curl https://pyenv.run | bash
```

#### Install pyenv-virtualenv
pyenv-virtualenv is included with pyenv when installed via `pyenv.run`.


#### Install direnv
[direnv](https://direnv.net/)

```bash
brew install direnv
```

Configure `direnv` by following the installation steps.


#### Shell Configuration

Add to your shell config (`~/.zshrc` or `~/.bashrc`):

```bash
export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```

## Install Python

Install the required Python version via pyenv:
```bash
pyenv install 3.14.6
```

Verify the installation:
```bash
pyenv versions
```

## Create Virtualenv

Create a virtualenv for the project (name it however you prefer):
```bash
pyenv virtualenv 3.14.6 ansible13_3.14.6
```

## Project Setup

```bash
# Clone repo and cd into it
git clone
cd

# Set local virtualenv
pyenv local ansible13_3.14.5

# Verify the correct virtualenv is active
pyenv version
```

## Installation

Install Ansible and other dependencies:
```bash
pip install -r requirements.txt
```

Upgrade Ansible Collection dependenecies and upgrade latest if required
```bash
ansible-galaxy collection install -r requirements.yml --upgrade
```


Verify the installation:
```bash
ansible --version
```

