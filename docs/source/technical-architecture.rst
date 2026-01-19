ACRE Technical Architecture
===========================

ACRE is designed as a modular, layered system that cleanly separates legal
authority, immutable records, and high-performance operations. This separation
ensures regulatory compatibility, long-term data integrity, and practical
usability at national scale.

At a high level, the architecture consists of three coordinated layers:

1. An immutable registry layer  
2. A high-performance operational layer  
3. External legal and institutional systems  

Each layer has a clearly defined role and responsibility.

6.1 Layered Architecture Overview
---------------------------------

Layer 1 – Immutable Registry (Bitcoin)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The foundation of ACRE is an immutable data layer implemented on the Bitcoin
blockchain using Ordinals.

This layer serves as:

- A permanent proof-of-record for land and property data,
- A cryptographically verifiable historical archive,
- A neutral anchor independent of any single institution or vendor.

Stored data includes:

- Geospatial definitions such as GeoJSON polygons,
- Asset identifiers and metadata,
- Cryptographic references (hashes) to legal documents,
- Parent–child relationships supporting versioning and updates.

Once written, data on this layer:

- Cannot be altered,
- Cannot be deleted,
- Can only be extended through new inscriptions.

This makes Bitcoin the single source of historical truth, while still allowing
controlled evolution of records through append-only updates.

Layer 2 – High-Performance Operational Layer
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The second layer handles all dynamic activity that would be impractical or
inefficient to execute directly on Bitcoin.

This includes:

- Property listings,
- Offers and bids,
- Escrow logic,
- Ownership state transitions,
- Payment settlement,
- Referral systems and incentive mechanisms,
- User interaction and marketplace logic.

This layer is currently implemented on Solana, but it is not chain-exclusive by
design.

Any blockchain capable of providing:

- Fast transaction finality,
- Low and predictable transaction costs,
- NFT- or token-based state representation, including text-based NFTs,

can technically serve as the operational layer.

Solana is used because it offers:

- High throughput suitable for national-scale systems,
- Predictable and low transaction fees,
- Mature tooling for wallets, smart contracts, and indexing.

Importantly, no critical historical or legal data is stored exclusively on this
layer. If the operational layer changes in the future, the immutable registry
remains intact.

Off-Chain Legal and Institutional Systems
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The third component consists of existing real-world authorities, including:

- Land registries,
- Notaries,
- Courts,
- Government databases,
- Licensed escrow and payment providers.

These systems:

- Retain full legal authority,
- Perform identity verification and compliance checks (KYC/AML),
- Execute legally binding ownership changes,
- Issue official and legally recognized documents.

ACRE integrates with these systems through:

- Oracles,
- Digital signatures,
- API-based confirmations,
- Cryptographic hashes of legal documents.

This approach ensures that ACRE enhances, rather than replaces, existing legal
frameworks.

6.2 Why This Separation Matters
-------------------------------

The strict separation of concerns within the ACRE architecture is intentional.

- Bitcoin guarantees permanence and institutional neutrality,
- The operational layer enables speed, usability, and scalability,
- Off-chain systems preserve legal enforceability and sovereignty.

This separation prevents:

- Vendor lock-in,
- Dependency on a single execution blockchain,
- Legal ambiguity regarding ownership and authority,
- Single points of technical or institutional failure.

At the same time, it enables:

- Gradual adoption by governments and registries,
- Parallel operation with existing systems,
- Controlled pilot programs and phased rollouts.

6.3 Data Flow Summary
---------------------

A typical ACRE transaction follows a clearly defined sequence:

1. A property is defined and anchored immutably on Bitcoin.
2. The operational layer references this anchor for all subsequent actions.
3. Legal authorities validate and approve real-world changes.
4. Oracles attest to legal events and confirm them on-chain.
5. Ownership, payments, and records update atomically.

Every step in this process is:

- Traceable,
- Auditable,
- Cryptographically verifiable.

6.4 Architectural Benefits for Land Registries
-----------------------------------------------

This architecture allows land registries to:

- Maintain full sovereignty over legally authoritative records,
- Gain an immutable audit trail without requiring infrastructure overhaul,
- Reduce fraud and data disputes,
- Enable secure digital transactions without introducing legal risk,
- Integrate gradually, at their own pace.

ACRE is therefore not a disruptive replacement, but a structured technical
upgrade path for existing cadastral and land administration systems.

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
