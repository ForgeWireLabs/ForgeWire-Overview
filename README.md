<p align="center">
  <picture>
    <source media="(max-width: 640px)" srcset="assets/forgewire-hero-mobile.svg">
    <img src="assets/forgewire-hero.svg" alt="ForgeWire illustration: an operator-owned local workspace and a separate private direction for policy-gated remote compute" width="100%">
  </picture>
</p>

<p align="center">
  <picture>
    <source media="(max-width: 640px)" srcset="assets/coming-soon-banner-mobile.svg">
    <img src="assets/coming-soon-banner.svg" alt="ForgeWire is in private development. No public download or release date has been announced." width="100%">
  </picture>
</p>

# ForgeWire

### Where the Mind Is Forged

**Your intelligence. Your data. Your hardware. Your rules.**

> **Private development.** ForgeWire is not available to download or install. This repository is the public project overview; it does not contain the application source, a supported setup path, or a release date.

ForgeWire is an application under development for work that uses models, personas, tools, skills, saved context, and task execution. The application records state, separates responsibilities, and gives people a way to review work and handle failures.

**Start here:** [What ForgeWire is](#what-forgewire-is) · [Application preview](#application-preview) · [How the system fits together](#how-the-system-fits-together) · [What a user can do](#what-a-user-can-do-in-a-private-workspace) · [Current status](#current-status) · [Follow release updates](#follow-release-updates)

## Start here

| If you want to… | Here’s the current path |
| --- | --- |
| Try ForgeWire | There is no public build, installer, or supported installation path yet. |
| Understand the product | Read the system overview and diagrams below. Each diagram labels current composition separately from work in progress. |
| See the interface | View a genuine Projects workspace capture below. Other product views are listed with their capture status; setup screens remain secondary. |
| Follow a future release | Use **Watch → Custom → Releases** on this repository, or visit [Releases](https://github.com/ForgeWireLabs/ForgeWire-Overview/releases). No date has been announced. |
| Explore related public work | Visit [ForgeWire Labs](https://github.com/ForgeWireLabs), [SCOUT-2](https://github.com/ForgeWireLabs/SCOUT-2), [RepoPact Core](https://github.com/ForgeWireLabs/repopact-core), or [ForgeLink](https://github.com/JeremyShows/ForgeLink). Their availability and terms are described in their own repositories. |

**Reading the diagrams:** they describe verified code paths and architecture direction, not a feature checklist. Captions call out where composition is current, configuration-dependent, private, or still being reconciled. A picture does not mean every box is a public or end-to-end feature.

## Why ForgeWire exists

ForgeWire starts with the work a person needs to do. A request may involve a model, saved context, a tool, or several steps. The person should be able to see the result and review any proposed action.

Different models, software, data, and machines can handle different parts of a request. ForgeWire assigns those parts to specific services and exposes failures when a provider or machine is unavailable.

## What ForgeWire is

ForgeWire is an application and runtime with components for conversation, model access, tools, state, and execution. Each component has a defined job:

| Part | Responsibility | Maturity in the current private application |
| --- | --- | --- |
| **Personas** | Give an interaction a named identity and a policy reference; available persona definitions shape behavior and capability access. | Persona definitions are loaded by the application. The persona contract is a system boundary; catalog management and surrounding UX remain product features. |
| **Providers and models** | Supply language-model responses and tool-call proposals. | The private application resolves a configured provider/model. Which local or hosted providers work depends on integration and workspace configuration. |
| **Tools** | Perform bounded operations such as reading information or calling an integration. | Tools are reached through shared tooling services. Availability and permissions depend on the installed workspace and configuration. |
| **Skills** | Describe or compose capabilities into reusable workflows. | Skill metadata and tooling exist. Dynamic skill resolution is proposed; a shared vocabulary for capability requirements and routing is active design work. |
| **Agents** | Carry out delegated work with an explicit scope and return a result. | Selected workflows use existing agent and graph paths. One consistent run lifecycle across chat, tools, and delegated work remains architecture work. |
| **Services and stores** | Manage conversations, knowledge, memory, tasks, jobs, and other application state. | Multiple service and repository paths exist. A given path can be unavailable when its optional service or backend is not configured. |
| **Projects** | Group related chats with shared instructions and files without replacing the active persona. | The private GTK workspace supports project creation, files, chat association, and archive/restore. Project content remains account-scoped. |
| **Execution substrates** | Run bounded work in a portable runtime and, in a separate project direction, across authorized machines. | Graph execution is used in some private workflows. Unifying end-to-end run ownership and the runtime migration remain active work; Fabric integration and distribution are not public deployment options. |

Personas are more than renamed prompts: their operating profile includes identity, behavioral boundaries, and references to policy and capability access. The persona identity and policy-reference contract belongs to the system boundary, while catalogs, management interfaces, and other persona features remain product surfaces.

Model and provider choices should remain replaceable. Local, hosted, and specialist models can serve different needs when an installed workspace supports and configures them; provider availability is not uniform across workspaces.

### The ForgeWire thesis

> **Agentic systems are systems first and models second.**
>
> A system remains useful under failure when it can degrade gracefully, keep ownership clear, preserve audit trails, and replace a model or execution layer without losing the work. A benchmark score cannot measure all of that.

Models can be wrong, slow, or unavailable. ForgeWire keeps responsibility for state and actions outside the model. Some recovery paths are implemented today; others remain under development.

## Application preview

![Native ForgeWire Projects workspace showing sample projects, shared instructions, a file list, and associated chats](assets/screenshots/projects-workspace-development.png)

*Projects workspace in a private GTK development build, captured in August 2026 with disposable sample data. This is the real workspace widget rendered with the application stylesheet and service-backed sample state; it is not a full-window capture of the current signed-in shell. A project groups chats, files, and instructions while the active persona remains authoritative.*

The current conversation, persona, provider, tools and skills, knowledge, and task views still need clean captures and disclosure review. Their interfaces are described below where documentation and implementation support the claim; an unavailable preview is not replaced with a mockup.

| View | Public preview |
| --- | --- |
| Conversation and response review | Current signed-in capture pending |
| Persona selection and capability controls | Current signed-in capture pending |
| Provider and model controls | Current signed-in capture pending |
| Tools and skills | Current signed-in capture pending |
| Knowledge retrieval | Configured current-build capture pending |
| Task review | Current signed-in capture pending |
| Fabric operator and runner surfaces | Private development; not shown |

<details>
<summary>Secondary preview: genuine setup screens from an internal build</summary>

These three images are actual setup screens from an internal development build. They show setup concepts, not a finished product tour or a public installer.

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

## How the system fits together

The diagrams use a small visual key:

- **Blue** marks an existing implementation path. Availability may still depend on workspace configuration.
- **Purple** marks an optional or configuration-dependent path.
- **Green** marks private implementation, including Fabric's alpha control plane.
- **Amber and dashed** mark proposed or in-progress behavior that is not yet a complete product path.
- Each diagram has an editable Mermaid source beside its rendered SVG export.

### 1. System and service boundaries

The view separates the GTK user path and internal HTTP routes from application composition, core services, orchestration, provider and tooling integrations, persistence, and messaging. The ForgeWire Runtime Core is a conceptual boundary spanning packages; it is not the `forgewire_core/` package. Forge Core messaging and the Python graph execution path are distinct substrate roles. Fabric is a separate private execution control plane reached through limited, configured paths; it does not own the application's semantic state.

![ForgeWire system and service boundaries: user interfaces connect to application composition, services, providers and tools, state repositories, and messaging](assets/diagrams/system-boundaries.png)

Source: [`system-boundaries.mmd`](assets/diagrams/system-boundaries.mmd) · [SVG export](assets/diagrams/system-boundaries.svg).

**Boundary note:** GTK is the current desktop path; HTTP routes are an internal integration surface. Interface and service boundaries remain under reconciliation, so the diagram does not promise equivalent behavior across surfaces. A limited Fabric integration exists for selected, configured workflows; it is not a public remote service.

### 2. Personas, providers, tools, skills, and agents

ForgeWire keeps identity, model choice, available capabilities, and delegated execution conceptually distinct. A persona carries identity and a policy reference; provider/model selection is workspace-configured; tools perform bounded operations through capability boundaries. Skill metadata exists, while dynamic skill resolution is proposed and shared capability/routing contracts are active design work. Agent and multi-agent paths are used by selected workflows; a consistent run lifecycle across chat, tools, and delegated work remains architecture work.

![ForgeWire capability composition: persona identity, configured provider/model, bounded tools, optional skill metadata, existing delegated workflows, and lifecycle-unification work are shown as distinct paths](assets/diagrams/capability-composition.png)

Source: [`capability-composition.mmd`](assets/diagrams/capability-composition.mmd) · [SVG export](assets/diagrams/capability-composition.svg).

**User-facing instruction:** in a private workspace, select an available persona before starting a conversation. The active persona and provider choices are controlled by that workspace. Review a response and any proposed action; a model response alone is not authorization to perform a consequential action.

### 3. Fabric dispatch and remote execution

ForgeWire Fabric is a related, private execution control plane for authenticated, policy-gated work across machines. A limited, configuration-dependent integration exists for selected application workflows. The diagram separates the application's dispatch and semantic ownership from Fabric's remote placement and execution role. It shows the conceptual authority check, bounded work, returned status, and operator review without publishing private protocol, enrollment, endpoint, credential, or deployment details.

![ForgeWire Fabric dispatch: selected configuration-dependent application adapters request authorized remote work from a private alpha control plane, with status and failure evidence returned for operator review](assets/diagrams/fabric-dispatch.png)

Source: [`fabric-dispatch.mmd`](assets/diagrams/fabric-dispatch.mmd) · [SVG export](assets/diagrams/fabric-dispatch.svg).

**Status:** Fabric's current and future development is private and proprietary unless a specific distribution is explicitly licensed otherwise. Broader application integration, conformance, and release gates remain open. The flow is an architecture view, not a public service. The application owns the original dispatch decision; returned remote status is reviewed in the application, and the operator decides follow-up.

### 4. Memory, knowledge, events, and persistent state

Conversation history, short-term request context, optional memory services, knowledge retrieval, tasks, jobs, shared workflow state, and operational events have different purposes. The application has separate services and persistence paths; provider access, retention, knowledge indexing, and retrieval depend on workspace configuration. The diagram does not imply that every memory is persisted or supplied to every request.

![ForgeWire context and state: conversation history and request context are distinct from optional memory and knowledge services, task and job repositories, shared workflow state, asynchronous bus events, and local synchronous notifications](assets/diagrams/context-and-state.png)

Source: [`context-and-state.mmd`](assets/diagrams/context-and-state.mmd) · [SVG export](assets/diagrams/context-and-state.svg).

The application uses an in-process asynchronous message bus, while synchronous local notifications follow a separate path. Task/job records are operational state, not conversation memory. Distributed execution belongs to the separate Fabric direction; these mechanisms do not create a public durability, replication, or cross-shell event guarantee.

### 5. Task, failure, recovery, and escalation

The current user guide supports reviewing tasks produced by configured workflows. The task panel does not itself provide a general task-creation action. Selected graph and task paths include bounded retries, and the ManualInterventionPanel supports explicit operator review. Run-wide checkpoint/resume, idempotent replay, and automatic escalation are not established as universal product behavior.

![ForgeWire task flow and recovery: task review, selected bounded retries, and the ManualInterventionPanel are distinct from proposed universal replay, checkpoint resume, and automatic escalation](assets/diagrams/task-recovery.png)

Source: [`task-recovery.mmd`](assets/diagrams/task-recovery.mmd) · [SVG export](assets/diagrams/task-recovery.svg).

**Current private-workspace path:** open the task area, select a task, and review its description, status, and available actions. Ask the workspace operator which workflow creates tasks. The task UI does not provide general task creation, and its review controls do not imply an automated recovery path.

## What a user can do in a private workspace

These instructions apply only to a workspace that has already been installed and configured by its operator. They are not a public installation guide.

1. **Open ForgeWire.** Use the application launcher configured for your workspace.
2. **Sign in if required.** Use the workspace account. Contact its operator if you do not have one or sign-in is unavailable.
3. **Choose an active persona.** Open the Personas manager, choose an available persona, and confirm it is active. The current conversation uses that persona.
4. **Start a conversation.** Open the conversation workspace, send a short request, and review the response before acting on recommendations.
5. **Organize related chats in a project.** Under **History → Projects**, create a workspace for shared instructions and files. Project context supplements the active persona; it does not replace persona policy or capability grants.
6. **Use knowledge features when configured.** If retrieval is enabled, the workspace may allow document upload and knowledge-base queries. Check indexing and use the query test view to verify what was retrieved.
7. **Review tasks.** Open the task area and select a task created by a configured workflow. Review its description, status, and available actions. The UI does not currently provide general task creation.

Provider credentials, account access, storage, and optional knowledge services are operator-managed. If a provider request fails, ask the operator to confirm the persona has access to an available provider. These steps describe the current private application path and may change before a public release.

## Who ForgeWire is for

- **Operators** who need to understand where work runs, how it is configured, and where their decisions belong.
- **Builders** connecting providers, tools, application services, and user-facing workflows.
- **Researchers** studying reliability, bounded reasoning, state, evaluation, and failure behavior in agentic systems.
- **Teams** exploring reviewable work and durable state beyond a conversation transcript.

ForgeWire is not currently a hosted service, supported enterprise deployment, or open-source application framework. Its complete source is not published in this overview repository.

## Built around useful failure and human authority

Providers, dependencies, hardware, and remote connections can fail. ForgeWire aims to show those failures clearly and keep decisions about further action with the operator.

The engineering goals include:

- graceful degradation when optional components are unavailable
- clear service ownership and replaceable model or infrastructure choices
- parity evidence when alternative implementations are introduced
- traceable actions and outcomes
- scoped capabilities and human approval for consequential actions where policy requires it
- visible failure and a safe way to stop or escalate

Those are design requirements, not blanket assurances about current product coverage. The architecture and deployment boundaries continue to evolve. A future release should describe the controls present in that build and publish validation evidence for them.

## Research direction

ForgeWire Labs also researches bounded recurrent reasoning, task-local cognitive control, continual learning, adaptive routing, calibrated fusion, specialist models, hybrid language and state models, evaluation and replay, persistent agency, and temporal continuity.

Research ideas are tested separately before they are considered for the application. That work includes baseline comparisons, failure analysis, and limited trials.

## Project lineage

**SCOUT → SCOUT-2 → ATLAS → PhrenForge → ForgeWire**

The project evolved from a multi-agent assistant toward a broader application with personas, tools, services, structured messaging, execution boundaries, and repository-native governance. That history records repeated implementation and redesign; it does not mean every capability from an earlier generation exists in the current product.

## Related work

- **ForgeWire Fabric**: private distributed execution and control-plane development associated with ForgeWire. Current and future development is proprietary unless a specific distribution says otherwise. Historical copies previously distributed under Apache License 2.0 remain governed by the terms that accompanied those copies; their granted rights are not revoked here.
- [SCOUT-2](https://github.com/ForgeWireLabs/SCOUT-2): an earlier multi-agent assistant and part of the public project lineage.
- [ForgeWire Labs](https://github.com/ForgeWireLabs): independent engineering and applied AI research.
- [RepoPact Core](https://github.com/ForgeWireLabs/repopact-core) and [ForgeLink](https://github.com/JeremyShows/ForgeLink): separately maintained public projects. Consult their repositories for their own status and terms.

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

ForgeWire is an engineering and research effort led by [Jeremy Shows](https://github.com/JeremyShows) through [ForgeWire Labs](https://github.com/ForgeWireLabs). AI systems contribute materially across research, architecture exploration, implementation, debugging, testing, review, and documentation. Jeremy works directly across that lifecycle, makes technical and integration decisions, challenges proposed solutions, and retains responsibility for validation and acceptance.

The work draws on open research, open-source software, commercial AI tools, and established systems engineering. It does not claim unaided authorship or delegate technical responsibility wholesale to autonomous agents.

## Technical direction

Work across ForgeWire and adjacent components has included **Rust, Python, TypeScript, GTK, React, PostgreSQL, SQLite, and rqlite**, alongside structured messaging and local or hosted model-provider integrations. This lists technologies used across the private work. It does not mean they are all present in one build or available for public deployment. These are replaceable choices, not the identity of the system.

---

> ForgeWire is being built so people can see what happened, review actions, and continue work after a failure.
