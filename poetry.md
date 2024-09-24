# Installing Poetry and Managing Project Dependencies

[Poetry](https://python-poetry.org/) is a powerful dependency management and packaging tool for Python projects. It simplifies the process of building, publishing, and maintaining Python packages by handling dependencies and virtual environments automatically.

This guide will walk you through installing Poetry on different operating systems (Windows, macOS, and Linux) and using it to install project dependencies.

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Installing Poetry](#installing-poetry)
  - [Windows](#windows)
  - [macOS](#macos)
  - [Linux](#linux)
- [Setting Up a Project with Poetry](#setting-up-a-project-with-poetry)
- [Installing Project Dependencies](#installing-project-dependencies)
- [Additional Commands](#additional-commands)
- [Troubleshooting](#troubleshooting)
- [Resources](#resources)

---

## Prerequisites

- **Python 3.7 or higher**: Ensure you have Python installed. You can verify your Python version by running:

  ```bash
  python --version
  ```

- **Terminal Access**: You'll need to use a command-line interface (Terminal on macOS/Linux or Command Prompt/PowerShell on Windows).

---

## Installing Poetry

Poetry provides a custom installation script that works across different operating systems.

### Windows

1. **Open PowerShell**:

   - Press `Win + X` and select **Windows PowerShell** or **Windows Terminal**.

2. **Run the Installation Script**:

   ```powershell
   (Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | python -
   ```

3. **Configure Environment Variables**:

   After installation, you may need to add Poetry to your `PATH`. Add the following to your environment variables:

   ```
   %USERPROFILE%\AppData\Roaming\Python\Scripts
   ```

4. **Verify Installation**:

   Close and reopen your terminal, then run:

   ```powershell
   poetry --version
   ```

### macOS

1. **Open Terminal**:

   - Use Spotlight (`Cmd + Space`) and type **Terminal**.

2. **Run the Installation Script**:

   ```bash
   curl -sSL https://install.python-poetry.org | python3 -
   ```

3. **Configure Environment Variables**:

   Ensure Poetry is in your `PATH`. Add the following to your shell configuration file (`~/.bash_profile`, `~/.zshrc`, etc.):

   ```bash
   export PATH="$HOME/.local/bin:$PATH"
   ```

4. **Verify Installation**:

   Restart your terminal or source your profile:

   ```bash
   source ~/.zshrc  # or ~/.bash_profile
   poetry --version
   ```

### Linux

1. **Open Terminal**.

2. **Run the Installation Script**:

   ```bash
   curl -sSL https://install.python-poetry.org | python3 -
   ```

3. **Configure Environment Variables**:

   Add Poetry to your `PATH` by appending the following to `~/.bashrc` or `~/.zshrc`:

   ```bash
   export PATH="$HOME/.local/bin:$PATH"
   ```

4. **Verify Installation**:

   Reload your shell configuration:

   ```bash
   source ~/.bashrc  # or ~/.zshrc
   poetry --version
   ```

---

## Setting Up a Project with Poetry

Navigate to your project directory or create a new one:

```bash
mkdir my-project
cd my-project
```

Initialize a new Poetry project:

```bash
poetry init
```

Follow the interactive prompts to set up your `pyproject.toml` file, which manages your project metadata and dependencies.

---

## Installing Project Dependencies

If your project already has a `pyproject.toml` file with listed dependencies, you can install them using:

```bash
poetry install
```

This command will:

- Create a virtual environment for your project (if one doesn't exist).
- Install all dependencies specified in `pyproject.toml`.

### Adding Dependencies

To add a new dependency:

```bash
poetry add package-name
```

For a specific version:

```bash
poetry add package-name@^1.2.3
```

---

## Additional Commands

- **Activate the Virtual Environment**:

  ```bash
  poetry shell
  ```

- **Run a Command Inside the Virtual Environment**:

  ```bash
  poetry run python script.py
  ```

- **Update Dependencies**:

  ```bash
  poetry update
  ```

- **List Installed Packages**:

  ```bash
  poetry show --tree
  ```

---

## Troubleshooting

- **Poetry Not Found**: Ensure that Poetry's install location is in your `PATH`.

- **Permission Errors**: Use `python3` instead of `python` if multiple Python versions are installed.

- **Virtual Environment Issues**: Delete the existing virtual environment with `poetry env remove python` and reinstall dependencies.

---

## Resources

- [Official Poetry Documentation](https://python-poetry.org/docs/)
- [PyPI - The Python Package Index](https://pypi.org/)
- [Python Virtual Environments](https://docs.python.org/3/tutorial/venv.html)

---

By following this guide, you should have Poetry installed on your system and be able to manage your project's dependencies effortlessly.