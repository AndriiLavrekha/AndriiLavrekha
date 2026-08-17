# Andrii Lavrekha

> **[Unverified]** This profile is reconstructed from my professional experience and projects as described across my own notes and discussions. Exact employment dates, titles, and individual technology claims should be cross-checked against my current CV before being treated as authoritative.

## About me

I am a software, tools, build, DevOps, and platform engineer based in Berlin, Germany, with a large part of my professional experience centered around **game-development infrastructure, Unreal Engine, developer tooling, build systems, automation, CI/CD, and engineering productivity**.

I tend to work in the space between traditional software engineering and infrastructure engineering.

I am interested not only in writing software, but in understanding the entire system around it:

* How developers get the source code.
* How assets are stored and versioned.
* How a workstation is configured.
* How an Unreal Engine project is compiled.
* How distributed compilation works.
* How builds are generated.
* How artifacts are stored.
* How CI decides what to build.
* How developers receive those builds.
* How problems are diagnosed.
* How logs and metrics are collected.
* How infrastructure behaves across multiple offices.
* How permissions are delegated.
* How repetitive operational work can be automated.
* How all of this can remain understandable six months later when somebody else has to maintain it.

That last part matters to me.

I do not consider infrastructure successful merely because it works today.

I want systems that engineers can **understand, diagnose, modify, automate, and operate without tribal knowledge**.

---

# What I do

My work generally falls into several overlapping areas:

### Build Engineering

I design and maintain systems responsible for compiling, packaging, distributing, retaining, and diagnosing software builds.

### DevOps / Platform Engineering

I work on the infrastructure connecting source control, CI/CD, compute resources, build machines, storage, developer workstations, automation, monitoring, and internal services.

### Tools Engineering

I create tools that remove repetitive work from developers, artists, build engineers, and DevOps teams.

### Unreal Engine Infrastructure

A significant part of my recent work concerns the infrastructure surrounding large Unreal Engine projects rather than only gameplay code.

This includes:

* Unreal Build Tool
* Unreal Automation Tool
* BuildGraph
* Unreal Build Accelerator
* Horde
* Horde Agents
* Horde Server
* Zen Server
* Derived-data infrastructure
* distributed compilation
* CI/CD
* editor infrastructure
* build farms
* packaged builds
* telemetry
* log analysis
* Perforce integration
* multi-project Unreal environments

### Automation Engineering

If a task follows deterministic rules and somebody performs it repeatedly by hand, I will usually start asking why software is not doing it.

---

# Professional focus

The roles that best describe the work I am interested in are:

* Senior Build Engineer
* Senior DevOps Engineer
* Platform Engineer
* Tools Programmer
* Developer Infrastructure Engineer
* Automation Engineer
* Unreal Engine Infrastructure Engineer
* CI/CD Engineer
* Developer Productivity Engineer

My strongest area is the intersection between these roles.

I am particularly useful in environments where there are:

* large repositories,
* large Unreal Engine projects,
* expensive builds,
* many developers,
* multiple studios,
* build farms,
* distributed compilation,
* Perforce,
* CI/CD,
* custom internal tooling,
* infrastructure accumulated over many years,
* and operational problems that cross several systems at once.

---

# Unreal Engine engineering

Unreal Engine infrastructure is one of my strongest technical areas.

My work is generally less about implementing gameplay features and more about understanding everything that surrounds the engine from a developer-infrastructure perspective.

I work with concepts and systems including:

* Unreal Engine 5
* multiple simultaneous UE projects
* projects running different UE versions
* source-built Unreal Engine
* custom engine branches
* Unreal Build Tool
* Unreal Automation Tool
* BuildGraph
* Unreal Build Accelerator
* Horde
* Horde Server
* Horde Agents
* Zen Server
* CI/CD integration
* distributed compilation
* editor workflows
* build artifacts
* project packaging
* developer workstations
* build telemetry
* build logs
* engine/version inconsistencies
* asset-related build problems
* Derived Data Cache-related infrastructure

