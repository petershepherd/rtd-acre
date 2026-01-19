ACRE — Executive Summary
=======================

The global real estate and land registry system is built on trust, permanence, and legal
certainty. Yet today, land records are fragmented across jurisdictions, maintained in
siloed databases, and dependent on institutional processes that are often slow, opaque,
and difficult to audit. While many governments have digitized parts of their registries,
most systems still rely on centralized infrastructures that remain vulnerable to human
error, institutional risk, and long-term data integrity issues.

ACRE is designed to solve this problem at its root.

ACRE is a jurisdiction-agnostic, blockchain-based real estate infrastructure that
introduces a new, complementary digital layer for land and property records. Rather than
replacing existing land registries or legal frameworks, ACRE strengthens them by
providing an immutable, cryptographically verifiable proof-of-record that can coexist
with and integrate into current systems.

At the core of ACRE’s architecture is a simple but powerful principle:

    Critical land and property data should be anchored to the most secure and long-lived
    digital infrastructure humanity has ever created.

For this reason, ACRE uses the Bitcoin blockchain as its immutable registry layer. Through
Bitcoin Ordinals inscriptions, essential property metadata such as geospatial boundaries,
asset identifiers, and document hashes are written directly onto Bitcoin, ensuring that
once recorded, this information cannot be altered, deleted, or retroactively manipulated.
This creates a permanent, politically neutral, and globally verifiable reference point
for property records.

On top of this immutable foundation, ACRE employs a high-performance operational layer
to handle dynamic interactions such as listings, offers, escrow mechanisms, and
settlement logic. While Solana is currently used as a reference implementation due to its
low transaction costs, high throughput, and mature tooling, the ACRE architecture is not
Solana-exclusive by design.

From a technical standpoint, the operational layer is blockchain-agnostic. Any network
capable of supporting:

- programmable transactions,
- verifiable ownership transfers, and
- the creation and exchange of text-based or metadata-rich NFTs

can serve as an operational layer within the ACRE system.

This modular approach ensures that ACRE is not locked into a single execution environment.
As blockchain infrastructure evolves, or as regulatory, technical, or jurisdictional
requirements change, the operational layer can be migrated or extended to other
compatible networks without compromising the integrity of the immutable Bitcoin-based
anchor.

This separation of concerns allows:

- Bitcoin to fulfill its role as a permanent, neutral, and censorship-resistant data
  anchor, and
- high-performance chains to manage transactional logic and user-facing operations.

As a result, ACRE remains adaptable, future-proof, and interoperable, while preserving a
single source of immutable truth for land and property records.

Crucially, ACRE does not claim that a blockchain transaction alone constitutes legal
ownership. Legal title remains governed by national laws, land registries, and notaries.
Instead, ACRE introduces a Lock + Oracle model, where on-chain transactions are
cryptographically linked to off-chain legal processes. Ownership transfers, payments,
and settlements are finalized only when the corresponding legal registry actions are
completed and confirmed. This prevents double sales, fraud, and unauthorized transfers
while preserving the authority of existing institutions.

ACRE’s data model is designed to be compatible with international land administration
standards, including ISO 19152 (Land Administration Domain Model – LADM). Its parent-child
inscription architecture mirrors real-world cadastral hierarchies, making it suitable
for integration into national land registry systems, government pilot programs, and
regulatory sandboxes.

In practice, ACRE enables:

- Immutable proof-of-record for land and property data
- Transparent, auditable transaction histories
- Secure on-chain escrow and settlement mechanisms
- Seamless integration with existing legal and cadastral systems
- Cross-border interoperability without sacrificing sovereignty

ACRE is not a speculative tokenization experiment. It is a foundational infrastructure
layer for the next generation of real estate systems—one that aligns technological
innovation with legal reality, institutional requirements, and long-term public trust.

By combining Bitcoin’s unmatched security with modern high-performance blockchain
tooling, ACRE offers governments, land registries, and market participants a credible,
future-proof path toward transparent, resilient, and globally interoperable real estate
infrastructure.

.. note::

   This documentation describes ACRE as neutral public infrastructure. ACRE does not
   operate a marketplace, does not custody assets, and does not redefine legal ownership.

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
