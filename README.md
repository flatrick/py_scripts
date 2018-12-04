# py_scripts
My collection of tips, snippets and scripts in Python (2.7 and 3.X)

# Python on Windows

## Python 2.7 and 3.X installed?

If you have both Python 2.7.X and 3.X installed, you might want to create a shortcut to start a custom cmd.exe (Command Line Prompt) that only has Python 2.7 (or 3.X, depending on your needs) in it's path and that way, you don't risk starting the incorrect python-version while you're working on this!

The example below expects having the following tools at the specified directories:
- Python 2.7: `c:\python27\`  
- GIT: `C:\Program Files\Git\cmd`  
- FFmpeg: `C:\Program Files\FFmpeg\bin`  

```cmd
cmd /k "set PATH=C:\python27\;C:\python27\Scripts\;C:\Program Files\Git\cmd;C:\Program Files\FFmpeg\bin;%SystemRoot%\system32;%SystemRoot%;%SystemRoot%\System32\Wbem;%SYSTEMROOT%\System32\WindowsPowerShell\v1.0\"
```

## virtualenv

After starting cmd.exe using our shortcut we created above, we need to install virtualenv so we can create our virtual environments so we don't end up with mismatching/conflicting versions of python-libraries for different projects.

```
pip install virtualenv
```

Then, let's move to our root project-directory where you 

```
cd "X:\MY_WORKING_FOLDER\HERE"
```

And now we can create our virtual environment:

```
virtualenv env
```

When it's done, run this command to put your cmd-window in your new python virtual environment:

```
env\Scripts\activate.bat
```

And now we can install any libraries we want for our project using pip, like this:
```
pip install git+https://github.com/mapillary/Piexif
```