I have worked with environments containing **many Unreal Engine projects simultaneously**, including projects running different engine versions.

That changes the infrastructure problem significantly.

The question stops being:

> "How do we configure Unreal Engine?"

and becomes:

> "How do we build a platform where many Unreal projects, engine branches, teams, offices and pipelines can coexist without every project becoming its own isolated infrastructure island?"

That is the type of problem I enjoy.

---

# Epic Horde

One of my current areas of work is **Epic Games Horde**.

I have been working on architecture for deploying Horde in environments where multiple Unreal Engine projects coexist and where an organization may currently depend on Jenkins or TeamCity.

My interests around Horde include:

* Horde Server architecture
* Horde agents
* agent pools
* distributed compilation
* Unreal Build Accelerator
* BuildGraph integration
* CI pipelines
* project isolation
* multi-project Horde deployments
* different Unreal Engine versions
* telemetry
* build analytics
* migration from traditional CI systems
* integration with existing studio infrastructure

I am particularly interested in using Horde not simply as "another CI server", but as part of an Unreal-native developer infrastructure platform.

---

# Zen Server

I also work with Unreal Engine's **Zen Server** infrastructure.

My work and investigations include both:

* standalone/shared Zen deployments
* Zen instances running as part of Unreal development environments

I am interested in making Zen operationally observable instead of treating it as an opaque Unreal subsystem.

For example, when an asset repeatedly triggers compilation or processing because something believes that its version, engine state, or derived data is inconsistent, I want to be able to investigate:

* what Unreal believes about the asset,
* what Zen believes,
* where the relevant data came from,
* which engine version generated it,
* which changelist introduced it,
* whether the condition is machine-specific,
* whether it is project-specific,
* whether it affects the entire studio,
* and which logs or internal server state explain the behavior.

I have also explored the idea of exposing this diagnostic capability through **MCP-compatible tooling**, allowing engineering agents to inspect Zen infrastructure programmatically.

---

# Multi-site Unreal infrastructure

I have worked on architecture for Unreal Engine development across multiple physical studio locations.

One environment I have worked with includes sites in:

* Berlin
* Finland
* Bratislava

connected through studio networking, with central and local infrastructure responsibilities.

The architecture involves technologies such as:

* Perforce
* Horde
* Zen
* TeamCity
* Jenkins
* RoboMerge
* GitHub
* Gitea
* local build agents
* shared storage
* local caching
* central services

My preference in this kind of environment is generally a **central-control / local-execution architecture**.

Central systems are useful for things such as:

* policy
* source control
* pipeline definitions
* orchestration
* permissions
* build metadata

while latency-sensitive or bandwidth-heavy services can live closer to developers.

Examples include:

* Zen services near developers
* Horde agents near studios
* local caches
* local compute
* replicated or strategically placed storage

This architecture provides a useful balance between central governance and local performance.

---

# Perforce

Perforce is another major part of my game-development infrastructure experience.

I work with Perforce not simply as a source-control client but as an important component of studio architecture.

Areas I deal with include:

* Perforce users
* groups
* permissions
* streams
* ownership
* access delegation
* automation
* CLI workflows
* project isolation
* CI integration
* build integration

One principle I strongly prefer is **delegating the minimum operational capability necessary** instead of giving engineers broad administrative privileges.

For example, I have been designing workflows based on Perforce group ownership where selected DevOps or project representatives can manage the membership of specific groups without having access to the complete Perforce protection table.

Instead of giving somebody unrestricted administrative access simply because they need to add or remove developers from a project, the system can assign them ownership of the relevant groups.

They can then manage membership through controlled Perforce workflows while the global security model remains owned by the central infrastructure team.

This is representative of how I approach infrastructure design:

**give people the authority they require, but do not confuse operational responsibility with unrestricted administrative access.**

---

# CI/CD

I have substantial experience thinking about and working with CI/CD systems.

Technologies I have worked with or designed around include:

