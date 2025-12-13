### What is this page?

This is my workflow of studying the Hyprland functionality.

### Cheat Sheet

```mermaid
flowchart TD
    %% Core stack
    Kernel["Linux Kernel</br>DRM / KMS / Input"]:::cyan
    Wayland["Wayland Protocol"]:::cyan
    Core["Hyprland Core</br>(Compositor)"]:::cyan

    Kernel --> Wayland --> Core

    %% Parallel subsystems
    Input["Input & Binds</br>Keyboard / Mouse / Touch / Gestures"]:::blue
    Config["Configuration</br>monitor - workspace - rules"]:::green
    Security["Security & Permissions"]:::red

    Core --> Input
    Core --> Config
    Core --> Security

```
