# Chaos
#### Visualizations connecting chaos theory, fractals, and  the logistic map!
###### Written by [Jonny Hyman](https://www.jonnyhyman.com), 2020

This code was developed for [this YouTube video from Veritasium](https://www.youtube.com/watch?v=ovJcsL7vyrk)

This is not a library, but rather a collection of standalone scripts! As such, there is a bit of code duplication between scripts.

# Quick start guide

#### Install these requirements
- [Python 3.6 to 3.10](https://www.anaconda.com/distribution/)
- [Numpy](https://numpy.org) package : `pip install numpy`
- [Numba](https://numba.pydata.org) package : `pip install numba` _(not functional on Python 3.11+ as of 2/8/2023)_

- For the Logistic Map user interface:
  - [PyQt5](https://pypi.org/project/PyQt5/) : `pip install pyqt5`
  - [PyQtGraph](https://pyqtgraph.readthedocs.io/en/latest/) : `pip install pyqtgraph` (Python 3.6, 3.7) or `pip install pyqtgraph==0.11.0rc0` (Python 3.8)

- For the 3D Mandelbrot Set & Logistic Map Zoom:
  - [Vispy](http://vispy.org) : `pip install vispy`
  - [Matplotlib](https://matplotlib.org) : `pip install matplotlib`
  - [PyOpenGL](https://pypi.org/project/PyOpenGL/) : `pip install pyopengl`
  - [ffmpeg](https://www.ffmpeg.org) if you want to auto-stitch rendered frames to .movs
    - macOS: [Install homebrew](https://brew.sh) then `brew install ffmpeg`
    - Windows: [Install chocolatey](https://chocolatey.org) then `choco install ffmpeg`

All in one: `pip install numpy numba pyqt5 pyqtgraph vispy matplotlib pyopengl`

#### Run guide for total beginners
0. Open "Terminal" on macOS & Linux, "Powershell" or "Command Prompt" on Windows
1. Download this repository and unzip it or run `git clone https://github.com/jonnyhyman/Chaos.git`
2. Change directory into the folder where you extracted files `cd ~/route/to/your/folder`
3. Run the program you're interested in, like `python logistic_interactive.py`
4. To make changes to the code, install a text editor like [Visual Studio Code](https://code.visualstudio.com) and then open the file you want to edit. If this is your first python project, GO FOR IT, but also it might not be the easiest to get your head wrapped around (I use a lot of nuanced python functionality).

#### If you run into problems
0. Google the problem you're running into
1. If it seems to be a problem with **this** code, post in "Issues"

----

## Logistic Map - Interactive
`python logistic_interactive.py`
![Interactive](https://github.com/jonnyhyman/Chaos/blob/master/images/logistic-interactive.png?raw=true)

This visualization creates a cobweb plot, time series graph, and bifurcation plot for visualizing the logistic map. The font pictured is "Avenir Next" which is licensed as part of macOS. Other OSes will see their default font.

#### Shortcuts:
- Spacebar: play/pause
- Backspace: reset view & animation

----

## 3D Mandelbrot Set
`python logistic_mandelbrot.py`
![Mandelbrot Set within Logistic Map GIF](https://github.com/jonnyhyman/Chaos/blob/master/images/logistic-mandelbrot.gif?raw=true)

Here we see the Mandelbrot set on the x-y plane, and iterations of the Mandelbrot set in the z axis. This reveals the bifurcation plot beneath the Mandelbrot set!

Final visualization is accomplished by a volume rendering of 1000x1000x1000 voxels, oversampled by 16 to reduce aliasing. At that resolution the visual _does not run in realtime_.

----

## Logistic Map Zoom
`python logistic_zoom.py`
![Logistic Map Zoom GIF](https://github.com/jonnyhyman/Chaos/blob/master/images/logistic-zoom.gif?raw=true)

- Note: The final version of the visualization used a custom version of Vispy, modified to improve the appearance of axes. I have not released this and don't plan to.