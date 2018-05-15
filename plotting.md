# Plotting

I strongly suggest learning matplotlib, then plot.ly, then D3 or Mathbox, in that order. You are not required to learn D3 or Mathbox although you will need to know how to use matplotlib and plot.ly.

[Here are some examples](https://python-graph-gallery.com/all-charts/) of python charts.

You can see some plotting functions at the bottom of [this](https://github.com/inygy/nserc-analysis/blob/master/SelectionsTemplate.ipynb) file. In the future we may attempt to turn these into generalized plotting functions.

## matplotlib
Matplotlib is the easiest, it is good for mockups and initial plots.
You can import seaborn to make your matplotlib plots instantly look better or convert your matplotlib plot to a plot.ly plot for better interactivity.

[Example](http://pbpython.com/simple-graphing-pandas.html) of a simple graph with data

[How to](https://stackoverflow.com/questions/6974847/plot-with-non-numerical-data-on-x-axis-for-ex-dates) plot non numerical data on the x axis.

You can use [html5 to animate matplotlib](https://github.com/callysto/training-manual/blob/master/markdown/animate-graphs.md) however generally we suggest that you use plot.ly instead.

## Plot.ly
Plot.ly is good for interactivity. You can easily convert your matplotlib plots into plot.ly.

Plot.ly in Jupyter notebooks [tutorial](https://plot.ly/python/ipython-notebook-tutorial/)

[Plot data from a csv](https://plot.ly/python/plot-data-from-csv/()

Sample plot.ly graph, from a matplotlib plot:

```!pip install plotly --user;```

```
import numpy as np
import plotly.offline as py
from plotly.offline import init_notebook_mode, iplot
import plotly.tools as tls
import matplotlib.pylab as plt
from matplotlib.backends.backend_agg import FigureCanvasAgg as FigureCanvas

init_notebook_mode(connected=True)
fig = plt.Figure()
ax = fig.gca()
x = np.linspace(-10,10,200)
y = abs(x)
ax.plot(x,y)
canvas = FigureCanvas(fig)
plotly_fig = tls.mpl_to_plotly(fig)
py.iplot(plotly_fig)
```

The same plot using only plotly (preferred):
```
import numpy as np
import plotly.offline as py
from plotly.offline import init_notebook_mode, iplot
import plotly.tools as tls
import matplotlib.pylab as plt
from matplotlib.backends.backend_agg import FigureCanvasAgg as FigureCanvas

x = np.linspace(-10,10,200)
y = abs(x)

# Create a trace
trace = go.Scatter(
    x = x,
    y = y
)

data = [trace]

py.iplot(data, filename='absValue-plot')
```

## Advanced Plotting
Before starting there are a few distinctions you should know:

+ WebGL: is the Javascript API that allows you to create 3D graphics in the browser.

+ Three.js: a framework build on top of WebGL which makes it easier to create 3D graphics in the browser, it uses a canvas + WebGL to display the 3D scene.

+ D3.js: a data visualisation library. It makes it easy to generate and modify graphics based on data. Does not do 3D although you could theoretically combine it with three.js or mathbox to get 3D functionality. Has mediocre docs but a lot of great examples. Steep learning curve, slow to program.

+ Mathbox: uses three.js, WebGL and a few other libraries to create 3D graphics, 2D animated graphics, beautiful animated slideshows, render animated 3D objects with shaders in linear time, etc. Has a very steep learning curve and terrible docs.

You cannot easily convert from matplotlib/plot.ly to D3 or Mathbox. D3 and Mathbox are theoretically compatible with each other and could work in conjunction although it would require a prohibitive amount of knowledge of both.
Usually the workflow would be to imagine a visualization you want, and then directly begin to create it in D3 or Mathbox.

### D3
D3 is similar to but far better than, matplotlib or plot.ly. It has a large learning curve and you will mostly be on your own for debugging and troubleshooting.
If you really need D3 help you can contact Eric, eric.easthope@me.com.

Frankly the docs on D3 are not a great way to learn it. I suggest building off of [examples](https://bl.ocks.org/mbostock).

It is easiest to do D3 mockups using [observable](https://beta.observablehq.com/) and then port them over to the notebook.

If you are especially keen you can try combining D3 with three.js or related.

### Mathbox
Mathbox can do almost anything you want and pushes the limits of computer graphics. However... it is not actively maintained, the docs are terrible, and the learning curve is very steep.
Take a look at some of the pages of [acko.net](https://acko.net/blog/mathbox2/), feel free to explore to some of the other pages to see more examples.
