# PyInv Specification (Draft)

This document is in draft because we need this system soon.

## Core Library `inv`

`inv` is the core library for the entire system. It does very little by itself, but provides the glue that brings the whole system together.

`inv` essentially is a library that manipulates `Dict`s of data, and can change them based on given instructions. It does not care how the `Dict`s are stored, instead handing this off to a `Store` implementation that is handled by another module.

## High Level Requirements

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt).

### Definitions

- The `Inventory` is a collection of `Asset`s stored in one or multiple physical locations, with a real and stored state.
- The `System` is the set of computer programs and modules that manage the `Inventory`.
- An `Asset` is an individual item that exists in real space. An `Asset` MAY be marked as a `Container`.
- A `Container` is an `Asset` that can store or contain other `Asset`s within itself.

- The `System` aims to match the stored state of the `System` with the real state.
- A set of `Key Attribute`s MUST be defined, and all `Asset`s stored within the `Inventory` MUST have these `Attributes`. All `Key Attribute`s for an `Asset` MUST contain valid data and MUST NOT be undefined.
- A set of `Optional Attribute`s MUST be defined for an `Asset`. The value of an `Optional Attribute` MAY be undefined.
- 

### Classes

- `AssetType` - e.g Webcam
    - Also specifies if the asset can be a container, and what types it can contain.
- `AssetModel` - Logitech C210
- `Asset` - An individual webcam
- `Location` - A physical location.
- `Template` - A container can have a template applied to it, which specifies what it should contain.

- `Storage` - An abstract storage class - implementation varies
- `AssetCode` - An abstract asset code class - implementation varies
