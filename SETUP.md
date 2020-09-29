# Set up the digital pattern library

Version 0.5.0

Last updated: Tuesday 29 September 2020

<!-- MarkdownTOC -->

- [1. Prerequisites](#1-prerequisites)
    - [1.1 Git](#11-git)
    - [1.2 Node.js](#12-nodejs)
    - [1.3 Grunt CLI](#13-grunt-cli)
    - [1.4 Ruby](#14-ruby)
        - [Ruby on Windows](#ruby-on-windows)
        - [Ruby on MacOS X](#ruby-on-macos-x)
- [2. Initialize developer tools](#2-initialize-developer-tools)
    - [2.1 Clone the repository](#21-clone-the-repository)
    - [2.2 Install Grunt dependencies](#22-install-grunt-dependencies)
    - [2.3 Install Compass Ruby gem](#23-install-compass-ruby-gem)
    - [2.4 Run grunt](#24-run-grunt)
    - [2.5 How to contribute](#25-how-to-contribute)
- [3. How to update an existing install](#3-how-to-update-an-existing-install)
    - [3.1 Make sure your Node.js version is up-to-date.](#31-make-sure-your-nodejs-version-is-up-to-date)
    - [3.2 Checkout the branch from GitHub.](#32-checkout-the-branch-from-github)
    - [3.3 Delete the `node_modules` folder.](#33-delete-the-node_modules-folder)
    - [3.4 Reinstall npm to your DPL directory.](#34-reinstall-npm-to-your-dpl-directory)
    - [3.5 Verify it works.](#35-verify-it-works)
- [4. Troubleshooting](#4-troubleshooting)
    - [4.1 Node.js](#41-nodejs)
        - [Error: npm does not support Node.js vX.Y.Z](#error-npm-does-not-support-nodejs-vxyz)
    - [4.2 Grunt](#42-grunt)
        - [Error: Unable to connect to github.com](#error-unable-to-connect-to-githubcom)
        - [Error: handlebars does not support render](#error-handlebars-does-not-support-render)

<!-- /MarkdownTOC -->


---

This is a guide to get your environment set up to contribute to the digital pattern library.




## 1. Prerequisites

### 1.1 Git

The digital pattern library code is stored in a Git repository, so you will need a Git client to clone it to your local machine and commit changes back to the repository.

If you are a Windows user, we recommend that you always install the Git command line client, as this will allow you to right-click within a folder and select "Git Bash Here" to open a command-line prompt. You can use this to run Git, Node, Grunt, and Ruby commands.

* [Command line](https://git-scm.com/)

There are also a number of GUI clients available; our favourites, in order, are:

* [GitKraken](http://www.gitkraken.com/)
* [GitHub Desktop](https://desktop.github.com/)
* [SourceTree](https://www.sourcetreeapp.com/)


### 1.2 Node.js

The digital pattern library uses [Grunt](http://gruntjs.com/), the JavaScript task runner, to automate the build process. Grunt is built on [Node.js](http://nodejs.org/) which is a JavaScript runtime that uses [Google Chrome's V8 JavaScript engine](https://developers.google.com/v8/). If you're not familiar with either of these see [Getting started with Grunt](http://gruntjs.com/getting-started) for the basics.

To install Node.js:

1. Visit [http://nodejs.org/](http://nodejs.org/)
2. Download the latest stable release (LTS, recommended for most users).
3. Run the installer.

Having problems? See [troubleshooting Node.js](#41-nodejs).


### 1.3 Grunt CLI

Next install the [Grunt command line interface (CLI)](http://gruntjs.com/using-the-cli). Open an elevated "Node.js command prompt" (Windows), Terminal (OS X), or shell (*nix) and run the following command:

```
$ npm install -g grunt-cli
```





### 1.4 Ruby

We also use [Compass](http://compass-style.org/) to compile [Sass](http://sass-lang.com/) code to CSS. This requires [Ruby](https://www.ruby-lang.org/).


#### Ruby on Windows

The easiest way to install Ruby is with [RubyInstaller for Windows](http://rubyinstaller.org/downloads/).

Unless you know otherwise, stick to the default installation of Ruby.

When prompted at the beginning of the installation make sure that the box with the label "Add Ruby executables to your PATH" is checked (it should be by default). This will mean that you can run commands like `gem install ...`.

Once you're finished with the installation, you should close and reopen any command prompts that you have since they will need to get the updated PATH with Ruby added.


#### Ruby on MacOS X

Recent versions of MacOS X already have Ruby installed, no further installation is required.

---




## 2. Initialize developer tools


### 2.1 Clone the repository

Clone the Git repository into a folder on your computer using your Git client, or at the command line:

```
git clone https://github.com/garethjmsaunders/digital-pattern-library.git
```


### 2.2 Install Grunt dependencies

1. At the command line, navigate to the folder containing your local clone of
   the pattern library.
    ```
        $ cd path/to/folder
    ```
    Where `path/to/folder` is the path to the folder you cloned the pattern
    library locally. (Or in Windows right-click within the folder containing your local clone of the pattern library and select 'Git Bash'.)

2. Install the dependencies for building the pattern library using the [Node
   package manager, npm](https://www.npmjs.com/). The `package.json` file defines what dependencies are installed.

        $ npm install

Having problems? See [troubleshooting Grunt](#42-grunt).




### 2.3 Install Compass Ruby gem

Install the Compass Ruby gem to compile Sass code into CSS.

```
$ gem install compass
```


### 2.4 Run grunt

Before working on creating new patterns, test that everything works by opening your command prompt and running:

```
$ grunt
```


### 2.5 How to contribute

You should now be configured to start work on the pattern library. Read [CONTRIBUTING.md](CONTRIBUTING.md) for some guidelines and principles of development.




---




## 3. How to update an existing install

If you already have the DPL installed and need to update the underlying packages start here:


### 3.1 Make sure your Node.js version is up-to-date.

To find out which version you have, run `node -v` using Git Bash or the command line.

Update to version `6.9.1 LTS` if you don't already have it from [http://nodejs.org/](http://nodejs.org/). All the default installation options work so there is no need to change them.


### 3.2 Checkout the branch from GitHub.

Use your prefered Git client to checkout the branch containing the updated `package.json` files.


### 3.3 Delete the `node_modules` folder.

This can be found within the root of the DPL folder. This may take a long time due to the size of these files.


### 3.4 Reinstall npm to your DPL directory.

Run `npm install` using Git Bash or the command line.


### 3.5 Verify it works.

Run `grunt` and if it works then you're successfully updated.

---




## 4. Troubleshooting

### 4.1 Node.js

#### Error: npm does not support Node.js vX.Y.Z

If you get an error message saying `npm does not support Node.js vX.Y.Z` then you need to upgrade your version of NPM.

1. In your command prompt application of choice (Git Bash, Node.js Command Prompt, Windows PowerShell, etc.) run the following:

```
npm install -g npm@latest
```

2. You will likely get an error. Wait for the error to complete. It will show a message that includes the following:

```
A complete log of this run can be found in:
    C:\Users\NAME\AppData\Roaming\npm-cache...
```

3. Navigate to this folder in Windows Explorer, where `NAME` is your Windows user folder.

4. Delete the two folders, `NPM` and `NPM-Cache` from `C:\Users\NAME\AppData\Roaming`, where `NAME` is your Windows user folder.

5. In Git Bash (or other terminal window) run

```
npm install -g npm@latest
```

6. Finally, run

```
npm install -g grunt-cli
```



### 4.2 Grunt

#### Error: Unable to connect to github.com

While trying to install Grunt dependencies, if you get an error such as

```
npm ERR! Error: Command failed: fatal: unable to connect to github.com:
```

it may be that you are behind a firewall and need to use https instead of git and git+ssh. Append the following to your `.gitconfig` file:

```
# Use https instead of git and git+ssh
[url "https://github.com/"]
        insteadOf = git://github.com/
[url "https://github.com/"]
        insteadOf = git@github.com:
```

You can always find the location of your `.gitconfig` file by typing the following command into a command prompt: `git config --global --edit`.

(On Windows, to exit this editor press `Ctrl+C`, then type `:quit` and press Enter.)


#### Error: handlebars does not support render

If you get the following error when running Grunt:

```
Running "assemble:core_meta" (assemble) task
handlebars does not support render.
Assembling core/build.json ERROR
Warning: handlebars does not support render. Use --force to continue.

Aborted due to warnings.
```

it may be that `npm install` did not complete. It has been reported on [Stack Overflow](http://stackoverflow.com/questions/33568306/handlebars-not-supporting-render-when-adding-assemble-to-a-yeoman-webapp-project) that sometimes node doesn't recursively install the modules for assemble-handlebars; this is a known issue in grunt-assemble, [issue #31](https://github.com/assemble/grunt-assemble/issues/31).

You can easily test for this by adding a [pre-release identifier](http://semver.org/#spec-item-9) to the version number in `package.json`, e.g.

```
"version": "0.9.0-alpha",
```

If `grunt` breaks after adding this, do the following:

1. At the command line (e.g. using Git Bash) navigate to `node_modules/assemble-handlebars`.
2. Run `npm install`.
3. The remaining modules will install.
4. Run `grunt` – it should complete successfully now.