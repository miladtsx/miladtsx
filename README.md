## Failure Containment Engineering

**Systems will fail.**  
Engineering decides how.

---

I build systems that remain predictable  
when assumptions break.

---

Most outages do not come from missing features.  
They come from **hidden assumptions**.

---

My work focuses on exposing those assumptions early  
and enforcing structural guarantees so faults remain contained and recovery is clear.

---

### Method

• make invariants explicit  
• detect ambiguous state transitions  
• enforce fail-fast guarantees  
• define clear recovery boundaries

---

## Selected Infrastructure Investigations

<details>
<summary>NEAR MPC — Threshold Cryptography Infrastructure</summary>

Peer identity depended on implicit TLS ↔ participant binding.

Without explicit enforcement, node attribution could become ambiguous across the protocol network.  
[near/mpc#2250](https://github.com/near/mpc/issues/2250)

</details>

<details>
<summary>Ironclaw — AI Agent Orchestration</summary>

Plugin removal did not revoke associated credential authority.

Credential mappings could remain active after uninstall,
leaving permissions inconsistent with runtime state.

[nearai/ironclaw#358](https://github.com/nearai/ironclaw/issues/358)

</details>

<details>
<summary>Model Context Protocol — Filesystem MCP Server</summary>

Read-only mode relied on client hints rather than server enforcement.

Filesystem write tools remained callable despite read-only intent.

[modelcontextprotocol/servers#3505](https://github.com/modelcontextprotocol/servers/pull/3505)

</details>

---

## Field Notes

[failure-patterns](https://github.com/failuresmith/failure-patterns) → real-world investigations  
[failure-lab](https://github.com/failuresmith/failure-lab) → controlled experiments
