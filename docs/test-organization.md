# Test Suite Organization

> **Note:** The `robert-webdriver` test suite is located in the separate repository:
> [`dot-matrix-labs/robert-webdriver`](https://github.com/dot-matrix-labs/robert-webdriver)
>
> This document describes the test organization for the `robert-webdriver` library.

## Test Categories

The `robert-webdriver` test suite includes:

- **Meta/Infrastructure Tests** - Testing infrastructure verification
- **Validation Tests** - CDP JSON schema validation
- **E2E Tests** - End-to-end Chrome automation
- **Headless Integration Tests** - Headless browser testing
- **Chat UI Tests** - Chat interface testing
- **CDP API Tests** - Chrome DevTools Protocol testing

## Running Tests

All `robert-webdriver` tests are run from the separate repository:

```bash
# Clone the webdriver repository
git clone https://github.com/dot-matrix-labs/robert-webdriver
cd robert-webdriver

# Run tests
cargo test --package robert-webdriver
```

## Test Organization in This Repository

This repository (`robert-browser`) contains:
- `robert-app` - Tauri desktop application
- `robert-cli` - Command-line interface
- `robert-core` - Core automation logic
- `robert-server` - Server for remote execution

Each crate has its own tests, accessible via:
```bash
cargo test -p robert-app
cargo test -p robert-cli
cargo test -p robert-core
cargo test -p robert-server
```

## Related Documentation

- **CDP/WebDriver tests**: [`dot-matrix-labs/robert-webdriver`](https://github.com/dot-matrix-labs/robert-webdriver)
- Build instructions: `build-instructions.md`
- Linux setup: `linux-setup.md`