* TeamCity
* Jenkins
* Horde
* BuildGraph
* Perforce-triggered workflows
* GitHub-based workflows
* automation scripts
* build farms
* scheduled jobs
* retention jobs
* artifact publishing

I care about CI architecture beyond whether a pipeline becomes green or red.

A useful CI system should answer questions such as:

* What exactly was built?
* From which changelist?
* From which stream?
* Using which engine?
* Using which configuration?
* On which machine?
* Why was the build triggered?
* How long did every significant phase take?
* Where is the artifact?
* When does that artifact expire?
* Can somebody reproduce the build?
* Can we compare it with yesterday's build?
* What changed when compilation suddenly became 30% slower?

CI should produce information, not merely artifacts.

---

# Build infrastructure and artifact management

I have designed build-storage structures intended for studios generating many large artifacts.

One structure I have worked on consolidates builds under a common hierarchy such as:

`Projects / Project / Builds`

with build classification based on concepts such as:

* CI
* Nightly
* Custom
* Milestone
* Stream
* Project
* Changelist or tag
* Platform
* Configuration
* Package

I care about artifact lifecycle because unmanaged build storage eventually becomes an infrastructure problem.

I have designed policies involving concepts such as:

* temporary builds retained for approximately 14–21 days,
* automated nightly cleanup,
* creation-date-based retention,
* preservation of selected successful builds,
* Friday build archival,
* longer-lived `BuildArchive` storage,
* configurable archival based on stream/platform/configuration,
* hard archive retention limits,
* dry-run modes before destructive cleanup,
* explicit ownership of retention policy.

This is an example of something I consider important in engineering:

**automation should have policy behind it.**

A cron job deleting directories is not a retention strategy.

---

# Observability and telemetry

I have been working on approaches for collecting engineering metrics from Unreal Engine developer workstations and build infrastructure.

The goal is not surveillance of developers.

The goal is understanding the engineering system.

Examples of useful data include:

* build duration
* compilation duration
* Unreal Build Tool timing
* Unreal Automation Tool timing
* build failures
* cache performance
* distributed compilation performance
* shader-related activity
* editor startup
* machine utilization
* build queue times
* project differences
* engine-version differences
* recurring infrastructure failures

I have explored architectures involving:

* Unreal Engine plugins
* local workstation collectors
* log parsing
* Unreal Build Tool logs
* Horde telemetry
* Grafana
* Loki
* Elasticsearch
* centralized metric ingestion
* structured event pipelines

My preferred direction is generally **low-overhead collection close to the source, centralized storage, and independent visualization/analysis**.

Instrumentation should not materially interfere with the workload it is measuring.

---

# Developer productivity

Developer productivity is one of the recurring themes across my work.

I am interested in finding engineering problems that quietly waste hundreds or thousands of hours across an organization.

For example:

* slow builds,
* unnecessary recompilation,
* unreliable CI,
* inconsistent environments,
* difficult permission management,
* duplicated infrastructure,
* unclear build naming,
* missing telemetry,
* repetitive administrative work,
* logs nobody can practically investigate,
* systems requiring one specific person to understand them.

A ten-minute problem repeated by 100 developers every day is no longer a small problem.

It is infrastructure.

---

# Automation

Automation is one of the strongest recurring patterns in how I work.

I build or design automation around:

* build systems
* CI/CD
* source control
* access management
* artifact retention
* telemetry
* reporting
* email workflows
* scheduled processes
* log processing
* OCR
* data extraction
* engineering agents

My general approach is:

1. Understand the manual process.
2. Identify the source of truth.
3. Define deterministic rules.
4. Separate policy from implementation.
5. Automate the repetitive part.
6. Keep logs and diagnostics.
7. Make failure visible.
8. Keep destructive operations controlled.
9. Document how the system works.

---

# AI-assisted engineering and engineering agents

I am actively experimenting with AI-assisted engineering.

I am especially interested in **agents that interact with real engineering infrastructure rather than agents that only generate source code**.

Examples of systems I have explored include agents connected to:

