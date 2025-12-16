

## About Me

Hello! I'm Sean / Patchwork

- 🔭 I’m currently working on: HostFixture & Internet Emulator (See below!) 
- 💬 Ask me about: Infrastructure automation!
- 🔮 I'd like to work on: Large scale, distributed systems, putting Redis to work in a meaningful way.
- 📫 How to reach me: Paintcolt (at) gmail.com
- ⚡ Fun fact: I have a bicycle habit, and I sometimes run around dressed up as an animal.

## My Skills

- **Languages & Frameworks:** 
    - C# / .NET 
    - TypeScript / Angular
    - Bicep
    - Golang
    - PowerShell (Core)
    - Angular
    - WPF / MAUI
- **Platforms, Skills, Misc Knowledge**
    - Microsoft Azure - Everything from simple web apps to virtual networking with physical peering via ExpressRoute
    - Infrastructure automation (Mostly w/ Bicep & PowerShell Core)
    - DevOps (Mostly Azure) - Policy, building, testing, staging, deployment
    - Linux / Unix (Ubuntu is OS of choice, most derivatives of Debian will do)
    - MCP (Model Context Protocol) - Client & Server Implementations, mostly in .NET 
    - DNS (Specifically with BIND, experience with authoritative and recursive resolvers at ISP scale)
    - REST API design & Implementation
    - Asynchronous, message-based systems for loosely-coupled business services
    - Distributed caching with Redis (Let's talk about session caching!) 
    - Sendgrid (Both outbound & inbound w/ callbacks)
    - Salesforce REST API (Created a really cool .NET client for SF REST professionally)
    - OAuth Workflow (Extensive experience with Auth0/Okta)
    - Routing (BGP, OSPF, IS-IS, etc. Mostly w/ Juniper & Extreme Networks)
    - Passive and active optical networking
    - Datacenter power(AC and DC), cooling, operations



## Projects

### HostFixture
https://github.com/PatchworkHorse/HostFixture

HostFixture is a test fixturing framework intended to bring integration tests closer to the "Real" thing. HostFixture is designed to work with any IHostBuilder implementation and, among other things allows you to: 
- Manipulate IConfiguration values
- Replace ServiceCollection registrations (i.e., with mocks)
- Add programmable HTTP interceptors to log, alter, or mock HttpRequest and HttpResponse messages. 
- Intercept, alter, mock integrations with various Microsoft Azure services. 


### Internet Emulator
https://github.com/PatchworkHorse/InternetEmulator

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

- [Web](https://patchwork.horse)
- [LinkedIn](https://www.linkedin.com/in/sean-hogan-nh/)
- [Bluesky](https://bsky.app/profile/patchwork.horse)
- [Telegram](https://t.me/Patchwork)

