# pytest


## Plugins

### `@pytest.mark.only`

- [Pytest plugin](https://github.com/theY4Kman/pytest-only)
- Only run tests marked with `@pytest.mark.only`. 
- If none are marked, all tests run as usual.

```python
import pytest

def test_that_will_not_run():
    assert 0

@pytest.mark.only
def test_that_will_run():
    assert 1
```