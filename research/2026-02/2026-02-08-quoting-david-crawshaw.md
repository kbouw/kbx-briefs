# David Crawshaw on AI Coding Agents: From Joy to Transformation

## Executive Summary

David Crawshaw, co-founder and former CTO of Tailscale, reports a fundamental shift in programming experience with AI coding agents—describing it as "having more fun programming than I ever have" because previously time-constrained projects now become achievable. His latest blog post "Eight more months of agents" (February 2026) details dramatic improvements in AI coding capability, with models now writing "nine tenths" of his code compared to "a quarter" just one year ago.

> **Confidence: High** ✅ — Multiple direct quotes from Crawshaw's own technical blog posts spanning 14 months, with consistent technical detail and measurable claims

## Key Findings

### Dramatic Model Capability Jump
Crawshaw reports that frontier AI models experienced a qualitative leap in coding ability between February 2025 and February 2026:
- **February 2025**: Claude Code could write "a quarter" of his code
- **February 2026**: Latest Opus model writes "nine tenths" of his code
- This improvement occurred without obvious architectural breakthroughs—instead through incremental but substantial improvements in coding model effectiveness

### Workflow Transformation
His programming workflow has fundamentally shifted:
- **Previously at big company**: 80% reading code, 20% writing code  
- **Previously at startup**: 50% reading, 50% writing
- **Current with agents**: 95% reading, 5% writing
- He's abandoned IDEs entirely, returning to vim with only go-to-definition functionality
- Fresh VMs are essential—built-in agent sandboxes create friction with constant permission requests

### Economic and Philosophical Implications
Crawshaw advocates for expensive frontier models despite costs, arguing that using cheaper alternatives "do worse than waste your time, you learn the wrong lessons." His philosophy has evolved to: "the best software for an agent is whatever is best for a programmer"—since every customer will eventually have an agent writing code against products.

### Technical Architecture Insights
From his detailed technical examples:
- **Agents defined simply**: "9 lines of code" - essentially a for loop containing LLM calls with tool access
- **Essential agent tools**: bash, patch, todo, web navigation, keyword search, code review
- **Critical limitation**: Agents excel at "gluing well-known APIs together" but still require careful human oversight for security and performance issues
- **Sandbox recommendation**: Use fresh VMs rather than built-in sandboxes for unrestricted agent operation

## Technical Details

### Evolution of Perspective (2025-2026)
Crawshaw's blog series shows a progression:

**January 2025 - "How I program with LLMs"**: Focused on autocomplete and web search replacement
**June 2025 - "How I program with Agents"**: Introduced feedback-driven programming with tool access  
**February 2026 - "Eight more months of agents"**: Reports dramatic capability improvements and workflow transformation

### Real-World Implementation Examples
His GitHub App authentication implementation demonstrates both agent capabilities and limitations:
- **Success**: Agent implemented complete OAuth flow with minimal human input
- **Critical flaw**: Created security vulnerability allowing unauthorized repository access
- **Resolution**: Single sentence correction prompt fixed the authorization logic
- **Performance issue**: Naive implementation required O(users × repositories) API calls
- **Architectural fix**: Agent successfully redesigned to use per-user tokens when requirements changed

### Current Technical Stack
- **Primary model recommendation**: Frontier models only (Opus, GPT-7.9-xhigh-with-cheese)
- **Development environment**: Fresh VMs with unrestricted agent access
- **Editor**: Returned to vim after abandoning IDEs entirely
- **Cost example**: $1.15 for a "significant agent-driven commit"

### Building exe.dev
Crawshaw is developing exe.dev as a cloud platform optimized for agent workflows, recognizing that existing cloud products are "the worst product I had to use every day in this new world." The platform philosophy: build what programmers love, and agent-enabled customers will follow.

## Sources

---

## Sources Consulted

- https://simonwillison.net/2026/Feb/7/david-crawshaw/#atom-everything
- https://crawshaw.io/blog/eight-more-months-of-agents
- https://crawshaw.io/blog/programming-with-agents
