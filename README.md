# Sparv – Språkbanken's Analysis Platform

Sparv is a text analysis tool run from the command line. The documentation can be found here:
<https://spraakbanken.gu.se/sparv>.

Check the [changelog](CHANGELOG.md) to see what's new!

Sparv is developed by [Språkbanken](https://spraakbanken.gu.se/). The source code is available under the [MIT
license](https://opensource.org/licenses/MIT).

If you have any questions, problems or suggestions please contact <sb-sparv@svenska.gu.se>.

## Prerequisites

* A Unix-like environment (e.g. Linux, OS X or [Windows Subsystem for
  Linux](https://docs.microsoft.com/en-us/windows/wsl/about)) *Note:* Most of Sparv's features should work in a Windows
  environment as well, but since we don't do any testing on Windows we cannot guarantee anything.
* [Python 3.11](https://python.org/) or newer.

## Installation

Sparv is available on [PyPI](https://pypi.org/project/sparv/) under the name `sparv`. Refer to the [Sparv user
manual](https://spraakbanken.gu.se/sparv/user-manual/installation-and-setup/) for detailed installation and setup
instructions.

## Development

To set up a development environment for Sparv, we recommend using [uv](https://docs.astral.sh/uv/) to create a
virtual environment and install the dependencies.

1. Install [uv](https://docs.astral.sh/uv/getting-started/installation/) if you don't have it already.
2. While in the Sparv project directory, run:

   ```sh
   uv sync
   ```

   This will create a virtual environment in the `.venv` directory and install the dependencies listed in
   `pyproject.toml`, including the development dependencies.
3. Either activate the virtual environment manually:

   ```sh
   source .venv/bin/activate
   ```

   or use `uv run <command>` to run commands inside the virtual environment without activating it.

Alternatively, you can set up a virtual environment manually using Python's built-in `venv` module and install the
dependencies using pip:

```sh
python3 -m venv .venv
source .venv/bin/activate
pip install -e . && pip install . --group dev
```

### Running tests

To run the test suite, make sure you have set up the development environment as described above. You also need to have
[Git LFS](https://git-lfs.github.com/) installed to get the test data. If you cloned the repository before installing
Git LFS, you need to run

```sh
git lfs fetch
```

to download the test data files.

While in the Sparv project directory, you can run the tests using uv:

```sh
uv run pytest
```

Alternatively, if you have activated the virtual environment manually, you can simply run:

```sh
pytest
```

You can run specific tests using the provided markers (e.g. `pytest -m swe` to run the Swedish tests only) or via
substring matching (e.g. `pytest -k "not slow"` to skip the slow tests).