* Perforce
* TeamCity
* Horde
* Zen
* source repositories
* CI systems
* operational logs

I am interested in MCP-style interfaces where an engineering agent can inspect infrastructure through deliberately designed APIs and tools.

For example, instead of giving an AI system arbitrary machine access, I would rather expose operations such as:

* inspect a build
* query a changelist
* inspect a stream
* retrieve a log
* inspect Zen state
* check a Horde job
* retrieve build metadata
* identify the owner of a change
* compare build timing
* investigate a known failure

This provides much better control over what an agent can actually do.

---

# MCP

Model Context Protocol is an area I am actively exploring for developer infrastructure.

I have worked on or designed ideas around MCP interfaces for:

* Perforce
* TeamCity
* Horde
* Zen Server

The interesting part for me is not MCP itself.

The interesting part is turning historically difficult infrastructure into something that both humans and engineering agents can query systematically.

A useful infrastructure MCP should expose **semantic engineering operations**, not merely wrap shell commands.

---

# AI / LLM-driven products

Alongside infrastructure engineering, I have chosen to invest heavily in building and shipping products powered by AI/LLMs — both commercial and free — for people who need the service they provide. This is a deliberate direction, not a side experiment.

A few examples (project names withheld here by choice, described by function instead):

* **A sentiment/mood-analysis platform for the LLM provider space.** It tracks and analyzes how people feel about LLM platform providers — e.g. OpenAI, Anthropic (Claude), and their respective models/APIs — surfacing shifts in public sentiment, recurring complaints, and emerging trends across a fast-moving, opinionated market.
* **A PDF editor**, close to public release, aimed at everyday document editing without the friction and cost of traditional PDF software.
* **Several unreleased projects** at the intersection of gaming and AI/LLMs, some of them oriented toward emotional support use cases — applying conversational AI where it can genuinely help people, not just automate a task.

I treat these the same way I treat infrastructure: understand the real problem first, then decide where AI/LLMs are the right tool versus a novelty bolted onto an existing workflow.

---

# OCR and information extraction

I have also worked extensively on OCR and information-extraction experiments.

One practical problem involved extracting code and technical text from large numbers of screenshots.

My experimentation has included:

* PaddleOCR
* CPU/GPU OCR
* image preprocessing
* OCR accuracy
* source-code extraction
* screenshot processing
* multi-image document reconstruction
* Markdown output
* local OCR pipelines
* OCR workflow automation
* processing large collections of images
* potentially extracting code from video frames

I am particularly interested in OCR when it becomes part of an automated information-recovery pipeline rather than a one-off image-to-text conversion.

For example:

`images → preprocessing → OCR → reconstruction → validation → structured text`

This kind of pipeline can recover useful information from documentation, screenshots, recordings, or legacy sources that do not exist as machine-readable text.

---

# n8n and workflow automation

I use and experiment with **n8n** as an orchestration platform.

I am interested in using it for workflows where n8n coordinates systems but does not necessarily perform every expensive operation itself.

Examples include:

* scheduled checks
* API integration
* event processing
* notifications
* email campaigns
* local services
* AI processing
* state tracking
* data collection

I have worked on architectures where n8n interacts with separate services or containers deployed on local infrastructure.

This separation is useful when a workload is computationally expensive or requires software that does not belong inside the workflow engine itself.

---

# Self-hosted infrastructure

I strongly value being able to run infrastructure locally when appropriate.

I work with or experiment with:

* Linux servers
* Windows workstations
* containers
* Unraid
* VPS infrastructure
* VPN
* WireGuard
* self-hosted services
* local AI tooling
* local OCR
* local source-control services
* GitHub/Gitea-style repository hosting
* network services

I do not automatically assume that SaaS is the correct answer.

Sometimes it is.

Sometimes running a small service internally is dramatically simpler, cheaper, more controllable, or better aligned with the data involved.

The decision should be architectural rather than ideological.

---

# Languages

Languages and scripting technologies I have worked with include:

