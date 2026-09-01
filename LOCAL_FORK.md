# Local Claude-Mem Fork

This repository is a local source snapshot of Claude-Mem 13.21.2 based on
upstream commit `8f085b4f`.

The local patch makes an explicit `--provider claude`, `--provider openrouter`,
or `--provider gemini` selection bypass CMEM account OAuth. Omitting
`--provider` keeps the upstream interactive CMEM account flow.

The existing DeepSeek setup uses the Claude-compatible gateway path:

```bash
npx claude-mem install --provider claude
```

Choose API key/gateway and retain the existing DeepSeek gateway settings when
prompted. Credentials and runtime memory remain outside this repository under
`~/.claude-mem/` and are not copied here.

The complete prebuilt Claude Code plugin is preserved under `plugin/`, including
its manifest, lifecycle hooks, worker and MCP bundles, UI, modes, and skills.
This fallback is not installed or activated automatically.
