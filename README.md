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

ForgeWire is a modular environment being built to coordinate models, personas, tools, skills, memory, task execution, and compute around real work. The project starts from a systems-first premise: useful AI depends on the boundaries, state, recovery paths, and human decisions around a model—not only on the model itself.

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

Most assistants are organized around a model and a conversation window. ForgeWire is being organized around the work: understanding a request, selecting relevant capabilities, preserving useful context, coordinating bounded steps, and returning an outcome a person can review.

The aim is not to make one model pretend to do everything or to replace human judgment. The aim is to coordinate different models, software, data, and compute within visible responsibilities—and to make the system useful when a provider, dependency, or machine is constrained.

## What ForgeWire is

ForgeWire is an application and runtime for coordinating intelligent work. It is not a single chatbot, an autonomous agent with blanket authority, or a public model-hosting service. Its capabilities are divided among components with different jobs:

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
> Survivability under deployment—graceful degradation, layered ownership, parity paths, audit trails, and replaceable substrates—is the property that determines whether a system is useful, not benchmark scores on a model card.

Models can be useful and still be wrong, slow, unavailable, or replaced. ForgeWire treats them as one part of a larger system that must make state and ownership visible, preserve human control, and expose the limits of its current recovery paths. This thesis is an engineering direction; it is not a claim that every listed property is complete today.

## Application preview

![Native ForgeWire Projects workspace showing sample projects, shared instructions, a file list, and associated chats](assets/screenshots/projects-workspace-development.png)

*Projects workspace in a private GTK development build, captured in August 2026 with disposable sample data. This is the real workspace widget rendered with the application stylesheet and service-backed sample state; it is not a full-window capture of the current signed-in shell. A project groups chats, files, and instructions while the active persona remains authoritative.*

The signed-in tour remains in progress. Genuine captures from 2026-10-11 cover the corrected disabled Tasks and Jobs pages, Calendar and Budget views, several Operations surfaces, History, Settings, and Builder catalogs. The latest signed-in session recaptured Tasks and Jobs as explicitly disabled, with scheduling still off. The current Skills page displays an initialization error and is documented as unavailable. Fresh Knowledge captures show an empty Library with RAG off and a Docs text-preview fallback. Current File/Edit/View/Help menus were captured after restart. The empty Chat shell has no visible composer or conversation, so Chat behavior remains unverified. No private conversation content was captured; conversation metadata shown in History and Notifications was redacted. The inventory below lists remaining route and dialog gaps.

