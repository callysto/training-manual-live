# Extensions

You can extend the use of Jupyter notebooks by importing external extensions, building your own magics, or even creating 
your own kernels.

## External extensions and libraries
Callysto has our own collection of importable extensions, [nbplus](nbplus.md).

You can also use pip install `!pip3 install foo --user` where foo is the library you want to install.
Generally this is discouraged, we want to have programs installed on the docker image of the server rather than in individual notebooks. 
This avoids having messy user facing installs and helps maintain consistency across the notebooks. 
However there are exceptions, if you are unsure ask the developer channel in slack.

We discourage the use of the extensions in the nbextensions package as many of them are unstable and may cause issues 
with the server.
We also discourage use of plotting libraries outside of matplotlib/plot.ly/D3/mathbox, more about this can be found in the
[plotting section](plotting.md) of the manual.

We want to maintain consistency across notebooks, if there is an extension you would like to add to the server 
please post it in the developer slack channel.

## Magics
Magics allow you to use many different programming languages in Jupyter cells as well as extend the functionality 
of Jupyter by bringing useful functionality into the cell.
Clone the [Magics Guide notebook](guides/MagicsGuide.ipynb) or [view it with nbviewer ](https://nbviewer.jupyter.org/github/callysto/training-manual-live/guides/blob/master/MagicsGuide.ipynb)
for more information on using and creating magics.

## Kernels
The primary languages used by Callysto are Python 3, Javascript and HTML/CSS. 
All notebooks you create should be based on a Python 3 kernel (there may be exceptions). 
You can bring in additional kernels using magics (see subsection above).
