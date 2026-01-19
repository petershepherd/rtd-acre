Escrow, Lock & Oracle Security Model
===================================

One of the most critical elements of land and real estate transactions is
trust. Buyers must be confident that their funds cannot be lost or
misappropriated, while sellers must be assured that ownership will only be
transferred once payment has been properly secured and confirmed.

ACRE addresses this challenge through a multi-layered escrow, lock, and oracle
security model that combines on-chain guarantees with off-chain legal
validation.

This model is designed to prevent double sales, premature fund releases, and
ownership disputes, while remaining compatible with existing land registry
systems.

8.1 Escrow Mechanism
-------------------

At the core of the transaction flow is an escrow mechanism that temporarily
holds the buyer’s funds until all predefined conditions are satisfied.

Depending on jurisdiction and transaction type, escrow may be implemented as:

- On-chain escrow using smart contracts and stablecoins,
- Hybrid escrow combining on-chain locks with regulated custodians,
- Off-chain regulated escrow integrated through APIs.

In all cases, escrow logic follows the same principles:

- Funds are locked and cannot be accessed unilaterally,
- Release conditions are deterministic and verifiable,
- Neither party can bypass the process.

This ensures that payment and ownership transfer remain logically atomic, even
when legal systems operate asynchronously.

8.2 Legal Lock of the Asset
--------------------------

Before ownership transfer can occur, the property must be placed under a legal
lock.

This lock represents a formal commitment that the asset cannot be sold,
pledged, or transferred outside the ACRE transaction flow during settlement.

Depending on jurisdiction, the legal lock may be implemented through:

- A notary-issued restriction,
- A land registry flag or annotation,
- A contractual lock enforced by a licensed intermediary,
- A court-recognized escrow or trust arrangement.

The existence of a valid legal lock is a mandatory prerequisite for progressing
the transaction on-chain.

8.3 On-Chain Asset Lock
----------------------

In parallel with the legal lock, ACRE enforces an on-chain lock on the digital
representation of the property.

This includes:

- Freezing transfer functions of the Layer 2 NFT,
- Preventing listing cancellation or resale,
- Locking associated offers and state transitions.

Once activated, the asset cannot be transferred, duplicated, or altered until
the transaction reaches a terminal state, either settlement or rollback.

8.4 Oracle-Based Verification Layer
----------------------------------

Because land registries and notarization systems operate off-chain, ACRE relies
on oracles to bridge verified real-world events into the on-chain execution
layer.

Oracles confirm events such as:

- Legal lock successfully applied,
- Ownership change recorded in the land registry,
- Notarial deed execution completed,
- Regulatory approvals granted.

Only after a valid oracle confirmation does the smart contract advance the
transaction to the next stage.

Oracles may be implemented as:

- Trusted institutional APIs,
- Licensed notary or registry endpoints,
- Multi-signature oracle committees,
- Government-operated validation nodes.

8.5 Atomic Settlement Logic
---------------------------

Final settlement occurs only when all of the following conditions are
simultaneously satisfied:

1. Buyer funds are locked in escrow,
2. Legal lock is confirmed,
3. On-chain asset lock is active,
4. Oracle verification confirms ownership transfer readiness.

Once these conditions are met:

- Funds are released to the seller,
- The ownership NFT is transferred to the buyer,
- Transaction state is finalized and immutable.

This guarantees logical atomicity even when execution spans multiple technical
and legal systems.

8.6 Failure and Rollback Handling
--------------------------------

If any step fails, expires, or is invalidated:

- Escrow funds are returned to the buyer,
- Legal and on-chain locks are released,
- The transaction is marked as void,
- An immutable audit record remains on-chain.

This prevents partial execution and protects both parties from asymmetric risk.

8.7 Security Guarantees
----------------------

The Escrow, Lock & Oracle Security Model provides:

- Protection against double sales,
- Resistance to fraud and manipulation,
- Clear auditability for regulators and courts,
- Compatibility with national land registries,
- No reliance on trust in a single intermediary.

8.8 Legacy System Integration and Oracle Middleware Architecture
----------------------------------------------------------------

Purpose of the Oracle Layer
~~~~~~~~~~~~~~~~~~~~~~~~~~

The oracle layer is not designed to replace existing land registry systems. Its
sole purpose is to bridge authoritative off-chain registries with on-chain
execution logic in a secure, verifiable, and minimally invasive manner.

The oracle acts as a read-and-attest layer, not as a decision-making authority.

Design Principle: “Augment, Do Not Replace”
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Most land registries operate on mission-critical legacy systems, including
relational databases, document management platforms, internal approval
workflows, and regulated access controls.

ACRE assumes these systems remain the source of legal truth. Blockchain does
not overwrite registry data; it anchors registry state transitions immutably.

Oracle Middleware Architecture
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

At a technical level, the oracle is implemented as an API middleware service
operated by, or under the authority of, the registry.

Core components include:

Read Adapter
^^^^^^^^^^^^

- Secure, read-only access to registry databases,
- Pulls parcel identifiers, ownership state, and registry timestamps.

Validation Logic
^^^^^^^^^^^^^^^^

- Confirms registry actions have reached a legally valid state,
- Applies deterministic rules defined by the registry.

Signing Module
^^^^^^^^^^^^^^

- Uses registry-controlled private keys,
- Cryptographically signs confirmation payloads.

Blockchain Relay
^^^^^^^^^^^^^^^^

- Submits signed confirmations to on-chain oracle contracts,
- Verifies signatures, identifiers, and transaction references.

Security and Operational Guarantees
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

- No direct database exposure,
- One-way trust flow: registries attest, blockchain verifies,
- Signing keys remain under registry control,
- Fail-safe behavior: no oracle, no settlement.

Summary
-------

The ACRE oracle and escrow model integrates with existing land registry systems
through lightweight middleware. Registries remain authoritative, while the
blockchain provides execution, verification, and auditability without disrupting
legacy infrastructure or legal sovereignty.

Contents
--------

.. toctree::
   :maxdepth: 2

   index
   problem
   immutability
   bitcoin-as-data-layer
   bitcoin-ordinals-anchor
   law-and-blockchain
   technical-architecture
   practical-operation
   escrow-lock-oracle-security-model
   registry-integration-patterns
   threat-model-and-failure-scenarios
   acre-token-economy
   strategic-positioning-and-institutional-overview
