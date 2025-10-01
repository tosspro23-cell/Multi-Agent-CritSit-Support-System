# 🚀 Multi-Agent Critical Situation Support System

## 📖 Overview

This project introduces a **multi-agent collaboration framework** for managing **critical situation (CritSit) cases** in enterprise environments. Instead of relying on a single monolithic agent, this system leverages **specialized agents** that each focus on a distinct aspect of case handling — while working together in a **shared context**.

The design is fully **human-in-the-loop**: agents can propose, analyze, and trigger each other, but **final execution always requires human decision-making**.

---

## 🧑‍🤝‍🧑 Key Agents

1. **CritSit Advisor Agent**

   * Analyzes ongoing case progress.
   * Provides structured playbooks with timeline, blockers, and next steps.
   * Can trigger resourcing or escalation workflows (pending human confirmation).

2. **Executive Communication Agent**

   * Produces **four-part structured case updates**.
   * Adapts style depending on executive audience (e.g., VIP vs broad leadership).

3. **Wiki Agent**

   * Supplies **process, policy, and governance knowledge**.
   * Ensures compliance with internal protocols.

4. **Know Your Customer (KYC) Agent**

   * Delivers customer-specific insights (tenant usage, historical cases, adoption patterns).
   * Helps contextualize case impact and priority.

5. **CritSit Resourcing Agent** *(planned)*

   * Assists with **resource requests and duty manager escalations**.
   * Can auto-generate escalation emails or trigger escalation workflows.
   * **Execution requires human approval**.

6. **Handover Agent**

   * Generates structured **handover notes** for shift changes.
   * Highlights risks, pending tasks, and ownership clarity.

7. **Snapshot Retrieval (Graph & Dynamics)**

   * Pulls the **latest Teams conversation updates** from case channels.
   * Retrieves **Dynamics case background** or CMET Agent extracts.
   * Provides **context snapshots** that agents reference when producing outputs.

---

## 🔄 Automated Inter-Agent Collaboration

Agents can **request services from one another** to complete complex workflows:

* **CritSit Advisor** → may trigger **Resourcing Agent** if additional resources are needed.
* **Executive Communication Agent** → may call **Wiki Agent** or **KYC Agent** to enrich updates.
* **Handover Agent** → aggregates outputs from all others to prepare structured notes.

⚠️ **Human-in-the-Loop Control**

* While agents can invoke each other, **all actions that impact escalation, communication, or execution require explicit human approval**.
* This ensures **safety, accountability, and governance compliance**.

---

## 🧩 Why Multi-Agent Instead of One Big Agent?

* **Specialization** → Each agent focuses deeply on a single domain, ensuring precision and consistency.
* **Independent Workflows** → Agents run in parallel, avoiding bottlenecks or entangled logic.
* **Scalability** → New agents can be added without disrupting existing ones.
* **Robustness** → Failure of one agent doesn’t collapse the whole system.
* **Human Control** → Multi-agent orchestration allows **fine-grained human decision points** rather than delegating everything to one “black box” super-agent.

💡 **Analogy:**
This is like a hospital team: surgeons, nurses, and pharmacists each specialize in their domain. They coordinate, but **a human chief doctor makes the final call**.

---

## 🌟 Value Proposition

* **Faster insights** → Real-time snapshots from Teams & Dynamics.
* **Higher clarity** → Each agent delivers outputs in structured formats.
* **Reduced risk** → Human-in-the-loop approval ensures safe decisions.
* **Future-ready** → Easily extensible with new agents (e.g., Risk Prediction, Automated Reporting).

---

## 🛠️ System Flow (Mermaid Diagram)

```mermaid
flowchart TD

    A[Case Teams Chat + Dynamics Background] -->|Snapshot Retrieval| B[Case Snapshot]

    B --> C[CritSit Advisor Agent]
    B --> D[Executive Communication Agent]
    B --> E[Wiki Agent]
    B --> F[KYC Agent]

    C -->|Resource Needs| G[CritSit Resourcing Agent]
    D -->|Missing Context| E
    D -->|Customer Impact| F

    C --> H[Handover Agent]
    D --> H
    E --> H
    F --> H
    G --> H

    H --> I[👤 Human Decision & Approval]

    I -->|Approved| J[Final Execution (Escalation / Updates / Notes)]
    I -->|Not Approved| K[Revise / Retry Workflow]
```

---

## ✅ Human-in-the-Loop Guarantee

* **Agents provide analysis, drafts, and recommendations.**
* **Humans review, approve, or reject before execution.**
* **No fully autonomous escalation or customer communication is performed.**


要不要我再帮你写一个 **应用场景的具体示例**（比如一个实际 case，从 snapshot → advisor → resourcing → exec comm → handover → human approval → final outcome 的全过程）？
