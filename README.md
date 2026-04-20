# AgentsProtocol

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19642292.svg)](https://doi.org/10.5281/zenodo.19642292)
![Bitcoin Block](https://img.shields.io/badge/Bitcoin_Block-945622-orange)
![License](https://img.shields.io/badge/license-Apache--2.0-blue)
![CI](https://github.com/fatdinhero/agentsprotocol/actions/workflows/ci.yml/badge.svg)

> **MCP/A2A connect systems. AgentsProtocol proves the content is true.**

An open protocol and reference client for decentralised **semantic**
validation: every claim is scored against a public knowledge corpus, every
block is additionally gated by a statistical non-collusion test Psi, and
only blocks that clear both thresholds enter the canonical DAG.

## Four Research Pillars

| Layer     | Contribution                                   | Reference                                |
|-----------|------------------------------------------------|------------------------------------------|
| MBT       | Statistical certificate of validator independence (Psi) | Meta-Bell Theory (Dinc, 2026)      |
| PoWW      | Composite truth score T x C x R x E over information units | Proof of WiseWork v2 (Dinc, 2026)  |
| PoISV     | Operational protocol: S_con + Psi + GHOSTDAG ordering     | PoISV Whitepaper v1.0 (Dinc, 2026) |
| Bell-SPVU | Formal Proof of MetaBell Operator — Ψ ≈ 1 − \|Ŝ\|/(2√2) | [Bell-SPVU Paper (Dinc, 2026)](https://doi.org/10.5281/zenodo.19656679) |

## Quick Start

```bash
pip install agentsprotocol
```

```python
from agentsprotocol import compute_s_con, compute_psi, check_acceptance

s = compute_s_con("The sky is blue.", ["The sky is blue."], tau=0.7)
psi = compute_psi([[0.1, 0.2, 0.3, 0.4], [0.3, 0.2, 0.1, 0.4]])
print(check_acceptance([s], psi, theta_min=0.6, psi_min=0.3))
```

Full end-to-end demo: `examples/demo.py`.

## Repository Structure

```
agentsprotocol/
  src/agentsprotocol/       Python reference implementation
  src/validator/            Rust validator skeleton (tokio + libp2p + zkVM)
  schema/                   JSON schemas (claim-v1.0, control-set-v1)
  examples/                 Runnable demos + example claim + control set
  tests/                    pytest suite (62 tests, all green)
  docs/                     architecture.md, api.md, math.md
  .github/workflows/        CI (pytest + flake8 + cargo check)
```

## Roadmap

| Phase | Scope                                                              | Status        |
|-------|--------------------------------------------------------------------|---------------|
| 1     | Claim parser, S_con library, Psi-test, JSON-schema tests           | Reference code shipped |
| 2     | GHOSTDAG consensus engine, synthetic Psi simulations               | Skeleton      |
| 3     | Local testnet (no zkVM), then zkVM integration (Nexus / RISC Zero) | Planned       |
| 4     | Full consensus, security audit, testnet launch                      | Planned       |

## Citation

```bibtex
@software{dinc_agentsprotocol_2026,
  author       = {Fatih Dinc},
  title        = {AgentsProtocol: Reference Implementation},
  year         = 2026,
  publisher    = {Zenodo},
  version      = {1.0.0},
  doi          = {10.5281/zenodo.19642292},
  url          = {https://github.com/fatdinhero/agentsprotocol}
}
```

## License

Code: Apache-2.0 (`LICENSE-CODE`). Documentation: CC BY 4.0 (`LICENSE-DOCS`).

## Timestamp

All contents of this repository (source and docs) are included in the
SHA-256 hash attested on **Bitcoin block 945622 (2026-04-18)**.

---

**Author:** Fatih Dinc — `fatdinhero@gmail.com` — Pforzheim, Germany.