| View | Verified capture |
| --- | --- |
| Work: Tasks and Jobs | Latest session: [Tasks disabled](assets/screenshots/signed-in-tour-2026-10-11/tasks-disabled-current-session.png); [Jobs disabled](assets/screenshots/signed-in-tour-2026-10-11/jobs-disabled-current-session.png). Earlier after-restart captures remain linked: [Tasks](assets/screenshots/signed-in-tour-2026-10-11/tasks-disabled-after-restart.png); [Jobs](assets/screenshots/signed-in-tour-2026-10-11/jobs-disabled-after-restart.png). Historical initialization errors remain labeled below. |
| Work: Calendar and Budget | [Calendar Month](assets/screenshots/signed-in-tour-2026-10-11/calendar-month-current.png); [Budget Dashboard, redacted](assets/screenshots/signed-in-tour-2026-10-11/budget-dashboard-redacted.png). Full view inventory follows below. |
| Builder | [Personas](assets/screenshots/signed-in-tour-2026-10-11/builder-personas-current.png); [Providers](assets/screenshots/signed-in-tour-2026-10-11/builder-providers-current.png); [Tools](assets/screenshots/signed-in-tour-2026-10-11/builder-tools-current.png); [Skills initialization error](assets/screenshots/signed-in-tour-2026-10-11/builder-skills-initialization-error-current.png). |
| Knowledge | [Empty Library, RAG left off](assets/screenshots/signed-in-tour-2026-10-11/knowledge-library-empty-after-restart.png); [Docs text-preview fallback](assets/screenshots/signed-in-tour-2026-10-11/knowledge-docs-after-restart.png). |
| Operations | [Orchestration](assets/screenshots/signed-in-tour-2026-10-11/operations-orchestration-current.png); [Status](assets/screenshots/signed-in-tour-2026-10-11/operations-orchestration-status-current.png); [Agent Activity, 0 active agents](assets/screenshots/signed-in-tour-2026-10-11/operations-agent-activity-current-session.png); [Handoffs](assets/screenshots/signed-in-tour-2026-10-11/operations-handoffs-current.png); [Intervention form](assets/screenshots/signed-in-tour-2026-10-11/operations-intervention-current.png); [Health after restart](assets/screenshots/signed-in-tour-2026-10-11/operations-observability-health-after-restart.png); [BenchLab, worker details and log paths redacted](assets/screenshots/signed-in-tour-2026-10-11/operations-benchlab-after-restart.png); [Guardrails](assets/screenshots/signed-in-tour-2026-10-11/operations-guardrails-current.png); [MCP Servers, 0 configured](assets/screenshots/signed-in-tour-2026-10-11/operations-mcp-servers-current.png); [Vector Store](assets/screenshots/signed-in-tour-2026-10-11/operations-vector-store-current.png). |
| History | [All Chats empty after restart, sidebar metadata redacted](assets/screenshots/signed-in-tour-2026-10-11/history-all-chats-empty-after-restart-redacted.png); [Projects unavailable after restart](assets/screenshots/signed-in-tour-2026-10-11/history-all-projects-unavailable-after-restart.png). |
| Settings and Notifications | [Settings navigation](assets/screenshots/signed-in-tour-2026-10-11/settings-menu-after-restart.png); [Notifications empty, sidebar metadata redacted](assets/screenshots/signed-in-tour-2026-10-11/notifications-empty-after-restart-redacted.png); [API Keys, redacted](assets/screenshots/signed-in-tour-2026-10-11/settings-api-keys-redacted.png); [Background Automation disabled](assets/screenshots/signed-in-tour-2026-10-11/settings-background-automation-disabled.png). |
| Conversation and response review | [Empty Chat shell after restart](assets/screenshots/signed-in-tour-2026-10-11/chat-empty-current.png) - no visible composer or conversation; conversation behavior is not established. The older pre-conversation capture remains labeled in the historical section. |
| Global search and application menus | [Empty global-search palette](assets/screenshots/signed-in-tour-2026-10-11/global-search-empty-dialog-after-restart.png); [File](assets/screenshots/signed-in-tour-2026-10-11/file-menu-after-restart.png), [Edit](assets/screenshots/signed-in-tour-2026-10-11/edit-menu-after-restart.png), [View](assets/screenshots/signed-in-tour-2026-10-11/view-menu-after-restart.png), and [Help](assets/screenshots/signed-in-tour-2026-10-11/help-menu-after-restart.png) menus after restart. Older Knowledge and menu captures remain preserved below. |
| Fabric operator and runner surfaces | Private development; not shown. |


### Corrected first-run setup (isolated current build)

These genuine captures show the corrected deferred-model path in a separate process using temporary configuration and data roots. The recommended local model remains uninstalled, and the guidance says it can be acquired after setup. No account was registered and no credential was entered. The Finish action was not invoked. The optional Cloud AI page showed masked configured-provider states, so it was not retained as a capture.

| Step | Verified capture |
| --- | --- |
| Preflight | [Model installation can be deferred](assets/screenshots/current-build-2026-10/setup-09-preflight-deferred-model-current.jpg) — the recommended model is not installed, and setup can continue with the listed limitations. |
| Providers / Local AI | [Local model remains uninstalled](assets/screenshots/current-build-2026-10/setup-10-local-model-deferred-current.jpg) — the wizard says setup can finish first and Chat stays unavailable until a local model or cloud Chat provider is configured. |

