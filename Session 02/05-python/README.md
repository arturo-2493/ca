# Python for Customer Analytics

We can use [Python](https://www.python.org) for Customer Analytics as well. While is not the goal of this course. In each of the session you can check and practice some examples. If you are not familiar to Python, I recommend the book [Python Data Science Handbook](https://jakevdp.github.io/PythonDataScienceHandbook/).

## Installing Python in Windows (using Chocolatey)

First we must install [Chocolatey](https://chocolatey.org). After it has been installed, we can use the terminal to install python in Windows:

``` 
choco install -y python3
``` 

## Installing Python in Mac (using homebrew)

Open your Terminal app on your Mac and run the copy/paste the following command into the Terminal to install XCode onto your Mac:

``` 
xcode-select --install
``` 

Then we can install [HomeBrew](https://brew.sh) using the terminal:

``` 
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
``` 

Now we can install the latest version of python:

``` 
brew install python3
``` 

## Managing software packages using an environemnt

We will need to install [pip](https://pypi.org/project/pip/), [setuptools](https://pypi.org/project/setuptools/) and [wheel](https://pypi.org/project/wheel/) (recommended for the installation of other packages):

``` 
pip3 install --upgrade pip setuptools wheel
``` 

We can use a package that will help us to create an environment and the folder that we will use for our projects:

``` 
pip3 install virtualenv virtualenvwrapper
mkdir ~/python-ca
``` 

We configure the environment (in my case python-ca, use your folder):

``` 
echo '# needed for virtualenvwrapper' >> ~/.profile
echo export 'WORKON_HOME=$HOME/.virtualenvs' >> ~/.profile
echo export 'PROJECT_HOME=$HOME/python-ca' >> ~/.profile
echo export VIRTUALENVWRAPPER_PYTHON=/usr/local/bin/python3 >> ~/.profile
echo export VIRTUALENVWRAPPER_VIRTUALENV=/usr/local/bin/virtualenv >> ~/.profile
echo export PIP_REQUIRE_VIRTUALENV=true >> ~/.profile
echo source /usr/local/bin/virtualenvwrapper.sh >> ~/.profile
source ~/.profile
``` 

We active our environment with:

``` 
mkvirtualenv python-ca
``` 

Each time we want to work with the environment just execute:

``` 
workon python-ca
``` 

## Updating your packages

First we need a requirements.txt file (that is the list of the packages in our project):

``` 
pip3 freeze > requirements.txt
``` 

Then, we can use pip-upgrader to review the new packages. First we install it:

``` 
pip3 install pip-upgrader
``` 

then we excute it (It will work, if you have a requirements.txt file in your folder):

``` 
cd python-ca
pip-upgrade
``` 

## Installing base packages for data science

First some libraries, and thehn the proper packages.

``` 
brew install pkg-config libpng freetype xlrd
pip3 install numpy scipy matplotlib pandas sympy nose mlxtend
``` 

## Installing Jupyter

This is optional (and/or complementary to Atom). Jupyter is an interactive Python environment. Install jupyter with:

``` 
pip3 install jupyter
``` 

Run Jupyter with:

``` 
jupyter notebook
``` 

## Upgrading python

To upgrade python. First upgrade homebrew formulas, then python:

``` 
brew update
brew upgrade python3
``` 

Finally recreate the symlinks to your packages in your environment:

``` 
find ~/.virtualenvs/ca/ -type l -delete
virtualenv ~/.virtualenvs/ca
``` 

## Upgrading everything in brew

Open the terminal and execute:

``` 
brew update && brew upgrade `brew outdated`
``` 

## Cleaning not required files in brew

Open the terminal and execute:

``` 
brew clean
``` 

## Checking that everything is right for brewing

Open the terminal and execute:

``` 
brew doctor
``` 

## Atom

There are many GUI for Python. In our case, we are using [Atom](https://atom.io) and the package [hydrogen](https://atom.io/packages/hydrogen).

Atom (with hydrogen) is able to simulate Jupiter notebooks in your code. It needs ipykernel.

``` 
python -m pip install ipykernel 
python -m ipykernel install 
``` 

## Books

- [Python notes for professionals](https://goalkicker.com/PythonBook/)
