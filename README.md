# ClickClack console proof artifacts

Evidence images referenced from OpenClaw pull requests. Each directory holds the artifacts for one PR.

## pr-193951 — `gateway-console-vs-file-log.png`

`extensions/clickclack/src/inbound.ts`: ClickClack inbound warnings move from the plugin child logger
(file only) to the console-capable subsystem logger.

The image lays out the captured output of two isolated `gateway run` processes side by side:

- **before** — `inbound.ts` restored to `origin/main` (byte-identical to main's file)
- **after** — the PR head

Both runs received the same ClickClack realtime event from a local ClickClack-protocol peer, re-fetched
the message, and called a local OpenAI-compatible model endpoint that returned empty assistant content.
Text in the image is the captured output of those runs (stderr stream, log file records, ClickClack peer
and model peer request logs), not retyped. Hostname is redacted; token, ports and message id are local
fixtures.
