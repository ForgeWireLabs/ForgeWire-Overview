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
| See the interface | View 12 first-run captures and five earlier signed-in workspace captures below. The workspace captures predate the scheduler fix; the navigation coverage table marks every screen still awaiting a current capture. |
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

These captures show ForgeWire's actual GTK first-run setup and its native workspace folder picker, taken on 2026-10-10 from the `0.1.0` development build. Setup used an isolated disposable profile, a synthetic **Demo Operator** administrator profile, and a generic demo workspace. Cloud provider fields were left blank. No production profile or provider credentials were used.

![ForgeWire GTK setup introduction, 0.1.0 development build with disposable demo data](assets/screenshots/current-build-2026-10/setup-01-introduction.png)

*ForgeWire GTK first-run introduction in the `0.1.0` development build, captured with a disposable demo profile.*

![ForgeWire GTK setup preflight showing local hardware and model availability, 0.1.0 development build with disposable demo data](assets/screenshots/current-build-2026-10/setup-02-preflight.png)

*ForgeWire GTK preflight in the `0.1.0` development build, captured with a disposable demo profile. Hardware values are detected from the capture machine.*

<details>
<summary>Remaining setup captures (10 images)</summary>

The 12 screenshots cover every setup step. The introduction and preflight screens are shown above. Each remaining image is a genuine capture from the same ForgeWire `0.1.0` GTK development build and disposable demo profile. Images are shown separately so the setup text remains readable.

### Administrator account

![ForgeWire GTK administrator account setup page, 0.1.0 development build with disposable demo data](assets/screenshots/current-build-2026-10/setup-03-administrator-account.png)

*Users step in the ForgeWire GTK `0.1.0` development build, filled with a disposable administrator profile.*

### Storage

![ForgeWire GTK storage setup page, 0.1.0 development build with disposable demo data](assets/screenshots/current-build-2026-10/setup-04-storage.png)

*Storage choices in the ForgeWire GTK `0.1.0` development build, captured with a disposable demo profile.*

![ForgeWire GTK advanced storage settings, 0.1.0 development build with disposable demo data](assets/screenshots/current-build-2026-10/setup-04b-storage-advanced.png)

*Advanced storage settings in the ForgeWire GTK `0.1.0` development build, captured with a disposable demo profile.*

### Local workspace

![Windows folder picker opened by ForgeWire GTK setup at the synthetic demo folder, 0.1.0 development build with disposable demo data](assets/screenshots/current-build-2026-10/setup-05a-workspace-picker.png)

*Windows folder picker opened from the ForgeWire GTK `0.1.0` development build, showing only the disposable demo workspace.*

![ForgeWire GTK local workspace setup page showing the synthetic demo folder, 0.1.0 development build with disposable demo data](assets/screenshots/current-build-2026-10/setup-05-local-workspace.png)

*Local workspace scope in the ForgeWire GTK `0.1.0` development build, set to a generic disposable demo folder.*

### Providers and defaults

![ForgeWire GTK local AI model selection page, 0.1.0 development build with disposable demo data](assets/screenshots/current-build-2026-10/setup-06-providers-local-ai.png)

*Local AI choices in the ForgeWire GTK `0.1.0` development build, captured with a disposable demo profile. The selected model is not installed on the capture machine.*

![ForgeWire GTK lower local model catalog, 0.1.0 development build with disposable demo data](assets/screenshots/current-build-2026-10/setup-06b-providers-local-ai-lower.png)

*Lower local model catalog in the ForgeWire GTK `0.1.0` development build, captured with a disposable demo profile. The listed models are not installed on the capture machine.*

![ForgeWire GTK optional cloud provider setup page, upper section, 0.1.0 development build with disposable demo data](assets/screenshots/current-build-2026-10/setup-07-providers-cloud-top.png)

*Optional cloud providers in the ForgeWire GTK `0.1.0` development build, captured with a disposable demo profile. All credential fields are blank.*

![ForgeWire GTK optional cloud provider setup page, lower section, 0.1.0 development build with disposable demo data](assets/screenshots/current-build-2026-10/setup-07b-providers-cloud-bottom.png)

*Lower section of the cloud provider page in the ForgeWire GTK `0.1.0` development build, captured with a disposable demo profile. All credential fields are blank.*

![ForgeWire GTK provider defaults page with the current saved-provider warning, 0.1.0 development build with disposable demo data](assets/screenshots/current-build-2026-10/setup-08-provider-defaults.png)

*Provider defaults in the ForgeWire GTK `0.1.0` development build, captured with a disposable demo profile. The image preserves the visible warning that the saved `openai` choice is unavailable.*

</details>

### Signed-in workspace: earlier Tasks and Jobs state

These five captures show the running ForgeWire development workspace on 2026-10-10 with the existing local account; the checked-out source reported version `0.2.0`. They predate the scheduler-state change below. Tasks and Jobs showed initialization-error dialogs in that run. The three full-window images are cropped above the status footer to remove the local account name and provider/voice settings. The two close-ups contain only the dialogs.

![ForgeWire development workspace showing the Work navigation and pre-remediation task initialization error](assets/screenshots/workspace-2026-10-10/01-work-task-initialization-error.jpg)

*Earlier Tasks view, captured on 2026-10-10. The status footer is cropped to remove local account and provider details.*

![Close capture of the ForgeWire task initialization error dialog](assets/screenshots/workspace-2026-10-10/01b-work-task-initialization-dialog.jpg)

*Close view of the earlier initialization error dialog; no account or provider details are present.*

![ForgeWire Work area after dismissing the task initialization error](assets/screenshots/workspace-2026-10-10/02-work-after-error-dialog.jpg)

