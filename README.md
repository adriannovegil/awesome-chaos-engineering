# Awesome Chaos Engineering

Testing in production (TiP) is gaining steam as an accepted practice in DevOps and testing communities, but no amount of preproduction QA testing can foresee all the possible scenarios in your real production deployment.

The prevailing wisdom is that you will see failures in production; the only question is whether you'll be surprised by them or inflict them intentionally to test system resilience and learn from the experience.

The latter approach is chaos engineering.

> To understand all this knowledge is very important have a good background in Chaos Engineering, containers, fault injection, monitoring and observability.

__Introduction__

One of the earliest examples of a chaos fault injection was disabling servers using a tool created by Netflix called Chaos Monkey. Chaos Monkey worked by randomly disabled ___production server___ instances to ensure that they could handle such failure scenarios.

Similarly, for ___Kubernetes___ there are tools targeting deleting pods, such as Kube-monkey, Target’s Pod-reaper and Powerfulseal made by Bloomberg.

For ___Docker___ a tool called Pumba by A. Ledenev can target containers and for Docker Swarm the docker-chaosmonkey can target services.

Other tools in this area include BBC’s Chaos Lamdba for terminating ___EC2 instances___ and GomJabbar for targeting ___private clouds___.

Chaos related fault injection can also be done on a more ___application specific level___. Two such system are ChaosMachine and TripleAgent targeting JVM based applications.

The ___network layer___ is another fault injection vector with a lot of support from tools. Quite a few of them utilize Iptables in combination with Traffic Control network emulation to inject different kinds of network failures including latency and dropping a percentage of traffic.

Open-source examples include Netflix’s Latency Monkey, Pumba, Blockade, Muxy, and Comcast.

Some ___close-source alternatives___ are Gremlin and ChaosCat. All tools are capable to be used either directly with a deployment environment or with some setup.

For more resource based injection, at the ___level of CPU, RAM, disk and similar___, there are tools that can help with this. Gremlin, for example, can execute several such attacks, both ChaosCat and a dedicated tools like cpu-troll can facilitate the execution of CPU usage attacks.

## 1. Principles of Chaos Engineering

A chaos experiment is defined as the following five points by the Principles of chaos engineering

 * Build a Hypothesis around Steady State Behavior
 * Vary Real-world Events
 * Run Experiments in Production
 * Automate Experiments to Run Continuously
 * Minimize Blast Radius

