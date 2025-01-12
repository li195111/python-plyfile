# Information for Developers

Thanks for your interest in contributing to the project!

## Source code repository

[GitHub link](https://github.com/dranjan/python-plyfile)

## How to contribute code

The easiest and recommended way to contribute code is to follow GitHub's
usual pull request process. This will require a GitHub account.

1. Fork the repository into your own account.
2. Implement your changes on any branch.
3. Make a pull request on the main repository. The base branch should
   be `master`.

A documentation preview link will automatically be edited into the pull
request description. If you made any changes that could affect the
documentation, you can follow the link to make sure things look as they
should. You can also preview the documentation locally as described
further down.

## General information

- The implementation of the library is the single file `plyfile.py`.
- The test suite is contained in `test/test_plyfile.py`. It uses the
  `pytest` framework.
- Project metadata is managed through [PDM](https://pdm.fming.dev)
  in `pyproject.toml`.
  Developer workflow tooling is also configured there (more information
  below).

## Contribution guidelines

- Code style should follow [PEP-8](https://peps.python.org/pep-0008/).
- Best practice is for new features and bug fixes to be accompanied by
  unit tests.
- Bug fixes are welcome.
- New features are generally accepted if they are consistent with the
  design and philosophy of the project.
- However, extensions to the PLY format itself are generally not
  accepted, _unless_ they are already in widespread use in other PLY
  format libraries.

## Development environment setup

The project implements a few workflow helper commands to simplify
mundane activities like running tests, generating documentation, and
linting. These are all implemented as PDM user scripts. You can check
the `pyproject.toml` file to see exactly what they do.

### Installing PDM

This project uses PDM to manage project metadata and development
configurations. Thus, the first step is installing PDM using [any of the
listed methods](https://pdm.fming.dev/latest/#installation).
For example,

```none
pip install pdm
```

or

```none
pipx install pdm
```

### Installing dependencies

From the project root,

```none
pdm install
```

## Common actions

The PDM user scripts below are defined in the `pyproject.toml` file,
which should help you if want to know what each action exactly does.

### Running tests

#### Quick

To run the test suite on one Python interpreter and one version of
NumPy:

```none
pdm run test-quick
```

#### More comprehensive

To run the full test matrix, skipping unavailable Python versions:

```none
pdm run test-matrix
```

Test coverage will also be reported.

#### Full

To run the full test matrix:

```none
pdm run test-all
```

You must have all currently supported Python versions to run this
successfully.

### Generating documentation

```none
pdm run doc
```

Open `doc/build/index.html` in any web browser to peruse the generated
documentation.

### Running the linter

```none
pdm run lint
```

Generally speaking there should be no violations reported.
