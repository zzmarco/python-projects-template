---
applyTo: "**/*.py"
---
# Python Docstring Guidelines

When generating or updating Python docstrings (including via `/doc`), strictly follow the **Google Python Style Guide**:

- **Format:** Use triple double-quotes (`"""`) and Google-style sections (`Args:`, `Returns:`, `Raises:`, `Yields:`).
- **Summary line:** Start with a concise, one-line summary in the imperative mood (e.g., "Calculate the total...", not "Calculates..."), ending with a period.
- **Type annotations:** Repeat parameter and return types inside the docstring.
- **Sections:**
  - `Args:` List each parameter name followed by `(<type>)`, a colon and description. Omit `self` and `cls`.
  - `Returns:` Describe the return value and its type. Omit this section for functions returning `None`.
  - `Raises:` List exceptions that the function explicitly raises and the conditions under which they occur.
- **Private helpers:** Keep docstrings for private functions (`_helper`) brief (a single summary line) unless complex logic requires `Args:` or `Returns:`.

## Reference Example

```python
def fetch_user_orders(user_id: int, include_archived: bool = False) -> list[dict]:
    """Retrieve order records associated with a specific user.

    Queries the order repository and filters results based on archival status.

    Args:
        user_id (int): The unique identifier of the user.
        include_archived (bool): Whether to include archived orders in the output.
            Defaults to False.

    Returns:
        list[dict]: A list of dictionaries representing the user's orders.

    Raises:
        ValueError: If `user_id` is less than or equal to zero.
    """
```
