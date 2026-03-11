## Failure Containment Engineering

I assume systems will fail.  
My job is making sure they fail safely.

Engineer studying how complex systems break — and ensuring they fail safely.

Most systems do not fail because of missing features.  
They fail because of hidden assumptions.

My work focuses on exposing those assumptions and enforcing structural guarantees so failures remain predictable and contained.

Core method:

- make invariants explicit
- detect ambiguous state transitions
- enforce fail-fast guarantees
- define clear recovery boundaries

---

## Selected Infrastructure Investigations

<details>
<summary>NEAR MPC — Threshold Cryptography Infrastructure</summary>

Discovered identity-binding ambiguity during protocol startup.

Without strict participant ↔ TLS key binding, peer attribution can become ambiguous across nodes, weakening protocol safety assumptions.

https://github.com/near/mpc/issues/2250

</details>

<details>
<summary>Ironclaw — AI Agent Orchestration</summary>

Identified credential lifecycle mismatch during plugin removal.

Credential mappings could remain active after plugin uninstall, creating permission-state inconsistencies.

https://github.com/nearai/ironclaw/issues/358

</details>

<details>
<summary>Model Context Protocol — AI Tooling Infrastructure</summary>

Improved robustness of server request handling under malformed or unexpected input flows.

Focused on eliminating undefined behavior at protocol boundaries.

https://github.com/modelcontextprotocol/servers/pull/3505

</details>

---

## Engineering Principles

Systems rarely fail where designers expect.

Failures usually emerge from:

- implicit assumptions
- inconsistent state transitions
- edge conditions under load
- adversarial or unexpected inputs

I design systems assuming failure will happen —  
and enforce guarantees so they degrade safely instead of catastrophically.

---

## Field Notes

[failure-notes](https://github.com/failuresmith/failure-notes) → real-world failure investigations  
[failure-lab](https://github.com/failuresmith/failure-lab) → deterministic failure experiments
