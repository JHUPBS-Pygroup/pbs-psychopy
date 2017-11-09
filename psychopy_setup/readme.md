# Setup Psychopy Environment

There different ways to install psychopy. The official [installation document](http://psychopy.org/installation.html) is very helpful.

## Install Psychopy Standalone Version

You can download a standalone Psychopy from its [github releast page](https://github.com/psychopy/psychopy/releases) by choosing one of these two files

- `StandalonePsychoPy-1.85.4-win32.exe`
- `StandalonePsychoPy-1.85.4b-OSX_64bit.dmg`

## Install Psychopy with Conda

**You need to install Anaconda or MiniConda First!**

- You can try to use instructions [here](http://psychopy.org/installation.html#anaconda-and-miniconda) to setup conda environments for psychopy
	- It may not be up-to-date.

- Alternatively, you can create an `conda` environment `psychopy` from the configuration file `psychopy.yml`:
	- this configuration covers a subset of packages used by psychopy, see [Here](http://psychopy.org/installation.html#dependencies) for details.
	- use the following command line to create the environment
		- `conda env create -f psychopy.yml`
	- activate the environment
		- `source activate psychopy`
	- run experiment (use `pythonw`, not `python`)
		- `pythonw exp.py`

- **AUDIO dependency:** [download `pyo`](http://ajaxsoundstudio.com/software/pyo/) and install `pyo` indepdenently
	 - `pyo` does not have a binary distribution in `pip`, so you cannot use `pip install` to install this package.
	 - you may use `pygame` instead of `pyo`, but you have to change the configuration of psychopy. See [here](http://www.psychopy.org/api/preferences.html) for instructions: add these lines before you use psychopy audio modules.

```python
from psychopy import prefs
prefs.general['audioLib'] = ['pyo']
from psychopy import sound
```

## MacOS Trouble-Shooting

#### 1) invalid active developer path

You may encounter a problem of invalid active developer path after you upgrading to macOS Sierrra or a later version, errors like:

```
xcrun: error: invalid active developer path (/Library/
	Developer/CommandLineTools), missing xcrun at:
	/Library/Developer/CommandLineTools/usr/bin/xcrun.

error: command 'gcc' failed with exit status 1
```

You can run the following script in terminal:

```shell
$ xcode-select --install
```

- Credits to this [Solution Source](https://apple.stackexchange.com/questions/254380/macos-sierra-invalid-active-developer-path)

## Windows Trouble-Shooting

- To be added.
