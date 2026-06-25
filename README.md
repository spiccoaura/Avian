# <img width="64" height="64" alt="Avian" src="https://github.com/user-attachments/assets/5db6976b-9579-4bfc-807b-093394a0c600" /> Avian Framework

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![C#](https://img.shields.io/badge/Language-C%23-blue.svg)](https://docs.microsoft.com/en-us/dotnet/csharp/)
[![Performance](https://img.shields.io/badge/Status-Ultra%20Fast-brightgreen.svg)]()

**Avian** is a high-performance, zero-allocation event bus framework for C#. Designed for scenarios where latency and memory predictability are critical—such as game servers and real-time systems—Avian leverages compile-time code generation to eliminate runtime overhead.

---

## 🏗️ Architecture Overview

| Component | Responsibility |
| :--- | :--- |
| **Avian.Core** | Memory management (`RingBuffer`, `Pools`) |
| **Avian.Event** | Event brokering & Dispatching |
| **Avian.SourceGen** | Compile-time optimization (Roslyn) |

---

## ⚡ Why Avian?

> **"Don't let the Garbage Collector hold you back."**

* **Zero-Allocation:** Built for high-frequency loops. No hidden `new` objects.
* **Compile-Time Magic:** Uses Roslyn Source Generators to write the "bridge code" for you.
* **Predictable:** Full control over dispatching via manual `Execute()` cycles.

---

## 🛠️ Performance Comparison

| Feature | MediatR | **Avian** |
| :--- | :--- | :--- |
| **Reflection** | Yes | **No** |
| **Allocation** | High | **Zero** |
| **Runtime Speed** | Moderate | **Maximum** |

---

## 🚀 Quick Start

### 1. Define your event
```csharp
using Avian;

public struct PlayerMoveEvent : IEvent 
{ 
    public int X, Y; 
}
