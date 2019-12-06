# Awesome Chaos Engineering

## General Information

 * [PRINCIPLES OF CHAOS ENGINEERING](https://principlesofchaos.org/?lang=ENcontent)

## Tools

 * [Chaos Monkey](https://github.com/Netflix/chaosmonkey) - A resiliency tool that helps applications tolerate random instance failures.
 * [The Simian Army](https://github.com/Netflix/SimianArmy) - A suite of tools for keeping your cloud operating in top form.
 * [Orchestrator](https://github.com/github/orchestrator) - MySQL replication topology management and HA.
 * [kube-monkey](https://github.com/asobti/kube-monkey) - An implementation of Netflix's Chaos Monkey for Kubernetes clusters.
 * [Gremlin Inc.](https://www.gremlin.com/) - Failure as a Service.
 * [Chaos Toolkit](https://github.com/chaostoolkit/chaostoolkit) - A chaos engineering toolkit to help you build confidence in your software system.
 * [ChaoSlingr](https://github.com/Optum/ChaoSlingr) - Introducing Security Chaos Engineering. ChaoSlingr focuses primarily on the experimentation on AWS Infrastructure to proactively instrument system security failure through experimentation.
 * [Powerful Seal](https://github.com/bloomberg/powerfulseal) - PowerfulSeal adds chaos to your Kubernetes clusters, so that you can detect problems in your systems as early as possible. It kills targeted pods and takes VMs up and down.
 * [Drax](https://github.com/dcos-labs/drax) -  DC/OS Resilience Automated Xenodiagnosis tool. It helps to test DC/OS deployments by applying a Chaos Monkey-inspired, proactive and invasive testing approach.
 * [Wiremock](http://wiremock.org/) - API mocking (Service Virtualization) which enables modeling real world faults and delays
 * [MockLab](http://get.mocklab.io/) - API mocking (Service Virtualization) as a service which enables modeling real world faults and delays.
 * [Pod-Reaper](https://github.com/target/pod-reaper) - A rules based pod killing container. Pod-Reaper was designed to kill pods that meet specific conditions that can be used for Chaos testing in Kubernetes.
 * [Muxy](https://github.com/mefellows/muxy/) - A chaos testing tool for simulating a real-world distributed system failures.
 * [Toxiproxy](https://github.com/Shopify/toxiproxy) - A TCP proxy to simulate network and system conditions for chaos and resiliency testing.
 * Chaos engineering for Docker:
 * [Pumba](https://github.com/gaia-adm/pumba) - Chaos testing and network emulation for Docker containers (and clusters).
 * [Blockade](https://github.com/worstcase/blockade) - Docker-based utility for testing network failures and partitions in distributed applications.
 * [Chaos Lambda](https://github.com/bbc/chaos-lambda) - Randomly terminate ASG instances during business hours.
 * [Namazu](https://github.com/osrg/namazu) - Programmable fuzzy scheduler for testing distributed systems.
 * [Chaos Monkey for Spring Boot](https://codecentric.github.io/chaos-monkey-spring-boot/) - Injects latencies, exceptions, and terminations into Spring Boot applications
 * [Byte-Monkey](https://github.com/mrwilson/byte-monkey) - Bytecode-level fault injection for the JVM. It works by instrumenting application code on the fly to deliberately introduce faults like exceptions and latency.
 * [GomJabbar](https://github.com/outbrain/GomJabbar) - ChaosMonkey for your private cloud
 * [Turbulence](https://github.com/cppforlife/turbulence-release) - Tool focused on BOSH environments capable of stressing VMs, manipulating network traffic, and more. It is very simmilar to Gremlin.
 * [ChaosBlade](https://github.com/chaosblade-io/chaosblade) - Chaosblade is an experimental tool that follows the principles of Chaos Engineering and is used to simulate common fault scenarios, helping to improve the recoverability of faulty systems and the fault tolerance of faults.
 * [KubeInvaders](https://github.com/lucky-sideburn/KubeInvaders) - Gamfied Chaos engineering tool for Kubernetes Clusters
 * [Cthulhu](https://github.com/xmatters/cthulhu-chaos-testing) - Chaos Engineering tool that helps evaluating the resiliency of microservice systems simulating various disaster scenarios against a target infrastructure in a data-driven manner.
 * [VMware Mangle](https://vmware.github.io/mangle/) - Orchestrating Chaos Engineering.
 * [Byteman](https://byteman.jboss.org/) - A Swiss Army Knife for Byte Code Manipulation.
 * [Litmus](https://github.com/litmuschaos/litmus) - Framework for Kubernetes environments that enables users to run test suites, capture logs, generate reports and perform chaos tests.
 * [Perses](https://github.com/nicolasmanic/perses) - A project to cause (controlled) destruction to a JVM application.
 * [ChaosKube](https://github.com/linki/chaoskube) - chaoskube periodically kills random pods in your Kubernetes cluster.

## Cloud Services

 * [Testing Amazon Aurora Using Fault Injection Queries](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/AuroraMySQL.Managing.html#AuroraMySQL.Managing.FaultInjectionQueries)
 * [Azure Fault Analysis Service](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-testability-overview), see also [Include controlled Chaos in Service Fabric clusters](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-controlled-chaos)

## References

 * https://raw.githubusercontent.com/dastergon/awesome-chaos-engineering/master/README.md
 * [Maelstrom: Mitigating Datacenter-level Disasters by Draining Interdependent Traffic Safely and Efficiently](https://www.usenix.org/system/files/osdi18-veeraraghavan.pdf)
 * [Simple Testing Can Prevent Most Critical Failures: An Analysis of Production Failures in Distributed Data-Intensive Systems](https://www.usenix.org/system/files/conference/osdi14/osdi14-paper-yuan.pdf)
 * [Automating Failure Testing Research at Internet Scale ](https://people.ucsc.edu/~palvaro/fit-ldfi.pdf)
 * [Principles of Antifragile Software](https://arxiv.org/abs/1404.3056)
 * [Why is random testing effective for partition tolerance bugs?](https://dl.acm.org/citation.cfm?id=3177123.3158134)
 * [Chaos Engineering](https://arxiv.org/abs/1702.05843)
 * [A Platform for Automating Chaos Experiments](https://arxiv.org/abs/1702.05849)
 * [A Chaos Engineering System for Live Analysis and Falsification of Exception-handling in the JVM](https://arxiv.org/abs/1805.05246)
 * [TripleAgent: Monitoring, Perturbation And Failure-obliviousness for Automated Resilience Improvement in Java Applications](https://arxiv.org/abs/1812.10706)
 * [Lineage-driven Fault Injection](https://dl.acm.org/citation.cfm?id=2723711)
 * [Chaos Engineering: Building Confidence in System Behavior through Experiment](http://www.oreilly.com/webops-perf/free/chaos-engineering.csp)
 * [Site Reliability Engineering: How Google Runs Production Systems](https://landing.google.com/sre/book.html) -
 * [The Practice Of Cloud System Administration: Designing and Operating Large Distributed Systems](http://the-cloud-book.com/)
 * [Antifragile Systems and Teams](http://www.oreilly.com/webops-perf/free/antifragile-systems-and-teams.csp)
 * [The InfoQ eMag: Chaos Engineering](https://www.infoq.com/minibooks/emag-chaos-engineering)
 * [Learning Chaos Engineering](http://shop.oreilly.com/product/0636920251897.do)

## License

[![CC0](https://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0)

## Contributing

 Contributions welcome! Read the [contribution guidelines](CONTRIBUTING.md) first.

 Feel free to [open an issue](https://github.com/adriannovegil/awesome-observability/issues) or [create a pull request](https://github.com/adriannovegil/awesome-observability/pulls) with your additions.

 Thank you!
