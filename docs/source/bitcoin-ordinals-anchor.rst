Bitcoin Ordinals as a Land Registry Data Anchor (Anchor Layer)
==============================================================

4.1 What Are Bitcoin Ordinals?
------------------------------

Bitcoin Ordinals are a method for inscribing data directly onto the Bitcoin
blockchain at the level of individual satoshis, the smallest unit of Bitcoin.

From a land registry perspective, the most important properties of Bitcoin
Ordinals are the following.

Data Stored Directly On-Chain
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The inscription itself resides inside the Bitcoin blockchain. There are no
external links, no cloud storage, and no dependency on third-party systems.

Not a Reference, but the Data Itself
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Unlike many NFT systems where only a pointer or reference is stored on-chain,
Bitcoin Ordinals embed the actual data payload, such as structured JSON text,
directly into the blockchain.

Permanent by Design
~~~~~~~~~~~~~~~~~~~

Once an Ordinals inscription is confirmed in a Bitcoin block, it cannot be
altered or deleted. The data remains accessible for as long as the Bitcoin
network exists.

For land registry use cases, this means that core property records can be
anchored in a manner that is independent of institutions, vendors, or
political change.

4.2 Parent–Child Inscription Model
----------------------------------

Bitcoin Ordinals support parent–child relationships, allowing inscriptions to
reference other inscriptions as their logical parent. This enables the
construction of hierarchical, auditable data structures that closely resemble
real-world land registry systems.

Hierarchical Structure
~~~~~~~~~~~~~~~~~~~~~~

In the ACRE model, inscriptions are organized as follows.

Genesis / Master Anchor
^^^^^^^^^^^^^^^^^^^^^^

- The first inscription created by the ACRE system.
- Serves as the root of trust.
- Establishes provenance for all subsequent records.

Regional or Jurisdictional Anchors
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

- Child inscriptions referencing the Master Anchor.
- Represent countries, regions, or administrative zones.
- Optional and flexible depending on local requirements.

Individual Property Records
^^^^^^^^^^^^^^^^^^^^^^^^^^^

- Child inscriptions referencing a regional or master anchor.
- Contain the immutable core data of a specific land parcel or property.

This structure allows any observer to trace a property record back to its
origin, verifying authenticity without relying on any centralized authority.

Controlled Updates Without Breaking Immutability
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Immutability does not mean that updates are impossible. It means that silent or
retroactive changes are impossible.

If a land registry authority needs to modify a record, such as an ownership
change, zoning update, or correction:

- A new child inscription is created.
- It explicitly references the previous inscription.
- It includes the updated information along with the authority’s identifier
  and relevant metadata.

The full history remains visible and auditable, while the most recent valid
inscription represents the currently accepted state.

This mirrors real-world legal practice, where original deeds remain archived
and amendments are appended rather than erased, but with cryptographic
transparency.

4.3 ISO 19152 (LADM) Compatibility
----------------------------------

What Is ISO 19152 (LADM)?
~~~~~~~~~~~~~~~~~~~~~~~~

ISO 19152, also known as the Land Administration Domain Model (LADM), is an
international standard used by land registries to model:

- Parties such as owners and rights holders,
- Rights, restrictions, and responsibilities,
- Spatial units including parcels, buildings, and land areas,
- Source documents and legal references.

The standard focuses on structure and relationships rather than a specific
database implementation or technology.

How the ACRE Model Aligns with LADM
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The Ordinals-based anchor layer aligns naturally with LADM principles.

Spatial Units
^^^^^^^^^^^^^

- Represented using standardized geospatial data, such as GeoJSON polygons.
- Stored immutably within the anchor inscription.

Rights and Parties
^^^^^^^^^^^^^^^^^^

- Referenced through cryptographic identifiers.
- Linked to ownership and transactional records on higher operational layers.

Source Documents
^^^^^^^^^^^^^^^^

- Legal documents are referenced via cryptographic hashes.
- This ensures integrity without exposing sensitive data publicly.

Temporal Consistency
^^^^^^^^^^^^^^^^^^^^

- Parent–child inscriptions preserve historical states.
- Fully compatible with LADM’s temporal modeling approach.

Why This Matters for Land Registries
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Because the ACRE model aligns with ISO 19152:

- It can be mapped to existing cadastral and land registry systems.
- It does not require registries to abandon established legal frameworks.
- It provides a neutral, interoperable foundation for modernization.

Bitcoin Ordinals function as a global, immutable ledger of record, while local
land registries retain control over interpretation, enforcement, and legal
recognition.

Summary
-------

Bitcoin Ordinals are suitable as a land registry data anchor because they
provide:

- Direct on-chain data storage,
- Absolute immutability without central control,
- A hierarchical parent–child structure mirroring real cadastral systems,
- Transparent and auditable update history,
- Compatibility with ISO 19152 (LADM).

In the ACRE architecture, Bitcoin Ordinals do not replace land registries.
Instead, they provide a neutral and permanent foundation of truth upon which
modern, interoperable land administration systems can be built.
