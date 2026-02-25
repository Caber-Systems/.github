<p align="center">
  <a href="https://caber.com">
    <img src="CaberBanner.png" alt="Caber Systems" width="100%">
  </a>
</p>

<h2 align="center">Inference-Time Data Control Plane</h2>

<p align="center">
Deterministic, per-chunk policy enforcement for AI systems — before the model sees it.
</p>

<p align="center">
  <a href="https://caber.com">Website</a> ·
  <a href="https://caber.com/blogs">Blog</a> ·
  <a href="https://caber.com/request_briefing">Talk to Us</a>
</p>

---

### The Problem

AI agents assemble answers from chunks — sentences, tables, charts, byte sequences — pulled through RAG pipelines, MCP servers, and API chains. Governance has to happen at *that* granularity, at *that* moment, or it doesn't happen at all.

Existing approaches fail because they operate at the wrong time or the wrong resolution:

| Failure Mode | Root Cause |
|---|---|
| **Tenant data leaks at retrieval** | Storage isolation doesn't survive shared retrieval paths — chunks from Customer A end up in Customer B's response |
| **Stale chunks drive decisions** | Ingest-time labels don't track supersession, version status, or source changes after curation |
| **Blunt policy causes hallucination** | Document-level block/allow removes useful evidence and lets incompatible chunks through, creating gaps the model fills with noise |
| **Service credentials hide the human** | Agents query sources with service accounts — the requesting user's identity and permissions are lost by the second hop |
| **Duplicates break provenance** | The same sentence exists in 12 places with conflicting context; ingest-origin ≠ true authority |
| **Authorized ≠ relevant** | A chunk passes access control but is semantically incompatible with other chunks in the same context window |

---

### How Caber Works

Caber sits in the data path between retrieval and inference. It evaluates policy on every chunk using current context — not labels from ingest time.

```
┌─────────────┐    ┌─────────────┐    ┌──────────────────┐    ┌─────┐
│  RAG / MCP  │───▶│   Caber     │───▶│  Clean Context   │───▶│ LLM │
│  API / A2A  │    │  Control    │    │  Window          │    │     │
└─────────────┘    │  Plane      │    └──────────────────┘    └─────┘
                   │             │
                   │ Per-chunk:  │
                   │ ✓ Allow     │
                   │ ✗ Block     │
                   │ ◐ Redact    │
                   │ ↻ Replace   │
                   └──────┬──────┘
                          │
                   ┌──────▼──────┐
                   │  Context    │
                   │  Graph      │
                   └─────────────┘
```

**Five core capabilities:**

1. **Deterministic Chunk Identity** — Content-defined identification at the byte level. No probabilistic matching. The same 64-byte sequence gets the same identity regardless of where it appears.

2. **Duplicate-Aware Lineage** — When the same sentence appears in 12 sources, Caber links them all. Policy evaluates origin, ownership, freshness, and authority across the full duplicate set — not just the copy that was retrieved.

3. **Continuously Updated Context Graph** — Meaning and governance context change as documents move through workflows, versions ship, and business rules evolve. The Context Graph tracks what each chunk means and how it should be used, updated from live traffic — not a stale snapshot from ingest.

4. **Policy Evaluation Before Inference** — Each chunk is evaluated against current policy at the moment of use: freshness, authorization, conflicts, relevance, proper use. Enforcement is surgical — allow, block, redact, or replace individual chunks so the model gets clean input, not a bluntly truncated context window.

5. **On-Behalf-Of Attribution** — When Agent A calls Agent B calls a tool, Caber preserves the identity of the human whose request started the chain. Policy evaluates against that originating user, not the last service account in the chain.

---

### Architecture Highlights

- **Core algorithms in C, C++, and Rust** — chunk identification, deduplication, and graph traversal are compute-bound problems; we treat them that way
- **Deterministic, not probabilistic** — content-defined chunking and byte-level identity mean results are reproducible and auditable
- **Observes live traffic** — starts producing value from APIs, MCP, and RAG pipelines immediately; no prerequisite inventory or catalog project required
- **Context Graph builds continuously** — coverage deepens with every event; relationships between chunks compound over time
- **Protocol-native integration** — works where data actually moves: REST APIs, MCP servers, RAG retrieval, agent-to-agent calls

---

### Open Source

| Repo | What It Does |
|---|---|
| [**ComparePDFparsers**](https://github.com/Caber-Systems/ComparePDFparsers) | Benchmarks PDF parsers against HTML parsing for enterprise documents. Measured processing time, accuracy, and structural fidelity across popular parsers. ([Blog post](https://www.caber.com/blog/2e0a903d-caa2-4e93-a3a6-94636ec5ee2e)) |
| [**dream**](https://github.com/Caber-Systems/dream) | Caber DREAM — achieving consistent >90% precision for RAG LLM answer quality through deterministic context enrichment |

---

### From the Blog

- [**When What Data Looks Like Is Not What It Means**](https://www.caber.com/blog/e74c56ee-a15b-443a-be7b-3f3b82c68406) — Why semantic labels alone can't govern enterprise data
- [**How Duplicate Data Kills Your RAG**](https://www.caber.com/blog/9a7e0c13-c8f4-4917-9f2b-a777df2b50f5) — The provenance problem nobody talks about
- [**Context Graphs for Governance**](https://www.caber.com/blog/cafaa5ae-2273-4250-a293-5a0dd1e0f739) — Why governance needs continuously updated context, not static labels
- [**Why Securing MCP Servers is the Wrong Approach**](https://www.caber.com/blog/20094dd7-763a-46b8-a7da-40649737ca57) — The control point is the data flow, not the server
- [**Business Context on AI Data Won't Be Solved by Retrieval**](https://www.caber.com/blog/451348f8-0d28-4ac3-a43d-ecc47ab00cb1) — Why you need policy enforcement at inference time

---

### Building With Design Partners

We're working with engineering teams building and securing AI systems that use RAG, MCP, APIs, and agent workflows. If you're running into the problems above and want to talk architecture, [we'd value your perspective](https://caber.com/request_briefing).

<p align="center">
  <a href="https://caber.com">caber.com</a> · <a href="mailto:dev@caber.com">dev@caber.com</a> · <a href="https://linkedin.com/company/caber-systems">LinkedIn</a>
</p>

<p align="center">
  <sub>© 2026 Caber Systems, Inc.</sub>
</p>
