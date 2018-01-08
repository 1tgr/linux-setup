# `nbextensions`
Nice addin for notebooks, e.g. ExecuteTime shows you the last time you ran a cell, plus how long it took.

```shell
pip install jupyter_contrib_nbextensions
jupyter contrib nbextension install --user
```
Then restart Jupyter.

Jupyter home page -> Nbextensions tab -> enable the extensions you want:
- ExecuteTime adds 'Last executed...' under each cell

# `tqdm`
Package for progress bars. Also works on the command line, special mode for notebooks.

```shell
pip install tqdm
jupyter nbextension enable --py --sys-prefix widgetsnbextension
```

```python
import time
from tqdm import tqdm_notebook as tqdm

# general case
with tqdm(total=10, desc='Doing stuff') as progress:
    for i in range(10):
        print(i)
        time.sleep(0.5)
        progress.update(1)

# shortcut when you have an iterator with a known len()
for i in tqdm(range(10), desc='Doing stuff'):
    print(i)
    time.sleep(0.5)
```

# Public access to notebooks
Start a notebook server that can be accessed over the network:
```
jupyter-notebook --ip=0.0.0.0 --NotebookApp.token= --NotebookApp.password=
```

For the token and password stuff, see http://jupyter-notebook.readthedocs.io/en/latest/security.html.