* **C++**
* **C#**
* **Python**
* **Groovy**
* **JavaScript**
* **Go**
* **Kotlin**

My language choice is generally pragmatic.

For infrastructure and tooling work, I care more about:

* maintainability,
* deployment model,
* ecosystem,
* execution environment,
* team ownership,
* observability,
* and long-term support

than about using a particular programming language everywhere.

---

# Systems and technologies

My broader technical environment includes experience or active work around:

### Game development

* Unreal Engine
* Unreal Engine 5
* Unreal Build Tool
* Unreal Automation Tool
* BuildGraph
* Unreal Build Accelerator
* Horde
* Zen
* Derived-data infrastructure

### Source control

* Perforce
* Git
* GitHub
* Gitea

### CI/CD

* TeamCity
* Jenkins
* Horde
* automated build farms
* scheduled automation
* artifact management

### Programming

* C++
* C#
* Python
* Groovy
* JavaScript
* Go
* Kotlin

### Infrastructure

* Windows
* Linux
* containers
* VPS
* networking
* VPN
* WireGuard
* self-hosted services
* distributed systems

### Observability

* Grafana
* Loki
* Elasticsearch
* log processing
* metrics collection
* telemetry pipelines

### Automation / Integration

* n8n
* REST APIs
* CLI automation
* scheduled services
* custom tooling
* MCP

### AI / Data extraction

* engineering agents
* local AI tooling
* OCR
* PaddleOCR
* image processing
* automated information extraction

---

# How I approach engineering

## I start with the system, not the tool

I try not to begin architecture discussions with:

> "Let's deploy technology X."

I prefer starting with:

> "What problem are we actually trying to solve?"

Only after that should the technology be selected.

---

## I care about the operational path

I think about what happens after software is deployed.

Who operates it?

Who receives an alert?

Where are the logs?

What happens when the primary maintainer is on vacation?

How is configuration changed?

How do we migrate it?

How do we remove it?

How do we diagnose a partially broken state?

Those questions influence my architecture.

---

## I dislike black boxes

When infrastructure fails, I want enough information to understand why.

A system that responds with:

> "Something went wrong."

is not providing an engineering interface.

A useful system exposes enough context to investigate:

* inputs,
* outputs,
* timing,
* machine,
* version,
* changelist,
* dependency,
* logs,
* failure stage.

---

## I prefer boring infrastructure where boring works

I like new technology, but I do not think novelty is an architectural requirement.

A simple service with clear behavior is often better than a complicated platform introduced because it is fashionable.

Complexity needs to earn its place.

---

## I prefer incremental migration

Large infrastructure replacements are risky.

I prefer migration paths where old and new systems can coexist for a period of time.

For example:

`Jenkins / TeamCity → partial Horde adoption → broader Horde pipelines`

rather than an all-at-once rewrite of every pipeline.

This makes comparison, rollback, learning, and gradual adoption possible.

---

## I care about blast radius

Infrastructure permissions and destructive operations deserve additional thought.

Examples include:

* Perforce super-user access
* permission tables
* artifact deletion
* production configuration
* administrative APIs
* automated cleanup

I prefer narrow permissions and explicit ownership where possible.

---

## I like dry-run modes

Anything that automatically deletes, moves, rewrites, migrates, or modifies large amounts of data should ideally provide a way to inspect the proposed operation first.

This is particularly important for infrastructure automation.

---

## I care about naming and structure

Naming conventions are infrastructure.

A good directory hierarchy or build identifier can encode:

* project
* stream
* changelist
* platform
* configuration
* build type

and save engineers enormous amounts of investigation later.

I do not consider information architecture cosmetic.

---

# What I like

Professionally, I enjoy:

* difficult infrastructure problems
* developer tooling
* build engineering
* automation
* Unreal Engine internals
* diagnosing strange technical behavior
* distributed systems
* performance investigations
* observability
* internal platforms
* self-hosted systems
* engineering agents
* understanding how systems really work
* replacing repetitive processes with tooling
* connecting systems that were never originally designed to work together
* designing infrastructure for multiple projects rather than one-off solutions
* simplifying complicated operational workflows
* turning undocumented knowledge into explicit systems and documentation