The two captures verify the corrected guidance in the current source build. Finish completion without a model or token is verified by focused tests; this isolated run intentionally stopped before account creation.

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

<details>
<summary>Historical setup and partial signed-in captures (29 images)</summary>

These genuine GTK captures were taken on 2026-10-10 from the `0.1.0` setup build and the older signed-in process. The setup run used a disposable profile and demo workspace; it did not register the synthetic administrator. Cloud credential fields were blank. The signed-in images are historical and predate the setup and Tasks/Jobs fixes; they do not establish current behavior. New signed-in captures are cropped to the application window and have the personal status text masked. The Chat shell was captured before the current conversation began. The Tools detail pane is masked, and the menus retain only the relevant menu area.

### Earlier first-run sequence (12 images)

The sequence shows the earlier setup validation mismatch: Preflight described model acquisition after setup, while Finish required an installed model or Hugging Face token. No model or token was used. The wizard now supports deferred installation; Chat stays unavailable until a local model is installed or a cloud Chat provider is configured. An uninstalled recommendation is not saved as an active Chat default. A Hugging Face token is only needed for gated or private model sources.

![ForgeWire GTK setup introduction from a disposable profile](assets/screenshots/current-build-2026-10/setup-01-introduction.png)

![ForgeWire GTK setup preflight from a disposable profile](assets/screenshots/current-build-2026-10/setup-02-preflight.png)

![ForgeWire GTK administrator setup page with synthetic demo data](assets/screenshots/current-build-2026-10/setup-03-administrator-account.png)

![ForgeWire GTK storage setup page](assets/screenshots/current-build-2026-10/setup-04-storage.png)

![ForgeWire GTK advanced storage settings](assets/screenshots/current-build-2026-10/setup-04b-storage-advanced.png)

![Native folder picker showing the disposable demo workspace](assets/screenshots/current-build-2026-10/setup-05a-workspace-picker.png)

![ForgeWire GTK local workspace setup page](assets/screenshots/current-build-2026-10/setup-05-local-workspace.png)

![ForgeWire GTK Local AI model selection page; selected model was not installed](assets/screenshots/current-build-2026-10/setup-06-providers-local-ai.png)

![Lower section of the ForgeWire GTK local model catalog](assets/screenshots/current-build-2026-10/setup-06b-providers-local-ai-lower.png)

![ForgeWire GTK optional cloud provider setup with blank credential fields](assets/screenshots/current-build-2026-10/setup-07-providers-cloud-top.png)

![Lower section of the ForgeWire GTK optional cloud provider setup with blank credential fields](assets/screenshots/current-build-2026-10/setup-07b-providers-cloud-bottom.png)

![ForgeWire GTK provider defaults page showing an unavailable saved provider](assets/screenshots/current-build-2026-10/setup-08-provider-defaults.png)

### Additional signed-in screens (11 images; pre-fix process)

The following screens were captured from the already signed-in process. The Chat shell was empty before the current conversation began. The Library was empty. The Documentation Browser displayed its text-preview fallback because WebKit was unavailable. The Providers page showed provider names only. The Skills page raised an initialization error. These captures document the observed UI and must not be read as proof that those functions are currently working.

![Empty Chat shell captured before the current conversation started](assets/screenshots/signed-in-tour-2026-10-10/chat-empty-before-user-conversation.png)

![File menu in the signed-in ForgeWire shell](assets/screenshots/signed-in-tour-2026-10-10/file-menu.png)

![Edit menu in the signed-in ForgeWire shell](assets/screenshots/signed-in-tour-2026-10-10/edit-menu.png)

![View menu in the signed-in ForgeWire shell](assets/screenshots/signed-in-tour-2026-10-10/view-menu.png)

![Help menu in the signed-in ForgeWire shell](assets/screenshots/signed-in-tour-2026-10-10/help-menu.png)

