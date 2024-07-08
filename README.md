# Tutorials

Repository containing tutorials on how to access and do basic analysis of a variety of Space Physics datasets. We primarily use the [pySPEDAS] package for data acquisition.

## Tutorials

* [Parker Data Acquisition](https://github.com/tamarervin/tutorials/blob/main/parker.ipynb) using [pySPEDAS](https://pyspedas.readthedocs.io/en/latest/psp.html)
* [Solar Orbiter Data Acquisition](https://github.com/tamarervin/tutorials/blob/main/orbiter.ipynb) using [sunpy-soar](https://docs.sunpy.org/projects/soar/)
* [MAVEN In Situ Data Acquisition](https://github.com/tamarervin/tutorials/blob/main/maven.ipynb) using [pySPEDAS](https://pyspedas.readthedocs.io/en/latest/maven.html)
* [MAVEN IUVS Data Acquisition](https://github.com/tamarervin/tutorials/blob/main/iuvs.ipynb) using the [MAVEN IUVS](https://github.com/lasp/maven_iuvs/tree/master) package
* [SDO Data Acquisition](https://github.com/tamarervin/tutorials/blob/main/sdo.ipynb) using [Sunpy](https://sunpy.org/)

## Cloning Repository

To get started, clone this repository to your computer. You will need to have [git](https://github.com/git-guides/install-git) installed on your computer. Next, navigate (in git-bash (Windows) or Terminal (Mac/Unix/Linux)) to the location on your computer you want to save the repository.

You can either clone via SSH after following the steps in section [Setting Up an SSH Key]()  (tested in terminal Unix/Linux)
   
```
git clone git@github.com:tamarervin/tutorials.git
```
   
In Windows, if the ssh step doesn't work, use the https cloning method instead in git-bash :

```
git clone https://github.com/tamarervin/tutorials.git   
```   

## Pushing Code to Repository

To push your code to a repository, do the following:  

Add all the files to the repo

```
git add .
```

Commit to the repository with a message4

```
git commit -m 'your message here'
```

Push to the repository

```
git push
```

## Setting Up an SSH Key 

To clone a repository (including submodules) via SSH, you need to add a public/private SSH key to your GitHub account:
* 1.) <code>cd ~/.ssh</code>
    * navigate to the ssh folder on your computer
* 2.) <code>ls -l</code>
    * check if you already have an ssh key which would be in a file with the <code>.pub</code> extension
* 3.) <code>ssh-keygen -t rsa -b 4096</code>
    * creates public/private SSH key pair saved as a private (`file_name`) and public key file (`file_name.pub`)
* 4.) <code>cat <file_name>.pub</code>
    * view your public key file and copy the text which starts with "ssh-rsa"
* 5.) In your GitHub account, navigate to "Settings" then "SSH and GPG Keys". Then click "New SSH Key" and paste in your SSH key.
    * adds the SSH key to your GitHub account


## Environment Setup

This repository requires a custom environment. Do the following in Anaconda Prompt (windows), Terminal (Mac/Unic/Linux) (or use the GUI in Anaconda Navigator (Windows/Mac)
Check for conda-forge:
```
conda config --show channels
```
If needed, add conda-forge:
```
conda config --append channels conda-forge
```
Now we are ready to build the custom conda environment. Navigate to the folder containing the configuration file and run the below snippet.
```
conda env create --file conda_env.yml
```
To activate the conda environment run
```
conda activate analysis
```

## MAVEN IUVS Setup

In order to use the [MAVEN IUVS](https://github.com/lasp/maven_iuvs/tree/master) package, it must be in this repository as a submodule.

Setup the MAVEN IUVS submodule: 
* 1.) <code>git submodule init</code>
    * initiates the submodule instance found in the [.gitmodules](https://github.com/tamarervin/tutorials/blob/main/.gitmodules) file
* 2.) <code>git submodule update</code>
    * updates and clones the [MAVEN IUVS](https://github.com/lasp/maven_iuvs/tree/master) repository
* 3.) <code>pip install -e .</code>
    * navigate to the MAVEN IUVS directory and pip install the package
