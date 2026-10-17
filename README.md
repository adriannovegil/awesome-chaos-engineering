# Awesome Chaos Engineering [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of Chaos Engineering resources, tools, practices, case studies, and learning materials.

Chaos Engineering is the discipline of experimenting on a system to build confidence in its ability to withstand turbulent conditions in production. It is not about breaking things randomly, but about designing controlled experiments that uncover weaknesses before they affect users.

This repository focuses on Chaos Engineering principles, experiment practices, fault injection, GameDays, tools, and learning resources.

Related topics such as Site Reliability Engineering, observability, software engineering, and profiling are maintained in separate repositories to avoid unnecessary duplication.

## Contents

- [0. Introduction](#0-introduction)
- [1. Chaos in Practice](#1-chaos-in-practice)
- [2. Principles of Chaos Engineering](#2-principles-of-chaos-engineering)
- [3. Fault Injection](#3-fault-injection)
- [4. Observability](#4-observability)
- [5. Incident Management Tool](#5-incident-management-tool)
- [6. Cost of SEVs](#6-cost-of-sevs)
- [7. Chaos as a Service](#7-chaos-as-a-service)
- [8. Gamedays](#8-gamedays)
- [9. Books](#9-books)
- [10. Conferences and Talks](#10-conferences-and-talks)
- [11. Forums and Groups](#11-forums-and-groups)
- [12. References](#12-references)
- [13. License](#13-license)
- [14. Contributing](#14-contributing)

## 0. Introduction

__Chaos engineering__ is defined as "the discipline of experimenting on a system in order to build confidence in the system's capability to withstand turbulent conditions in production" (Principles of Chaos Engineering).

In other words, it's a software testing method focusing on finding evidence of problems before they are experienced by users.

It's a common misconception that chaos engineering is only about randomly breaking things in production. It's not. Although running experiments in production is a unique part of chaos engineering (more on that later), it's about much more than that—anything that helps us be confident the system can withstand turbulence.

> IMPORTANT!: Chaos engineering is not just about randomly breaking things ;-)

It interfaces with site reliability engineering (SRE), application and systems performance analysis, and other forms of testing.

Practicing chaos engineering can help you prepare for failure, and by doing that, learn to build better systems, improve existing ones, and make the world a safer place.

### Motivations for chaos engineering

There are at least three good reasons to implement chaos engineering:

- Determining risk and cost and setting service-level indicators, objectives, and agreements
- Testing a system (often complex and distributed) as a whole
- Finding emergent properties you were unaware of

### Related Awesome Lists

<!--lint disable double-link-->
- [My Awesome SRE Repo ;-)](https://github.com/adriannovegil/awesome-sre) - Curated list of Site Reliability Engineering tools and resources.
<!--lint ignore double-link-->
- [My Awesome Observability Repo ;-)](https://github.com/adriannovegil/awesome-observability) - Curated list of observability tools for monitoring, logging, and tracing.
<!--lint enable double-link-->

## 1. Chaos in Practice

To specifically address the uncertainty of distributed systems at scale, Chaos Engineering can be thought of as the facilitation of experiments to uncover systemic weaknesses. These experiments follow four steps:

- Start by defining 'steady state' as some measurable output of a system that indicates normal behavior.
- Hypothesize that this steady state will continue in both the control group and the experimental group.
- Introduce variables that reflect real world events like servers that crash, hard drives that malfunction, network connections that are severed, etc.
- Try to disprove the hypothesis by looking for a difference in steady state between the control group and the experimental group.

The harder it is to disrupt the steady state, the more confidence we have in the behavior of the system. If a weakness is uncovered, we now have a target for improvement before that behavior manifests in the system at large.

## 2. Principles of Chaos Engineering

A chaos experiment is defined as the following five points by the Principles of chaos engineering

- Build a Hypothesis around Steady State Behavior
- Vary Real-world Events
- Run Experiments in Production
- Automate Experiments to Run Continuously
- Minimize Blast Radius

More details in the following link ;-)

- [PRINCIPLES OF CHAOS ENGINEERING](https://principlesofchaos.org/)

## 3. Fault Injection

### Generic Tools

- [Chaos Monkey](https://github.com/Netflix/chaosmonkey) - A resiliency tool that helps applications tolerate random instance failures.
- [Chaos Toolkit](https://github.com/chaostoolkit/chaostoolkit) - A chaos engineering toolkit to help you build confidence in your software system.
- [Chaos Toolkit Turbulence](https://github.com/tmobile/chaostoolkit-turbulence) - Extension for Chaos Toolkit which adds support for Turbulence attacks.
- [Monarch](https://github.com/tmobile/monarch) - A series of tools for Chaos Toolkit.
- [Muxy](https://github.com/mefellows/muxy/) - A chaos testing tool for simulating real-world distributed system failures.
- [Chaos Blade](https://github.com/chaosblade-io/chaosblade) - Experimental tool that follows the principles of Chaos Engineering to simulate common fault scenarios.
- [Cthulhu](https://github.com/xmatters/cthulhu-chaos-testing) - Chaos Engineering tool that helps evaluating the resiliency of microservice systems in a data-driven manner.
- [Namazu](https://github.com/osrg/namazu) - Programmable fuzzy scheduler for testing distributed systems.
- [Chaos Scimmia](https://github.com/joshuamckenty/chaos-scimmia) - Chaos Engineering for Redis.
- [HavocLeopard](https://github.com/jonfast565/HavocLeopard) - A set of simple chaos engineering apps for on-prem servers.
- [AWS Chaos Scripts](https://github.com/adhorn/aws-chaos-scripts) - Collection of Python scripts to run failure injection on AWS infrastructure.
- [Dev Proxy](https://github.com/dotnet/dev-proxy) - Command-line API simulator for testing how apps respond to API failures, throttling, and slow APIs.
- [Jepsen](https://github.com/jepsen-io/jepsen) - Framework for testing distributed systems under faults and verifying the correctness of their operation histories.
- [Simoorg](https://github.com/linkedin/simoorg) - LinkedIn's failure inducer framework for testing the resilience of distributed systems.
- [Chaos Experimentation Framework](https://github.com/lyft/clutch) - Extensible platform for infrastructure management including Chaos Engineering.
- [The Simian Army](https://github.com/Netflix/SimianArmy) - Suite of tools from Netflix for keeping your cloud operating in top form (retired).

### CPU

- [CPU Troll](https://github.com/TrollScripts/cpu-troll) - Dedicated to raising CPU latency by the requested percentage and timespan.
<!--lint ignore double-link-->
- [stress-ng](https://github.com/ColinIanKing/stress-ng) - Tool to load and stress a computer system in various selectable ways, including CPU, memory, I/O, and more.

### Memory

- [totalChaos](https://github.com/Rayan25062011/totalChaos) - Overloads RAM and simulates system resource exhaustion scenarios.

### Disk

- [Disk Fillup](https://litmuschaos.github.io/litmus/experiments/categories/pods/disk-fill/) - LitmusChaos experiment to fill up disk space on a target node to test storage-related failure handling.
- [unreliablefs](https://github.com/ligurio/unreliablefs) - FUSE-based fault injection filesystem allowing runtime error injection into file operations.
- [CharybdeFS](https://github.com/scylladb/charybdefs) - FUSE-based fault injection filesystem from ScyllaDB with a Thrift RPC interface for instrumentation.
- [LazyFS](https://github.com/dsrhaslab/lazyfs) - FUSE filesystem simulating lost and torn writes to test data durability and crash recovery.

### Networking

- [Toxiproxy](https://github.com/Shopify/toxiproxy) - A TCP proxy to simulate network and system conditions for chaos and resiliency testing.
- [Comcast](https://github.com/tylertreat/comcast) - A tool designed to simulate common network problems like latency, bandwidth restrictions, and dropped/reordered/corrupted packets.
- [Chaos HTTP Proxy](https://github.com/bouncestorage/chaos-http-proxy) - Introduces failures into HTTP requests via a proxy server.
- [tc netem](https://man7.org/linux/man-pages/man8/tc-netem.8.html) - Linux network emulation tool for injecting delay, packet loss, duplication, corruption, reordering, and bandwidth limitations.
- [tcconfig](https://github.com/thombashi/tcconfig) - A tc command wrapper that makes it easy to set up traffic control of bandwidth, latency, packet loss, and corruption on network interfaces and Docker containers.
- [clumsy](https://github.com/jagt/clumsy) - Network condition simulator for Windows, injecting lag, drop, throttle, and reordering.
- [speedbump](https://github.com/kffl/speedbump) - TCP proxy for simulating variable yet predictable network latency, written in Go.
- [Noxious](https://github.com/oguzbilgener/noxious) - Rust port of the Toxiproxy server, fully compatible with its REST API and client libraries.
- [Tickchaos](https://github.com/mirotvoretts/tickchaos) - Protocol-aware UDP chaos proxy for market data feed handlers, injecting packet loss, jitter, reordering, and sequence-gap faults.
- [Saboteur](https://github.com/tomakehurst/saboteur) - __(Not for production)__ Network fault injection tool with an agent that configures partitions, delays, and packet loss via HTTP commands.

### Security

- [Infection Monkey](https://github.com/guardicore/monkey) - Open source security tool for testing a data center's resiliency to perimeter breaches and internal server infection.
- [ChaoSlingr](https://github.com/Optum/ChaoSlingr) - Security Chaos Engineering focused on experimentation on AWS Infrastructure.
- [Mitigant](https://www.mitigant.io/) - Security chaos engineering for cloud cyber resilience.

### Languages

#### Compilation Time

- [ChaosCat](https://github.com/Torvaney/chaoscat) - Chaos engineering for Pull Requests - Taking a not-even-good joke a bit too far.

#### Runtime

- [Byteman](https://byteman.jboss.org/) - A Swiss Army Knife for Byte Code Manipulation.
- [Byte-Monkey](https://github.com/mrwilson/byte-monkey) - Bytecode-level fault injection for the JVM via instrumentation.
- [Perses](https://github.com/nicolasmanic/perses) - A project to cause controlled destruction to a JVM application.
- [Wiremock](http://wiremock.org/) - API mocking (Service Virtualization) which enables modeling real world faults and delays.
- [MockLab](http://get.mocklab.io/) - API mocking (Service Virtualization) as a service.
- [Flaw](https://github.com/GaruGaru/flaw) - Injects failures on API calls for local chaos engineering.
- [Havoc](https://github.com/bchavez/Havoc) - Collection of dangerous code that wreaks havoc in .NET applications for chaos-engineering.
- [Utilities for frontend chaos engineering](https://github.com/jchiatt/chaos) - JavaScript utilities to introduce chaos into frontend applications.
- [CHAOS GOPHER](https://github.com/chaostesting/chaosgopher) - A collection of Unix-style tools in Go for chaos engineering or testing.
- [Chaos Monkey for Spring Boot](https://codecentric.github.io/chaos-monkey-spring-boot/) - Injects latencies, exceptions, and terminations into Spring Boot applications.
- [Polly Chaos Engineering](https://github.com/App-vNext/Polly) - .NET resilience and transient-fault-handling library with chaos engineering strategies for injecting faults, latency, and outcomes.
- [gofail](https://github.com/etcd-io/gofail) - Failpoints for Go from the etcd ecosystem, allowing fault injection at specific program points.
- [PingCAP failpoint](https://github.com/pingcap/failpoint) - Failpoint implementation for Go with configurable actions like returns, pauses, and panics.
- [fail-rs](https://github.com/tikv/fail-rs) - Fail points for Rust, enabling error and behavior injection at runtime for testing.
- [falzm/chaos](https://github.com/falzm/chaos) - __(Archived)__ Go HTTP middleware for injecting delays and errors into web applications, configurable on the fly via a management controller.
- [Pastaay](https://github.com/CemAkan/pastaay) - __(Experimental)__ Cloud-native chaos engineering toolkit for Go with fault injection across HTTP, gRPC, Kafka, Redis, SQL, and MongoDB.
- [React Chaos](https://github.com/jchiatt/react-chaos) - Chaos Engineering for your React apps.
- [Vue Chaos](https://github.com/aviadhahami/vue-chaos) - A simple yet chaotic component to introduce chaos in your Vue app.
- [Chaos QoaLa](https://github.com/oslabs-beta/ChaosQoaLa) - Chaos engineering tool for injecting failure into JavaScript-backed GraphQL endpoints.
- [Chaos Reverse-engineering](https://github.com/pcoppens/chaos-re) - Chaos engineering approach by reverse-engineering.
- [Fault](https://github.com/lingrino/go-fault) - Go HTTP middleware that makes it easy to inject faults into your service.
- [GORM SQLChaos](https://github.com/u2386/gorm-sqlchaos) - Manipulates DML at program runtime based on GORM callbacks.
- [Chaos Frontend Toolkit](https://chaos-frontend-toolkit.web.app/) - A set of tools to break your web apps and find ways to improve them.

### Database

- [RedFI](https://github.com/openfip/redfi) - Acts as a proxy between the client and Redis with the capability of injecting faults on the fly.
- [orchestrator](https://github.com/github/orchestrator) - MySQL replication topology management and HA tool, used for controlled failure testing of database clusters.

### Virtual Machine

- [ChaosMachine](https://github.com/KTH/royal-chaos/tree/master/chaosmachine) - Tool to do chaos engineering at the application level in the JVM.
- [TripleAgent](https://github.com/KTH/royal-chaos/tree/master/tripleagent) - System for fault injection for Java applications.

### Containers & Orchestrators

- [ChaosOrca](https://github.com/KTH/royal-chaos/tree/master/chaosorca) - Tool for doing Chaos Engineering on containers by perturbing system calls.
- [POBS](https://github.com/KTH/royal-chaos/tree/master/pobs) - Automatic Observability and Chaos for Dockerized Java Applications.
- [Pumba](https://github.com/gaia-adm/pumba) - Chaos testing and network emulation for Docker containers and clusters.
- [Blockade](https://github.com/worstcase/blockade) - Docker-based utility for testing network failures and partitions in distributed applications.
- [Chaos Engineering for Docker](https://github.com/cloudchaos/docker) - Experiments and tools for applying chaos engineering in Docker environments.
- [Chaos Engineering with Docker EE](https://github.com/sameerkasi200x/docker-chaos-engineering) - Examples and practices for applying chaos engineering with Docker Enterprise Edition.
- [Chaos Util](https://github.com/abnamrocoesd/chaos-util) - Docker image with utilities for Chaos Engineering.
- [Drax](https://github.com/dcos-labs/drax) - DC/OS Resilience Automated Xenodiagnosis tool for testing DC/OS deployments.
- [Pod-Reaper](https://github.com/target/pod-reaper) - A rules-based pod killing container for Chaos testing in Kubernetes.
- [Chaoskube](https://github.com/linki/chaoskube) - Periodically kills random pods in your Kubernetes cluster.
- [Litmus](https://github.com/litmuschaos/litmus) - Framework for Kubernetes environments that enables users to run test suites, capture logs, generate reports and perform chaos tests.
- [Chaos Operator](https://github.com/litmuschaos/chaos-operator) - Chaos engineering via Kubernetes operator.
- [Kube Entropy](https://github.com/alexlokshin/kube-entropy) - A little chaos engineering application for Kubernetes resilience testing.
- [kubernetes-chaos-lab](https://github.com/matthewbrahms/kubernetes-chaos-lab) - A brief guide to setting up your first chaos engineering lab on Kubernetes.
- [Chaos Mesh](https://github.com/pingcap/chaos-mesh) - A Chaos Engineering Platform for Kubernetes.
- [xk6-disruptor](https://github.com/grafana/xk6-disruptor) - Grafana k6 extension for injecting HTTP and gRPC faults into Kubernetes pods and services.

### Hypervisors

- [Turbulence](https://github.com/cppforlife/turbulence-release) - Tool focused on BOSH environments capable of stressing VMs and manipulating network traffic.
- [Chaos Lemur](https://github.com/strepsirrhini-army/chaos-lemur) - Self-hostable application to randomly destroy virtual machines in a BOSH-managed environment.

### Kernel & Operating System

<!--lint ignore double-link-->
- [stress-ng](https://github.com/ColinIanKing/stress-ng) - Stress test tool for Linux systems covering CPU, memory, I/O, network, and kernel-level stressors.
- [sysdig](https://github.com/draios/sysdig) - Linux system exploration and troubleshooting tool with first-class support for containers.
- [libfiu](https://github.com/albertito/libfiu) - C library for fault injection in userspace, including POSIX API failure injection without modifying application code.
- [bpfki](https://github.com/chaos-mesh/bpfki) - BPF-based kernel fault injection service from the Chaos Mesh ecosystem.
- [libfaketime](https://github.com/wolfcw/libfaketime) - Library that modifies the time perceived by an application for testing time-dependent behavior.

### Simulation and Verification

- [Turmoil](https://github.com/tokio-rs/turmoil) - Deterministic simulation testing for distributed systems in Rust, injecting latency, drops, partitions, and crashes.
- [MadSim](https://github.com/madsim-rs/madsim) - Deterministic simulation runtime for distributed systems in Rust, complementing Turmoil.
- [Loom](https://github.com/tokio-rs/loom) - Concurrency permutation testing tool for Rust, exploring possible concurrent executions.
- [Microsoft Coyote](https://github.com/microsoft/coyote) - Testing framework for concurrent C# code with deterministic bug reproduction.
- [Shuttle](https://github.com/awslabs/shuttle) - Deterministic testing framework for Rust concurrency, exploring thread schedules to find bugs.
- [Porcupine](https://github.com/anishathalye/porcupine) - Fast linearizability checker in Go for verifying whether operation histories match the expected consistency model.
- [Elle](https://github.com/jepsen-io/elle) - Transactional safety analyzer using cycle detection to evaluate consistency of database histories, complementing Jepsen.
- [FaultFuzz](https://github.com/fwhdzh/FaultFuzz) - __(Research)__ Fault injection tool extending the prior CrashFuzz work.
- [CoFI](https://github.com/hanseychen/CoFI) - __(Research)__ Consistency-guided fault injection for cloud systems, injecting network partitions at inconsistent states.
- [FIES](https://github.com/ahoeller/fies) - __(Research)__ QEMU-based fault injection framework for system-level analysis of fault tolerance and countermeasures.

### Research Prototypes

- [Filibuster](https://github.com/filibuster-testing/filibuster) - __(Research)__ Prototype of service-level fault injection testing in Python, injecting faults in inter-service communication.
- [Mallory](https://github.com/dsfuzz/mallory) - __(Research)__ Greybox fuzzing of distributed systems, an adaptive extension of Jepsen that injects faults based on runtime behavior.
- [Molly](https://github.com/palvaro/molly) - __(Research)__ Implementation of lineage-driven fault injection, reasoning backwards from correct outcomes to find failure combinations.
- [ChaosEater](https://github.com/ntt-dkiku/chaos-eater) - __(Research)__ LLM-based system that fully automates the chaos engineering cycle on Kubernetes with Chaos Mesh.
- [agent-chaos](https://github.com/deepankarm/agent-chaos) - __(Experimental)__ Chaos engineering for AI agents, injecting LLM and tool failures with LLM-as-judge evaluation.
- [langchain-chaos-middleware](https://github.com/iroy2000/langchain-chaos-middleware) - __(Experimental)__ Middleware for LangChain agents that injects exceptions into tool and model calls.
- [Chaosbringer](https://github.com/mizchi/chaosbringer) - __(Experimental)__ Chaos engineering for web apps using a Playwright-based crawler that injects network, lifecycle, and runtime faults.
- [Fuzzbox](https://github.com/eneswritescode/fuzzbox) - __(Experimental)__ Chaos engineering and API fuzzing middleware for Express.js and Next.js, injecting latency, errors, and data corruption.

### Cloud

- [Chaos Engine](https://github.com/ThalesGroup/chaos-engine) - Application for creating random Chaos Events in cloud applications to test resiliency.

#### Private Cloud

- [Glooshot](https://github.com/solo-io/glooshot) - Chaos engineering framework to help you immunize your service mesh.
- [kube-monkey](https://github.com/asobti/kube-monkey) - An implementation of Netflix's Chaos Monkey for Kubernetes clusters.
- [Powerful Seal](https://github.com/bloomberg/powerfulseal) - Adds chaos to your Kubernetes clusters, killing targeted pods and taking VMs up and down.
- [KubeInvaders](https://github.com/lucky-sideburn/KubeInvaders) - Gamified chaos engineering tool for Kubernetes clusters.
- [Kube DOOM](https://github.com/storax/kubedoom) - Kill pods inside your Kubernetes cluster by shooting them in Doom.
- [GomJabbar](https://github.com/outbrain/GomJabbar) - ChaosMonkey for your private cloud.
- [kubethanos](https://github.com/berkay-dincer/kubethanos) - Kills half of your pods randomly to engineer chaos in your preferred environment.
- [krkn](https://github.com/redhat-chaos/krkn) - Chaos and resiliency testing tool for Kubernetes and OpenShift.
- [kube-burner](https://github.com/cloud-bulldozer/kube-burner) - Kubernetes performance and scale test orchestration toolset.
- [Chaos Controller](https://github.com/DataDog/chaos-controller) - Kubernetes controller for injecting various systemic failures at scale.
- [VMware Mangle](https://github.com/vmware-archive/mangle) - Orchestrating Chaos Engineering for vSphere, Docker, Kubernetes, and AWS environments (archived).

#### Amazon AWS

- [AWS Fault Injection Service (FIS)](https://aws.amazon.com/fis/) - Fully managed service for running fault injection experiments on AWS workloads to improve resilience.
- [Testing Amazon Aurora Using Fault Injection Queries](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/AuroraMySQL.Managing.html#AuroraMySQL.Managing.FaultInjectionQueries) - Fault injection queries for Amazon Aurora.
- [Chaos SSM Documents](https://github.com/adhorn/chaos-ssm-documents) - Collection of AWS SSM Documents to perform Chaos Engineering experiments.
- [failure-lambda](https://github.com/gunnargrosch/failure-lambda) - Small Node module for injecting failure into AWS Lambda.
- [chaos_lambda](https://github.com/adhorn/aws-lambda-chaos-injection) - Small library injecting chaos into AWS Lambda.
- [Chaos Lambda](https://github.com/bbc/chaos-lambda) - Randomly terminate ASG instances during business hours.
- [AWSSSMChaosRunner](https://github.com/amzn/awsssmchaosrunner) - Library which simplifies failure injection testing and chaos engineering for EC2 and ECS.
- [Chaos Machine](https://github.com/awslabs/chaos-machine) - Complete chaos engineering workflow using AWS Fault Injection Service, CloudWatch, and Prometheus to test hypotheses.

#### Azure Cloud

- [Azure Chaos Studio](https://azure.microsoft.com/en-us/products/chaos-studio/) - Fully managed chaos engineering experimentation platform for improving resilience of Azure applications and services.
- [Azure Fault Analysis Service](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-testability-overview) - Fault testing for Azure Service Fabric applications.
- [Include controlled Chaos in Service Fabric clusters](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-controlled-chaos) - Controlled chaos in Service Fabric clusters.
- [chaos-dingo](https://github.com/jmspring/chaos-dingo) - Tool to mess with Azure services using the Azure Node.js SDK.

#### Google Cloud Platform

- [Chaos Engineering on Google Cloud Platform](https://github.com/cloudchaos/google-cloud-platform) - Experiments and tools for chaos engineering on GCP services and infrastructure.
- [Chaosgarden](https://github.com/gardener/chaos-engineering) - Chaos Toolkit modules for simulating compute and network outages on AWS, Azure, GCP, OpenStack, and VMware, plus pod disruptions on Kubernetes.

### Example Projects

- [A Chaos Engineering Bootcamp](https://github.com/tammybutow/chaosengineeringbootcamp) - Hands-on workshop materials for learning chaos engineering fundamentals.
- [HW4](https://github.com/kbalakr/Chaos-Engineering---DevOps-Demo) - Express servers used to implement service topologies.
- [Serverless Chaos Engineering Demo](https://github.com/gunnargrosch/serverless-chaos-demo) - Demonstrates how to use Failure Injection Layer to perform chaos engineering experiments on a serverless environment.
- [Chaos Engineering Demo](https://github.com/fazdevils/chaos-engineeing-demo) - Simple project demonstrating chaos engineering with Chaos Monkey and Resilience4J.
- [Chaos Engineering Demo](https://github.com/ericwyles/chaos-engineering-demo) - Resilience4j combined with Chaos Toolkit, Wiremock, and Chaos Monkey for Spring Boot.
- [How to Create a Kubernetes Cluster on Ubuntu 16.04 with kudeadm and Weave Net](https://www.gremlin.com/community/tutorials/how-to-create-a-kubernetes-cluster-on-ubuntu-16-04-with-kudeadm-and-weave-net/) - Tutorial from Gremlin on setting up a Kubernetes cluster for chaos experiments.

## 4. Observability

<!--lint ignore double-link-->
- [My Awesome Observability Repo ;-)](https://github.com/adriannovegil/awesome-observability)

## 5. Incident Management Tool

<!--lint ignore double-link-->
<!--lint ignore double-link-->
- [My Awesome SRE Repo ;-)](https://github.com/adriannovegil/awesome-sre)

## 6. Cost of SEVs

- [Availability Calculator](https://github.com/dastergon/availability-calculator) - Calculate how much downtime should be permitted in your SLA.

## 7. Chaos as a Service

- [Gremlin Inc.](https://www.gremlin.com/) - Failure as a Service.
- [Chaos Engineering Experiment Automation](https://chaostoolkit.org/) - Open-source platform for running automated chaos engineering experiments with extensible drivers.
- [Chaos Platform](https://github.com/chaostoolkit/chaosplatform) - Chaos Engineering Platform for Everyone.
- [steadybit](https://www.steadybit.com/) - Chaos Engineering platform that helps to proactively reduce downtime and provide visibility into systems.
- [Cavisson](https://www.cavisson.com/nethavoc-resilience-testing-solution/) - Chaos engineering platform for resilience testing.
- [Harness Chaos Engineering](https://developer.harness.io/docs/chaos-engineering/) - Enterprise resilience testing platform for running controlled experiments across Kubernetes, Linux, and Windows environments.
- [Antithesis](https://antithesis.com/) - Deterministic testing platform that runs workloads in a simulated environment to find bugs and verify fault tolerance.
- [ChaosMeta](https://github.com/traas-stack/chaosmeta) - __(Archived)__ Cloud-native chaos engineering platform from Ant Group covering the complete fault drill lifecycle.
- [Tumult](https://github.com/mwigge/tumult) - __(Experimental)__ Rust-native chaos engineering platform with OpenTelemetry, embedded analytics, and plugins for Kubernetes, databases, and Kafka.
- [Proofdock's Chaos Engineering Platform](https://marketplace.visualstudio.com/items?itemName=proofdock.chaos-platform) - A chaos engineering platform that integrates in Azure DevOps and focuses on the Azure cloud platform.
- [Pystol](https://github.com/pystol/pystol) - Fault injection platform for executing fault injection actions in cloud-native environments in a controlled way.

## 8. Gamedays

- [Target: What is a Gameday?](https://tech.target.com/2019/05/09/chaos-engineering-at-Target.html) - Chaos Gamedays experience by Target.
- [Codecentric: Chaos Engineering Gamedays](https://www.codecentric.de/wissens-hub/blog/chaos-engineering-gameday) - Chaos Gamedays by Codecentric.
- [New Relic: How to run a Gameday?](https://blog.newrelic.com/engineering/how-to-run-a-game-day/) - Chaos Gamedays experience by New Relic.
- [Gremlin: Gamedays](https://www.gremlin.com/gameday/) - Resources for getting started with GameDay.
- [Gremlin: Planning your own Chaos Day](https://www.gremlin.com/community/tutorials/planning-your-own-chaos-day/) - Example of a Gameday with DynamoDB by Gremlin.
- [Gremlin: How to run a Gameday?](https://www.gremlin.com/community/tutorials/how-to-run-a-gameday/) - Methodology to run Gamedays according to Gremlin.
- [Gremlin DB: Breaking Dynamo DB](https://www.gremlin.com/community/tutorials/gremlin-gameday-breaking-dynamodb/) - Example of a Gameday with DynamoDB.
- [Gremlin: Introduction to Gameday](https://www.gremlin.com/community/tutorials/introduction-to-gamedays/) - What is a Gameday according to Gremlin.
- [Gremlin: Inside Gremlin 2019 Gremlin Gamedays Roadmap](https://www.gremlin.com/community/tutorials/inside-gremlin-2019-gremlin-gamedays-roadmap/) - Chaos Gamedays experience by Gremlin.
- [Gremlin: What I learned running the Chaos Lab with Kafka](https://www.gremlin.com/community/tutorials/what-i-learned-running-the-chaos-lab-kafka-breaks/) - Example of a Gameday with Kafka.
- [Chaos Toolkit: Chaos Engineering with Humans in the loop](https://medium.com/chaos-toolkit/chaos-engineering-with-humans-in-the-loop-f4854900b1eb) - Article about Chaos Gamedays.
<!--lint ignore double-link-->
- [GoCardless: All fun and games until you start with Gamedays](https://gocardless.com/blog/game-days-at-gc/) - Article about Chaos Gamedays.
- [InfoQ: Gamedays - Achieving Resilience through Chaos Engineering](https://www.infoq.com/presentations/gameday-chaos-engineering) - Presentation about Chaos Gamedays.

## 9. Books

- [Chaos Engineering: System Resiliency in Practice](https://www.oreilly.com/library/view/chaos-engineering/9781492043850/) - Comprehensive guide by Casey Rosenthal and Nora Jones covering the discipline of chaos engineering.
- [Learning Chaos Engineering](https://www.oreilly.com/library/view/learning-chaos-engineering/9781492050995/) - Practical guide to designing and executing controlled experiments to discover system weaknesses.
- [Chaos Engineering Observability](https://www.oreilly.com/library/view/chaos-engineering-observability/9781492051046/) - Free report on the intersection of chaos engineering and observability.
- [Security Chaos Engineering](https://www.oreilly.com/library/view/security-chaos-engineering/9781098113810/) - Sustaining resilience in software and systems by Aaron Rinehart and Kelly Shortridge.
<!--lint ignore double-link-->
- [The Chaos Engineering Collection](https://www.gremlin.com/community/tutorials/chaos-engineering-the-history-principles-and-practice/) - Gremlin's comprehensive guide to the history, principles, and practice of chaos engineering.

## 10. Conferences and Talks

- [Chaos Conf](https://www.chaosconf.io/) - Annual conference dedicated to the practice of chaos engineering.
- [SREcon](https://www.usenix.org/srecon) - USENIX conference covering SRE and chaos engineering topics.
- [KubeCon Chaos Engineering Track](https://www.cncf.io/kubecon-cloudnativecon-events/) - Chaos engineering sessions at KubeCon + CloudNativeCon.
- [Awesome Chaos Engineering Talks](https://github.com/dastergon/awesome-chaos-engineering#talks) - Curated list of talks on chaos engineering.
- [Netflix: Mastering Chaos](https://www.youtube.com/watch?v=CZ3wIuvmHeM) - Josh Evans' talk on how Netflix handles chaos at scale.

## 11. Forums and Groups

<!--lint ignore double-link-->
- [CNCF Chaos Engineering Working Group](https://groups.google.com/forum/#!forum/chaoseng-wg)
- CNCF Chaos Engineering Working Group Slack: #chaosengineering (slack.cncf.io)
- [CNCF Chaos Engineering Working Group GitHub](https://github.com/chaoseng/wg-chaoseng)
<!--lint ignore double-link-->
- [Chaos Community Google Group](https://groups.google.com/forum/#!forum/chaos-community)
- [Chaos Engineering LinkedIn Group](https://www.linkedin.com/groups/7057761)
- [Chaos Engineering Slack Community](https://gremlin.com/community)

## 12. References

- https://kth.diva-portal.org/smash/get/diva2:1707948/SUMMARY01.pdf
- https://github.com/dastergon/awesome-chaos-engineering
- https://github.com/seeker89/chaos-engineering-book
- [What is security chaos engineering and why is it important?](https://hub.packtpub.com/what-is-security-chaos-engineering-and-why-is-it-important/)
- [Security Chaos Engineering: A new paradigm for cybersecurity](https://opensource.com/article/18/1/new-paradigm-cybersecurity)
- [Injecting chaos experiments into security log pipelines](https://opensource.com/article/18/9/injecting-chaos-experiments-security-log-pipelines)
- [Purple testing and chaos engineering in security experimentation](https://opensource.com/article/18/6/security-experimentation)
- [A new approach to security instrumentation](https://opensource.com/article/18/4/new-approach-security-instrumentation)
- [Security Chaos Engineering for Cloud Services](https://medium.com/@run2obtain/from-resilience-to-dependability-security-chaos-engineering-for-cloud-services-9c6d6d152ed2) - From resilience to dependability: security chaos engineering for cloud services.
- https://github.com/chaoseng/wg-chaoseng/blob/master/WHITEPAPER.md
- https://www.techrepublic.com/article/chaos-engineering-a-cheat-sheet/
- https://medium.com/capital-one-tech/4-real-world-scenarios-that-read-like-chaos-engineering-experiments-8dbf40c5f247
- https://thenewstack.io/gremlins-tammy-butow-on-the-business-side-of-chaos-engineering/
- https://learnkube.com/blog/kubernetes-chaos-engineering-lessons-learned
- https://engineering.grab.com/chaos-engineering
- https://blog.newrelic.com/engineering/chaos-engineering-explained/
- https://slack.engineering/disasterpiece-theater-slacks-process-for-approachable-chaos-engineering-3434422afb54
- https://www.usenix.org/system/files/osdi18-veeraraghavan.pdf
- https://www.usenix.org/system/files/conference/osdi14/osdi14-paper-yuan.pdf
- https://people.ucsc.edu/\~palvaro/fit-ldfi.pdf
- https://landing.google.com/sre/book.html
- https://www.infoq.com/minibooks/emag-chaos-engineering
- https://softwareengineeringdaily.com/2018/02/02/chaos-engineering-with-kolton-andrus/
- https://blog.codeship.com/embracing-the-chaos-of-chaos-engineering/
- https://azure.microsoft.com/en-us/blog/inside-azure-search-chaos-engineering/
- https://www.gremlin.com/blog/the-discipline-of-chaos-engineering/
- http://kth.diva-portal.org/smash/get/diva2:1366436/FULLTEXT01.pdf
- https://arxiv.org/pdf/1907.13039.pdf
- https://arxiv.org/abs/1404.3056
- https://arxiv.org/abs/1702.05843
- https://arxiv.org/abs/1702.05849
- https://arxiv.org/abs/1805.05246
- https://arxiv.org/abs/1812.10706

## 13. License

[![CC0](https://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0)

## 14. Contributing

Contributions welcome! Read the [contribution guidelines](contributing.md) first.

Thank you!
