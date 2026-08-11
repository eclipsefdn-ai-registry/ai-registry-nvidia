# AI Registry — NVIDIA (Inferred)

> **Inferred vendor repository.** This repo is maintained by the [AI Registry](https://github.com/eclipsefdn-ai-registry/ai-registry-core) project, not by NVIDIA. It pre-seeds the registry with Agent Skills published by NVIDIA at [github.com/NVIDIA/skills](https://github.com/NVIDIA/skills) and [github.com/NVIDIA/nurec-skills](https://github.com/NVIDIA/nurec-skills), plus two NVIDIA-published MCP servers already listed in the official MCP registry.
>
> *This entry is based solely on information published through NVIDIA's official public channels. NVIDIA has not endorsed, approved or validated this listing, and is not necessarily participating in the AI Registry.*

## What this repo contains

### Agent Skills

- All skills under `skills/*` in [NVIDIA/skills](https://github.com/NVIDIA/skills) — NVIDIA's own "NVIDIA-Verified" Agent Skills catalog (~330 skills at the time of writing). The repo's README states it is the *"Official, NVIDIA-verified Agent Skills for Claude Code, Codex, and other coding agents"*, sourced from individual NVIDIA product teams (cuOpt, NeMo, DeepStream, DOCA, Jetson, TAO, VSS, and more) and mirrored into this catalog daily via an automated sync pipeline. Every published skill carries a detached cryptographic signature (`skill.oms.sig`) verifiable against NVIDIA's own trust anchor certificate. This one glob covers the large majority of NVIDIA's published skills, including ones that live in per-product repos (e.g. `NVIDIA-AI-IOT/jetson-device-skills`, `NVIDIA/digital-health-skills`, `nvidia-riva/Nemotron-speech-skills`) but are re-published into this catalog once they pass NVIDIA's verification pipeline — approving those source repos separately would create duplicate entries for skills already covered here.
- All skills under `skills/*` in [NVIDIA/nurec-skills](https://github.com/NVIDIA/nurec-skills) — direct NVIDIA GitHub org repo for NVIDIA Omniverse NuRec, self-attributed in each skill's frontmatter (`metadata.author: "NVIDIA NRS <nurec-skills@nvidia.com>"`). Not mirrored into the main `NVIDIA/skills` catalog (its skill names — `nurec-index`, `ncore`, `nre`, `asset-harvester`, `nurec-fixer`, `physical-ai-datasets` — don't appear there), so it's approved as its own source.

**Considered and excluded:** scattered `SKILL.md` files found inside individual NVIDIA product repos for internal contributor tooling (e.g. `NVIDIA/TensorRT-LLM`, `NVIDIA/Megatron-LM`, `NVIDIA/warp`, `NVIDIA/OpenShell`, `NVIDIA/cuopt`) — these are engineering-internal skills for contributing to those projects rather than user-facing product skills, and are not part of NVIDIA's verified public catalog. Left out as out of scope for a conservative first pass.

### MCP Servers

Both already listed in the official MCP registry (`registry.modelcontextprotocol.io`), so each approval here is just a `serverId` + `date` — consolidation enriches name/description/version automatically:

- **`io.github.NVIDIA/elements`** — NVIDIA Elements, a UI design system and agent-tooling CLI for AI/ML, robotics, and autonomous-vehicle projects (`@nvidia-elements/cli`). Published under the `io.github.NVIDIA` MCP registry namespace, which requires GitHub-org-ownership verification for `github.com/NVIDIA` at publish time, and the linked repository (`github.com/NVIDIA/elements`) is owned directly by the NVIDIA org.
- **`com.nvidia.ngc.nsight.copilot.api/cuda-docs`** — NVIDIA CUDA Docs, a remote MCP server exposing NVIDIA CUDA documentation and code samples to coding agents. Published under the `com.nvidia.*` reverse-domain namespace, which requires proof of `nvidia.com` domain ownership at publish time.

**Considered and excluded:** several other MCP registry entries mention "NVIDIA" in their name or description (e.g. `io.github.Yarmoluk/ckg-nvidia-ai`, `io.github.david-eve-za/nvidia-nim-mcp`) but are published by unrelated third-party GitHub accounts, not NVIDIA — excluded as community projects about NVIDIA products, not NVIDIA's own servers.

### Agent Plugins

No Agent Plugin approval is included: no [agent-plugins.org](https://agent-plugins.org)-conformant plugin (`plugin.json` manifest matching the spec at `agent-plugins.org/schemas/1.0.0/plugin.schema.json`) was found published by NVIDIA. NVIDIA does have its own separate plugin mechanism for the NeMo Agent Toolkit, but it predates and is unrelated to the agent-plugins.org specification, so it doesn't fit this registry's Agent Plugin artifact type.

### A2A Agents

No A2A agent approval is included: NVIDIA's NeMo Agent Toolkit has first-party support for building and connecting to Agent2Agent (A2A) protocol agents (`nvidia_nat_a2a` package, `docs/source/*/a2a-*.md`), but the concrete artifacts found under that support are toolkit examples (e.g. `examples/A2A/math_assistant_a2a`) rather than a standalone, publicly hosted NVIDIA agent with a real Agent Card — there's no genuinely deployed A2A agent to approve.

## Documentation

See the [Vendor Guide](https://github.com/eclipsefdn-ai-registry/ai-registry-core#vendor-guide) in the central repository for how vendor repos work, how to add approvals, and how validation runs.