![Empty Knowledge Library](assets/screenshots/signed-in-tour-2026-10-10/knowledge-library.png)

![Documentation Browser with its text-preview fallback](assets/screenshots/signed-in-tour-2026-10-10/knowledge-docs.png)

![Builder persona catalog](assets/screenshots/signed-in-tour-2026-10-10/builder-personas.png)

![Provider names without opening configuration or credential fields](assets/screenshots/signed-in-tour-2026-10-10/builder-providers.png)

![Tools catalog with private detail pane masked](assets/screenshots/signed-in-tour-2026-10-10/builder-tools.png)

![Skills page showing an initialization error](assets/screenshots/signed-in-tour-2026-10-10/builder-skills-initialization-error.png)

### Earlier signed-in Tasks and Jobs states (6 images)

These screens show initialization errors and the blank Work content area before the disabled-state fix. They are evidence of the earlier state, not the current Tasks or Jobs result.

![Pre-fix ForgeWire Tasks view showing the task orchestration initialization error](assets/screenshots/signed-in-tour-2026-10-10/tasks-init-error-pre-fix.png)

![Earlier ForgeWire Tasks view showing an initialization error](assets/screenshots/workspace-2026-10-10/01-work-task-initialization-error.jpg)

![Close view of the earlier Tasks initialization error dialog](assets/screenshots/workspace-2026-10-10/01b-work-task-initialization-dialog.jpg)

![Earlier Work area after dismissing the Tasks error dialog](assets/screenshots/workspace-2026-10-10/02-work-after-error-dialog.jpg)

![Earlier ForgeWire Jobs view showing a scheduling error](assets/screenshots/workspace-2026-10-10/03-work-jobs-scheduling-error.jpg)

![Close view of the earlier Jobs scheduling error dialog](assets/screenshots/workspace-2026-10-10/03b-work-jobs-error-dialog.jpg)

### Navigation and dialog coverage

