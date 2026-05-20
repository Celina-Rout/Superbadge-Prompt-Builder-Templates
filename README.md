# Prompt Builder Templates Superbadge — Reference Project

> Salesforce DX project containing the configuration and metadata for the **Prompt Builder Templates Superbadge** (part of the *Agentblazer Innovator* trail on Trailhead).

[![Trailhead](https://img.shields.io/badge/Trailhead-Superbadge-00A1E0?logo=salesforce&logoColor=white)](https://trailhead.salesforce.com/content/learn/superbadges/superbadge_prompt_builder_templates_sbu)
[![Salesforce DX](https://img.shields.io/badge/Salesforce-DX-009EDB?logo=salesforce&logoColor=white)](https://developer.salesforce.com/tools/sfdxcli)

---

## 📖 About

This repository contains my completed SFDX project for the **Prompt Builder Templates Superbadge**, where you act as a Salesforce admin/developer for **Tranquil Trails** — a wellness company using generative AI to translate content, summarize client data, and personalize outbound emails.

The superbadge validates hands-on skills in:

- Using the **Prompt Template Workspace** to configure **Flex**, **Field Generation**, and **Sales Email** prompt template types
- Inserting **merge fields, related records, and prompt instructions** into templates
- Modifying an **existing record-triggered flow** to invoke a prompt template
- Grounding prompts with the right Salesforce data so the LLM returns relevant, on-brand output
- Testing prompts in the **Prompt Template Workspace** and verifying behavior on real records

🔗 **Superbadge link:** <https://trailhead.salesforce.com/content/learn/superbadges/superbadge_prompt_builder_templates_sbu>

---

## ⚠️ Disclaimer — Please Read Before Using

This repo is shared for **learning and reference purposes only**.

- ✅ Use it to **understand** the prompt structure, resource references, and flow wiring — and to unblock yourself when stuck.
- ❌ Do **not** blindly copy-deploy it into your special Developer Edition org and submit it as your own work.

The whole point of a superbadge is building the muscle memory. Read the prompts here, then write your own. **Earn the badge honestly.**

---

## 🧰 Prerequisites

Before you start, make sure you have:

1. A **special Developer Edition org** for this superbadge — sign up via the link in the **Prework and Notes** section on the Trailhead page (a standard Playground will **not** work; this org has *Tranquil Trails* sample data pre-installed and no Data Cloud).
2. **Einstein Generative AI enabled** in the org — without it, no challenge will pass.
3. **English** set as the user language in *My Personal Information* — required for the translation challenge.
4. (Recommended) **"Enable secure and persistent browser caching to improve performance"** turned **off** in *Session Settings* to avoid stale UI issues.
5. **Salesforce CLI (`sf`)** installed → [Install guide](https://developer.salesforce.com/tools/sfdxcli)
6. **VS Code** with the **Salesforce Extension Pack**
7. **Git** installed locally
8. Completion of the recommended prerequisite modules (Prompt Builder Basics, Generative AI fundamentals, Flow Builder essentials).

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Celina-Rout/Superbadge-Prompt-Builder-Templates.git
cd Superbadge-Prompt-Builder-Templates
```

### 2. Authorize your Superbadge Developer Edition org

```bash
sf org login web --alias PromptBuilderSBOrg --set-default
```

### 3. Deploy the metadata to your org

```bash
sf project deploy start --target-org PromptBuilderSBOrg
```

### 4. Open the org

```bash
sf org open --target-org PromptBuilderSBOrg
```

> 💡 Some prompt template definitions may need to be **activated** in the UI after deploy. Go to *Setup → Prompt Builder*, open each template, and click **Activate**.

---

## 🗂️ Project Structure

```
.
├── force-app/
│   └── main/
│       └── default/
│           ├── genAiPromptTemplates/   # Prompt templates (Flex, Field Generation, Sales Email)
│           ├── flows/                  # Record-triggered flow updated to invoke a prompt
│           ├── objects/                # Fields used as prompt inputs / outputs
│           ├── flexipages/             # Lightning pages where templates are surfaced
│           └── permissionsets/         # Permissions for prompt template users
├── config/
│   └── project-scratch-def.json
├── manifest/
│   └── package.xml
├── sfdx-project.json
└── README.md
```

---

## ✅ Challenges Covered

| # | Challenge | Template Type | What it builds |
|---|-----------|---------------|----------------|
| 1 | **Translate Related Record Content** | Flex | A Flex template that translates record content, invoked from an existing record-triggered flow |
| 2 | **Summarize Related Records** | Field Generation | A "Summarize Client Goals" template on Contact that grounds the LLM with related Fitness records |
| 3 | **Personalize Outbound Emails** | Sales Email | A Sales Email template that drafts a personalized message using Contact + related data |
| 4 | **Activate and Test** | — | Activate templates, surface them on the right Lightning page, and verify end-to-end behavior |

> Detailed exercise walkthroughs are on the official Trailhead page — this repo only contains the resulting metadata.

---

## 💡 Tips That Helped Me

- **Use the exact names** the challenge specifies — the API name, label, and description all matter. One typo = a failed check.
- **Set your user language to English** *before* you start. Switching mid-way doesn't always retrigger correctly.
- When inserting resources (merge fields, related lists), make sure you're picking the **correct object path** — e.g., the *related list* of Fitness records on Contact, not a similarly named field elsewhere.
- After updating a prompt, **save and re-test in the workspace** with a real record before running the flow. The workspace gives you faster feedback than the record page.
- If the **Check Challenge** button fails with a vague error, re-read the prompt instructions in the exercise notes — usually a required word, tone, or instruction line was omitted.
- **Deactivate and reactivate** a template if changes don't seem to take effect.

---

## 🤝 Contributing

Found a cleaner prompt or noticed something has gone stale as Salesforce updates Prompt Builder? PRs and issues are welcome.

---

## 📬 Connect

If this helped you earn your badge, drop a ⭐ on the repo — it keeps me motivated to share more.

- **Trailhead:** <https://www.salesforce.com/trailblazer/cr99>
- **LinkedIn:** <https://www.linkedin.com/in/celina-rout9999/>

---
