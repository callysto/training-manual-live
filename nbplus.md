
# nbplus

[nbplus](https://github.com/callysto/nbplus) (working title) is a collection of Callysto-made Python modules for Creators wanting greater interactivity and visual aesthetic in Jupyter notebooks. These tools reflect a desire for aggregation of reusable code and uniformity in how we develop interactive content.

## Getting Started

Submodules are installed separately.

Use the following command, replacing `<submodule>` with the name of a subdirectory in [nbplus](https://github.com/callysto/nbplus):

`pip install --upgrade --force-reinstall --user git+git://github.com/callysto/nbplus.git#egg=<submodule>\&subdirectory=<submodule>`

Once installed, import a submodule by referring to itself.

e.g.

```python
from geogebra.ggb import *
from nbvis.classes import D3, MathBox, Vis
```

To contribute, see the [repository](https://github.com/callysto/nbplus).

## Submodules

### <a name="geogebra">GeoGebra</a>

GeoGebra is an interactive mathematics application for visualization and interaction with geometry, algebra, statistics and calculus. We have developed a Jupyter magic so that GeoGebra may used within notebooks.

---

### <a name="nbvis">nbvis</a>

This is a Python [wrapper library](https://en.wikipedia.org/wiki/Wrapper_library) for JavaScript-based visualizations in Jupyter, and provides a streamlined means of specifying and updating visualization code. We are actively supporting [D3.js](https://d3js.org/) and [MathBox.js](https://github.com/unconed/mathbox).

A sample guide outlining the creation of a slider bar using `nbvis` is available [here](https://github.com/callysto/training-manual-live/blob/extensions/guides/nbvisGuide.ipynb).

---

_class_ `classes.D3(name, silent=True)` [[`source`]](https://github.com/callysto/nbplus/blob/master/nbvis/classes.py)

Containerizes D3 structures.

#### Parameters:
* _name_ (`string`) – a unique identifier for a class instance
* _silent_ (`boolean`) – toggles verbose output

#### Methods:
* `svg(height=None)` – appends code to display an [SVG](https://en.wikipedia.org/wiki/Scalable_Vector_Graphics) element
* `canvas(height=None)` – appends code to display a [Canvas](https://en.wikipedia.org/wiki/Canvas_element) element
* `require(*args)` – requires JavaScript modules from [unpkg](https://unpkg.com/) via [asynchronous modules definition](https://en.wikipedia.org/wiki/Asynchronous_module_definition) 

#### Returns: 

* D3 object class instance

#### Return type:	

* `nbvis.classes.D3`

#### Usage:


```python
>>> D3.reset()
>>> foo = D3("foo", silent=False).svg(height=100)
>>> foo.require("d3-selection-multi", "d3-force-constant")
```

    Reset list of D3 class instances!
    New D3 object "foo" added to instances ...
    Will require "d3-selection-multi", "d3-force-constant" ...


---

_class_ `classes.MathBox(name, silent=True)` [[`source`]](https://github.com/callysto/nbplus/blob/master/nbvis/classes.py)

Containerizes MathBox structures.

#### Parameters:
* _name_ (`string`) – a unique identifier for a class instance
* _silent_ (`boolean`) – toggles verbose output

#### Methods:
* `canvas(height=None)` – appends code to display a [Canvas](https://en.wikipedia.org/wiki/Canvas_element) element
* `require(*args)` – requires JavaScript modules from [unpkg](https://unpkg.com/) via [asynchronous modules definition](https://en.wikipedia.org/wiki/Asynchronous_module_definition) 

#### Returns: 

* MathBox object class instance

#### Return type:	

* `nbvis.classes.MathBox`

#### Usage:


```python
>>> bar = MathBox("bar").canvas(height=200)
```


```python
>>> bar = MathBox("bar", silent=True).canvas(height=300)
```

    Replaced duplicate MathBox object "bar" ...


---

_class_ `classes.Vis(*args, js="", silent=True)` [[`source`]](https://github.com/callysto/nbplus/blob/master/nbvis/classes.py)

#### Parameters:
* _*args_ (`D3` or `MathBox`) – specifies object class instances to be displayed immediately
* _js_ (`string`) – prepends custom JavaScript before visualization code
* _silent_ (`boolean`) – toggles verbose output

#### Methods:
* None

#### Returns: 

* Visualization object class instance

#### Return type:	

* `nbvis.classes.Vis`

#### Usage:


```python
>>> Vis(foo, bar, silent=False);
```

    Found D3 instance of "foo" ...
    Requiring "d3-selection-multi", "d3-force-constant" ...
    Found MathBox instance of "bar" ...



    <IPython.core.display.Javascript object>


---

_magic_ `%%d3` [[`source`]](https://github.com/callysto/nbplus/blob/master/nbvis/magics.py)

Creates a global variable `d3_code` and appends the content of the cell to it for later use in a D3 object class instance. 

#### Flags:
* to reset all code : `--reset`
* to queue code for later execution : `--queue` or `-q`

#### Usage:


```python
>>> import nbvis.magics
```


```javascript
%%d3 --reset --queue
// a JavaScript comment
var svg = d3.select("svg");
console.log(svg);
```

    Initialized d3_code container!
    Code added to D3 visualization queue ...


---

_magic_ `%%mathbox` [[`source`]](https://github.com/callysto/nbplus/blob/master/nbvis/magics.py)

Creates a global variable `mathbox_code` and appends the content of the cell to it for later use in a MathBox object class instance.

#### Flags:
* to reset all code : `--reset`
* to queue code for later execution : `--queue` or `-q`

#### Usage:


```javascript
%%mathbox --queue
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

    Initialized mathbox_code container!
    Code added to MathBox visualization queue ...


---
