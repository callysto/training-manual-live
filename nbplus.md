
# nbplus

[nbplus](https://github.com/callysto/nbplus) (working title) is a collection of Callysto-made Python modules for Creators wanting greater interactivity and visual aesthetic in Jupyter notebooks. These tools reflect a desire for aggregation of reusable code and uniformity in how we develop interactive content.

## Getting Started

All submodules are installed via the command line using

`pip install --upgrade --force-reinstall --user git+git://github.com/callysto/nbplus.git#egg=nbplus`.

Once installed, submodules may be imported separately.

e.g.


```python
import nblayout.uiButtons
from nbvis.ggb import *
```

To contribute, see the [repository](https://github.com/callysto/nbplus).

## Submodules

### <a name="geogebra">GeoGebra</a>

GeoGebra is an interactive mathematics application for visualization and interaction with geometry, algebra, statistics and calculus. We have developed a Jupyter magic so that GeoGebra may used within notebooks.

---

### <a name="nbvis">nbvis</a>

This is a Python [wrapper library](https://en.wikipedia.org/wiki/Wrapper_library) that enables JavaScript-based visualization in Jupyter, and provides a streamlined means of specifying and updating visualization code. We are actively supporting [D3.js](https://d3js.org/) and [MathBox.js](https://github.com/unconed/mathbox).

_class_ `classes.D3(name)` [[`source`]](https://github.com/callysto/nbplus/blob/master/nbvis/objects.py)

Containerizes D3 structures.

#### Parameters:
* name (string) – an unique identifier for a class instance

#### Methods:
* `svg(height=None)` – appends code to display an SVG element
* `canvas(height=None)` – appends code to display a Canvas element

#### Returns: 

* D3 object class instance

#### Return type:	

* `nbvis.objects.D3`

#### Usage:

```python
>>> plot1 = D3("plot").svg(height=300)
```

`New D3 object called "plot" added to instances ...`

```python
>>> plot2 = D3("plot").svg(height=500)
```

`D3 object "plot" is a duplicate ... replacing ...`

_class_ `classes.MathBox(name)` [[`source`]](https://github.com/callysto/nbplus/blob/master/nbvis/classes.py)

Containerizes MathBox structures.

#### Parameters:
* name (string) – an unique identifier for a class instance

#### Methods:
* `canvas(height=None)` – appends code to display a Canvas element

#### Returns: 

* MathBox object class instance

#### Return type:	

* `nbvis.objects.MathBox`

#### Usage:

```python
>>> plot1 = MathBox("plot").canvas(height=300)
```

`New MathBox object called "plot" added to instances ...`

```python
>>> plot2 = MathBox("plot").canvas(height=500)
```
`MathBox object "plot" is a duplicate ... replacing ...`

_magic_ `%%d3` [[`source`]](https://github.com/callysto/nbplus/blob/master/nbvis/magics.py)

Creates a global variable `d3_code` and appends the content of the cell to it for later use in a D3 object class instance. 

#### Flags:
* to reset **all** code : `--reset`
* to immediately wrap and run code using D3 : `--now`

#### Usage:

```javascript
%%d3
// some JavaScript comment
var svg = d3.select("svg");
console.log(svg);
```

`Code added to D3 visualization stack!`

_magic_ `%%mathbox` [[`source`]](https://github.com/callysto/nbplus/blob/master/nbvis/magics.py)

Creates a global variable `mathbox_code` and appends the content of the cell to it for later use in a MathBox object class instance.

#### Flags:
* to reset **all** code : `--reset`
* to immediately wrap and run code using MathBox : `--now`

#### Usage:

```javascript
%%mathbox
var view = mathbox
  .cartesian({
    range: [[-2, 2], [-1, 1], [-1, 1]],
    scale: [2, 1, 1],
  })
    .axis({
      axis: 1,
    })
    .axis({
      axis: 2,
    })
var axis = mathbox.select("cartesian > axis")
console.log(axis);
```

`Code added to MathBox visualization stack!`

---

### <a name="nblayout">nblayout</a>

This is a collection of magic commands and Python functions for on-the-fly modifications to the notebook user interface and its layout.

#### Hide All Code Cells

Use this in the first code cell of a notebook:

```python
import nblayout.uiButtons
%uiButtons
```

We expect this code cell to be replaced with two buttons: <input type="submit" id="toggleButton" value="Show Code"> <input id="init" type="submit" value="Initialize">

#### A Column View

First, `import nblayout.nbshape`. Then, begin any code cell with the magic command `%columns`, like this:

```python
%columns
<code>
```
