## Node-RED + OLA: Smart DMX Channel Update Subflow

This Node-RED subflow receives a DMX update string (e.g. `"255,,128,,,1"`) via `msg.payload` and sends an optimized update to an OLA (Open Lighting Architecture) universe.

### Features

- Retrieves the current DMX state from the OLA REST API
- Updates only the specified channels; empty values (`""`) are ignored
- Channels with values that are already set (no actual change) are not updated — similar to how traditional lighting consoles behave
- Sends a minimal and efficient update containing only the changed channels
- Useful for integrating other systems or UIs with DMX lighting via OLA