I particularly enjoy problems where several layers interact.

For example:

`Developer → Unreal → UBT → UBA → Horde → Perforce → storage → network → CI`

Those are difficult problems because the visible symptom may appear several layers away from the actual cause.

That kind of investigation suits me.

---

# What I dislike

I dislike engineering environments built around:

### Tribal knowledge

> "Ask John. He knows how it works."

That is not documentation.

---

### Manual repetition

If highly qualified engineers repeatedly perform the same deterministic administrative operation, there is probably an automation opportunity.

---

### Unlimited permissions as a shortcut

Giving somebody administrator access because implementing proper delegation requires additional work usually creates a larger problem later.

---

### Infrastructure nobody can observe

If a service is important enough to depend on, it should be possible to understand its state.

---

### Unstructured build storage

Directories containing thousands of arbitrarily named builds eventually become operational debt.

---

### Automation without diagnostics

An automated process that fails silently is often worse than a manual process.

---

### Technology-first architecture

I dislike selecting an implementation before clearly defining the problem.

---

### Unnecessary complexity

Ten services are not automatically better engineering than three.

---

### One-off solutions that should have been platforms

If ten Unreal projects solve the same infrastructure problem independently, I start looking for the common layer.

---

# Multi-project thinking

One characteristic of my recent work is that I frequently think beyond a single project.

For example, I have dealt with environments containing around **ten Unreal Engine 5+ projects**, potentially running different engine versions.

That creates interesting platform questions:

* Does every project deploy its own Horde?
* Can infrastructure be shared?
* How are versions isolated?
* How are agent pools allocated?
* How is project ownership represented?
* How are credentials handled?
* How do we compare telemetry between projects?
* How do we upgrade infrastructure without disrupting every team?
* Which capabilities belong to a project and which belong to the studio?

I am interested in solving those questions at the platform level.

---

# Representative engineering problems I work on

Some examples of the kinds of problems I have been investigating or designing solutions for:

### Horde adoption

Deploying StudioTelemetry/Horde infrastructure across multiple Unreal Engine projects and investigating how Horde can gradually replace or complement Jenkins/TeamCity for distributed compiling and CI/CD.

### Unreal telemetry

Collecting metrics from developer workstations and Unreal build processes with minimal impact on developer performance.

### Zen diagnostics

Making Unreal Zen Server behavior easier to investigate when unusual asset, engine-version, caching, or recompilation behavior occurs.

### Perforce delegated administration

Allowing project DevOps engineers to manage membership of specific Perforce groups without exposing unrestricted Perforce administration.

### Build-storage lifecycle

Designing common build storage, naming, archival, and retention policies across projects.

### Multi-studio infrastructure

Designing Unreal infrastructure across geographically separated development sites.

### Engineering MCP servers

Creating interfaces through which engineering agents can safely investigate systems such as Perforce, TeamCity, Horde, and Zen.

### OCR pipelines

Building local workflows capable of turning large screenshot collections into structured, readable text.

### Workflow orchestration

Using systems such as n8n to connect scheduled processes, external APIs, local services, and event-driven automation.

### AI/LLM products

Building and operating AI/LLM-driven products — including an LLM-provider sentiment platform, a PDF editor, and unreleased gaming/emotional-support projects — end to end, from infrastructure to the service people actually use.

---

# Security mindset

I am not a security engineer, but security boundaries matter in the infrastructure I design.

I pay particular attention to:

* least-privilege access
* administrative separation
* trusted agents
* credential boundaries
* network boundaries
* restricted services
* project-specific permissions
* auditing
* explicit ownership

My general assumption is that convenience alone is not sufficient justification for broad administrative access.

---

# Documentation

I consider documentation part of engineering work.

Infrastructure documentation should explain more than installation commands.

It should describe:

