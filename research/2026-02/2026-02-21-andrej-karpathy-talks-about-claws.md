# Andrej Karpathy's "Claws": The New AI Agent Orchestration Layer

## Executive Summary

Andrej Karpathy has identified "Claws" as an emerging category of AI agent systems representing a new orchestration layer above LLMs. These systems run locally on personal hardware, communicate via messaging protocols, and handle both direct instructions and task scheduling—positioning them as the next evolution beyond basic LLM agents. However, security vulnerabilities in the flagship OpenClaw implementation have prompted the development of lightweight alternatives like NanoClaw.

> **Confidence: High** ✅ — Multiple independent sources confirm Karpathy's coining of the term, technical details verified through code repositories, security vulnerabilities documented by multiple security firms.

## Key Findings

**Architectural Evolution**: Karpathy positions Claws as "a new layer on top of LLM agents, taking the orchestration, scheduling, context, tool calls and a kind of persistence to a next level." This represents a shift from stateless chat interfaces to persistent, locally-running agent systems that can maintain context and execute scheduled tasks.

**OpenClaw Security Crisis**: The flagship implementation faces severe security challenges with over 50,000 exposed instances vulnerable to remote code execution (RCE), up from 12,812 when initially reported. Critical vulnerabilities include CVE-2026-25253 (CVSS 8.8) enabling one-click RCE, supply chain poisoning in the skills marketplace, and systemic architectural weaknesses.

**Alternative Implementations Emerging**: The security concerns have sparked development of lighter alternatives:
- **NanoClaw**: ~4,000 lines of code (99% smaller than OpenClaw's 430K+ lines), runs in containers by default, uses Anthropic's Agents SDK
- **ZeroClaw**: Rust-based implementation optimizing for speed and clean architecture  
- **IronClaw**: Security-focused implementation with NEAR AI integration
- **PicoClaw**: Optimized for low-resource hardware deployments

## Technical Details

**Core Architecture**: Claws systems typically consist of:
- Local orchestration layer running on personal hardware
- Messaging protocol adapters (WhatsApp, Telegram, Slack, Discord)
- LLM provider integrations (Claude, GPT, Gemini, local models via Ollama)
- Task scheduling and persistence capabilities
- Container isolation for security (in newer implementations)

**Security Model Differences**: 
- OpenClaw: Application-level security, 52+ modules, 45+ dependencies, ~430K lines
- NanoClaw: OS-level container isolation, single Node.js process, minimal dependencies
- The security model represents a fundamental architectural choice between feature completeness and attack surface reduction

**Messaging Integration**: All implementations focus on integrating AI capabilities into existing messaging workflows rather than requiring new interfaces. This "ambient computing" approach aligns with Karpathy's vision of Claws as infrastructure rather than applications.

**Hardware Requirements**: Most Claws run effectively on consumer hardware including Raspberry Pi 5, with the actual LLM inference typically handled by cloud APIs rather than local compute.

## Industry Context

The rapid proliferation of "*claw" implementations (OpenClaw, NanoClaw, ZeroClaw, IronClaw, PicoClaw, etc.) suggests this architectural pattern addresses a genuine market need for persistent, locally-controlled AI agents. However, the security crisis around OpenClaw demonstrates the risks of rushing complex agent systems to market without adequate security review.

Karpathy's terminology appears to be sticking—"Claw" is becoming the accepted term for this category, complete with established emoji (🦞) and a growing ecosystem of implementations optimizing for different constraints (security, resource usage, hardware compatibility).

The trend aligns with broader industry movement toward local AI deployment and personal data sovereignty, but the security challenges highlight the tension between capability and safety in autonomous agent systems.

## Sources

---

## Sources Consulted

- https://simonwillison.net/2026/Feb/21/claws/
- https://www.infosecurity-magazine.com/news/researchers-40000-exposed-openclaw/
- https://conscia.com/blog/the-openclaw-security-crisis/
- https://www.theregister.com/2026/02/09/openclaw_instances_exposed_vibe_code/
- https://github.com/qwibitai/nanoclaw
- https://nanoclaw.dev
- https://dev.to/setas/what-are-claws-and-why-you-shouldnt-run-them-on-your-mac-mini-4o1b
- https://evoailabs.medium.com/openclaw-nanobot-picoclaw-ironclaw-and-zeroclaw-this-claw-craziness-is-continuing-87c72456e6dc
- https://sonusahani.com/blogs/openclaw-vs-picoclaw-vs-nullclaw-vs-zeroclaw-vs-nanobot-tinyclaw
