mypy mirror
===========

Mirror of mypy for pre-commit.

For pre-commit: see https://github.com/pre-commit/pre-commit
For mypy: see https://github.com/python/mypy

### Using mypy with pre-commit:

Add this to your `.pre-commit-config.yaml`

```yaml
-   repo: https://github.com/pre-commit/mirrors-mypy
    rev: ''  # Use the sha / tag you want to point at
    hooks:
    -   id: mypy
```


By default, mypy will run with `mypy --ignore-missing-imports`, `pre-commit`
runs `mypy` from an isolated virtualenv so it won't have access to those.
To change the arguments, override the `args` as follows:

```yaml
    hooks:
    -   id: mypy
        args: [--no-strict-optional, --ignore-missing-imports]
```