| Surface | Screens and relevant dialogs | Verified coverage |
| --- | --- | --- |
| First-run setup | Introduction, Preflight, Users/Admin, Storage/Advanced Storage, local workspace and native folder picker, Local AI, Cloud AI, Defaults | All 12 historical first-run captures remain preserved. Current isolated Preflight and Local AI pages show deferred installation. Focused tests verify Finish validation without a model or token. Finish was not invoked; no account or model was created. |
| Signed-in Chat | Main Chat, Blackboard, Context, Debug, conversation view | The current shell is empty and has no visible composer. No active conversation content was recorded; the shell does not establish end-to-end Chat behavior. |
| Work: Tasks and Jobs | Current task/job pages; earlier initialization dialogs | Latest-session [Tasks](assets/screenshots/signed-in-tour-2026-10-11/tasks-disabled-current-session.png) and [Jobs](assets/screenshots/signed-in-tour-2026-10-11/jobs-disabled-current-session.png) captures show the deliberate disabled state. Earlier error captures remain historical. Scheduling stayed disabled; no real jobs were run. |
| Work: Calendar | Month, Week, Day, Agenda, Sources, Categories, Settings, Sync | All eight listed pages captured on 2026-10-11. |
| Work: Budget | Dashboard, Policies, History, Reports, Alerts, Channels | All six listed pages captured on 2026-10-11. Financial totals and history entries were redacted where visible. |
| Knowledge | Library, Docs, Memory, RAG | Current [Library](assets/screenshots/signed-in-tour-2026-10-11/knowledge-library-empty-after-restart.png) reports 0 items with RAG left off. Current [Docs](assets/screenshots/signed-in-tour-2026-10-11/knowledge-docs-after-restart.png) uses the text-preview fallback because WebKit is unavailable. No separate Memory route or RAG page appeared. Earlier captures remain preserved. |
| Builder | Personas, Background personas, Providers, Tools, Skills | Current catalog captures are available. Skills displays an initialization error stating that metadata could not load; this is not a working Skills view. Provider credentials were not opened. |
| Operations | Orchestration (Status, Agent Activity, Handoffs, Intervention), Observability (Health, BenchLab), Guardrails, MCP (Servers only; 0 configured), Vector Store | Current captures cover the listed views, including the refreshed Health and BenchLab pages and the latest-session [Agent Activity](assets/screenshots/signed-in-tour-2026-10-11/operations-agent-activity-current-session.png). The blank Add BenchLab host form is captured; no form was submitted. Worker diagnostics and log paths are redacted. Metrics, Traces, Alerts, Approvals, Audit Log, MCP Tools, and MCP Status were not surfaced in the current Operations navigation and remain uncovered. |
| History | All Chats, Projects, project creation, archived projects | Current [All Chats](assets/screenshots/signed-in-tour-2026-10-11/history-all-chats-empty-after-restart-redacted.png) reports no stored conversations; the current-conversation label and timestamp in the sidebar are redacted. Current [Projects](assets/screenshots/signed-in-tour-2026-10-11/history-all-projects-unavailable-after-restart.png) says project access is unavailable until sign-in and project storage initialization; the blank project form was not submitted. Archived-project contents could not be verified while project storage was unavailable. |
| Settings | API Keys, Search & Weather, Image Generation, Communication Channels, Message Bus, Calendar Sources, Speech providers, Background Automation, Keyboard Shortcuts, Backups, Factory Reset | Current captures cover the listed pages. Credentials and conversation metadata are masked. Automation remains disabled. Backup/restore and factory-reset actions were not run; the factory-reset page is a safe inspection only. |
| Other navigation | Account, global search, notifications | The empty [global-search palette](assets/screenshots/signed-in-tour-2026-10-11/global-search-empty-dialog-after-restart.png) and [Notifications](assets/screenshots/signed-in-tour-2026-10-11/notifications-empty-after-restart-redacted.png) are captured. The account icon did not open a separate account page; Account remains uncovered. |
| Menus | File, Edit, View, Help | Current captures from 2026-10-11 are linked above; older captures remain preserved. |
| Dialogs | Setup picker and setup pages; Skills initialization error; MCP add-server and Operations intervention forms; blank BenchLab Add host form; empty global-search palette; Factory Reset inspection; historical Tasks/Jobs errors | Forms were not submitted and destructive actions were not confirmed. Account/project editing, library file actions, provider verification, calendar authorization, and approval/review dialogs remain uncovered. |

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

The first-run wizard can finish without an installed local model or cloud credentials. Chat remains unavailable until a local model is installed or a cloud Chat provider is configured. The wizard requires a Hugging Face token only for gated or private model sources.

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
- scoped capabilities and human approval for consequential actions where policy requires it
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

ForgeWire is designed and developed by [Jeremy Shows](https://github.com/JeremyShows) through [ForgeWire Labs](https://github.com/ForgeWireLabs). He defines the problems, designs the architecture, establishes engineering constraints, and drives implementation, integration, debugging, and validation. His approach draws on a lifelong background in fabrication, mechanical systems, IT, and software development, with an emphasis on making complex systems work under real constraints.

AI models and coding agents contribute across research, architecture exploration, implementation, debugging, testing, review, and documentation. Jeremy directs that work, challenges assumptions, resolves conflicting recommendations, and evaluates results through code review, tests, experiments, and observed system behavior. The architecture, technical judgment, and responsibility for what ships remain his.

## Technical direction

Work across ForgeWire and adjacent components has included **Rust, Python, TypeScript, GTK, React, PostgreSQL, SQLite, and rqlite**, alongside structured messaging and local or hosted model-provider integrations. This is a high-level inventory across a broader private effort—not a compatibility list, deployment guide, or promise that each technology is currently composed in the application. These are replaceable choices, not the identity of the system.

---

> Most assistants optimize for conversation. ForgeWire is being built to make AI-assisted work more inspectable, bounded, recoverable, and useful under real constraints.
