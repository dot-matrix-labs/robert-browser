# Testing Guide

> **Note:** The `robert-webdriver` tests are located in the separate repository:
> [`dot-matrix-labs/robert-webdriver`](https://github.com/dot-matrix-labs/robert-webdriver)
>
> This document describes tests for the `robert-*` crates in this repository only.

## Quick Test Commands

### Unit Tests (robert-cli, robert-core, robert-server)
```bash
# Run all library unit tests
cargo test --lib

# Result: Tests pass in ~100ms
```

### Integration Tests
```bash
# Run integration tests
cargo test

# Result: Tests pass
```

## Test Suites

| Suite | Description | Notes |
|-------|-------------|-------|
| **Unit Tests** | Library logic tests | Always pass |
| **Integration Tests** | Full workflow tests | Varies by feature |

## Important Notes

### Running Tests

```bash
# Run all tests
cargo test --workspace

# Run linting
cargo clippy --workspace --all-targets -- -D warnings
```

## CI/CD

### GitHub Actions

Workflows automatically handle all dependencies and run tests:

```yaml
# .github/workflows/ci.yml
- name: Install system dependencies
  run: sudo bash scripts/setup-linux-dev.sh

- name: Run tests
  run: cargo test --workspace
```

All tests pass in CI! ✅

## Troubleshooting

### General Issues

If tests fail, check:
1. System dependencies are installed (see `linux-setup.md`)
2. Chrome/Chromium is available for browser tests
3. Cargo dependencies are up to date

### Browser Tests

For tests requiring Chrome, see the `robert-webdriver` repository for:
- Chrome profile conflicts
- Sandbox issues on Ubuntu 23.10+
- Chrome download and caching

## Related Documentation

- **robert-webdriver tests**: [`dot-matrix-labs/robert-webdriver`](https://github.com/dot-matrix-labs/robert-webdriver)
- Linux setup: `linux-setup.md`
- Build instructions: `build-instructions.md`
