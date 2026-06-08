---
marp: true
theme: default
paginate: true
html: true
size: 16:9
---

<!-- This is slide 1 -->
# OWASP MCP Top 10

The OWASP Model Context Protocol (MCP) Top 10 is a security framework that highlights the most critical risks facing MCP-enabled AI applications and agents, helping organizations build safer, more secure, and trustworthy AI systems.

---

<!-- This is slide MCP01-1 -->
<!-- _class: image -->
![bg contain](../../Resources/1_What_is_MCP.png)

---

# MCP Server for Application Security Testing (AST)
MCP (Model Context Protocol) connects AI Security Agents with Application Security tools such as SAST, DAST, SCA, and API Security. 

It enables automated scan orchestration, centralized findings, and risk-based remediation through a single protocol. MCP improves efficiency with secure authentication, audit logging, and standardized data exchange.

---

<!-- This is slide MCP01-2 -->
<!-- _class: image -->
![bg contain](../../Resources/2_MCP_in_Security.png)

---

# How MCP (Model Context Protocol) Works

MCP acts as a universal communication layer between AI agents and external tools, enabling secure, standardized, and automated interactions. 

The AI agent sends requests through the MCP Server, which authenticates, routes, and orchestrates the appropriate tools, then normalizes the results into a consistent format. This allows AI systems to seamlessly leverage multiple tools and services through a single protocol without requiring custom integrations.


User → AI Agent → MCP Server → Tool Connectors → External Tools → Results

---

<!-- This is slide MCP02-1 -->
<!-- _class: image -->
![bg contain](../../Resources/3_How_MCP_Works.png)

---

<!-- _class: image -->
![bg contain](../../Resources/MCP_RealTime_Example.png)

---

<!-- This is slide MCP02-2 -->
<!-- _class: image -->
![bg contain](../../Resources/4_MCP_Top10.png)

---



# MCP01 - Token Mismanagement & Secret Exposure

Hard-coded credentials, long-lived tokens, and secrets stored in model memory or protocol logs can expose sensitive environments to unauthorized access. Attackers may retrieve these tokens through prompt injection, compromised context, or debug traces, leading to full compromise of connected systems.

---
<!-- This is slide MCP03-1 -->
![bg contain](../../Resources/5MCP01.png)

---

<!-- This is slide MCP03-2 -->
![bg contain](../../Resources/MCP01_Part2.png)

---


# MCP02 - Privilege Escalation via Scope Creep

Temporary or loosely defined permissions within MCP servers often expand over time, granting agents excessive capabilities. 
An attacker exploiting weak scope enforcement can perform unintended actions such as repository modification, system control, or data exfiltration.

--- 

![bg contain](../../Resources/7MCP02-1.png)

---


![bg contain](../../Resources/MCP02_Part2.png)


---
<!-- This is slide MCP03 -->
# MCP03 - Tool Poisoning

Tool poisoning occurs when an adversary compromises the tools, plugins, or their outputs that an AI model depends on, injecting malicious, misleading, or biased context to manipulate the model's behavior.

---

![bg contain](../../Resources/9MCP03.png)

---


![bg contain](../../Resources/MCP03_Part2.png)

---

<!-- This is slide MCP04 -->

# MCP04 - Software Supply Chain Attacks & Dependency Tampering

A compromised dependency can alter agent behavior or introduce execution-level backdoors.

---

![bg contain](../../Resources/11MCP04.png)

---

![bg contain](../../Resources/MCP04_Part2.png)

---

<!-- This is slide MCP05 -->

# MCP05 - Command Injection & Execution

Command injection occurs when an AI agent constructs and executes system commands, shell scripts, API calls, or code snippets using untrusted input whether from user prompts, retrieved context, or third-party data sources, without proper validation or sanitization.

---

![bg contain](../../Resources/13MCP05.png)

---

![bg contain](../../Resources/14MCP05.png)

---

<!-- This is slide MCP06 -->

# MCP06 - Intent Flow Subversion

The Model Context Protocol enables agents to retrieve complex context that can act as a secondary instruction channel. 

Subversion occurs when malicious instructions embedded in context hijack the “Intent Flow,” steering the agent away from the user’s original goal toward an attacker’s objective.

---

![bg contain](../../Resources/15MCP06.png)

---

![bg contain](../../Resources/16MCP06.png)

---
<!-- This is slide MCP07 -->

# MCP07 - Insufficient Authentication & Authorization

Inadequate authentication and authorization occur when MCP servers, tools, or agents fail to properly verify identities or enforce access controls during interactions. 

Since MCP ecosystems often involve multiple agents, users, and services exchanging data and executing actions, weak or missing identity validation exposes critical attack paths.

---
![bg contain](../../Resources/17MCP07.png)

---

![bg contain](../../Resources/18MCP07.png)

---




<!-- This is slide MCP08 -->

# MCP08 - Lack of Audit and Telemetry

Limited telemetry from MCP servers and agents impedes investigation and incident response. 

Maintain detailed logs of tool invocations, context changes, and user-agent interactions with immutable audit trails.

---
![bg contain](../../Resources/19MCP08.png)

---

![bg contain](../../Resources/20MCP08.png)


---
<!-- This is slide MCP09 -->

# MCP09 - Shadow MCP Servers

“Shadow MCP Servers” refer to unapproved or unsupervised deployments of Model Context Protocol instances that operate outside the organization’s formal security governance.

Much like Shadow IT, these rogue MCP nodes are often spun up by developers, research teams, or data scientists for experimentation, testing, or convenience, frequently using default credentials, permissive configurations, or unsecured APIs.

---
![bg contain](../../Resources/21MCP09.png)

---

![bg contain](../../Resources/22MCP09.png)

---
<!-- This is slide MCP10 -->

# MCP10 - Context Injection & Over-Sharing

In the Model Context Protocol (MCP), “context” represents the working memory that stores prompts, retrieved data, and intermediate outputs across agents or sessions. 

When context windows are shared, persistent, or insufficiently scoped, sensitive information from one task, user, or agent may be exposed to another. This phenomenon known as context over-sharing turns convenience into a liability.

---
![bg contain](../../Resources/23MCP10.png)

---

![bg contain](../../Resources/24MCP10.png)











