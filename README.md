<p align="center">
  <img src="assets/forgewire-hero.svg" alt="ForgeWire — a systems-first foundation for AI-assisted work" width="100%">
</p>

<p align="center">
  <img src="assets/coming-soon-banner.svg" alt="ForgeWire is in private development. No public release date has been announced." width="100%">
</p>

# ForgeWire

### Where the mind is forged

**Your intelligence. Your data. Your hardware. Your rules.**

> **Private development.** ForgeWire is not available to download or install. This repository is the public project overview; it does not contain the application source, a supported setup path, or a release date.

ForgeWire is a modular environment being built to coordinate models, personas, tools, skills, memory, task execution, and compute around real work. The project starts from a systems-first premise: useful AI depends on the boundaries, state, recovery paths, and human decisions around a model—not only on the model itself.

**Start here:** [What ForgeWire is](#what-forgewire-is) · [How the system fits together](#how-the-system-fits-together) · [What a user can do](#what-a-user-can-do-in-a-private-workspace) · [Current status](#current-status) · [Follow release updates](#follow-release-updates)

## Start here

| If you want to… | Here’s the current path |
| --- | --- |
| Try ForgeWire | There is no public build, installer, or supported installation path yet. |
| Understand the product | Read the system overview and diagrams below. Each diagram labels current composition separately from work in progress. |
| See the interface | The gallery identifies the product screenshots still pending. A few genuine setup screens are available in the secondary preview. |
| Follow a future release | Use **Watch → Custom → Releases** on this repository, or visit [Releases](https://github.com/ForgeWireLabs/ForgeWire-Overview/releases). No date has been announced. |
| Explore related public work | Visit [ForgeWire Labs](https://github.com/ForgeWireLabs), [SCOUT-2](https://github.com/ForgeWireLabs/SCOUT-2), [RepoPact Core](https://github.com/ForgeWireLabs/repopact-core), or [ForgeLink](https://github.com/JeremyShows/ForgeLink). Their availability and terms are described in their own repositories. |

**Reading the diagrams:** they describe verified code paths and architecture direction, not a feature checklist. Captions call out where composition is current, configuration-dependent, private, or still being reconciled. A picture does not mean every box is a public or end-to-end feature.

## Why ForgeWire exists

Most assistants are organized around a model and a conversation window. ForgeWire is being organized around the work: understanding a request, selecting relevant capabilities, preserving useful context, coordinating bounded steps, and returning an outcome a person can review.

The aim is not to make one model pretend to do everything or to replace human judgment. The aim is to coordinate different models, software, data, and compute within visible responsibilities—and to make the system useful when a provider, dependency, or machine is constrained.

## What ForgeWire is

ForgeWire is an application and runtime for coordinating intelligent work. It is not a single chatbot, an autonomous agent with blanket authority, or a public model-hosting service. Its capabilities are divided among components with different jobs:

| Part | Responsibility | Maturity in the current private application |
| --- | --- | --- |
| **Personas** | Give an interaction a named identity and a policy reference; available persona definitions shape behavior and capability access. | Persona definitions are loaded by the application. The persona contract is a system boundary; catalog management and surrounding UX remain product features. |
| **Providers and models** | Supply language-model responses and tool-call proposals. | The private application resolves a configured provider/model. Which local or hosted providers work depends on integration and workspace configuration. |
| **Tools** | Perform bounded operations such as reading information or calling an integration. | Tools are reached through shared tooling services. Availability and permissions depend on the installed workspace and configuration. |
| **Skills** | Describe or compose capabilities into reusable workflows. | Skill metadata and tooling exist; dynamic resolution and consistent requirements/routing are active engineering work. |
| **Agents** | Carry out delegated work with an explicit scope and return a result. | Agent and multi-agent paths exist in the private application, while their end-to-end run lifecycle is still being unified. The diagrams do not imply that every workflow already uses one universal agent runtime. |
| **Services and stores** | Manage conversations, knowledge, memory, tasks, jobs, and other application state. | Multiple service and repository paths exist. A given path can be unavailable when its optional service or backend is not configured. |
| **Execution substrates** | Run bounded work in a portable runtime and, in a separate project direction, across authorized machines. | Graph execution is used in some private workflows. Unifying end-to-end run ownership and the runtime migration remain active work; Fabric integration and distribution are not public deployment options. |

Personas are more than renamed prompts: their operating profile includes identity, behavioral boundaries, and references to policy and capability access. The persona identity and policy-reference contract belongs to the system boundary, while catalogs, management interfaces, and other persona features remain product surfaces.

Model and provider choices should remain replaceable. Local, hosted, and specialist models can serve different needs when an installed workspace supports and configures them; provider availability is not uniform across workspaces.

### The ForgeWire thesis

> **Agentic systems are systems first and models second.**
>
> Survivability under deployment—graceful degradation, layered ownership, parity paths, audit trails, and replaceable substrates—is the property that determines whether a system is useful, not benchmark scores on a model card.

Models can be useful and still be wrong, slow, unavailable, or replaced. ForgeWire treats them as one part of a larger system that must make state and ownership visible, preserve human control, and expose the limits of its current recovery paths. This thesis is an engineering direction; it is not a claim that every listed property is complete today.

## How the system fits together

The diagrams use a small visual key:

- **Solid blue** marks an implementation path described by the current architecture and user guides. Availability may still depend on workspace configuration.
- **Amber or dashed** marks private related work, an active migration, or an intended behavior that is not established as a complete product path.
- Each diagram has an editable Mermaid source beside its rendered SVG export.

### 1. System and service boundaries

The private application composes provider, persona, conversation, knowledge, task, and messaging services behind its user and integration surfaces. The ForgeWire Runtime Core is a conceptual product boundary; no single package or model defines the whole system. Individual execution and messaging substrates are replaceable building blocks.

![ForgeWire system and service boundaries: user interfaces connect to application composition, services, providers and tools, state repositories, and messaging](assets/diagrams/system-boundaries.png)

Source: [`system-boundaries.mmd`](assets/diagrams/system-boundaries.mmd) · [SVG export](assets/diagrams/system-boundaries.svg).

**Boundary note:** a GTK desktop shell is the current user path, and the private application has an HTTP integration surface. Interface and service boundaries are under active reconciliation, so the diagram does not promise identical behavior across every surface or that each one is suitable for public deployment.

### 2. Personas, providers, tools, skills, and agents

ForgeWire keeps identity, model choice, available capabilities, and delegated execution conceptually distinct. The persona supplies an identity and policy reference; configured providers supply model responses; tools perform bounded operations. A fully integrated agent-run path remains in development.

![ForgeWire capability composition: a request uses a persona and configured provider, then crosses capability boundaries to tools, skills, or scoped agent work](assets/diagrams/capability-composition.png)

Source: [`capability-composition.mmd`](assets/diagrams/capability-composition.mmd) · [SVG export](assets/diagrams/capability-composition.svg).

**User-facing instruction:** in a private workspace, select an available persona before starting a conversation. The active persona and provider choices are controlled by that workspace. Review a response and any proposed action; a model response alone is not authorization to perform a consequential action.

### 3. Fabric dispatch and remote execution

ForgeWire Fabric is a related, private project direction for authenticated, policy-gated work across machines. Its dispatch path is shown to explain the intended trust boundary; this overview does not provide Fabric source, runner enrollment, endpoints, credentials, or deployment instructions.

![ForgeWire Fabric remote execution direction: an authorized dispatch passes an identity and capability envelope to a runner for verification before bounded execution and a structured result](assets/diagrams/fabric-dispatch.png)

Source: [`fabric-dispatch.mmd`](assets/diagrams/fabric-dispatch.mmd) · [SVG export](assets/diagrams/fabric-dispatch.svg).

**Status:** Fabric's current and future development is private and proprietary unless a specific distribution is explicitly licensed otherwise. Integration, conformance, and release gates remain open. The flow is an architecture view, not an available service.

### 4. Memory, knowledge, events, and persistent state

Conversation history, short-term context, semantic or episodic memory paths, knowledge bases, tasks, and jobs are not one undifferentiated transcript. The current code has separate services and persistence paths. Configuration determines which stores and retrieval features are usable.

![ForgeWire context and state: conversations and short-term context connect to configured knowledge retrieval and distinct conversation, task, job, and knowledge persistence paths, with application messaging](assets/diagrams/context-and-state.png)

Source: [`context-and-state.mmd`](assets/diagrams/context-and-state.mmd) · [SVG export](assets/diagrams/context-and-state.svg).

The application uses an in-process asynchronous message bus, while synchronous local notifications follow a separate path. Distributed execution belongs to the Fabric direction; these mechanisms have different scopes and should not be read as one public event or replication guarantee.

### 5. Task, failure, recovery, and escalation

The current user guide supports reviewing tasks produced by configured workflows. The task panel does not itself provide a general task-creation action. The recovery branches in the diagram express engineering requirements—visible failure, bounded recovery, and operator escalation—not a guarantee that each branch is already automated.

![ForgeWire task flow and recovery: configured work can be reviewed, execution returns a result or visible failure, then a permitted recovery path or operator review is selected](assets/diagrams/task-recovery.png)

Source: [`task-recovery.mmd`](assets/diagrams/task-recovery.mmd) · [SVG export](assets/diagrams/task-recovery.svg).

**Current private-workspace path:** open the task area, select a task, and review its description, status, and available actions. Ask the workspace operator which workflow creates tasks. Do not assume the task UI can create or execute every task.

## What a user can do in a private workspace

These instructions apply only to a workspace that has already been installed and configured by its operator. They are not a public installation guide.

1. **Open ForgeWire.** Use the application launcher configured for your workspace.
2. **Sign in if required.** Use the workspace account. Contact its operator if you do not have one or sign-in is unavailable.
3. **Choose an active persona.** Open the Personas manager, choose an available persona, and confirm it is active. The current conversation uses that persona.
4. **Start a conversation.** Open the conversation workspace, send a short request, and review the response before acting on recommendations.
5. **Use knowledge features when configured.** If retrieval is enabled, the workspace may allow document upload and knowledge-base queries. Check indexing and use the query test view to verify what was retrieved.
6. **Review tasks.** Open the task area and select a task created by a configured workflow. Review its description, status, and available actions. The UI does not currently provide general task creation.

Provider credentials, account access, storage, and optional knowledge services are operator-managed. If a provider request fails, ask the operator to confirm the persona has access to an available provider. These steps describe the current private application path and may change before a public release.

## Interface preview

Clean captures of the current conversation, persona and capability controls, knowledge retrieval, and task review are **pending**. We will add them after current-build, disclosure, and desktop-boundary review. No mock product screens are used here to imply that an unfinished view exists.

| Screen | Public preview |
| --- | --- |
| Conversation and response review | Pending a clean current-build capture |
| Persona and capability controls | Pending a clean current-build capture |
| Knowledge-base retrieval | Pending a configured current-build capture |
| Task review | Pending a clean current-build capture |
| Fabric operator and runner surfaces | Private development; not shown |

<details>
<summary>Secondary preview: genuine setup screens from an internal build</summary>

These three images are actual setup screens from an internal development build. They show setup concepts, not a finished product tour or a public installer. They are kept secondary because the current end-user conversation and task screens have not yet been cleared for a public preview.

<table>
  <tr>
    <td width="50%" valign="top"><strong>Welcome</strong><br><img src="assets/screenshots/first-run-welcome.png" alt="Actual ForgeWire first-run setup welcome screen from an internal build" width="100%"></td>
    <td width="50%" valign="top"><strong>Storage options</strong><br><img src="assets/screenshots/storage-options.png" alt="Actual internal ForgeWire setup screen describing local desktop and shared storage choices" width="100%"></td>
  </tr>
  <tr>
    <td colspan="2" valign="top"><strong>Local workspace</strong><br><img src="assets/screenshots/local-workspace.png" alt="Actual internal ForgeWire setup screen for choosing a local work folder" width="100%"></td>
  </tr>
</table>

</details>

## Who ForgeWire is for

- **Operators** who need to understand where work runs, how it is configured, and where their decisions belong.
- **Builders** connecting providers, tools, application services, and user-facing workflows.
- **Researchers** studying reliability, bounded reasoning, state, evaluation, and failure behavior in agentic systems.
- **Teams** exploring reviewable work and durable state beyond a conversation transcript.

ForgeWire is not currently a hosted service, supported enterprise deployment, or open-source application framework. Its complete source is not published in this overview repository.

## Built around useful failure and human authority

ForgeWire is developed around the assumption that providers, dependencies, hardware, and remote connections can fail. The system should make that state inspectable and keep action authority explicit.

The engineering goals include:

- graceful degradation when optional components are unavailable
- clear service ownership and replaceable model or infrastructure choices
- parity evidence when alternative implementations are introduced
- traceable actions and outcomes
- scoped capabilities and operator decisions for consequential work
- visible failure and a safe way to stop or escalate

Those are design requirements, not blanket assurances about current product coverage. The architecture and deployment boundaries continue to evolve. A future release should describe the controls present in that build and publish validation evidence for them.

## Research direction

ForgeWire provides a product path for selected research from ForgeWire Labs. Current areas of interest include bounded recurrent reasoning, task-local cognitive control, continual learning, adaptive routing, calibrated fusion, specialist models, hybrid language and state models, evaluation and replay, persistent agency, and temporal continuity.

Research is not automatically product capability. Experimental work should move through isolation, baseline comparison, controlled evaluation, failure analysis, observe-only integration, and limited canary use before production adoption is considered.

## Project lineage

**SCOUT → SCOUT-2 → ATLAS → PhrenForge → ForgeWire**

The project evolved from a multi-agent assistant toward a broader application with personas, tools, services, structured messaging, execution boundaries, and repository-native governance. That history records repeated implementation and redesign; it does not mean every capability from an earlier generation exists in the current product.

## Related work

- **ForgeWire Fabric** — private distributed execution and control-plane development associated with ForgeWire. Current and future development is proprietary unless a specific distribution says otherwise. Historical copies previously distributed under Apache License 2.0 remain governed by the terms that accompanied those copies; their granted rights are not revoked here.
- [SCOUT-2](https://github.com/ForgeWireLabs/SCOUT-2) — an earlier multi-agent assistant and part of the public project lineage.
- [ForgeWire Labs](https://github.com/ForgeWireLabs) — independent engineering and applied AI research.
- [RepoPact Core](https://github.com/ForgeWireLabs/repopact-core) and [ForgeLink](https://github.com/JeremyShows/ForgeLink) — separately maintained public projects. Consult their repositories for their own status and terms.

## Current status

| Area | Status |
| --- | --- |
| Public overview | Available in this repository |
| Complete ForgeWire application source | Private development; not published here |
| Public download or installer | Not available |
| Supported public installation path | Not available |
| Stable public API or compatibility promise | Not announced |
| Public release date | Not announced |
| ForgeWire Fabric source and deployment | Private development; not available from this repository |

Private development is proprietary unless a specific distribution is explicitly licensed otherwise. Historical releases or copies that ForgeWire Labs previously distributed under Apache License 2.0 remain under the license terms that accompanied those specific copies. This overview does not change those terms or license current private development.

A public release should include supported-platform and installation guidance, security and data-handling details, known limitations, migration and recovery guidance, and validation evidence for the released build. There is no waitlist or announced release date.

## Follow release updates

1. Select **Watch** near the top of this repository.
2. Choose **Custom**, then enable **Releases** to receive release notifications. See [GitHub's notification guide](https://docs.github.com/en/subscriptions-and-notifications/get-started/configuring-notifications#configuring-your-watch-settings-for-an-individual-repository) for the current steps.
3. Star this repository if you want to keep it in your GitHub bookmarks.
4. Check the [Releases page](https://github.com/ForgeWireLabs/ForgeWire-Overview/releases) and this README for current status. A release will be announced here when one is ready.

## How ForgeWire is built

ForgeWire is a human-led, deeply AI-assisted engineering and research effort led by [Jeremy Shows](https://github.com/JeremyShows) through [ForgeWire Labs](https://github.com/ForgeWireLabs). AI systems contribute materially across research, architecture exploration, implementation, debugging, testing, review, and documentation. Jeremy works directly across that lifecycle, makes technical and integration decisions, challenges proposed solutions, and retains responsibility for validation and acceptance.

The work draws on open research, open-source software, commercial AI tools, and established systems engineering. It does not claim unaided authorship or delegate technical responsibility wholesale to autonomous agents.

## Technical direction

Work across ForgeWire and adjacent components has included **Rust, Python, TypeScript, GTK, React, PostgreSQL, SQLite, and rqlite**, alongside structured messaging and local or hosted model-provider integrations. This is a high-level inventory across a broader private effort—not a compatibility list, deployment guide, or promise that each technology is currently composed in the application. These are replaceable choices, not the identity of the system.

---

> Most assistants optimize for conversation. ForgeWire is being built to make AI-assisted work more inspectable, bounded, recoverable, and useful under real constraints.
