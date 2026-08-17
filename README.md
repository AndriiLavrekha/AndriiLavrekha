# Hey, I'm Andrii Lavrekha 👋

**Build / DevOps / Platform Engineer** based in Berlin, Germany. Living in the space between software engineering and infrastructure engineering, with deep roots in **Unreal Engine developer infrastructure** and a growing side quest in **AI/LLM-driven products**.

I don't just write software. I obsess over the *entire system* around it: how code gets to a developer, how it gets built, how it gets diagnosed when it breaks at 2am, and how it stays understandable six months later when someone else has to touch it.

> 🧠 **In one sentence:** I build the infrastructure between *a developer changing something* and *a studio turning that change into a reliable, observable, reproducible build*, and I build AI/LLM products that apply the same systems-thinking to real people's problems.

---

## 🛠️ What I Do

| Area | Focus |
|---|---|
| **Build Engineering** | Compiling, packaging, distributing, retaining, diagnosing builds |
| **DevOps / Platform Engineering** | Source control, CI/CD, compute, storage, and workstations, wired together |
| **Tools Engineering** | Killing repetitive work for devs, artists, build & DevOps engineers |
| **Unreal Engine Infrastructure** | Everything *around* the engine, not gameplay code |
| **Automation Engineering** | If a human repeats a deterministic task, I start asking why software isn't doing it |

**Roles that fit me:** Senior Build Engineer, Senior DevOps Engineer, Platform Engineer, Tools Programmer, Developer Infrastructure Engineer, Unreal Engine Infrastructure Engineer, CI/CD Engineer, Developer Productivity Engineer

I thrive where there are: large repos, expensive builds, many developers, multiple studios, Perforce, build farms, distributed compilation, and years of accumulated infrastructure nobody fully understands anymore. 🧩

---

## 🎮 Unreal Engine Infrastructure

This is my strongest technical ground. I've worked with environments running **~10 simultaneous Unreal Engine 5+ projects**, sometimes on different engine versions. That turns a simple question:

> "How do we configure Unreal Engine?"

into a much more interesting one:

> "How do we build a **platform** where many projects, engine branches, teams, and offices coexist without every project becoming its own isolated infrastructure island?"

**Stack I live in:**
`Unreal Build Tool`, `Unreal Automation Tool`, `BuildGraph`, `Unreal Build Accelerator`, `Horde` (server + agents), `Zen Server`, Derived Data Cache, distributed compilation, Perforce integration

### 🐴 Epic Horde
Architecting Horde deployments across multi-project studios currently on Jenkins/TeamCity, not as "another CI server," but as an Unreal-native developer infrastructure platform. Agent pools, distributed compilation, BuildGraph integration, project isolation, migration paths.

### 🧊 Zen Server
I want Zen to be **observable**, not an opaque black box. When an asset keeps re-triggering compilation, I want to trace it: what Unreal believes, what Zen believes, which changelist or engine version caused it, and whether it's machine-specific or studio-wide. I've explored exposing this diagnostic layer through **MCP tooling** so agents (human or AI) can query it too.

### 🌍 Multi-site infrastructure
Designed architecture across studios in **Berlin, Finland, and Bratislava**: Perforce, Horde, Zen, TeamCity, Jenkins, RoboMerge, GitHub, Gitea. My default pattern is **central control, local execution**. Policy and orchestration stay central; latency-sensitive stuff (caches, agents, compute) lives close to developers.

---

## 🔀 Perforce

Perforce, treated as studio architecture, not just a source-control client: users, groups, streams, permissions, delegation, CI integration.

**Principle I push hard on:** delegate the *minimum* operational capability, not blanket admin access. Example: instead of giving someone full Perforce admin just to manage a project's team roster, I design workflows where they **own a specific group** and manage its membership, while the global security model stays with central infra.

> Give people the authority they need. Don't confuse operational responsibility with unrestricted admin access. 🔑

---

## 🔁 CI/CD & Build Artifacts

Worked with `TeamCity`, `Jenkins`, `Horde`, `BuildGraph`, GitHub Actions-style workflows, build farms, scheduled/retention jobs.

A good CI system should answer more than "green or red":
- What was built, from which changelist/stream/engine/config?
- Why was it triggered, and how long did each phase take?
- Can it be reproduced? Compared to yesterday's build?
- Why did compilation suddenly get 30% slower? 📉

