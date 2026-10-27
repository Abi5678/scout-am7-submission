# GauntletScout — Agent Gauntlet submission (`scout-am7`)

This repository contains the packaged submission for **GauntletScout**, an entry in the NVIDIA Agent Gauntlet.

| File | Purpose |
|---|---|
| `scout-am7-submission.tar.gz` | Submission archive produced by the starter kit packager (`python -m arena_clients.package`) |
| `scout-am7-submission.tar.gz.sha256` | SHA-256 checksum of the archive |

The archive unpacks to `gauntlet-submission/`, with `submission.json` at its root. The entrypoint is
`python gauntletscout/agent.py`, and dependencies are pinned with hashes in `requirements.lock` (Python 3.12).

## Checksum

SHA-256 of `scout-am7-submission.tar.gz` (built from source commit `f2638d9`):

```
293d7ef91a05731fa596eed53859dc4ff3d0a16238cd44449975f676365ccaf4
```

## Verify

```bash
sha256sum -c scout-am7-submission.tar.gz.sha256
tar tzf scout-am7-submission.tar.gz
```

## About the agent

GauntletScout is a Python agent built on LangGraph. It discovers the arena's MCP tools at runtime, reads the
challenge, gathers evidence with the available tools, and submits one answer within the time limit. It reads
the model roster from the arena proxy at runtime, so no model names, endpoints, or credentials are baked in.
The runner supplies all configuration through `ARENA_SERVER`, `ARENA_API_KEY`, and `AGENT_ID`.

The archive contains no secrets, logs, or practice outputs.

## License

Apache License 2.0. The bundled `arena_clients/`, `base_strategy.py`, and `model_selector.py` come from the
Agent Gauntlet starter kit.
