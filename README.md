# Dockyard — downloads

Builds of the **Dockyard** IntelliJ plugin: Docker, Kubernetes and request tracing in one tool
window. This repository holds **releases only** — the source is private.

## Install

1. Download the `.zip` from [Releases](../../releases/latest).
2. In your IDE: **Settings → Plugins → ⚙ → Install Plugin from Disk…** and pick the zip.
3. Restart, then open the **Docker Manager** tool window (bottom).

## Requirements

- IntelliJ IDEA **2024.2 or newer** (the action layer uses a data-context API introduced then)
- the `docker` CLI on PATH; `kubectl` for the Kubernetes tabs
- a **JDK-bearing image** for the JVM diagnostics — most production images ship a JRE, which has no
  `jcmd`/`jstack`
- a **local** Docker daemon for tracing attach; container, image, volume, network and pod management
  work against any context or `DOCKER_HOST`

## What it does

| Tab | Contents |
|---|---|
| **Stacks / Containers** | compose stacks and containers: start, stop, restart, pause, kill, remove, prune; logs in a tailing editor tab with pause, filter and timestamp controls; inspect; live stats |
| **Diagnostics** | thread dumps with a state/deadlock summary, heap histograms, heap dumps copied out as `.hprof`, a live memory monitor, container file browser and exec |
| **Images / Volumes / Networks** | pull, inspect, remove, prune unused |
| **Kubernetes** | namespaces and pods from your `kubectl` contexts, with the same logs, exec and diagnostics |
| **Traces** | one-click Jaeger + OpenTelemetry attach, a service-coloured span waterfall, and workflow tracking that follows one user across separate traces |

Pre-release builds are marked as such: they work, but parts of them have not been exercised in
anger yet.
