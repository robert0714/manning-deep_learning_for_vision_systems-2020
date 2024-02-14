# appendix A. Getting set up
All of the code in this book is written in Python 3, Open CV, Keras, and TensorFlow. The process of setting up a DL environment on your computer is fairly involved and consists of the following steps, which this appendix covers in detail:

1. Download the code repository.
1. Install Anaconda.
1. Set up your DL environment: install all the packages that you need for projects in this book (NumPy, OpenCV, Keras, TensorFlow, and others).
1. [Optional] Set up the AWS EC2 environment. This step is optional if you want to train your networks on GPUs.
## Setting up your DL environment
Now you will create a new environment and install the packages that you will use for your projects. You will use conda as a package manager to install libraries that you need. You are probably already familiar with pip; it’s the default package manager for Python libraries. Conda is similar to pip, except that the available packages are focused around data science, while pip is for general use.

Conda is also a virtual environment manager. It’s similar to other popular environment managers like virtualenv (https://virtualenv.pypa.io/en/stable) and pyenv (https://github.com/pyenv/pyenv). However, conda is not Python-specific like pip is: it can also install non-Python packages. It is a package manager for any software stack. That being said, not all Python libraries are available from the Anaconda distribution and conda. You can (and will) still use pip alongside conda to install packages.
### Setting up your development environment manually
Follow these steps to manually install all the libraries needed for the projects in this book. Otherwise, skip to the next section to install the environment created for you in the book’s GitHub repo.
1. On your terminal, create a new conda environment with Python 3 and call it **deep_learning_for_vision_systems**:
    ```bash
    conda create -n deep_learning_for_vision_systems python=3
    ```
   Note that to remove a conda environment, you use ``conda env remove -n <env_name>``.
1. Activate your environment. You must activate the environment before installing your packages. This way, all packages are installed only for this environment:
    ```bash
    conda activate deep_learning_for_vision_systems 
    ```
    Note that to deactivate an environment, you use ``conda deactivate <env_name>``.
    
    Now you are inside your new environment. To see the default packages installed in this environment, type the following command: conda list. Next, you will install the packages used for the projects in this book.
1. Install NumPy, pandas, and Matplotlib. These are very common ML packages that you will almost always use in your projects for math operations, data manipulation, and visualization tasks:
    ```bash
    conda install numpy pandas matplotlib
    ```
     Note that throughout these installs, you will be prompted to confirm to proceed (Proceed ([y]/n)?). Type y and press Enter to continue the installation.
1. Install the Jupyter notebooks. We use Jupyter notebooks in this book for easier development:
    ```bash
    conda install jupyter notebook
    ```
1. Install OpenCV (the most popular open source CV library):
    ```bash
    conda install -c conda-forge opencv
    ```
1. Install Keras:
    ```bash
    pip install keras
    ```
1. Install TensorFlow:
    ```bash
    pip install tensorflow
    ```
    Now everything is complete and your environment is ready to start developing. If you want to view all the libraries installed in your environment, type the following command:
    ```bash
    conda list
    ```
    These packages are separate from your other environments. This way, you can avoid any version-conflict issues.
### Using the conda environment in the book’s repo
1. Clone the book’s GitHub repository from https://github.com/moelgendy/deep_learning_for_vision_systems. The environment is located in the installer/application.yaml file:
    ```bash
    cd installer
    ```
1. Create the conda deep_learning environment:
    ```bash
    conda env create -f my_environment.yaml
    ```
1. Activate the conda environment:
    ```bash
    conda activate deep_learning
    ```
1. Launch your Jupyter notebook (make sure you are located in the root of the deep_learning_for_vision_systems repository):
    ```bash
    jupyter notebook
    ```
Now you are ready to run the notebooks associated with the book.

###  Saving and loading environments
It is best practice to save your environment if you want to share it with others so that they can install all the packages used in your code with the correct version. To do that, you can save the packages to a YAML (https://yaml.org) file with this command:
```bash
conda env export > my_environment.yaml 
```
This way, others can use this YAML file to replicate your environment on their machine using the following command:
```
conda env create -f my_environment.yaml 
```
You can also export the list of packages in an environment to a .txt file and then include that file with your code. This allows other people to easily load all the dependencies for your code. Pip has similar functionality with this command:
```
pip freeze > requirements.txt
```
You can find the environment details used for this book’s projects in the downloaded code in the installer directory. You can use it to replicate my environment in your machine.
