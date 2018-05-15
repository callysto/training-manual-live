# Notebook Binders, Pullers and Viewers

**Binder:** To use Binder, go to this site <https://mybinder.org/> and paste in a copy of your githib repo with your notebooks. Read the notes on the site to figure out how to make this work. For instance, you need a file called requirements.txt that lists the Python packages that are needed to run.

Mybinder will give you something to copy, that looks like this:

```
[![Binder](https://mybinder.org/badge.svg)](https://mybinder.org/v2/gh/mlamoureux/Callysto/master)
```

Paste that into a markdown cell. The result is a button that you can click on, like this:

[![Binder](https://mybinder.org/badge.svg)](https://mybinder.org/v2/gh/mlamoureux/Callysto/master)

The notebook is then "live." You can edit it, make changes, run it. But it only exist effemerally, which means it will disappear after some time. But, you can always download it directly onto your machine.

**GitHub:** GitHub will let you view a Jupyter notebook directly, but it doesn't actually run. Just type in the link in Markdown, like this: <https://github.com/mlamoureux/Callysto/blob/master/ASimplePlot.ipynb>

**Puller:** Under development.

**Viewer:** nbviewer lets you see a rendered Jupyter notebook, but it is not "live." That is, you can't make any changes. To use it, you take the web address `http://nbviewer.ipython.org/` and tack onto the end `url/` and the address of your notebook. Something like this:

<http://nbviewer.ipython.org/url/github.com/mlamoureux/Callysto/blob/master/ASimplePlot.ipynb>
