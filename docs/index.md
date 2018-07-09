# How Do I Pyenv?

A how-to guide for using pyenv, a program to help you install and manage
multipe versions of Python side-by-side in an easy and pain-free way!

HTML pages for this tutorial (you are here): <https://pages.charlesreid1.com/how-do-i-pyenv>

Source code for this tutorial: <https://git.charlesreid1.com/charlesreid1/how-do-i-pyenv>

Mirror on Github: <https://github.com/charlesreid1/how-do-i-pyenv>


# Installing pyenv

Start by running the pyenv installer (see [pyenv-installer](https://github.com/pyenv/pyenv-installer)):

```
# Install pyenv
curl -L https://raw.githubusercontent.com/pyenv/pyenv-installer/master/bin/pyenv-installer | bash
```

This will install all pyenv-related things to `~/.pyenv`.

Next, add pyenv's bin directory to $PATH (should already be in ~/.bash_profile but just in case):

```
echo 'export PATH="~/.pyenv/bin:$PATH"' >> ~/.bash_profile
```

Now you can log out and log back in, or do `source ~/.bash_profile`, and 
check that the following command returns the location of pyenv:

```
$ which pyenv
```

# Installing conda

Now we set the version of python we wish to install. We will install miniconda 4.3.30 for python 3:

```
CONDA="miniconda3-4.3.30"
```

First tell pyenv to install this version of conda (this will download and build it):

```
pyenv install $CONDA
```

Next, tell pyenv that you want this to be the default version of pyenv Python:

```
pyenv global $CONDA
```

Finally, if you want to put this verison of Python on your path, you should run:

```
eval "$(pyenv init -)"
```

Now you can check to make sure you have the pyenv-installed version of conda:

```
which conda
conda --version
python --version
```

If you want to make this version of Python the one on your path, and you want
that to happen *always*, you can add the above line to your `~/.bash_profile`:

```
echo 'eval "$(pyenv init -)"' >> ~/.bash_profile
```

