---
agent: agent
description: Automatically add or update Google-style Python docstrings across target files.
---
# Automated Docstring Task

Review the target Python file(s) or folder and add missing docstrings or update outdated ones.

## Rules

1. Follow all formatting, section, and tone rules defined in `python-docstrings.instructions.md`.
2. Add docstrings to all public modules, classes, methods, and functions that lack them.
3. Update existing docstrings if parameter names, return values, or raised exceptions no longer match the implementation.
4. **Do not** alter any executable code, type hints, or imports—only insert or update docstrings.
5. After editing, review your changes to verify valid Python syntax and proper indentation.
6. **Always** ask for clarification when unsure.
