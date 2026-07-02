## About Me

- 🔭 I’m currently: Working through the CCNP-SP course and building **TransitLab** (a containerized multi-AS network emulation framework) & **HostFixture** (an open-source .NET integration testing library).
- 💬 Ask me about: Infrastructure automation, BGP Anycast, and dynamic traffic steering!
- 🔮 I'd like to work on: Global edge infrastructure, network control planes, distributed systems, and learning more about eBPF/Rust.
- 📫 How to reach me: hello.sean.hogan (at) gmail.com
- ⚡ Fun fact: I have a bicycle habit, and I sometimes run around dressed up as an animal.

## My Skills

**Core Languages & Tooling**
- Go
- C# / .NET Core
- Rust (Currently Learning the language: Experimenting with eBPF and XDP)
- Bash / PowerShell (Core)
- Infrastructure as Code (Bicep)

**Networking & Infrastructure**
- **Routing & Edge:** BGP, OSPF, IS-IS, Anycast (Experience spanning software emulators to Extreme Networks / Juniper hardware).
- **Linux Operations:** Ubuntu/Debian high-availability environments, HAProxy, layer 7 load balancing.
- **DNS Architecture:** BIND, with hands-on experience running authoritative and recursive resolvers at ISP scale.
- **Physical Layer:** Datacenter operations, passive/active optical networking (CWDM), ExpressRoute physical peering. 

**Systems Architecture**
- **Distributed Systems:** Asynchronous, message-based architectures and distributed caching / horizontal scaling with Redis.
- **Cloud & DevOps:** Microsoft Azure (from containerized build agents to strict Zero-Trust virtual networking).
- **Security & Identity:** Enterprise OAuth 2.0 / SSO workflows (Auth0, Okta), JWT, Managed Identities.
- **Emerging Tech:** Model Context Protocol (MCP) client & server implementations for secure AI integration.

## Projects

### 🌐 TransitLab
https://github.com/PatchworkHorse/TransitLab

A high-fidelity, programmatic inter-domain routing emulation framework that orchestrates multi-AS internet topologies using **FRRouting (FRR)**, **Go**, and deterministic Linux container networking.

TransitLab allows engineers to simulate, test, and automate service-provider-level traffic engineering, BGP/OSPF convergence, and edge architectures—running real routing software without the overhead of heavy, specialized network simulators.

> 🛠️ **Control Plane Tooling:** Includes a custom orchestration CLI written in **Go** to dynamically spin up, isolate, and manage discrete topology namespaces via Docker Compose profiles.

#### ✨ System Highlights
* **Programmatic Topologies:** Topology configurations are modularized by Autonomous System (AS) fragments, leveraging shared router templates to enable rapid, composable network expansion.
* **Deterministic Interface Binding:** Bypasses unpredictable Docker network provisioning by utilizing `macvlan`/`ipvlan` driver architectures and explicit interface assignments to maintain rigid, consistent link naming across executions.
* **Production-Grade Routing Stack:** Routers utilize a hardened Ubuntu + FRR base image executing native routing daemons (BGP, iBGP, OSPF, IS-IS) with kernel-level IPv4 forwarding enabled.
* **Local or Cloud-Native Execution:** Fully optimized to launch in a single click via GitHub Codespaces or locally on any Linux host with Docker Compose V2.

#### 🏗️ Architecture & Core Components
The repository organizes compose bundles, router bootstrap sequences, and routing engine configurations by topology under `topologies/<name>/`:

---

### 🧪 HostFixture
https://github.com/PatchworkHorse/HostFixture

HostFixture is a fluent, highly extensible integration testing framework for .NET designed to intercept, mutate, and isolate `IHost` and `IHostApplicationBuilder` service collections, configuration pipelines, and HTTP dependencies at runtime.

By providing an intuitive, chainable abstraction layer over native .NET dependency injection (`IServiceCollection`), HostFixture allows developers to orchestrate deterministic, side-effect-free integration tests without relying on complex, boilerplate-heavy testing sub-structures.

#### 🛠️ Framework Features
* **Fluent Service Mutations:** Seamlessly replace, stub, or register services (`Singleton`, `Scoped`, `Transient`) via an expressive API directly against the host builder infrastructure.
* **Deterministic HTTP Interception:** Intercept, filter, and mock outbound traffic from injected `HttpClient` instances with advanced URI and method-level request/response routing.
* **Runtime Configuration Injections:** Overwrite individual configuration elements, merge dedicated JSON blocks, or patch entire test-specific settings files into active application providers on the fly.
* **Architecture-Agnostic Core:** Natively integrates with any component relying on .NET Generic Host—including ASP.NET Core Minimal APIs, Web APIs, Worker Services, and background daemons.

#### 🚀 Architectural Setup
To leverage HostFixture, decouple your initialization sequence from the standard `Main` execution path by exposing your `WebApplicationBuilder` setup logic. This allows the integration testing layer to hook into the service collection before the pipeline is compiled.

##### Application Boundary (`Program.cs`)
```csharp
public class Program
{
    public static WebApplicationBuilder CreateBuilder(string[] args)
    {
        var builder = WebApplication.CreateBuilder(args);
        // Domain services configuration...
        return builder;
    }

    public static void Main(string[] args)
    {
        var builder = CreateBuilder(args);
        var app = builder.Build();
        // Routing and pipeline middleware...
        app.Run();
    }
}
