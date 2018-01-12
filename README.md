# ``pdvega``

This package is an experiment in making [vega](https://vega.github.io/) and [vega-lite](https://vega.github.io/vega-lite/) plots easier to generate in Python.

Pandas currently has a built-in set of [Visualization tools](https://pandas.pydata.org/pandas-docs/stable/visualization.html) based on matplotlib. So, for example, you can create a plot this way:

```python
import numpy as np
import pandas as pd

df = pd.DataFrame({'x': np.random.randn(100), 'y': np.random.randn(100)})
df.plot.scatter(x='x', y='y')
```

![matplotlib scatter output](images/mpl-scatter.png?raw=true)

The goal of ``pdvega`` is that any time you use ``dataframe.plot``, you'll be able to replace it with ``dataframe.vgplot`` and instead get a similar (but not identical) visualization output in Vega or Vega-Lite:

```python
import pdvega  # import adds vgplot attribute to pandas

df.vgplot.scatter(x='x', y='y')
```

![vega-lite scatter output](images/vg-scatter.png?raw=true)

Currently only a small part of the pandas plotting API is covered; see the [example notebook](notebooks/pdvega_example.ipynb) for a few working examples.

## Relationship to Altair

[Altair](http://altair-viz.github.io) is a project that seeks to design an intuitive declarative API for generating Vega-Lite and Vega visualizations, using Pandas dataframes as data sources.

By contrast, ``pdvega`` seeks not to design new visualization APIs, but to use the existing ``DataFrame.plot`` [visualization api](https://pandas.pydata.org/pandas-docs/stable/visualization.html) and output visualizations with Vega/Vega-Lite rather than with matplotlib.

In this respect, ``pdvega`` is quite similar in spirit to the now-defunct [mpld3](http://mpld3.github.io) project, though the scope is smaller and (hopefully) **much** more manageable.
