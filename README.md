

## About Me

- 🔭 I’m currently working on: **TransitLab** (a containerized multi-AS network emulation framework) & **HostFixture** (an open-source .NET integration testing library).
- 💬 Ask me about: Infrastructure automation, BGP Anycast, and dynamic traffic steering!
- 🔮 I'd like to work on: Global edge infrastructure, network control planes, distributed systems, and learning more about eBPF/Rust.
- 📫 How to reach me: Paintcolt (at) gmail.com
- ⚡ Fun fact: I have a bicycle habit, and I sometimes run around dressed up as an animal.

## My Skills

**Core Languages & Tooling**
- Go
- C# / .NET Core
- Rust (Currently Learning / eBPF focus)
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

### HostFixture
https://github.com/PatchworkHorse/HostFixture

HostFixture is a test fixturing framework intended to bring integration tests closer to the "Real" thing. HostFixture is designed to work with any IHostBuilder implementation and, among other things allows you to: 
- Manipulate IConfiguration values
- Replace ServiceCollection registrations (i.e., with mocks)
- Add programmable HTTP interceptors to log, alter, or mock HttpRequest and HttpResponse messages. 
- Intercept, alter, mock integrations with various Microsoft Azure services. 


### Internet Emulator
https://github.com/PatchworkHorse/TransitLab

A Docker-based implementation of a multi-AS network topology for learning and experimenting. Support for inter-AS (BGP) routing, as well as intra-AS (OSPF) routing. Each router is implemented as a Docker container running FRR. Aside cool networking stuff, there's also some novel Docker use such as partitioning compose files, semi-dynamically generation of configuration files, etc.

**Features:**
- Multi-AS network topology with simulated ISPs, CDNs, etc. 
- BGP peering relationships between autonomous systems
- OSPF and iBGP for routing within autonomous systems
- Simulated customer networks connected to each ISP
- Simulated Internet Exchange with bilateral and transit peering
- FRR-based routing with Docker containers
- Interactive CLI access to verify BGP peering and connectivity

** Planned Features:**
- DNS with custom TLDs (Think root servers)
- Route reflection 
- Emulate Netflix Open Connect (IP Anycast, simulate OCAs within an AS)


### DistributedTranscoder
https://github.com/PatchworkHorse/DistributedTranscoder

Learning project as part of learning Golang & gRPC as well as sharpening containerization skills. DistributedTranscoder is intended to perform transcoding operations on video in a distributed, platform-agnostic manner using cheap cloud resources. 

- Accept incoming video (blobs for now, streams later) and break it into configurable chunks, drop chunks into an S3 bucket. 
- Orchestrate operations on containerized workers. Currently workers use FFmpeg for transcoding and other manipulation tasks
- Re-assemble transcoded chunks into useful output

## Connect with Me

- [LinkedIn](https://www.linkedin.com/in/sean-hogan-nh/)
- [Telegram](https://t.me/Patchwork)

