# Software Development Policies

## Python
- All Python projects shall use the [psf "black" code formatter](https://github.com/psf/black) or the [ruff linter](https://docs.astral.sh/ruff/) and the [mypy type checker](https://github.com/python/mypy).
    - All linting and type checking shall be performed in pre-commit hooks and GitHub Actions.
    - Badges shall be added to the project's README file for linting and type checking. 
- All Python projects shall use [pre-commit hooks](https://pre-commit.com/) for linting, type checking, and formatting.
    - Formatting shall be done in pre-commit hooks so that linting and type checking are done on formatted code and the git history is clean.
- All Python projects shall have unittests that execute automatically on pull requests to pre-production and main branches
- All Python projects shall follow this [style guide](python_style_guide.md).
- Follow the [Zen of Python](https://en.wikipedia.org/wiki/Zen_of_Python).
- All Python classes and functions shall have type hints and doc strings, no matter how trivial (e.g. a function doesn't return anything: `def f(...) -> None:`)

## API
- All endpoints shall use `kebab-case`.
- All fields in responses shall use `snake_case`.

## Web Development
- Web applications shall be built using React.
- Web applications should be built using a React metaframework; Refine.dev is preferred.
- Web applications shall use MaterialUI or PrimeReact as a UI component library.
- Web applications shall be bundled using Vite.

## Database
- PostgreSQL shall be used for all projects.
    - Extensions, such as PostGIS and TimescaleDB, may be used in conjunction with PostgreSQL.
- Databases shall be maintained such that they are never using an EOL version.

## Git & Collaboration
- Git commits shall follow [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) standards.
- All default branches shall be named `main`.
- All base development branches shall be named `pre-production`.
    - All users shall base their development branches off of `pre-production`.
    - When ready, a pull request shall be opened from a user's development branch into `pre-production`. After mergeing with `pre-production`, all project participants shall pull the latest `pre-production` updates to their local environments, merge those changes to their development branches, and resolve merge conflicts.
- All tests must pass before a development branch can be merged with `pre-production`.
- All merge conflicts must be resolved before a development branch can be merged with `pre-production`.
