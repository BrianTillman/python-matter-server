# AGENTS Instructions

## Running tests
- The repository's `pyproject.toml` configures `pytest` with `addopts = "--cov"`. If the `pytest-cov` plugin is missing, test collection will fail. You can bypass this by running `pytest -c /dev/null` or by disabling the coverage plugin with `-p no:pytest_cov`.
- Many tests rely on external packages that may not be available in the execution environment. Notably, `cryptography` and the `chip` module (provided by packages such as `home-assistant-chip-clusters` or `home-assistant-chip-core`) are required. Without them, several tests fail during collection.
- The execution environment used by Codex becomes offline after setup, so any required dependencies must be installed ahead of time (for example via a setup script). If these packages are missing, only a subset of the tests will run.

## Known passing tests with minimal dependencies
- `tests/common/test_parser.py::test_dataclass_from_dict`
- `tests/common/test_parser.py::test_parse_value`
