Practical Operation
===================

End-to-End Property Registration, Anchoring and Settlement Flow
---------------------------------------------------------------

This section describes the complete lifecycle of a real-world property within
the ACRE protocol, from initial registration to final settlement. The process
is designed to integrate with existing land registry workflows while
introducing an immutable, auditable on-chain backbone.

7.1 Property Registration (Off-Chain → On-Chain Entry)
------------------------------------------------------

The process begins with property registration within the ACRE system.

At this stage:

- The property already exists in the real world,
- Legal ownership remains unchanged,
- No blockchain settlement has occurred.

The registrant submits:

- Property identifiers such as address, parcel reference, or registry ID,
- Geospatial boundaries represented as GeoJSON polygons,
- Documentation of ownership or usage rights,
- Jurisdictional metadata where applicable.

This step corresponds to pre-registration or application filing in traditional
land registry systems.

At completion, the property enters the ACRE system in a pending and
non-transferable state.

7.2 Layer 2 NFT Creation (Pre-Anchored Operational Asset)
---------------------------------------------------------

Once registration data is accepted, a Layer 2 property NFT is created. This NFT
serves as the operational representation of the asset.

Key characteristics include:

- The NFT is minted on a high-performance operational blockchain,
- It is non-transferable at this stage,
- It references a pre-reserved Bitcoin ``satoshi_id``.

Example metadata:

::

  {
    "assetType": "realEstate",
    "btc_anchor_satoshi_id": "757047175618153",
    "anchor_status": "reserved",
    "registration_status": "pending",
    "jurisdiction": "agnostic",
    "geometry": {
      "type": "Polygon",
      "coordinates": [...]
    }
  }

Important properties of this step:

- The ``satoshi_id`` is known and reserved in advance,
- No Bitcoin inscription exists yet,
- This prevents anchor reassignment or duplication.

7.3 Ordinals Inscription Creation (Immutable Anchor)
----------------------------------------------------

After registration review and validation, the reserved satoshi is inscribed on
Bitcoin using Ordinals.

The inscription contains:

- The canonical asset definition,
- A cryptographic reference to the Layer 2 NFT,
- Hashes of legal documents (never the documents themselves).

Example inscription payload:

::

  {
    "assetType": "realEstate",
    "linked_layer2_nft": {
      "chain": "Solana",
      "mint": "F1dF4A3b9JzDqJvXx6qYgLp9Vv...xyz"
    },
    "geometry": {
      "type": "Polygon",
      "coordinates": [...]
    },
    "metadata": {
      "version": "1.0",
      "integrityHash": "SHA256(hash-of-object)"
    }
  }

From this point forward:

- The asset has a permanent, immutable on-chain anchor,
- The Bitcoin Layer 1 record becomes the authoritative source of truth.

7.4 On-Chain Offer and Escrow Initiation
----------------------------------------

With anchoring completed, the property becomes eligible for on-chain offers.

Buyers may:

- Submit offers directly on-chain,
- Lock funds into escrow, either crypto-native or hybrid,
- Bind offers explicitly to the anchored asset.

All offers are:

- Publicly verifiable,
- Time-bound,
- Non-repudiable.

This step replaces informal off-market negotiation with cryptographically
enforceable intent.

7.5 Legal Lock (Off-Chain Restriction + On-Chain Signal)
-------------------------------------------------------

Once an offer is accepted, a legal lock is applied.

This lock:

- Restricts resale or double-sale outside the platform,
- Mirrors traditional "under contract" or encumbrance status,
- Is enforced through a combination of:
  
  - Legal agreements,
  - Registry-level flags,
  - On-chain state transitions.

The Layer 2 NFT reflects this state change as follows:

::

  {
    "transfer_state": "locked",
    "legal_status": "under_transfer"
  }

7.6 Ownership Transfer and Oracle Confirmation
----------------------------------------------

Ownership transfer occurs off-chain within the legal domain, such as a land
registry update or notarial act.

Once the transfer is legally completed:

- An oracle or authorized verifier confirms the registry update,
- The oracle submits a cryptographically signed confirmation on-chain.

This confirmation:

- References the original Bitcoin inscription,
- Attests that legal ownership has changed,
- Authorizes final settlement.

7.7 Settlement and State Finalization
-------------------------------------

Upon oracle confirmation:

- Escrowed funds are released to the seller,
- The Layer 2 NFT becomes transferable,
- Ownership metadata is updated,
- The transaction is finalized atomically.

Any future corrections, amendments, or registry updates are recorded through
child inscriptions, never by modifying the original anchor.

7.8 Two-Way Anchoring Guarantee
-------------------------------

The system enforces permanent bidirectional linkage:

- Layer 2 NFT → references ``btc_anchor_satoshi_id``,
- Bitcoin inscription → references the Layer 2 NFT mint.

This guarantees:

- No duplicate assets,
- No retroactive manipulation,
- Full auditability for courts, registries, and regulators.

7.9 Practical Outcome
---------------------

This operational model ensures that:

- Blockchain does not replace land registries,
- It augments them with immutability and auditability,
- Double-selling is both technically and legally prevented,
- Registry authorities retain control over legal validity,
- Historical integrity is preserved indefinitely.

ACRE does not replace land registries. It provides them with a secure,
interoperable, and future-proof execution layer for registration, transfer, and
auditability.
