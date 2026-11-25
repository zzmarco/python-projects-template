# Python Projects Template

A reusable Python project template with a VS Code Dev Container and GitHub
Copilot configuration for Google-style docstrings and Conventional Commit
messages.

## Included configuration

- `.devcontainer/devcontainer.json` — builds the Python development container
  and enables the Python, Pylance, and Copilot VS Code extensions.
- `.devcontainer/Dockerfile` — uses Python 3.13 by default and installs the
  dependencies in `requirements.txt` and `requirements-dev.txt`.
- `.github/agents/docstring-writer.agent.md` — defines the Docstring Writer
  Copilot agent.
- `.github/instructions/python-docstrings.instructions.md` — applies Google
  Python Style docstring rules to `**/*.py` files.
- `.github/instructions/commit-instructions.md` — defines Conventional Commit
  1.0.0 commit message formatting.
- `.github/prompts/document-code.prompt.md` — provides a reusable prompt for
  documenting Python code.
- `.github/workflows/init-template.yml` — initializes repositories created
  from this template and removes itself after one run.
- `.gitignore` — covers common Python, virtual environment, testing, IDE,
  packaging, and notebook generated files.
- `requirements.txt` — runtime dependencies.
- `requirements-dev.txt` — development and test dependencies.

## Create a project from the template

1. On GitHub, select **Use this template** and create a new repository.
2. Grant the initialization workflow write permission under **Settings >
   Actions > General > Workflow permissions**.
3. Push or merge to the `main` branch. The initialization workflow updates the
   Dev Container name and replaces `README.md` with a minimal project README,
   then removes the workflow.

The workflow only runs for a repository generated from the template, not in
the template repository itself.

## Open the project

### VS Code Dev Container

1. Clone the repository.
2. Open the repository folder in VS Code.
3. Run **Dev Containers: Reopen in Container** from the Command Palette.

The container installs `pip` and both requirements files during image build.
Run **Dev Containers: Rebuild Container** after changing dependencies or the
Python version.

### Local Python environment

For a local setup, create and activate a virtual environment, then install the
dependency files:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
python -m pip install -r requirements-dev.txt
```

Both requirements files are currently empty because this template does not
prescribe a framework or testing package.

## Customize the Python version

Set `PYTHON_VERSION` in `.devcontainer/devcontainer.json`:

```json
"args": {
    "PYTHON_VERSION": "3.12"
}
```

The Dockerfile receives the same argument. Rebuild the container after
changing it.

## Generate docstrings

Open GitHub Copilot Chat and select the **Docstring Writer** agent, or run the
**Document Code** prompt from the prompt picker. Ask it to document a specific
file or folder, for example:

```text
Add missing Google-style docstrings to src/
```

The configured instructions apply to Python files and preserve executable code,
signatures, imports, and type hints.

## Commit messages

GitHub Copilot and contributors should use the Conventional Commits format
defined in `.github/instructions/commit-instructions.md`:

```text
<type>(<scope>): <subject>
```

For example:

```text
docs: update Python setup instructions
fix(api): prevent duplicate request submissions
```

## License

This template is licensed under the [MIT License](LICENSE).