*After dismissing the earlier Tasks dialog, the Work content area was blank in this capture. The status footer is cropped.*

![ForgeWire development workspace showing the Jobs navigation and pre-remediation scheduling error](assets/screenshots/workspace-2026-10-10/03-work-jobs-scheduling-error.jpg)

*Earlier Jobs view, captured on 2026-10-10. The status footer is cropped to remove local account and provider details.*

![Close capture of the ForgeWire Jobs scheduling error dialog](assets/screenshots/workspace-2026-10-10/03b-work-jobs-error-dialog.jpg)

*Close view of the earlier Jobs initialization error dialog; no account or provider details are present.*

### Setup capture notes

The setup screenshots show a run made before the deferred-model validation fix. The wizard reached Provider Defaults but did not complete; the synthetic administrator profile was not registered. Preflight said the recommended Bonsai 8B model could be installed after setup, while Finish still required an installed model or a Hugging Face token. The selected model was not installed, and no token was entered. The saved `openai` default was also reported as unavailable. The source change now allows setup to finish without either requirement and explains that Chat remains unavailable until a local model is installed or a cloud Chat provider is configured. These images preserve the earlier run and do not depict the corrected screen.

The app's source now distinguishes an intentional scheduler opt-out and renders a disabled-state page for Tasks and Jobs. That result has not yet been captured in a signed-in window. The five existing workspace images remain historical evidence of the prior error state.

### Signed-in navigation and dialog coverage

This inventory follows the GTK navigation surfaces. “Not captured” means the page was not reached in the screenshot run; it is not a claim that the screen is broken or working.

| Surface | Distinct screens and relevant dialogs | Capture status |
| --- | --- | --- |
| First-run setup | Introduction, Preflight, Users, Admin, Storage, Advanced Storage, local workspace, native folder picker, Local AI, Cloud AI, Defaults | 12 first-run images present; these show the pre-fix deferred-model validation behavior. |
| Chat | Main Chat and conversation view | Not captured. |
| Work | Tasks and Jobs | Earlier initialization-error states captured; current disabled-state screens still need recapturing. |
| Work | Calendar and Budget | Not captured. |
| Knowledge | Library, Memory, Docs, RAG Settings | Not captured. |
| Builder | Personas, Providers, Tools, Skills | Not captured. |
| Operations | Orchestration; Health, Metrics, Traces, Alerts; Guardrails, Approvals, Audit Log; MCP Servers, MCP Tools, MCP Status; Vector Store | Not captured. |
| History | All Chats, recent conversations, Projects, project creation, archived projects | Not captured. |
| Settings | API Keys, Search & Weather, Image Generation, Communication Channels, Message Bus, Calendar Sources, Speech, Background Automation, Keyboard Shortcuts, Backups, Factory Reset | Not captured. No credential fields were opened during the capture run. |
| Other navigation | Account, global search, notifications, File/Edit/View/Help menus | Not captured. |
| Dialogs | Advanced Storage and the native folder picker are present in the first-run set; prior Tasks and Jobs initialization dialogs are shown above. Account/project editing, library file actions, provider verification, MCP server actions, backup/restore, factory reset, calendar authorization, and approval/review dialogs remain to inspect. | Remaining workspace dialogs not captured. |

## Using a private development build

These notes describe the current internal setup flow for invited testers. ForgeWire has no public installer or supported public installation path.

1. Review the preflight page for detected hardware and installed models.
2. Create an administrator account for the isolated workspace. Use a dedicated demo identity when capturing or evaluating the interface.
3. Choose storage. Local SQLite is suited to a single-machine trial. Shared or custom storage needs operator configuration.
4. Choose a local workspace folder. Keep runner-accessible demo files in that folder.
5. Finish without a local model or Hugging Face token if you want to defer acquisition. After setup, install a model from Model Library. A token is needed only for gated or private model sources.
6. Cloud provider credentials are optional in the wizard. If neither a local model nor a cloud Chat provider is configured, Chat remains unavailable until one is added.
7. Review the eligible provider defaults and finish setup. An uninstalled local model is not saved as an active Chat default.

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

**Configuration-dependent path:** when scheduling is enabled and initialized, open the task area, select a task, and review its description, status, and available actions. The task UI does not provide general task creation, and its review controls do not imply an automated recovery path. In the captured 2026-10-10 workspace, Tasks and Jobs did not initialize; the current source now distinguishes an intentional disabled configuration, but the new screen has not been recaptured.

## What a user can do in a private workspace

These instructions apply only to a workspace that has already been installed and configured by its operator. They are not a public installation guide.

1. **Open ForgeWire.** Use the application launcher configured for your workspace.
2. **Sign in if required.** Use the workspace account. Contact its operator if you do not have one or sign-in is unavailable.
3. **Choose an active persona.** Open the Personas manager, choose an available persona, and confirm it is active. The current conversation uses that persona.
4. **Start a conversation.** Open the conversation workspace, send a short request, and review the response before acting on recommendations.
5. **Organize related chats in a project.** Under **History → Projects**, create a workspace for shared instructions and files. Project context supplements the active persona; it does not replace persona policy or capability grants.
6. **Use knowledge features when configured.** If retrieval is enabled, the workspace may allow document upload and knowledge-base queries. Check indexing and use the query test view to verify what was retrieved.
7. **Review tasks when scheduling is available.** Tasks and Jobs require scheduling to be enabled and initialized. If the workspace shows them as disabled, ask its operator to review `job_scheduling.enabled` and the configured job store. The UI does not currently provide general task creation.

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
