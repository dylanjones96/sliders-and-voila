# Using Voilà to render interactive slider plots 

## Notes on implementation
- This repository was copied from https://github.com/binder-examples/voila. Changes have been made. The index.ipynb notebook was used as a template. 
- Currently, every time a slider value is changed the instance of the figure window is cleared, a new figure is created, then the new bands are drawn. It would probaly be more efficient to link the update function to the lines belonging to the figure object, but I couldn't get that to work (although honestly I didn't try that hard). 
- Also, Matplotlib is used to draw the figures. The main drawback here is that Matplotlib figures are not types of ipython widgets. Instead, the matplotlib figure object is embedded within a widgets Box. I _think_ this can make integration with other ipython widgets tricky, especially when it comes to scaling/resizing. There exist potential alternatives that seem to have higher resolution and look 'cleaner'. These are
   - bqplot: the figure objects in this library are themselves widgets and would be the optimal choice, but it seems (to me at least) that one can't write maths symbols or provide a list of custom tick labels to axes locations,
   - ipympl: using %matplotlib widget magic command to turn matplotib figure into interactive one works, but when the figure object is redrawn in the current implementation the effect is quite jarring. 


## Build a conda environment and launch jupyter-lab
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/dylanjones96/Voila-tests/HEAD)

## Render sliders-voila10.ipynb notebook outputs in a browser window using Voilà package
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/dylanjones96/Voila-tests/main?urlpath=voila%2Frender%2Findex_test8.ipynb)

## Some instructions lifted from host repository README

If you would like to use the same configuration as this repository but for another project, check out the following steps:

1. Make sure the repository is publicly available (on GitHub, Gitlab or as a [GitHub Gist](https://gist.github.com)
2. Define the dependencies in [`environment.yml`](./environment.yml). `requirements.txt` is also supported. In the dependency file, add `voila`.
3. Go to [mybinder.org](https://mybinder.org) and enter the URL of the repository.
4. In `Path to a notebook file`, select `URL` and use the Voilà endpoint: `voila/render/path/to/notebook.ipynb`
5. Click `Launch`.
6. Binder will trigger a new build if this is the first launch (or if there have been new changes since
   the last build). This might take a few minutes to complete. If an image is already available,
   the server will be able to start within a few seconds.

Here is an overview of the Binder configuration on [mybinder.org](https://mybinder.org):

![image](https://user-images.githubusercontent.com/591645/132292481-01f877c3-77f8-46ba-b265-23bd3e25f513.png)

For more details, check out the Voilà documentation on https://voila.readthedocs.io/en/latest/deploy.html#deployment-on-binder
