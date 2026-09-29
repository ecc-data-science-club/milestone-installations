# Installing Python extension and libraries for Data Science in Visual Studio Code

This guide assumes Python 3 and VS Code are already installed.

1. Install extensions:
Navigate to the extensions on the side bar (Ctrl+shift+X on Windows/Linux and cmd+Shift+X on Mac) and install:
- Python (by Microsoft)
- Jupyter (by Microsoft)


2. Create a project directory:
In your built-in VS Code terminal (Ctrl+\`` or Cmd+``), create a folder for your project and open it
```sh
mkdir folder-name
cd folder-name
code .
```
'code . ' opens the folder and will popup a new window. Do the remaining steps in that window. 

3. Move your datasets (.csv or .xlsx, etc.) inside this folder so that your code can load them with relative paths like 'data.csv'. You can move them manually with File explorer or Finder or using terminal commnads.

4. Create a virtual environment

A virtual environment keeps the project's packages separate from the system software and is necessary to...

**Mac**
```sh
python3 -m venv .venv
source .venv/bin/activate
```

**Windows**
```sh
py -m venv .venv
.venv\Scripts\activate
```

After activating, '.venv' will appear at the start of your terminal prompt. If VS Code asks if it should use the new environment, click **yes**.


5. Install essential data analysis packages

Inside the active environment:
```sh
python -m pip install pandas numpy matplotlib seaborn scikit-learn
```

Or Individually:
```sh
python -m pip install numpy
python -m pip install scikit-learn
python -m pip install matplotlib seaborn
```

May need to update the pip installer: 
```sh
python -m pip install --upgrade pip
```

6. Select the interpreter

1. Open the command palette (ctrl+shift+p or cmd+shift+p)
2. Run 'Python: select interpreter'
3. Choose the one inside '.venv'


7. Ignore the .venv environment in Git

Some files you don't want to allow to push to GitHub - APIs, sensitive keys, and .venv environments. 

Add this line to a file named '.gitignore' in your folder:

```sh
.venv/
```


8. Create either a .py file (python file with a .venv environment) or a .ipynb file (python file with a Jupyter Notebook environment)


## .py files Python File

Must use # %% to create interactive code cells

1. Create a file ending in '.py'
2. Run it with the play button in the top right
3. Optional: Type '# %%' to create a cell that runs in the Jupyter window (requires the Jupyter extension)


## .ipynb files - Jupyter Notebook Interface

1. Create a file ending in '.pynb'
2. Click 'select kernel' in the top right and choose the '.venv' environment
3. Run cells with 'shift+enter' or by hitting the play button on the cell


9. Test your setup

```python
import pandas as pd
print(pd.__version__)
```

Setup was successfulif a version number is returned. 