* why the system exists,
* architecture,
* responsibilities,
* dependencies,
* ownership,
* workflows,
* permissions,
* operational procedures,
* failure modes,
* troubleshooting,
* migration,
* and known limitations.

I especially value documentation that allows another engineer to reason about the system rather than merely repeat commands.

---

# My engineering philosophy

A few principles summarize how I tend to work.

**Understand before automating.**

Automating a process nobody understands usually automates its mistakes as well.

**Measure before optimizing.**

Build performance arguments are much more useful when supported by telemetry.

**Make ownership explicit.**

Infrastructure without an owner slowly becomes archaeology.

**Prefer explainable systems.**

I want to be able to explain why a system behaves the way it does.

**Reduce repeated human work.**

Humans should make decisions. Machines are generally better suited to repeating deterministic procedures.

**Design for failure.**

Failures are part of infrastructure. The interesting question is how quickly somebody can identify what failed and why.

**Think beyond the first project.**

When several teams share the same fundamental problem, it is worth investigating whether the solution belongs at the platform level.

---

# The type of problems I want to solve

I am particularly interested in roles where the question sounds something like:

> "We have several Unreal projects, hundreds of developers, multiple studios, Perforce, huge builds, expensive CI, inconsistent tooling, and nobody has a complete picture of how everything fits together."

That is interesting to me.

So are questions such as:

> "Why are our builds getting slower?"

> "How do we migrate this pipeline without stopping development?"

> "Why is Unreal rebuilding this asset on every machine?"

> "How do we distribute compilation across the studio?"

> "How do we understand what developers are actually waiting for?"

> "How do we delegate this operational task without handing out administrator access?"

> "How do we make ten projects share infrastructure without coupling them together?"

> "How can an engineering agent investigate this system safely?"

These are the kinds of problems where I can contribute most.

---

# Beyond individual tools

I do not define my experience by a checklist of technologies.

Perforce can be replaced.

Jenkins can be replaced.

TeamCity can be replaced.

Horde will evolve.

Unreal Engine will evolve.

The important skill is understanding the underlying engineering problems:

* dependency management
* compute distribution
* artifact lifecycle
* source control
* build reproducibility
* access control
* orchestration
* caching
* observability
* automation
* failure recovery
* developer experience
* system ownership

Tools are implementations of those ideas.

Understanding the ideas makes learning the next tool much easier.

---

# What I bring to a team

The combination I bring is relatively specific:

**software engineering + build engineering + DevOps + Unreal Engine + automation + systems thinking + AI/LLM product delivery.**

I can move between discussions with:

* software developers,
* Unreal programmers,
* build engineers,
* DevOps engineers,
* IT/infrastructure teams,
* technical leadership,
* and project teams

because many of the problems I work on exist between those disciplines.

My contribution is often not simply implementing another service.

It is identifying where the boundaries between those systems are creating unnecessary complexity and designing a better engineering workflow around them.

---

# Current areas of interest

I am currently particularly interested in:

* Unreal Engine infrastructure
* Epic Horde
* Unreal Build Accelerator
* Zen Server
* BuildGraph
* developer telemetry
* distributed compilation
* multi-project build platforms
* multi-studio infrastructure
* engineering observability
* AI-assisted DevOps
* Model Context Protocol
* engineering agents
* self-hosted AI
* infrastructure automation
* developer productivity
* build-performance analysis
* commercial and free AI/LLM-driven products

---

# In one sentence

I build and improve the infrastructure between **a developer changing something and a studio successfully turning that change into a reliable, observable, reproducible build** — and I build AI/LLM-driven products that turn that same systems-thinking into services people actually use.

---

## Contact

**Andrii Lavrekha**
Berlin, Germany

GitHub: [@AndriiLavrekha](https://github.com/AndriiLavrekha)
LinkedIn: [andrii-lavrekha](https://www.linkedin.com/in/andrii-lavrekha/)
Email: andriilavrekha@gmail.com

---

*This repository describes the engineering problems I work on, the systems I have experience with, and the principles I use when designing developer infrastructure.*
