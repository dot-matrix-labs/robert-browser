# Standalone Webdriver Extraction Plan

> **Status:** ✅ COMPLETED
>
> This plan has been fully implemented. The `robert-webdriver` crate is now maintained in a separate repository:
> [`dot-matrix-labs/robert-webdriver`](https://github.com/dot-matrix-labs/robert-webdriver)

## Summary

The `robert-webdriver` crate has been extracted from this repository and is now maintained independently. This allows for:
- Separate release cycles for the CDP library
- Focused development on browser automation
- Clear separation of concerns

## Related Documentation

- **robert-webdriver repository**: [`dot-matrix-labs/robert-webdriver`](https://github.com/dot-matrix-labs/robert-webdriver)
- ADR: `adr-standalone-webdriver.md`


## Verification Plan

### Automated Tests
*   **Unit Tests**: Ensure `robert-webdriver` handlers are unit tested.
*   **Integration**:
    1.  Start `cargo run -p robert-webdriver`.
    2.  Run `curl http://localhost:<PORT>/health`.
    3.  Run `cargo run -p robert-app`.
    4.  Verify `robert-app` detects the running server.

### Manual Verification
1.  **Scenario A: Server Running**
    *   Start `robert-webdriver`.
    *   Open `robert-app`.
    *   Check Developer/Debug section -> Webdriver features should be **visible**.
    *   Send a request -> Should verify it hits the webdriver server logs.
2.  **Scenario B: Server Stopped**
    *   Stop `robert-webdriver`.
    *   Restart `robert-app` (or wait for polling).
    *   Check Developer/Debug section -> Webdriver features should be **hidden**.
