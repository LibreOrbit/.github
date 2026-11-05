# LibreOrbit

**Open building blocks for space software.**

LibreOrbit is an open-source initiative providing modular and reusable software components for embedded and space systems.

The goal is simple: make space software building blocks accessible to everyone, from students and universities to research teams and companies.

LibreOrbit is not intended to be a single monolithic flight software framework. Instead, it is designed as a collection of independent projects that can be used individually or combined to build larger onboard software architectures.

Projects range from low-level embedded C utilities to space communication protocols, flight software services, simulation tools and, eventually, distributed systems for cooperative spacecraft.

## Philosophy

LibreOrbit is built around a few principles:

- **Open**: software should be accessible, understandable and reusable.
- **Modular**: use only the components required by your mission.
- **Portable**: target bare-metal systems, RTOS environments and host platforms where relevant.
- **Embedded-oriented**: memory, CPU usage, determinism and reliability are considered from the beginning.
- **Testable**: components should be designed for unit testing, integration testing and simulation.
- **Extensible**: LibreOrbit is not limited to the projects listed below.

The objective is not to provide one mandatory architecture, but a toolbox from which projects can select the components they need.

## Projects

### OrbitC

A lightweight C foundation for embedded systems.

OrbitC provides configurable low-level utilities without relying on a full standard C library.

Current and planned components include:

- portable types and status handling
- memory and string utilities
- checksums and CRC algorithms
- deterministic memory allocation
- memory pools
- endian conversion
- bit manipulation
- containers and buffers
- safe integer utilities
- time utilities

OrbitC acts as the common foundation for many other LibreOrbit projects.

### OrbitFMS

An embedded File Management System designed for onboard storage.

Planned features include:

- storage backend abstraction
- file and volume management
- integrity checking
- persistent storage management
- configurable memory usage
- fault-aware storage operations

### OrbitCCSDS

Reusable implementations of CCSDS communication standards and primitives.

The project is intended to provide independent protocol components that can be reused by higher-level software such as OrbitPUS.

Potential components include:

- Space Packets
- transfer frames
- CLTU handling
- packet encoding and decoding
- sequence management
- integrity mechanisms
- additional CCSDS protocols over time

### OrbitPUS

An implementation of ECSS Packet Utilization Standard concepts and services.

OrbitPUS will build on the lower-level communication components provided by OrbitCCSDS and provide reusable services for spacecraft telemetry and telecommand applications.

### OrbitRT

A lightweight abstraction layer for execution environments.

Its purpose is to provide common interfaces for:

- tasks
- timers
- mutexes
- semaphores
- queues
- critical sections

Backends may target bare-metal platforms and RTOS environments.

### OrbitLink

A common abstraction for communication links and hardware interfaces.

OrbitLink aims to decouple protocols and applications from the underlying communication interface, allowing different backends such as UART, CAN, SpaceWire or Ethernet to be integrated without changing higher-level software.

### OrbitFDIR

Reusable mechanisms for Fault Detection, Isolation and Recovery.

Planned capabilities include:

- health monitoring
- watchdog integration
- error reporting
- fault counters
- recovery policies
- safe-mode hooks

### OrbitFSW

A higher-level flight software framework integrating LibreOrbit components.

OrbitFSW is intended to provide the common infrastructure required to build complete onboard applications while keeping individual LibreOrbit components usable independently.

## Distributed Space Systems

A longer-term objective of LibreOrbit is to explore software architectures for cooperative spacecraft and distributed orbital systems.

Several projects are planned around this objective.

### OrbitISL

Common infrastructure for Inter-Satellite Link communication.

### OrbitMesh

Networking and routing mechanisms for dynamic spacecraft networks, including disrupted or intermittent links.

### OrbitAgent

A lightweight multi-agent runtime allowing spacecraft to expose capabilities, exchange tasks and cooperate.

### OrbitServices

A distributed service layer allowing capabilities to be discovered and executed across multiple spacecraft.

The long-term objective is to allow several spacecraft to cooperate as a distributed computing infrastructure rather than operating exclusively as isolated systems.

## Simulation and Validation

### OrbitSim

Simulation infrastructure for LibreOrbit systems.

The objective is to execute multiple simulated spacecraft, communication links and failure scenarios on development platforms before deployment on embedded hardware.

### OrbitTest

Common tools for integration, validation and system testing across LibreOrbit projects.

## Roadmap

Development is expected to progress incrementally.

**Foundation**

OrbitC → OrbitFMS → OrbitCCSDS → OrbitPUS

**Flight Software Infrastructure**

OrbitRT → OrbitLink → OrbitFDIR → OrbitFSW

**Distributed Systems**

OrbitISL → OrbitMesh → OrbitAgent → OrbitServices

**Simulation & Validation**

OrbitSim → OrbitTest

This roadmap is indicative rather than fixed. Projects may evolve independently and new components can be introduced as the ecosystem grows.
