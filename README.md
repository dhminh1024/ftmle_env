# CS-FTMLE Set up the working environment

## Windows

### Install Bash for Windows

`Git` is a version control system that lets you track who made changes to what and when, and it has options for easily updating a shared or public version of your code on [GitHub](https://github.com/).

Download the [Git for Windows installer](https://git-scm.com/download/win).

Run the installer by double-clicking on the downloaded file and by following the steps bellow:

1. Click on “Run”.
2. Click on “Next”.
3. Click on “Next”.
4. Click on “Next”.
5. Click on “Next”.
6. Click on “Next”.
7. **Leave the selection on “Git from the command line and also from 3rd party software”** and click on “Next”. NOTE: If you forgot to do this, the programs that you need for the workshop will not work properly. If this happens, rerun the installer and select the appropriate option.
8. Click on “Next”.
9. **Leave the selection on “Checkout Windows-style, commit Unix-style line endings”** and click on “Next”.
10. Select the second option for **Use Windows’ default console window** and click on “Next”.
11. Click on “Next”.
12. Click on “Install”.
13. When the install is complete, click on “Finish”.

This installation will provide you with both `Git` and `Bash` within the `Git Bash` program.

### Setup Miniconda

**IMPORTANT:** if you already have a `Python` installation on your Windows computer, the settings below will replace it with Miniconda `Python 3.7` as the default `Python`.

Download the [Miniconda installer for Windows](https://docs.conda.io/en/latest/miniconda.html). Be sure to download the `Python` 3.7 version!

Run the installer by double-clicking on the downloaded file and follow the steps below.

1. Click “Run”.
2. Click on “Next”.
3. Click on “I agree”.
4. Leave the selection on “Just me” and click on “Next”.
5. Click on “Next”.
6. **Select the first option for “Add Anaconda to my PATH environment variable”** and also **leave the selection on “Register Anaconda as my default Python 3.7”.** Click on “Install”.
    - Note that even though the installation is for Miniconda, the installer uses the word Anaconda in these options.
    - You will also see a message in red text that selecting “Add Anaconda to my PATH environment variable” is not recommended; continue with this selection to make using conda easier in Git Bash. If you have questions or concerns, please contact your instructor.
7. When the install is complete, Click on “Next”.
8. Click on “Finish”.

## MAC

## Git Setup

`Git` is a version control system that lets you track who made changes to what and when, and it has options for easily updating a shared or public version of your code on [GitHub](https://github.com/).

Install `Git` on Macs by downloading and running the most recent installer for “mavericks” if you are using OS X 10.9 and higher -or- if using an earlier OS X, choose the most recent “snow leopard” installer, from [this list](http://sourceforge.net/projects/git-osx-installer/files/).

After installing `Git`, there will not be anything in your /Applications folder, as `Git` is a command line program.

**Data Tip:** If you are running Mac OSX El Capitan, you might encounter errors when trying to use `Git`. Make sure you update XCODE. [Read more - a Stack Overflow Issue](http://stackoverflow.com/questions/32893412/command-line-tools-not-working-os-x-el-capitan).

### Install Miniconda

1. Download the installer: [Miniconda bash installer for Mac](https://docs.conda.io/en/latest/miniconda.html). Be sure to download the `Python` 3.x version!
2. In your Terminal window, run: `bash Miniconda3-latest-MacOSX-x86_64.sh`.
3. Follow the prompts on the installer screens.
4. If you are unsure about any setting, accept the defaults. You can change them later.
5. To make sure that the changes take effect, close and then re-open your Terminal window.


## Linux

### **Git on Linux**

If `Git` is not already available on your machine, you can try to install it via your distro’s package manager. For Debian/Ubuntu, run `sudo apt-get install git` and for Fedora run `sudo yum install git`.

### Install Miniconda

1. Download the installer: [Miniconda bash installer for Linux](https://docs.conda.io/en/latest/miniconda.html). Be sure to download the `Python` 3.x version!
2. In your Terminal window, run: `bash Miniconda3-latest-Linux-x86_64.sh`.
3. Follow the prompts on the installer screens.
4. If you are unsure about any setting, accept the defaults. You can change them later.
5. To make sure that the changes take effect, close and then re-open your Terminal window.


## Next

### Test your setup of Bash, Git and Miniconda

1. On Window, search for and open the `Git Bash` program. On Mac or Linux open `Terminal` window. In this `Terminal` window, type `bash` and hit enter. If you do not get a message back, then `Bash` is available for use.
2. Next, type `git` and hit enter. If you see a list of commands that you can execute, then `Git` has been installed correctly.
3. Next, type `conda` and hit enter. Again, if you see a list of commands that you can execute, then Miniconda `Python` has been installed correctly.

### Config Miniconda and install packages

1. Prevent the base environment from automatically activating `conda`:

    `conda config --set auto_activate_base false`

2. Add `conda-forge` as the first channel, and ensure that `conda-forge` is used if the package is available

    `conda config --env --add channels conda-forge`

    `conda config --env --set channel_priority strict`

3. Install the environment using:

    `conda env create -f environment.yml`

	This will take a bit of time to run.

4. Activate the environment:

    `conda activate cs_ftmle`

```
    # environment.yml
    name: cs_ftmle
    channels:
    	- conda-forge
    	- defaults
    
    dependencies:
    	- python=3.7
    	- pip
    	# Core specific python
    	- numpy
    	- matplotlib
    	- seaborn
    	# NLP
    	- nltk
    	- textblob
    	# Jupyter environment
    	- autopep8
    	- jupyterlab
    	- notebook
    	- ipython
    	- jupyter_contrib_nbextensions
    	- nbclean
    	# Autograding
    	- matplotcheck=0.0.11
    	- nbgrader
```