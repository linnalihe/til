# Pyenv and Anaconda together on MacOS

Anaconda is primarily for doing data work
Python distribution comes pre-installed
Can be used to create environment that isolate your libraries and versions
It has it's own package manager -> conda; but also works with pip for packages that are not in conda

```
conda create --name your-enviro-name
conda activate your-enviro-name
conda install tensorflow
pip install tensorflow=1.4
```

Can use virtualenv and anaconda by using pyenv; sits on top of virtualenv and anaconda; can control versions of python being run; able to set a default environment for a directory

github.com/pyenv/pyenv
```
pyenv local 2.7.10
pyenv activate py27_tf11

pyenv local 3.5.2
pyenv activate py35_tf12 
```


https://stackoverflow.com/questions/57640272/how-can-i-install-anaconda-aside-an-existing-pyenv-installation-on-osx

Install homebrew:  https://brew.sh/ 
Install pyenv https://github.com/pyenv/pyenv
```
brew install --cask anaconda
echo 'export PATH=/usr/local/anaconda3/bin:$PATH' >> ~/.zshrc
export PATH=/opt/homebrew/anaconda3/bin:$PATH' >> ~/.zshrc
source ~/.zshrc
conda # health check
conda init
conda config --set auto_activate_base false
```
