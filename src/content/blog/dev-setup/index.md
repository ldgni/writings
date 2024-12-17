---
title: "Web development setup"
description: "macOS development environment setup"
date: "Jul 22 2024"
---

# Table of Contents

- [Settings](#settings)
- [Xcode](#xcode)
- [Homebrew](#homebrew)
- [Terminal](#terminal)
- [Git](#git)
- [Visual Studio Code](#visual-studio-code)
- [Node.js](#nodejs)
- [Utilities](#utilites)

<hr />

# Settings

## Appearance

- Show scroll bars : **Always**

## Desktop & Dock

- Prefer tabs when opening documents : **Always**

## Keyboard

- Key repeat rate : **Fast**
- Delay until repeat : **Short**

# Xcode

Open Terminal and run the following command:

```
xcode-select --install
```

Verify that you've successfully installed Xcode Command Line Tools:

```sh
xcode-select -p
```

The output should be the following: `/Library/Developer/CommandLineTools`

# Homebrew

To install Homebrew, simply run the installation command provided on their [website](https://brew.sh/) within the terminal.

Follow & execute the `Next steps` shown inside the Terminal.

Check everything is working with:

```sh
brew doctor
```

The output should be the following: `Your system is ready to brew.`

# Terminal

## Oh My Zsh

Install [Oh My Zsh](https://ohmyz.sh/#install).

### Theme

Get [Powerlevel10k](https://github.com/romkatv/powerlevel10k?tab=readme-ov-file#getting-started).

### Plugins

[zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md#oh-my-zsh)

[zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md#oh-my-zsh)

# Git

macOS comes with a pre-installed version of Git, but we'll install our own through Homebrew to allow easy upgrades and not interfere with the system version. To do so, simply run:

```sh
brew install git
```

Restart the terminal.

When done, check that the version is >= 2.28 :

```sh
git --version
```

Let's define our Git user :

```sh
git config --global user.name "Your Name Here"
```

```sh
git config --global user.email "your_email@youremail.com"
```

To verify that things are working properly, enter these commands and verify whether the output matches your name and email address.

```sh
git config --get user.name
```

```sh
git config --get user.email
```

GitHub changed the default branch on new repositories from master to main. Change the default branch for Git using this command:

```sh
git config --global init.defaultBranch main
```

Run these two commands to tell git to ignore .DS_Store files:

```sh
echo .DS_Store >> ~/.gitignore_global
```

```sh
git config --global core.excludesfile ~/.gitignore_global
```

## SSH Key

To create a new SSH key, run the following command inside your terminal. The -C flag followed by your email address ensures that GitHub knows who you are.

```sh
ssh-keygen -t ed25519 -C "your@email.com"
```

When it prompts you for a location to save the generated key, just push Enter.
Next, it will ask you for a password; enter one if you wish, but it’s not required.

Now you need to copy your public SSH key. To do this, we’re going to use a command called `cat` to read the file to the console (Note that the `.pub` file extension is important in this case).

```sh
cat ~/.ssh/id_ed25519.pub
```

Highlight and copy the output, which starts with ssh-ed25519 and ends with your email address.

Now, go into your GitHub settings > `SSH and GPG keys`. Click `New SSH Key`. Name your key something that is descriptive enough for you to remember where it came from and paste the content of your public key here.

Test the SSH connection by following the instructions [here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/testing-your-ssh-connection).

# Visual Studio Code

Get Visual Studio Code from their [website](https://code.visualstudio.com/).

Open the Command Palette and select `Shell Command: Install 'code' command in PATH`.

## Settings & Extensions

Sync your configuration with the integrated `Settings Sync` functionality.

# Node.js

Let's grab nvm:

```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash
```

Restart your terminal.

Test your nvm installation by running:

```sh
nvm --version
```

Now that we have nvm installed, we can install Node.

```sh
nvm install --lts
```

This will install the most recent stable version of Node in ‘long-term support’ (LTS).

We need to tell nvm which version of Node to use when we run the node command. It’s easy; just run the following command:

```sh
nvm use --lts
```

Now when you run `node -v`, you should see vXX.xx.x or something similar (with the X’s replaced with actual numbers).

# Utilites

- [LinearMouse](https://linearmouse.app/)
- [Rectangle](https://rectangleapp.com/)
