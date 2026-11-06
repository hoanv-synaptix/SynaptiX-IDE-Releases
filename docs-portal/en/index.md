# SynaptiX IDE Technical Documentation Wiki

<div class="doc-meta-bar">
  <span><strong>Document ID:</strong> SYNX-DOC-IDE-000</span>
  <span><strong>Software Suite:</strong> SynaptiX IDE (.NET 8 Desktop Engineering Environment)</span>
  <span><strong>Audience:</strong> System Integrators, Automation &amp; IIoT Engineers</span>
  <span><strong>Standard:</strong> IEC/IEEE 82079-1 &bull; ANSI/ISA-101</span>
</div>

Welcome to the official engineering reference manual for **SynaptiX IDE** — the unified desktop development, simulation, commissioning, and telemetry configuration environment for the **SynaptiX Edge Automation & IIoT Ecosystem**.

Unlike fragmented configuration utilities that separate local control logic from fieldbus polling and cloud telemetry, **SynaptiX IDE** integrates visual graph authoring, strict physical type checking, cycle-accurate offline simulation, atomic flash deployment, and live 20 FPS telemetry diagnostics inside a single deterministic workbench.

![SynaptiX IDE Main Engineering Workbench](/images/synaptix_main_anatomy.png)

---

## Documentation Reading Path

This manual is organized sequentially into **six progressive chapters** in the left navigation tree, taking you from foundational architecture through installation, workspace mastery, block-by-block specifications, and system integration:

<div class="wiki-chapter-grid">
  <a class="wiki-card" href="./concepts/ecosystem-overview">
    <span class="wiki-card-step">CHAPTER 01</span>
    <h3>Introduction &amp; Core Concepts</h3>
    <p>Understand the 7 built-in SynaptiX device presets, physical memory tag model (BOOL, INT32, REAL), Bad-Data Defense, and deterministic rule-plus-block execution pipeline.</p>
  </a>
  <a class="wiki-card" href="./getting-started/installation">
    <span class="wiki-card-step">CHAPTER 02</span>
    <h3>Installation &amp; Quickstart</h3>
    <p>Install SynaptiX IDE on Windows 10/11, configure USB CDC &amp; TCP transports, tour the user interface, and commission your first project in 10 minutes.</p>
  </a>
  <a class="wiki-card" href="./workspaces/device-tab">
    <span class="wiki-card-step">CHAPTER 03</span>
    <h3>IDE Workspaces (7 Tabs)</h3>
    <p>In-depth operational reference for every main tab (Ctrl+1 to Ctrl+7): Device, Logic Graph, Tag Catalog, Rule Table, Blueprints, Deploy, and Live Watch.</p>
  </a>
  <a class="wiki-card" href="./blocks/overview">
    <span class="wiki-card-step">CHAPTER 04</span>
    <h3>Function Blocks Reference</h3>
    <p>Dedicated datasheet specifications for all 18 visual blocks: Core Rule Pipeline, Timers, Counters, Linear Scale, Modbus RTU Master, Direct Hardware Output, MQTT, HTTP, and TCP.</p>
  </a>
  <a class="wiki-card" href="./tools/rs485-and-scada-slave">
    <span class="wiki-card-step">CHAPTER 05</span>
    <h3>Connectivity, DTU &amp; Tools</h3>
    <p>Configure RS-485 buses, poll the Fixed SCADA Modbus Slave Map, provision MQTT TLS &amp; Wi-Fi, operate DTU Gateway Studio, simulate offline, and leverage AI Copilot.</p>
  </a>
  <a class="wiki-card" href="./appendices/keyboard-shortcuts">
    <span class="wiki-card-step">CHAPTER 06</span>
    <h3>Quick Reference Appendices</h3>
    <p>Instant lookup tables for global &amp; canvas keyboard shortcuts, payload template macro tokens ({val1:N}, {ts}, {device}), resource limits, and runtime error codes.</p>
  </a>
</div>

---

## End-to-End Engineering Workflow

```mermaid
flowchart LR
    A["1. Select Device Preset<br/>(New Project / Auto-Detect)"] --> B["2. Define Physical &amp; Virtual Tags<br/>(Tag Catalog · Ctrl+3)"]
    B --> C["3. Wire Control &amp; IIoT Blocks<br/>(Logic Graph · Ctrl+2)"]
    C --> D["4. Verify Offline &amp; Compile<br/>(Simulator F5 · Compile F7)"]
    D --> E["5. Two-Phase Atomic Commit<br/>(Deploy · Ctrl+F5)"]
    E --> F["6. Observe &amp; Commission<br/>(Live Watch Ctrl+7 · Live Debug F8)"]
```

## Key Architectural Pillars of SynaptiX IDE

| Pillar | Engineering Guarantee | Where to Learn More |
| :--- | :--- | :--- |
| **Visual Truth & Type Integrity** | Every input field enforces strict physical memory contracts (`BOOL`, `INT32`, IEEE-754 `REAL`) with automatic normalization and invalid-input auto-revert upon commit. | [Tag Architecture & Data Types](./concepts/data-model-and-types) |
| **Hybrid Deterministic Engine** | Combines sub-millisecond 4-stage Event-Condition-Action rules (up to 100 rules) with stateful timers, counters, linear calibrators, and asynchronous fieldbus/cloud workers. | [Deterministic Execution Pipeline](./concepts/execution-pipeline) |
| **18 Self-Contained Function Blocks** | Zero external scripting required — native blocks cover edge detection, RTC shift windows, Modbus RTU Master read/write, PWM/PTO hardware pins, MQTT JSON builders, HTTP REST, and raw TCP streams. | [Function Blocks Catalog](./blocks/overview) |
| **Zero-Hardware Offline Verification** | Cycle-accurate desktop simulation (`F5`) and inbound JSON payload injection let engineers validate 100% of logic before connecting to physical hardware. | [Simulator & Online Live Debug](./tools/simulator-and-live-debug) |
| **Safe Atomic Deployment** | Two-phase flash staging with pre-flight validation ensures power loss or cable disconnection during transfer never leaves an edge controller in a corrupted state. | [Atomic Deploy Workspace](./workspaces/deploy-tab) |

::: tip Instant Bilingual Support
Both **SynaptiX IDE** and this documentation portal support instant switching between **English** and **Tiếng Việt** (use the language menu in the top-right navigation bar).
:::
