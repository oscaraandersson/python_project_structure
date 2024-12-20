# Python project structure template

## Setup project

  ```
  python3 -m venv .venv
  source .venv/bin/activate
  pip install -e .[dev]
  ```

## Zed configuration
  Zed will automatically configure pyright and ruff and use the configuration
  from `pyproject.toml` file. If you to automatically use ruff to format or fix
  imports, use the following settings in zed.

  ```
  "languages": {
    "Python": {
      "language_servers": ["pyright", "ruff"],
      "format_on_save": "off",
      "formatter": [
        {
          "code_actions": {
            "source.organizeImports.ruff": true,
            "source.fixAll.ruff": true
          }
        },
        {
          "language_server": {
            "name": "ruff"
          }
        }
      ]
    }
  }
  ```

  Format on save is set to false. You can format the document directly in zed
  from the command palette.