**Build storage** I've designed: `Projects / Project / Builds`, classified by type (CI / Nightly / Milestone / Custom), with real retention policy. 14-21 day temp builds, automated nightly cleanup, `BuildArchive` for long-lived builds, **dry-run mode before anything destructive**.

> A cron job deleting directories is not a retention strategy.

---

## 📊 Observability & Developer Productivity

Collecting engineering telemetry (build/compile duration, cache hit rates, queue times, failures) from workstations and CI, via `Grafana`, `Loki`, `Elasticsearch`, UBT/Horde log parsing. Low overhead at the source, centralized storage, independent analysis.

The goal isn't watching developers. It's understanding the system. A 10-minute problem repeated by 100 developers daily isn't small. **It's infrastructure.**

---

## 🤖 AI / LLM-Driven Products

This is my current big bet: building and shipping **commercial and free AI/LLM-powered products** for people who actually need them. A few, described by function (names withheld on purpose 🤫):

- **A sentiment-tracking platform for the LLM industry**: analyzes public mood around LLM providers (OpenAI, Anthropic/Claude, etc.), surfacing trends and recurring complaints across a very opinionated market.
- **A PDF editor**, close to public release: everyday document editing without the bloat and cost of traditional PDF software.
- **A few unreleased projects** at the intersection of **gaming + AI/LLMs**, some aimed at emotional support, applying conversational AI where it can genuinely help, not just automate.

Same rule as infrastructure: understand the real problem first, *then* decide if AI/LLM is the right tool or just a shiny bolt-on.

### 🧠 Engineering agents & MCP
I'm actively exploring **Model Context Protocol** interfaces for Perforce, TeamCity, Horde, and Zen, giving engineering agents deliberately scoped operations (inspect a build, query a changelist, check a Horde job) instead of raw machine access. Safer, more useful, more auditable.

---

## 🧰 Other things in the toolbox

- **OCR / information extraction**: PaddleOCR pipelines turning screenshots and legacy sources into structured Markdown.
- **n8n**: orchestrating scheduled checks, APIs, notifications, and local AI/OCR services without cramming everything into one engine.
- **Self-hosted infrastructure**: Linux, Unraid, VPS, WireGuard, local AI/OCR, Gitea. SaaS isn't automatically the right answer.

**Languages:** `C++`, `C#`, `Python`, `Groovy`, `JavaScript`, `Go`, `Kotlin`. Pragmatic choice per job, not a religion.

---

## 💭 How I Think About Engineering

- **Start with the system, not the tool.** "What problem are we solving?" comes before "let's deploy X."
- **I hate black boxes.** "Something went wrong" isn't an engineering interface.
- **Boring infrastructure wins when boring works.** Complexity has to earn its place.
- **Migrate incrementally.** `Jenkins to partial Horde adoption to broader rollout`, never a big-bang rewrite.
- **Mind the blast radius.** Narrow permissions, explicit ownership, dry-run before anything destructive.
- **Naming is infrastructure.** A good build ID saves hours of future investigation.
- **Understand before automating.** Automating a process nobody understands automates its mistakes too.
- **Think beyond the first project.** If ten Unreal projects solve the same problem independently, that's a platform waiting to happen.

---

## 🎯 Problems I want to solve

> "We've got several Unreal projects, hundreds of developers, multiple studios, huge builds, expensive CI, and nobody has the full picture."

That's my kind of Tuesday. Also:

- Why are builds getting slower?
- Why does Unreal keep rebuilding this one asset on every machine?
- How do we distribute compilation across the studio?
- How do ten projects share infrastructure *without* getting coupled together?
- How can an AI agent investigate this system safely?

Tools change. Perforce, Jenkins, Horde, even Unreal Engine itself will evolve. The underlying problems (dependency management, artifact lifecycle, access control, observability, automation) don't. Learn the ideas, and the next tool is easy. 🧩

---

## 📫 Contact

**Andrii Lavrekha**, Berlin, Germany

[![GitHub](https://img.shields.io/badge/GitHub-AndriiLavrekha-181717?style=flat&logo=github)](https://github.com/AndriiLavrekha)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-andrii--lavrekha-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/andrii-lavrekha/)
[![Email](https://img.shields.io/badge/Email-andriilavrekha%40gmail.com-EA4335?style=flat&logo=gmail&logoColor=white)](mailto:andriilavrekha@gmail.com)

---

*If you made it this far, hi, we should probably talk. ☕*
