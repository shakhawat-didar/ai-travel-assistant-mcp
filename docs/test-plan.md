# Test Plan

Use a test spreadsheet and non-sensitive demo user IDs.

| Test | Input / setup | Expected behavior |
|---|---|---|
| Weather lookup | Known valid latitude/longitude | Current weather fields returned and summarized accurately |
| Place search | Specific location and category | Results are relevant to query; empty/error results are disclosed |
| Exchange rates | Tool still disabled | Agent must not claim it checked live rates |
| Preference retrieval | Existing `user_id` row | Saved preference fields are returned |
| Preference save | New user preference | A row is added with all supported fields |
| Preference update | Existing user changes budget | Existing row is updated once `user_id` matching is configured |
| Missing user_id | User asks for a plan without ID | Agent uses general preferences and does not invent stored history |
| Memory session | Several turns with same sessionId | Short-window context is retained as expected |
| MCP unavailable | Stop server or use invalid test endpoint | Agent responds gracefully and does not fabricate tool results |
| Invalid Maps key | Use a restricted/invalid test key | Error is handled; no false claim that places were found |
| Invalid coordinates | Malformed latitude/longitude | Tool failure is handled gracefully |
| Privacy | Request to save sensitive data | Only intended travel preferences are stored; avoid unnecessary sensitive data |

## Execution log

Record test ID, inputs, tool invoked, source result, final response correctness, preference store result, execution status, and follow-up fixes. Do not report metrics until a representative test set is complete.
