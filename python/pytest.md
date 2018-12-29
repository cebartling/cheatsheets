# pytest


## pytest-mock

- [GitHub](https://github.com/pytest-dev/pytest-mock/)
- This plugin installs a `mocker` fixture into your pytests. 
- The `mocker` fixture is a thin-wrapper around the patching API provided by the [`mock` package](https://docs.python.org/dev/library/unittest.mock.html), 
but with the benefit of not having to worry about undoing patches at the end of a test.

### `assert_called_with`

- [Reference](https://docs.python.org/3/library/unittest.mock.html#unittest.mock.Mock.assert_called_with)

```python
method_patch = mocker.patch('collaborator.do_something')
system_under_test('foobar', another_arg='barfoo')
method_patch.assert_called_with('foobar')
```

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