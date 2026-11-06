# BackToWin — Automatic Windows Reinstall with a Safety Net

**Reinstall Windows automatically. If anything fails, it rolls itself back.**

BackToWin reinstalls Windows 10/11 end-to-end from **official Microsoft images** — including the Windows 11 → Windows 10 downgrade Microsoft does not offer. On failure, the system returns to its pre-install state automatically.

- 🏠 Homepage & docs: <https://backtowin.net>
- 🤖 AI agents: [backtowin-mcp](https://github.com/weib321/backtowin-mcp) — run the whole flow from your agent

## How it works

1. **Check the machine** — a read-only profile of the PC: Windows version, firmware (UEFI/BIOS), disk encryption status. Windows 11 machines are eligible for the downgrade path.
2. **Back up files** — the plan includes a backup checklist before anything destructive happens. Rollback protects the system; a backup protects files chosen for deletion.
3. **Reinstall, unattended** — official Microsoft images are checked against official hash records — and the tool **refuses to proceed when no hash is on record**. On failure it rolls the system back automatically.

> **Why this exists:** an unverified reinstall is a point of no return. If a reinstall fails mid-way on an unprepared machine, the machine may not boot; recovery then requires physical media and a second device. BackToWin is built around that failure mode: verified official images, a rehearsed install recipe, and automatic rollback when a run fails.

## Download

Windows builds (EN / DE / FR): **[GitHub Releases](https://github.com/weib321/backtowin/releases/latest)**
Every release publishes the executable's md5 fingerprint, checked against the tool's version whitelist before shipping.

## For AI agents (MCP)

[backtowin-mcp](https://github.com/weib321/backtowin-mcp) exposes the flow as 8 MCP tools — machine assessment, quote, pre-check, install plan, official-image guidance, image verification, activation, follow-up.

```json
{
  "mcpServers": {
    "BackToWin": {
      "command": "python",
      "args": ["C:\\BackToWin\\backtowin-mcp\\server.py"],
      "env": { "ONEBOOT_CLOUD_URL": "https://backtowin.net" }
    }
  }
}
```

## Pricing

- **Free trial** — 1 reinstall
- **$6.9** — single reinstall
- **$9.9** — 3 reinstalls
- If a code doesn't work: full refund by email.

## Public pilot

BackToWin is in public pilot. Verified install statistics are published as they accumulate at [backtowin.net](https://backtowin.net); until an install record is archived, the number honestly reads **Pending**. No invented figures, ever.

## Scope

BackToWin promises one thing: your machine **boots and reaches the internet — both ways**. Nothing more, nothing less.

## License

MIT — see [LICENSE](LICENSE).

## Credits

- [Fido](https://github.com/pbatard/Fido) (GPL-3.0-or-later) — bundled for official Windows image link resolution; its license text ships with the tool.

