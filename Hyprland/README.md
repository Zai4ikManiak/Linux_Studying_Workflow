### What is this page?

This is my workflow of studying the Hyprland functionality.

### Cheat Sheet

```mermaid
flowchart TB
    %% ─────────────────────────────
    %% Kernel / Wayland Layer
    %% ─────────────────────────────
    KERNEL["Linux Kernel<br/>DRM / KMS"]
    WAYLAND["Wayland<br/>Protocol"]
    HYPR["Hyprland Core<br/>[Compositor]"]

    KERNEL --> WAYLAND --> HYPR

    %% ─────────────────────────────
    %% Core Branches
    %% ─────────────────────────────
    INPUT["INPUT / BINDS<br/>keyboard / mouse<br/>gestures / binds"]
    CONFIG["CONFIGURATION<br/>general / monitor<br/>workspace / layouts<br/>windowrule / layerrule<br/>animations / decoration"]
    SECURITY["SECURITY<br/>permissions<br/>allow_exec<br/>allow_input"]

    HYPR --> INPUT
    HYPR --> CONFIG
    HYPR --> SECURITY

    %% ─────────────────────────────
    %% Dispatcher & Monitor Flow
    %% ─────────────────────────────
    DISPATCH["DISPATCHER<br/>Binds → Dispatcher"]
    MONITORS["Monitors<br/>monitor"]

    INPUT --> DISPATCH
    CONFIG --> MONITORS
    MONITORS --> DISPATCH

    %% ─────────────────────────────
    %% Rendering Pipeline
    %% ─────────────────────────────
    WORKSPACES["Workspaces<br/>workspace"]
    LAYOUT["Layout Engine<br/>dwindle / master"]
    WINDOWS["Windows<br/>windowrule / float"]
    LAYERS["Layers<br/>layerrule"]
    DECOR["Decorations & Effects<br/>blur / decoration"]
    ANIM["Animations"]
    RENDER["Renderer<br/>misc.vfr<br/>allow_tearing"]
    OUTPUT["Monitor Output"]
    CLIENTS["External Clients<br/>exec / xwayland"]
    IPC["IPC / Runtime<br/>hyprctl"]

    DISPATCH --> WORKSPACES
    WORKSPACES --> LAYOUT
    LAYOUT --> WINDOWS
    WINDOWS --> LAYERS
    LAYERS --> DECOR
    DECOR --> ANIM
    ANIM --> RENDER
    RENDER --> OUTPUT
    OUTPUT --> CLIENTS
    CLIENTS --> IPC

    %% ─────────────────────────────
    %% Styling (Dark Theme Friendly)
    %% ─────────────────────────────
    classDef cyan fill:#0f2a33,stroke:#4dd0e1,color:#e0f7fa
    classDef blue fill:#10243a,stroke:#64b5f6,color:#e3f2fd
    classDef green fill:#0f2f1f,stroke:#66bb6a,color:#e8f5e9
    classDef red fill:#331010,stroke:#ef5350,color:#ffebee
    classDef yellow fill:#332b0f,stroke:#fbc02d,color:#fff8e1
    classDef magenta fill:#2b0f2f,stroke:#ce93d8,color:#f3e5f5

    class KERNEL,WAYLAND,HYPR,MONITORS,RENDER,OUTPUT cyan
    class INPUT,DISPATCH blue
    class CONFIG green
    class SECURITY red
    class WORKSPACES,LAYOUT,WINDOWS,LAYERS,DECOR,ANIM yellow
    class CLIENTS,IPC magenta

```
