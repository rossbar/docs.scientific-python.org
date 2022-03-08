# docs.scientific-python.org

## Generating API docs with `papyri`

`papyri` includes example configuration files for some scientific Python
projects, including `numpy`, `scipy`, `matplotlib`, etc.

### Getting set up

```bash
git clone git@github.com:jupyter/papyri.git
cd papyri
git clone https://github.com/stsewd/tree-sitter-rst
papyri build-parser
```

Papyri grabs the API docs from the current installed version of the library.
The example configuration files seem to mostly work for the latest versions,
with the exception of scipy::

```bash
pip install numpy scipy==1.7.3 matplotlib ipython pandas scikit-image
```

### Building API docs

Using the example configuration files:

```bash
papyri gen examples/numpy.toml
papyri gen examples/scipy.toml
...
```

Once all the docs have been `gen`-ed, then ingest them:

```bash
papyri ingest ~/.papyri/data/*
```

Finally, build the html output with `render`

```bash
papyri render
```

Results will be in `~/.papyri/html` (by default)
