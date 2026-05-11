# vendor/

This directory contains local Python wheels that cannot be distributed
through PyPI and must be installed manually.

## specpy-1.2.3-cp312-cp312-win_amd64.whl

**What it is:** Abberior Instruments' Python SDK for reading `.msr` and
`.obf` files produced by Imspector acquisition software.

**Why it is here:** specpy is not published on PyPI. Abberior distributes
it as a platform-specific binary bundled with Imspector. This copy was
extracted from the MINFLUX_msr_reader repository.

**Platform:** Windows 64-bit only (`win_amd64`), Python 3.12, numpy ≥ 2.0.

**Required for:** Opening `.msr` raw acquisition files via
`File → Open .msr file…` or drag-and-drop. The rest of the viewer works
without it.

### Installation

See the project-level `INSTALL_MSR.md` for the one-line install command.
Do **not** add this wheel to `[tool.poetry.dependencies]` — Poetry would
fail to resolve it on Linux/macOS.
