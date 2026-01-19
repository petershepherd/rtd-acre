Threat Model & Failure Scenarios
================================

Double Sale, Oracle Failure, Registry Mismatch, Dispute Handling
---------------------------------------------------------------

Any real-world asset infrastructure must be evaluated not only by how it
functions under ideal conditions, but by how it behaves when things go wrong.
Real estate transactions involve high-value assets, multiple stakeholders, and
legal finality, making failure scenarios unavoidable considerations rather than
edge cases.

ACRE is designed with a conservative threat model that assumes:

- Human error is inevitable,
- External systems may fail or experience delays,
- Legal registries remain the final authority,
- Adversarial behavior must be expected.

This section outlines the primary risks and how ACRE mitigates them at both the
protocol and operational levels.

10.1 Double Sale Risk (On-Chain vs Off-Chain)
---------------------------------------------

Threat
~~~~~~

A property owner could theoretically attempt to sell the same property:

- Once through the ACRE platform, and
- Once outside the platform via traditional channels.

This is the most frequently cited concern in real estate tokenization models.

Mitigation Strategy
~~~~~~~~~~~~~~~~~~~

ACRE mitigates this risk through a combination of legal enforcement, registry
coupling, and execution sequencing.

1. Legal Lock Before Settlement  
   Once an on-chain offer is accepted, the property enters a legal lock state.
   The seller contractually commits not to transact elsewhere, and violations
   are legally enforceable under the governing jurisdiction.

2. Registry-Coupled Execution Flow  
   Ownership transfer and settlement are not finalized until the official land
   registry confirms the transfer or a registry-authorized oracle validates the
   update.

3. Immutable Audit Trail  
   All actions are permanently recorded on-chain, creating evidentiary proof in
   the event of disputes.

Key Principle
~~~~~~~~~~~~~

ACRE does not rely on blockchain alone to prevent double sales. It explicitly
aligns on-chain execution with off-chain legal finality.

10.2 Oracle Failure or Delay
----------------------------

Threat
~~~~~~

Oracles connect on-chain logic with off-chain reality. They may fail
temporarily, experience delays, or become unavailable due to technical or
administrative issues.

Mitigation Strategy
~~~~~~~~~~~~~~~~~~~

1. Non-Custodial Escrow Design  
   Funds and ownership tokens remain locked until oracle confirmation arrives.
   Premature settlement is impossible.

2. Multi-Source Oracle Architecture  
   Where feasible, multiple oracle inputs may be used, including registry APIs,
   licensed notary confirmations, and government-authorized data providers.

3. Fail-Safe Default Behavior  
   In the event of oracle failure, transactions pause safely. No funds are
   released and no ownership changes are finalized.

Key Principle
~~~~~~~~~~~~~

Oracle failure causes delay, not loss or corruption.

10.3 Registry Mismatch Scenarios
--------------------------------

Threat
~~~~~~

Temporary divergence may occur between on-chain records and official land
registries due to delayed updates, administrative corrections, court orders, or
clerical errors.

Mitigation Strategy
~~~~~~~~~~~~~~~~~~~

1. Registry Supremacy Rule  
   The official land registry always overrides on-chain representations.

2. Parent–Child Correction Model  
   Corrections are handled by issuing new child inscriptions that reference the
   prior record while preserving full historical traceability.

3. Versioned Property State  
   The latest valid registry-backed state is always determinable through on-chain
   history.

Key Principle
~~~~~~~~~~~~~

Immutability does not mean irreversibility. It means transparent and auditable
change history.

10.4 Dispute Handling and Legal Intervention
--------------------------------------------

Threat
~~~~~~

Disputes may arise from ownership claims, inheritance cases, fraud allegations,
or regulatory intervention.

Mitigation Strategy
~~~~~~~~~~~~~~~~~~~

1. Human-in-the-Loop Governance  
   ACRE explicitly supports court orders, registry overrides, and administrative
   corrections.

2. Dispute Flagging Mechanism  
   Properties under dispute can be temporarily frozen, excluded from settlement,
   and clearly marked within the system.

3. On-Chain Evidence for Off-Chain Courts  
   The blockchain provides timestamped records, cryptographic proofs, and full
   transaction lineage as evidentiary material.

Key Principle
~~~~~~~~~~~~~

ACRE supports the legal system; it does not attempt to replace it.

10.5 Design Philosophy
---------------------

ACRE is built on the assumption that real estate is not a purely technical
domain.

Security is achieved not by eliminating trust, but by:

- Minimizing blind trust,
- Maximizing verifiability,
- Aligning on-chain execution with legal reality.

The protocol prioritizes safety over speed, correctness over convenience, and
institutional compatibility over ideological purity.

10.6 Smart Contract Risk Mitigation
-----------------------------------

All smart contracts deployed on operational layers undergo rigorous external
security audits prior to mainnet deployment.

Audits are performed by independent security firms and focus on vulnerability
detection, logical correctness, and adversarial behavior. While no software
system can be entirely risk-free, this process significantly reduces technical
attack surfaces and aligns ACRE with institutional security expectations.

10.7 Conclusion
---------------

Failure scenarios are not weaknesses in the ACRE model; they are explicitly
anticipated design inputs.

By treating land registries as authorities, oracles as bridges rather than
judges, and blockchain as an execution and audit layer, ACRE remains stable even
when parts of the surrounding environment fail.

This approach makes ACRE suitable for governments, land offices, courts, and
institutional stakeholders, not only for crypto-native users.
