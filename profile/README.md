# Open Engineering Resolvers

Stable identifiers. Intelligent resolution. Open by design.

The Open Engineering Resolvers organization provides the resolver infrastructure for the Open Engineering Platform.

Resolvers translate stable Open Engineering identifiers into their current destinations, allowing documentation, ontologies, APIs, products, stories, and other engineering assets to evolve without breaking references.

Rather than embedding physical URLs into QR codes, applications, or documentation, Open Engineering promotes the use of stable identifiers that remain valid over time.

⸻

## Why Resolvers?

Software evolves.

Repositories move.

Documentation is reorganized.

APIs are versioned.

Products mature.

Stories gain new chapters.

Traditional hyperlinks eventually become outdated.

Open Engineering solves this by separating identity from location.

Instead of referencing:

https://docs.open-engineering.io/conventions/networking/http

systems reference a stable identifier:

oe://convention/networking/http

or

https://resolver.open-engineering.io/r/convention/networking/http

The resolver determines where that identifier currently lives.

⸻

## Position within the Open Engineering Platform

The Open Engineering Platform consists of multiple complementary architectural dimensions.
```
Open Engineering Platform
│
├── Architecture Dimensions
│   ├── Ontology
│   ├── Product Model
│   ├── Systems of Record
│   └── Runtime Architecture
│
├── Kernel
├── Operating Systems
├── Capsules
├── Applications
│
└── Shared Platform Services
    ├── Registry
    ├── Resolver
    ├── Documentation
    ├── APIs
    └── QR Codes
```
Resolvers are shared platform services used by every operating system, capsule, and application.

⸻

## Relationship with the Registry

Resolvers and registries have distinct responsibilities.

Registry

The Registry is the authoritative source of engineering identifiers.

It stores:

* identifiers
* metadata
* ownership
* aliases
* versions
* lifecycle information

Resolver

The Resolver answers incoming requests.

It:

* receives an identifier
* consults the registry (or cache)
* determines the current destination
* redirects users or returns metadata

This separation allows the registry to evolve independently while keeping resolution fast and reliable.

⸻

## Resolution Flow
```
QR Code
    │
    ▼
resolver.open-engineering.io
    │
    ▼
Resolver Kernel
    │
    ▼
Registry
    │
    ▼
Current Target
    │
    ▼
Documentation
API
Ontology
Application
Story
Product
```
The identifier remains stable while destinations may change.

⸻

## Resolver Pipeline

Open Engineering treats resolution as a pipeline.
```
Identifier
      │
      ▼
Parser
      │
      ▼
Namespace Resolver
      │
      ▼
Alias Resolver
      │
      ▼
Version Resolver
      │
      ▼
Target Resolver
      │
      ▼
Response Generator
```
Each stage has a single responsibility and may evolve independently.

⸻

## Stable Identifier Scheme

Resolvers support identifiers such as:
```
oe://ontology/identity
oe://convention/github/repository
oe://os/detective
oe://os/game
oe://os/runner
oe://os/star
oe://capsule/character
oe://application/code-smell-detectives
oe://application/agility-games
oe://application/pixstars
oe://story/pki/introduction
oe://skill/software-architect
oe://mission/repository-audit
```
These identifiers remain constant even when repositories or documentation locations change.

⸻

## QR Code Integration

One of the primary purposes of the resolver infrastructure is to support durable QR codes.

Instead of embedding destination URLs, QR codes point to the resolver.
```
QR Code
      │
      ▼
resolver.open-engineering.io
      │
      ▼
Current Resource
```
This allows printed books, conference slides, posters, stickers, training materials, and physical products to continue working long after their original publication.

⸻

## Repository Structure

The organization is expected to grow into multiple focused repositories.
```
open-engineering-resolvers
│
├── resolver-kernel
├── registry-client
├── http-resolver
├── github-resolver
├── documentation-resolver
├── ontology-resolver
├── api-resolver
├── qr-code-resolver
├── resolver-cli
├── resolver-sdk-go
├── resolver-sdk-python
└── .github
```
Each repository focuses on a specific aspect of identifier resolution.

⸻

## Design Principles

Every resolver should follow a common set of principles.

* Stable identifiers over physical locations.
* Clear separation between identity and storage.
* Multiple resolver implementations sharing common conventions.
* Support for both humans and machines.
* Open standards wherever possible.
* Version-aware resolution.
* Extensible resolver pipeline.
* Language-independent protocols.
* Cache-friendly architecture.
* Observable and auditable resolution.

⸻

## Supported Targets

Resolvers may return many kinds of resources.

Examples include:

* documentation
* ontology definitions
* API specifications
* GitHub repositories
* engineering products
* software releases
* stories
* performances
* games
* engineering skills
* missions
* investigations
* dashboards
* metadata

Resolution is therefore not limited to web pages.

⸻

## Ecosystem

Open Engineering Resolvers support the wider Open Engineering ecosystem, including:

* Open Engineering Platform
* Open Engineering Conventions
* Detective Operating System
* Game Operating System
* Runner Operating System
* Star Operating System

along with every capsule, application, and engineering product built on top of the platform.

⸻

## Vision

The goal of Open Engineering Resolvers is to provide a universal, open, and extensible identifier resolution infrastructure for engineering knowledge.

By separating identity from location, engineering assets become durable, discoverable, and evolvable.

Whether a resource is documentation, an ontology concept, an API, a QR code, a product, a game, a performance, or an investigation, it can always be referenced through a stable identifier that continues to resolve as the ecosystem evolves.
