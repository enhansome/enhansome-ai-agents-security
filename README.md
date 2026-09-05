# Awesome AI Agents Security with stars

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/ProjectRecon/awesome-ai-agents-security/blob/main/CONTRIBUTING.md) ⭐ 68 | 🐛 81 | 📅 2026-06-12
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/ProjectRecon/awesome-ai-agents-security/graphs/commit-activity) ⭐ 68 | 🐛 81 | 📅 2026-06-12

A curated list of open-source tools, frameworks, and resources for securing autonomous AI agents.

This list is organized by the **security lifecycle** of an autonomous agent, covering red teaming, runtime protection, sandboxing, and governance.

## 📖 Table of Contents

* [Agent Firewalls & Gateways (Runtime Protection)](#-agent-firewalls--gateways-runtime-protection)
* [Red Teaming & Vulnerability Scanners](#-red-teaming--vulnerability-scanners)
* [Static Analysis & Linters](#-static-analysis--linters)
* [Sandboxing & Isolation Environments](#-sandboxing--isolation-environments)
* [Guardrails & Compliance](#-guardrails--compliance)
* [Benchmarks & Datasets](#-benchmarks--datasets)
* [Identity & Authentication](#-identity--authentication)
* [Contributing](#-contributing)

***

## 🛡️ Agent Firewalls & Gateways (Runtime Protection)

*Tools that sit between the agent and the world to filter traffic, prevent unauthorized tool access, and block prompt injections.*

* **[AgentGateway](https://github.com/agentgateway/agentgateway) ⭐ 4,728 | 🐛 273 | 🌐 Rust | 📅 2026-09-05** - A Linux Foundation project providing an AI-native proxy for secure connectivity (A2A & MCP protocols). It adds RBAC, observability, and policy enforcement to agent-tool interactions.
* **[Immunity Agent](https://github.com/PrismorSec/immunity-agent) ⭐ 338 | 🐛 51 | 🌐 Python | 📅 2026-09-05** - Security-focused AI agent runtime for scanning prompt injection, MCP risks, unsafe package installs, and dangerous agent actions before execution.
* **[Envoy AI Gateway](https://gateway.envoyproxy.io/)** - An Envoy-based gateway that manages request traffic to GenAI services, providing a control point for rate limiting and policy enforcement.

## ⚔️ Red Teaming & Vulnerability Scanners

*Offensive tools to test agents for security flaws, loop conditions, and unauthorized actions.*

* **[Strix](https://github.com/usestrix/strix) ⭐ 60,686 | 🐛 361 | 🌐 Python | 📅 2026-09-05** - An autonomous AI agent designed for penetration testing. It runs inside a docker sandbox to actively probe applications and generate verified exploit capabilities.
* **[Cybersecurity AI (CAI)](https://github.com/aliasrobotics/cai) ⚠️ Archived** - A framework for building specialized security agents for offensive and defensive operations, often used in CTF (Capture The Flag) scenarios.
* **[Garak](https://github.com/leondz/garak) ⭐ 9,116 | 🐛 416 | 🌐 Python | 📅 2026-09-04** - The "Nmap for LLMs." A vulnerability scanner that probes models for hallucination, data leakage, and prompt injection susceptibilities.
* **[Agentic Security](https://github.com/msoedov/agentic_security) ⭐ 1,985 | 🐛 73 | 🌐 Python | 📅 2026-09-01** - A dedicated vulnerability scanner for agent workflows and LLMs capable of running multi-step jailbreaks and fuzzing attacks against agent logic.
* **[A2A Scanner](https://github.com/cisco-ai-defense/a2a-scanner) ⭐ 166 | 🐛 4 | 🌐 Python | 📅 2026-04-16** - A scanner by Cisco designed to inspect "Agent-to-Agent" communication protocols for threats, validating agent identities and ensuring compliance with communication specs.
* **[PyRIT](https://github.com/Azure/PyRIT) ⚠️ Archived** - Microsoft's open-source red teaming framework for generative AI. It automates multi-turn adversarial attacks to test if an agent can be coerced into harmful behavior.

## 🔍 Static Analysis & Linters

*Tools to analyze agent configuration and logic code before deployment.*

* **[Checkov](https://github.com/bridgecrewio/checkov) ⭐ 8,983 | 🐛 162 | 🌐 Python | 📅 2026-09-05** - While primarily for IaC, Checkov includes policies for scanning AI infrastructure and configurations to prevent misconfigurations in deployment.
* **[Agentic Radar](https://github.com/splx-ai/agentic-radar) ⭐ 1,046 | 🐛 15 | 🌐 Python | 📅 2025-11-27** - A static analysis tool that visualizes agent workflows (LangGraph, CrewAI, AutoGen). It detects risky tool usage, permission loops, and maps them to known vulnerabilities.
* **[ATR (Agent Threat Rules)](https://github.com/Agent-Threat-Rule/agent-threat-rules) ⭐ 382 | 🐛 72 | 🌐 TypeScript | 📅 2026-09-05** - 108 open-source regex detection rules for AI agent threats (prompt injection, tool poisoning, credential exfiltration, skill compromise). <1ms per scan. Adopted by Cisco AI Defense.
* **[Aguara](https://github.com/garagon/aguara) ⭐ 88 | 🐛 5 | 🌐 Go | 📅 2026-09-02** - A static security scanner for AI agent skills and MCP server configurations. Detects prompt injection, credential leaks, data exfiltration, and supply-chain attacks with 173 built-in rules, 4 analysis layers, and remediation guidance.
* **[Agent Bound](https://github.com/ElPaisano/agent-bound)** - A design-time analysis tool that calculates "Agentic Entropy"—a metric to quantify the unpredictability and risk of infinite loops or unconstrained actions in agent architectures.

## 📦 Sandboxing & Isolation Environments

*Secure runtimes to prevent agents from damaging the host system during code execution.*

* **[OpenHands](https://github.com/All-Hands-AI/OpenHands) ⭐ 86,244 | 🐛 659 | 🌐 TypeScript | 📅 2026-09-05** - Formerly OpenDevin, this platform includes a secure runtime environment for autonomous coding agents to operate without accessing the host machine's sensitive files.
* **[Agent-Infra Sandbox](https://github.com/agent-infra/sandbox) ⭐ 5,847 | 🐛 70 | 🌐 Python | 📅 2026-08-25** - An "All-In-One" sandbox combining Browser, Shell, VSCode, and File System access in a single Docker container, optimized for agentic tasks.
* **[Kubernetes Agent Sandbox](https://github.com/kubernetes-sigs/agent-sandbox) ⭐ 3,747 | 🐛 227 | 🌐 Go | 📅 2026-09-05** - A Kubernetes Native project providing a Sandbox Custom Resource Definition (CRD) to manage isolated, stateful workloads for AI agents.
* **[SandboxAI](https://github.com/substratusai/sandboxai) ⭐ 144 | 🐛 5 | 🌐 Go | 📅 2025-02-05** - An open-source runtime for executing AI-generated code (Python/Shell) in isolated containers with granular permission controls.

## 🚧 Guardrails & Compliance

*Middleware to enforce business logic and safety policies on inputs and outputs.*

* **[LiteLLM Guardrails](https://github.com/BerriAI/litellm) ⭐ 58,090 | 🐛 4,906 | 🌐 Python | 📅 2026-09-05** - While known for model proxying, LiteLLM includes built-in guardrail features to filter requests and responses across multiple LLM providers.
* **[Guardrails](https://github.com/guardrails-ai/guardrails) ⭐ 7,357 | 🐛 82 | 🌐 Python | 📅 2026-09-04** - A Python framework for validating LLM outputs against structural and semantic rules (e.g., "must return valid JSON," "must not contain PII").
* **[NeMo Guardrails](https://github.com/NVIDIA/NeMo-Guardrails) ⭐ 7,068 | 🐛 217 | 🌐 Python | 📅 2026-09-04** - NVIDIA's toolkit for adding programmable rails to LLM-based apps. It ensures agents stay on topic, avoid jailbreaks, and adhere to defined safety policies.
* **[OWASP Agent Memory Guard](https://github.com/OWASP/www-project-agent-memory-guard) ⭐ 170 | 🐛 26 | 🌐 Python | 📅 2026-09-05** - An official OWASP project that detects and blocks AI agent memory poisoning attacks (OWASP ASI06). Provides a drop-in middleware for LangChain, AutoGen, and CrewAI pipelines with real-time threat detection, sanitization hooks, and audit logging. `pip install agent-memory-guard`.

## 📊 Benchmarks & Datasets

*Resources to evaluate agent security performance.*

* **[CVE Bench](https://github.com/uiuc-kang-lab/cve-bench) ⭐ 279 | 🐛 8 | 🌐 Python | 📅 2026-01-14** - A benchmark for evaluating an AI agent's ability to exploit real-world web application vulnerabilities (useful for testing defensive agents).

## 🆔 Identity & Authentication

*Tools to manage agent identity (non-human identities).*

* **[OneCLI](https://github.com/onecli/onecli) ⭐ 3,448 | 🐛 139 | 🌐 TypeScript | 📅 2026-09-03** - Open-source credential vault for AI agents. A Rust HTTP gateway intercepts agent requests and injects API credentials transparently, so agents never handle raw keys. Supports per-agent scoped tokens and AES-256-GCM encryption at rest.
* **[WSO2](https://github.com/wso2)** - An identity management solution that treats AI agents as first-class identities, enabling secure authentication and authorization for agent actions.

***

## 🤝 Contributing

Contributions are welcome! Please read the contribution guidelines first.

1. Fork the project.
2. Create your feature branch (`git checkout -b feature/AmazingFeature`).
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`).
4. Push to the branch (`git push origin feature/AmazingFeature`).
5. Open a Pull Request.

***

> _Enhansomed by [enhansome](https://github.com/enhansome) on 2026-09-05._
