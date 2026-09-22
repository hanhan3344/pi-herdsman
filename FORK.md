# hanhan3344 distribution

Based on upstream pi-herdsman 0.12.1, commit
58ea85b981f400c43d35812dac6fbf69afbb61a3. Apache-2.0 license retained.

## 0.12.1-hanhan.1

- Retry harmless startup readiness probes after a structured output timeout,
  bounded to six attempts and gated by foreground shell ownership. This handles
  login shells discarding typeahead. Task submission is never retried here.
- Include the built dist for pinned Pi Git installations.
- Support Sakura child UI through existing role `extensions` overrides. Keep
  `noExtensions: true`, and explicitly include the installed Sakura package's
  five extension entrypoints (header, matrix, zentui, dual-quota, claude-shimmer).
  The deployment resolves absolute paths on each host; no machine paths or
  private environment configuration are embedded in this repository.

Use an immutable commit with `pi install git:github.com/hanhan3344/pi-herdsman@SHA`.
Existing sessions keep their loaded version until safely reloaded. Do not reload
an active owner with working children solely to change their appearance.
