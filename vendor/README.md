# vendor/

This directory is the conventional place to drop a local specpy wheel before
installing it.  **No wheel file is committed to this repository.**

---

## specpy — Abberior Instruments' Python SDK

specpy is a **proprietary, closed-source** library distributed by Abberior
Instruments GmbH as part of the Imspector acquisition software.  It is **not
on PyPI** and may not be redistributed.

### Why it is needed

specpy is required only for opening `.msr` raw acquisition files
(`File → Open .msr file…` or drag-and-drop).  All other viewer functionality
(`.mat`, `.npy`, `.csv`, `.json`, filter, scatter, histogram, render…) works
without it.

### Where to find your wheel

Imspector ships a version-matched wheel for each installed Python × NumPy
combination.  On the Windows PC that runs Imspector, look in:

```
C:\Imspector\Versions\<your-imspector-version>\python\specpy\
```

Inside you will find one subfolder per Python × NumPy combination, each
containing a `.whl` file, for example:

```
SpecPy-Python3.12-NumPy2.0.0\
    specpy-1.2.3-cp312-cp312-win_amd64.whl
```

Pick the subfolder that matches your Python version (`cp312` = Python 3.12,
`cp311` = Python 3.11, …) and your installed NumPy major version.

### Version compatibility

| specpy build tag | Python | NumPy   |
|------------------|--------|---------|
| `cp312-cp312`    | 3.12.x | ≥ 2.0   |
| `cp311-cp311`    | 3.11.x | 1.x     |
| *(others)*       | …      | …       |

If you are unsure, run:
```powershell
poetry run python --version
poetry run python -c "import numpy; print(numpy.__version__)"
```

### Installation

Copy the correct `.whl` file into this `vendor/` directory, then run:

```powershell
poetry run pip install vendor\<wheel-filename>.whl
```

Or install directly from the Imspector path without copying:

```powershell
poetry run pip install "C:\Imspector\Versions\<ver>\python\specpy\SpecPy-Python3.12-NumPy2.0.0\specpy-1.2.3-cp312-cp312-win_amd64.whl"
```

See `INSTALL_MSR.md` in the project root for full instructions and
troubleshooting.
