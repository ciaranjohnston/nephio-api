# Nephio APIs

## Overview

Nephio APIs primarily consist of a collection of Go API objects, CRDs and other KRM types,
specified and maintained in the [Nephio API repository](https://github.com/nephio-project/api).
this page aims to give a high level overview of the objects that are available and their
relationships, and is based on an
[original document](https://docs.google.com/document/d/1-5nlpY4FbuhWtdKTvIqPOv4bWmA6zx6TdHoEfk9Jc_Q/edit)
developed ny Tal Liron.

## How to read this page

Diagrams in this context have been kept as simple as possible for now, and do not attempt to convey all the details of the
modelled entities. Instead they give a high-level overview of the entities and relationships that can be accessed and modified via the Nephio API, and provide reference to documentation where available.

## Topology (Mermaid minimized)

```mermaid
flowchart TD
    NFTopology-- 1 .. n -->NFInstance
    NFInstance -. refers .-> NFTemplate
    NFTemplate -- 1..n --> NFInterface
    NFInterface -. refers (by name) .-> NetworkInstance
    NFTemplate-.refers..->Capacity
    NFTemplate -. refers (by name) .-> NFClass
    NFClass -. refers .-> PackageRevisionReference

```

## Topology - original draw.io

![Topology](diagrams/topology.svg)

## Network Requirements

![Network Requirements](diagrams/requirements.svg)

## Capacity Requirements

![Capacity Requirements](diagrams/capacity-requirements.svg)

# Issues
Please raise any issues in the [nephio](https://github.com/nephio-project/nephio) repository
instead of in here, using the prefix "api: " in the issue title.
