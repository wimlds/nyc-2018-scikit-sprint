# Pre-workshop Requirements

Installing Software and Setting up Virtual Environment
have Python installed via Anaconda. (Anaconda includes Jupyter Notebook)


## Install Python via Anaconda

1.  Install [Anaconda](https://docs.anaconda.com/anaconda/install/)
- [Windows](https://docs.anaconda.com/anaconda/install/windows/)
- [Mac](https://docs.anaconda.com/anaconda/install/mac-os/)
- [Linux](https://docs.anaconda.com/anaconda/install/linux/)


## Instal Git
- Mac:  
	- [Git](https://git-scm.com/download/mac)
- Windows:  
	- [Git for Windows (Git Bash)](https://gitforwindows.org/)
  
- Confirm Git is installed by typing `git --version` on your terminal

## Step 3:  Sign up for a GitHub Account
- [github.com](https://github.com/)
- Save your user ID and password somewhere you can easily find it

## Gitter
Join gitter using your GitHub ID:  gitter.im/scikit-learn/wimlds 
  
## Choose a Graphical Editor
- Try Visual Studio Code
	* [Visual Studio Code](https://visualstudio.microsoft.com/downloads/)
- OR one of these other editors
	* [Sublime Text 3](https://www.sublimetext.com/)
 	* [Atom](https://atom.io/)
 	* [Notepad++](https://notepad-plus-plus.org/) (for Windows)
  
 
## Set up Virtual Environment

```bash
# Create virtual environment
conda create --name sklearndev numpy scipy matplotlib pytest sphinx cython ipykernel

# To activate this environment, use
conda activate sklearndev

# To deactivate an active environment, use
conda deactivate
```