More details in the following link ;-)

 * [PRINCIPLES OF CHAOS ENGINEERING](https://principlesofchaos.org/?lang=ENcontent)

## 2. Fault Injection

### Generic Tools

 * [The Simian Army](https://github.com/Netflix/SimianArmy) - A suite of tools for keeping your cloud operating in top form.
 * [Chaos Monkey](https://github.com/Netflix/chaosmonkey) - A resiliency tool that helps applications tolerate random instance failures.
 * [Chaos Toolkit](https://github.com/chaostoolkit/chaostoolkit) - A chaos engineering toolkit to help you build confidence in your software system.
 * [Chaos Toolkit Turbulence](https://github.com/tmobile/chaostoolkit-turbulence) - This is an extension for Chaos Toolkit which adds support for Turbulence attacks.
 * [Monarch](https://github.com/tmobile/monarch) - This is a series of tools for Chaos Toolkit
 * [Muxy](https://github.com/mefellows/muxy/) - A chaos testing tool for simulating a real-world distributed system failures.
 * [Chaos Blade](https://github.com/chaosblade-io/chaosblade) - Chaosblade is an experimental tool that follows the principles of Chaos Engineering and is used to simulate common fault scenarios, helping to improve the recoverability of faulty systems and the fault tolerance of faults.
 * [Cthulhu](https://github.com/xmatters/cthulhu-chaos-testing) - Chaos Engineering tool that helps evaluating the resiliency of microservice systems simulating various disaster scenarios against a target infrastructure in a data-driven manner.
 * [Namazu](https://github.com/osrg/namazu) - Programmable fuzzy scheduler for testing distributed systems.  
 * [Chaos Scimmia](https://github.com/joshuamckenty/chaos-scimmia) - Chaos Engineering for Redis
 * [HavocLeopard](https://github.com/jonfast565/HavocLeopard) - A set of simple chaos engineering apps that can be used to royally screw up your on-prem servers
 * [Arcdata](https://github.com/redcross/arcdata) - Open source incident management and volunteer scheduling application for Red Cross Disaster Services
 * [AWS Chaos Scripts](https://github.com/adhorn/aws-chaos-scripts) - Collection of python scripts to run failure injection on AWS infrastructure

### CPU's

### Memory

### File system

### Disk

### Networking

 * [Toxiproxy](https://github.com/Shopify/toxiproxy) - A TCP proxy to simulate network and system conditions for chaos and resiliency testing.

### Security

 * [Infection Monkey](https://github.com/guardicore/monkey) - Open source security tool for testing a data center's resiliency to perimeter breaches and internal server infection. The Monkey uses various methods to self propagate across a data center and reports success to a centralized Monkey Island server.
 * [ChaoSlingr](https://github.com/Optum/ChaoSlingr) - Introducing Security Chaos Engineering. ChaoSlingr focuses primarily on the experimentation on AWS Infrastructure to proactively instrument system security failure through experimentation.
 * [What is security chaos engineering and why is it important?](https://hub.packtpub.com/what-is-security-chaos-engineering-and-why-is-it-important/)
 * [Security Chaos Engineering: A new paradigm for cybersecurity](https://opensource.com/article/18/1/new-paradigm-cybersecurity)
 * [Injecting chaos experiments into security log pipelines](https://opensource.com/article/18/9/injecting-chaos-experiments-security-log-pipelines)
 * [Purple testing and chaos engineering in securityexperimentation](https://opensource.com/article/18/6/security-experimentation)
 * [A new approach to security instrumentation](https://opensource.com/article/18/4/new-approach-security-instrumentation)

### Languages

#### Compilation time

 * [ChaosCat](https://github.com/Torvaney/chaoscat) - Chaos engineering for Pull Requests - Taking a not-even-good joke a bit too far

#### Run time

 * [Byteman](https://byteman.jboss.org/) - A Swiss Army Knife for Byte Code Manipulation.
 * [Byte-Monkey](https://github.com/mrwilson/byte-monkey) - Bytecode-level fault injection for the JVM. It works by instrumenting application code on the fly to deliberately introduce faults like exceptions and latency.
 * [Perses](https://github.com/nicolasmanic/perses) - A project to cause (controlled) destruction to a JVM application.
 * [Wiremock](http://wiremock.org/) - API mocking (Service Virtualization) which enables modeling real world faults and delays
 * [MockLab](http://get.mocklab.io/) - API mocking (Service Virtualization) as a service which enables modeling real world faults and delays.
 * [Flaw](https://github.com/GaruGaru/flaw) - Inject failures on api calls for local chaos engineering
 * [Havoc](https://github.com/bchavez/Havoc) - Havoc is a collection of dangerous code that wreck havoc in .NET applications and the operating system for chaos-engineering.
 * [Utilities for frontend chaos engineering](https://github.com/jchiatt/chaos) - Utilities for frontend chaos engineering.
 * [CHAOS GOPHER](https://github.com/chaostesting/chaosgopher) - A collection of unix style tools in GO to do chaos engineering or testing.
 * [Chaos Monkey for Spring Boot](https://codecentric.github.io/chaos-monkey-spring-boot/) - Injects latencies, exceptions, and terminations into Spring Boot applications
 * [React Chaos](https://github.com/jchiatt/react-chaos) - Chaos Engineering for your React apps.
 * [Chaos QoaLa](https://github.com/oslabs-beta/ChaosQoaLa) - ChaosQoaLa is a chaos engineering tool for injecting failure into JavaScript backed GraphQL end points.
 * [Chaos Reverse-engineering](https://github.com/pcoppens/chaos-re) - Chaos engineering approach by Reverse-engineering.

### Application

### Kernel & Operating System

### Containers & Orchestrators

 * [Royal Chaos](https://github.com/KTH/royal-chaos) - This repository contains the chaos engineering systems invented at KTH Royal Institute of Technology.
 * [Pumba](https://github.com/gaia-adm/pumba) - Chaos testing and network emulation for Docker containers (and clusters).
 * [Blockade](https://github.com/worstcase/blockade) - Docker-based utility for testing network failures and partitions in distributed applications.
 * [Chaos Engineering for Docker](https://github.com/cloudchaos/docker) - Chaos Engineering for Docker
 * [Chaos Engineering with Docker EE](https://github.com/sameerkasi200x/docker-chaos-engineering) - Chaos Engineering with Docker EE
 * [Chaos Util](https://github.com/abnamrocoesd/chaos-util) - Docker image with utilities for Chaos Engineering
 * [Drax](https://github.com/dcos-labs/drax) -  DC/OS Resilience Automated Xenodiagnosis tool. It helps to test DC/OS deployments by applying a Chaos Monkey-inspired, proactive and invasive testing approach.
 * [Pod-Reaper](https://github.com/target/pod-reaper) - A rules based pod killing container. Pod-Reaper was designed to kill pods that meet specific conditions that can be used for Chaos testing in Kubernetes.
 * [Chaoskube](https://github.com/linki/chaoskube) - chaoskube periodically kills random pods in your Kubernetes cluster.
 * [Litmus](https://github.com/litmuschaos/litmus) - Framework for Kubernetes environments that enables users to run test suites, capture logs, generate reports and perform chaos tests.
 * [Chaos Operator](https://github.com/litmuschaos/chaos-operator) - Chaos engineering via kubernetes operator
 * [Kube Entropy](https://github.com/alexlokshin/kube-entropy) - A little chaos engineering application for kubernetes resilience testing.
 * [Chaos Coordinator](https://github.com/UtheMan/chaoscoordinator) - Chaos Coordinator is a set of tools that allow for chaos testing of the infrastructure used by Kubernetes clusters on Azure.
 * [kubernetes-chaos-lab](https://github.com/matthewbrahms/kubernetes-chaos-lab) - A brief guide to setting up your first chaos engineering lab on Kubernetes!
 * [Chaos Mesh](https://github.com/pingcap/chaos-mesh) - A Chaos Engineering Platform for Kubernetes

### Hypervisors

 * [VMware Mangle](https://vmware.github.io/mangle/) - Orchestrating Chaos Engineering.
 * [Turbulence](https://github.com/cppforlife/turbulence-release) - Tool focused on BOSH environments capable of stressing VMs, manipulating network traffic, and more. It is very simmilar to Gremlin.

### Cloud

 * [Glooshot](https://github.com/solo-io/glooshot) - Chaos engineering framework to help you Immunize your service mesh
 * [kube-monkey](https://github.com/asobti/kube-monkey) - An implementation of Netflix's Chaos Monkey for Kubernetes clusters.
 * [Powerful Seal](https://github.com/bloomberg/powerfulseal) - PowerfulSeal adds chaos to your Kubernetes clusters, so that you can detect problems in your systems as early as possible. It kills targeted pods and takes VMs up and down.
 * [KubeInvaders](https://github.com/lucky-sideburn/KubeInvaders) - Gamfied Chaos engineering tool for Kubernetes Clusters
 * [Testing Amazon Aurora Using Fault Injection Queries](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/AuroraMySQL.Managing.html#AuroraMySQL.Managing.FaultInjectionQueries) - Testing Amazon Aurora Using Fault Injection Queries
 * [Azure Fault Analysis Service](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-testability-overview)
 * [Include controlled Chaos in Service Fabric clusters](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-controlled-chaos) - Include controlled Chaos in Service Fabric clusters
 * [Chaos Lambda](https://github.com/bbc/chaos-lambda) - Randomly terminate ASG instances during business hours.
 * [GomJabbar](https://github.com/outbrain/GomJabbar) - ChaosMonkey for your private cloud
 * [Chaos Engineering on Google Cloud Platform](https://github.com/cloudchaos/google-cloud-platform) - Chaos Engineering on Google Cloud Platform
 * [Chaos SSM Documents](https://github.com/adhorn/chaos-ssm-documents) - Collection of AWS SSM Documents to perform Chaos Engineering experiments

### Examples Projects

 * [A Chaos Engineering Bootcamp](https://github.com/tammybutow/chaosengineeringbootcamp) - A Chaos Engineering Bootcamp
 * [HW4](https://github.com/kbalakr/Chaos-Engineering---DevOps-Demo) - Express servers were used to implement service topologies
 * [Serverless Chaos Engineering Demo](https://github.com/gunnargrosch/serverless-chaos-demo) - This example demonstrates how to use Adrian Hornsby's Failure Injection Layer (https://github.com/adhorn/FailureInjectionLayer) to perform chaos engineering experiments on a serverless environment.
 * [Chaos Engineeing Demo](https://github.com/fazdevils/chaos-engineeing-demo) - Simple project demonstrating chaos engineering with Chaos Monkey and Resiliance4J
 * [Chaos Engineering Demo](https://github.com/ericwyles/chaos-engineering-demo) - resilience4j + chaos toolkit + wiremock + chaos monkey for spring boot sample application
 * [How to Create a Kubernetes Cluster on Ubuntu 16.04 with kudeadm and Weave Net](https://www.gremlin.com/community/tutorials/how-to-create-a-kubernetes-cluster-on-ubuntu-16-04-with-kudeadm-and-weave-net/)

## 3. Observability

### Specific tools

### General Use

 * [My Awesome Observability Repo ;-)](https://github.com/adriannovegil/awesome-observability)

## 4. Incident Management Tool

 * [Banjaxed](https://github.com/intercom-archive/banjaxed) - Open source incident management tool

## 5. Cost of SEVs

 * [Availability Calculator](https://github.com/dastergon/availability-calculator) - Calculate how much downtime should be permitted in your SLA

## 6. Chaos As A Sevice

  * [Gremlin Inc.](https://www.gremlin.com/) - Failure as a Service.
  * [Chaos Engineering Experiment Automation](https://chaostoolkit.org/) - Chaos Engineering Experiment Automation
  * [Pystol.org](https://www.pystol.org/) - THE CLOUD CHAOS ENGINEERING TOOLBOX
  * [Cyphon](https://github.com/dunbarcyber/cyphon) - Open source incident management and response platform
  * [Controlled Chaos](https://github.com/DylanCauwels/ControlledChaos) - An all-in-one application that allows teams to create, execute, and analyze chaos engineering experiments with no previous DevOps experience or additional infrastructure setup.
  * [Chaos Platform](https://github.com/chaostoolkit/chaosplatform) - Chaos Engineering Platform for Everyone
  * [Chaos Hub](https://github.com/chaostoolkit/chaoshub-archive) - Chaos Hub stands on the shoulders of the Chaos Toolkit to provide a complete, user-friendly, platform to automate and collaborate on your Chaos Engineering and Resiliency efforts.

## 7. Gamedays

 * [Target: What is a Gameday?](https://tech.target.com/2019/05/09/chaos-engineering-at-Target.html) - Chaos Gamedays experience by Target.
 * [Codecentric: Chaos Engineering Gamedays](https://blog.codecentric.de/en/2018/08/chaos-engineering-gameday/) - Chaos Gamedays by Codecentric.
 * [New Relic: How to run a Gameday?](https://blog.newrelic.com/engineering/how-to-run-a-game-day/) - Chaos Gamedays experience by New Relic.
 * [Dius: Gamedays resources](https://dius.com.au/resources/game-day/) - Resources for getting started with GameDay and Chaos Engineering.
 * [Gremlin: Gamedays](https://www.gremlin.com/gameday/) - Resources for getting started with GameDay and Chaos Engineering.
 * [Gremlin: What is a Chaos Day?](https://www.gremlin.com/community/tutorials/planning-your-own-chaos-day/#what-is-a-chaos-day) - What is a Gameday according Gremlin.
 * [Gremlin: Why run a Chaos Day?](https://www.gremlin.com/community/tutorials/planning-your-own-chaos-day/#why-run-a-chaos-day) - Reasons to run Gamedays according Gremlin.
 * [Gremlin: How to run a Gameday?](https://www.gremlin.com/community/tutorials/how-to-run-a-gameday/) - Methodology to run Gamedays according Gremlin.
 * [Gremlin DB: Breaking Dynamo DB](https://www.gremlin.com/community/tutorials/gremlin-gameday-breaking-dynamodb/) - Example of a Gameday with DynamoDB by Gremlin.
 * [Gremlin: Introduction to Gameday](https://www.gremlin.com/community/tutorials/introduction-to-gamedays/) - What is a Gameday according Gremlin.
 * [Gremlin: Planning your own Chaos Day](https://www.gremlin.com/community/tutorials/planning-your-own-chaos-day/) - Example of a Gameday with DynamoDB by Gremlin.
 * [Gremlin: Inside Gremlin 2019 Gremlin Gamedays Roadmap](https://www.gremlin.com/community/tutorials/inside-gremlin-2019-gremlin-gamedays-roadmap/) - Chaos Gamedays experience by Gremlin.
 * [Gremlin: What I lerned running the Chaos Lab with Kafka](https://www.gremlin.com/community/tutorials/what-i-learned-running-the-chaos-lab-kafka-breaks/) - Example of a Gameday with Kafka by Gremlin.
 * [Chaos Toolkit: Chaos Engineering with Humans in the loop](https://medium.com/chaos-toolkit/chaos-engineering-with-humans-in-the-loop-f4854900b1eb) - Article about Chaos Gamedays.
 * [GooCardless: All fun and games until you start with Gamedays](https://gocardless.com/blog/game-days-at-gc/) - Article about Chaos Gamedays.
 * [InfoQ: Gamedays - Achieving Resilience through Chaos Engineering](https://www.infoq.com/presentations/gameday-chaos-engineering) - InfoQ Presentation with experiences about Chaos Gamedays.

## 8. Forums and Groups

 * [Working Group Proposal](https://github.com/chaoseng/wg-chaoseng) - Working Group Proposal: Chaos Engineering
 * [Chaos Community Google Group](https://groups.google.com/forum/#!forum/chaos-community)
 * [Chaos Engineering LinkedIn Group](https://www.linkedin.com/groups/7057761)
 * [Chaos Engineering Slack Community](https://gremlin.com/community)
 * [CNCF Chaos Engineering Working Group](https://groups.google.com/forum/#!forum/chaoseng-wg)
 * CNCF Chaos Engineering Working Group Slack: #chaosengineering (slack.cncf.io)
 * [CNCF Chaos Engineering Working Group Github](https://github.com/chaoseng/wg-chaoseng)
 * [Chaos Toolkit Slack Community](https://join.chaostoolkit.org)

## 9. References

 * https://github.com/chaoseng/wg-chaoseng/blob/master/WHITEPAPER.md
 * https://docs.google.com/document/d/1BeeJZIyReCFNLJQrZjwA4KMlUJelxFFEv3IwED16lHE/edit?ts=5ace0eab#heading=h.ephtflhfpd1d
 * https://github.com/dastergon/awesome-chaos-engineering
 * https://techbeacon.com/app-dev-testing/chaos-engineering-testing-34-tools-tutorials
 * https://github.com/dastergon/awesome-chaos-engineering
 * https://www.techrepublic.com/article/chaos-engineering-a-cheat-sheet/
 * https://medium.com/capital-one-tech/4-real-world-scenarios-that-read-like-chaos-engineering-experiments-8dbf40c5f247
 * https://thenewstack.io/gremlins-tammy-butow-on-the-business-side-of-chaos-engineering/
 * https://learnk8s.io/blog/kubernetes-chaos-engineering-lessons-learned
 * https://gocardless.com/blog/game-days-at-gc/
 * https://engineering.grab.com/chaos-engineering
 * https://blog.newrelic.com/engineering/chaos-engineering-explained/
 * https://slack.engineering/disasterpiece-theater-slacks-process-for-approachable-chaos-engineering-3434422afb54
 * https://www.usenix.org/system/files/osdi18-veeraraghavan.pdf
 * https://www.usenix.org/system/files/conference/osdi14/osdi14-paper-yuan.pdf
 * https://people.ucsc.edu/~palvaro/fit-ldfi.pdf
 * https://landing.google.com/sre/book.html
 * http://the-cloud-book.com/
 * https://www.infoq.com/minibooks/emag-chaos-engineering
 * https://www.pagerduty.com/blog/failure-fridays-four-years/
 * https://www.slideshare.net/zgrinch/monkeys-lemurs-and-locusts-oh-my
 * https://www.cloudreach.com/fr/blog/training-cloud-operations-teams-met-office/
 * https://softwareengineeringdaily.com/2018/02/02/chaos-engineering-with-kolton-andrus/
 * https://blog.codeship.com/embracing-the-chaos-of-chaos-engineering/
 * https://sharpend.io/chaos-monkey-for-fun-and-profit/
 * https://queue.acm.org/detail.cfm?id=2353017
 * https://dl.acm.org/citation.cfm?id=3177123.3158134
 * https://dl.acm.org/citation.cfm?id=2723711
 * https://azure.microsoft.com/en-us/blog/inside-azure-search-chaos-engineering/
 * https://devops.com/netflix-the-simian-army-and-the-culture-of-freedom-and-responsibility/
 * http://www.oreilly.com/webops-perf/free/chaos-engineering.csp
 * http://www.oreilly.com/webops-perf/free/antifragile-systems-and-teams.csp
 * http://shop.oreilly.com/product/0636920251897.do
 * https://www.gremlin.com/community/tutorials/chaos-engineering-the-history-principles-and-practice/
 * https://www.gremlin.com/blog/the-discipline-of-chaos-engineering/
 * http://kth.diva-portal.org/smash/get/diva2:1366436/FULLTEXT01.pdf
 * https://arxiv.org/pdf/1907.13039.pdf
 * https://arxiv.org/abs/1404.3056
 * https://arxiv.org/abs/1702.05843
 * https://arxiv.org/abs/1702.05849
 * https://arxiv.org/abs/1805.05246
 * https://arxiv.org/abs/1812.10706
 * https://medium.com/@bbideep/why-should-chaos-be-part-of-your-distributed-systems-engineering-5bcb21497660
 * https://medium.com/@njones_18523/chaos-engineering-traps-e3486c526059
 * https://medium.com/@adhorn/chaos-engineering-ab0cc9fbd12a
 * https://medium.com/netflix-techblog/fit-failure-injection-testing-35d8e2a9bb2
 * https://medium.com/netflix-techblog/the-netflix-simian-army-16e57fbab116
 * https://medium.com/netflix-techblog/automated-failure-testing-86c1b8bc841f
 * https://medium.com/netflix-techblog/chaos-engineering-upgraded-878d341f15fa
 * https://medium.com/netflix-techblog/chap-chaos-automation-platform-53e6d528371f
 * https://medium.com/@crochefolle/how-to-convince-your-boss-to-make-them-say-yes-to-chaos-engineering-796ba119bd7
 * https://medium.com/chaosiq/cloud-native-and-chaos-engineering-20842ee2fa8a
 * https://www.wired.com/story/netflix-ddos-attack/
 * https://github.com/gremlin/chaos-engineering-tools
 * https://github.com/greenlearner01/Chaos-Engineering/blob/master/Chaos-Engineering.md

## 10. License

[![CC0](https://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0)

## 11. Contributing

Contributions welcome! Read the [contribution guidelines](CONTRIBUTING.md) first.

Feel free to [open an issue](https://github.com/adriannovegil/awesome-observability/issues) or [create a pull request](https://github.com/adriannovegil/awesome-observability/pulls) with your additions.

Thank you!
