## Failure Containment Engineering

Systems will fail.  
Engineering decides how.

I build systems that remain predictable when assumptions break.

Most outages do not come from missing features.  
They come from hidden assumptions.

My work focuses on exposing those assumptions early and enforcing structural guarantees so faults remain contained and recovery is clear.

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

## Field Notes

[failure-notes](https://github.com/failuresmith/failure-notes) → investigations into real-world failure modes  
[failure-lab](https://github.com/failuresmith/failure-lab) → deterministic experiments for discovering system weaknesses
