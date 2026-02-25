# Writing Code is Cheap Now: Research Report

## Executive Summary

AI coding agents have dramatically reduced the raw cost of generating code, but a significant gap remains between "code generation" and "production-ready software." While top agents like Cursor and Claude Code achieve 75%+ success rates on standardized benchmarks, real-world productivity gains are proving more elusive—a rigorous METR study found experienced developers actually took 19% longer when using AI tools, contradicting both their expectations and subjective experience.

> **Confidence: High** ✅ — Multiple independent sources including peer-reviewed research, benchmark data, and extensive hands-on analysis from credible technical sources converge on this assessment.

## Key Findings

### 1. Benchmark Performance Shows Impressive Technical Capabilities

Current top-tier coding agents demonstrate remarkable performance on standardized tasks:
- **Verdent**: 76.1% success rate on SWE-bench Verified (pass@1), 81.2% within 3 attempts
- **Cursor**: 70-80% success rates with fast response times (320ms vs GitHub Copilot's 890ms)
- **Aider**: 85-90% success rates on coding benchmarks
- **Performance trajectory**: From ~2% success in early 2024 to 75%+ by 2025 on verified benchmarks

These agents excel at understanding complex, multi-file codebases and implementing sophisticated changes that would challenge many human developers.

### 2. Real-World Productivity Impact Remains Contested

The METR study provides the most rigorous real-world evidence to date:
- **Methodology**: 16 experienced open-source developers, 246 tasks (averaging 2 hours each), randomized controlled trial
- **Result**: 19% slower completion times when using AI tools (Cursor Pro with Claude 3.5/3.7 Sonnet)
- **Perception gap**: Developers expected 24% speedup, believed they achieved 20% speedup, but actually experienced 19% slowdown
- **Quality**: No significant difference in pull request quality between AI-assisted and manual work

### 3. The "Good Code" Gap

Simon Willison's analysis identifies why raw code generation doesn't translate to productivity:

**What's now cheap:**
- Writing syntactically correct code
- Basic functionality implementation
- Quick prototypes and throwaway scripts

**What remains expensive:**
- Comprehensive testing and edge case handling
- Documentation that stays current
- Code that integrates well with existing systems
- Meeting non-functional requirements (security, scalability, maintainability)
- Human review and quality assurance

### 4. Emerging Engineering Patterns

New practices are developing around AI-assisted development:
- **"Red/green TDD"**: Using test-first prompts to improve agent reliability
- **Asynchronous experimentation**: Running agents on previously dismissed ideas
- **Multi-model workflows**: Switching between models for different phases (planning vs. implementation vs. review)
- **Explicit verification loops**: Building testing and review into agent workflows

## Technical Details

### Agent Architecture Evolution

Current leading systems employ sophisticated scaffolding:
- **Multi-agent coordination**: Separate agents for planning, implementation, and review
- **Context management**: Maintaining todo lists and progress tracking to prevent "model drift"
- **Tool integration**: Access to bash, git, file editors, and testing frameworks
- **Model switching**: Seamless transitions between specialized models (GPT-5 for planning, Claude for implementation)

### Benchmark vs. Reality Discrepancies

Three key factors explain the gap between benchmark success and real-world impact:

1. **Task scope**: Benchmarks use well-defined, self-contained problems vs. real-world ambiguity
2. **Quality standards**: Algorithmic scoring vs. human review with implicit requirements
3. **Context richness**: Clean test environments vs. complex, legacy codebases

### Factor Analysis from METR Study

Five confirmed factors contributing to productivity slowdown:
1. **Low AI reliability** requiring extensive validation
2. **Context switching** overhead between AI assistance and manual work
3. **Quality verification** time not captured in traditional metrics
4. **Learning curve** for effective AI tool usage
5. **Over-reliance** on AI for tasks better done manually

## Implications for Engineering Organizations

### Strategic Considerations

1. **Reframe value propositions**: Focus on AI for exploration and rapid prototyping rather than productivity acceleration
2. **Invest in verification infrastructure**: Enhanced testing, review processes, and quality gates
3. **Develop AI-native workflows**: New practices around asynchronous agent usage and multi-model coordination
4. **Recalibrate project planning**: Current productivity assumptions may be invalid

### Tactical Recommendations

1. **Start small**: Use AI for well-scoped, low-risk experiments
2. **Measure carefully**: Track actual completion times, not subjective satisfaction
3. **Build quality gates**: Automated testing and review processes become more critical
4. **Train developers**: Effective AI tool usage requires new skills and habits

## Open Questions and Gaps

1. **Learning effects**: Do productivity gains emerge after months of heavy AI tool usage?
2. **Domain specificity**: Do results vary significantly across different types of software development?
3. **Team dynamics**: How do AI tools affect collaboration and knowledge transfer?
4. **Quality evolution**: Will verification and testing tools advance to close the "good code" gap?

The fundamental insight remains valid: while the marginal cost of generating code has approached zero, the total cost of delivering reliable, maintainable software has not followed the same trajectory. Organizations adopting AI coding tools need to understand this distinction and plan accordingly.

---

## Sources Consulted

- https://simonwillison.net/guides/agentic-engineering-patterns/code-is-cheap/#atom-everything
- https://artificialanalysis.ai/insights/coding-agents-comparison
- https://www.verdent.ai/blog/swe-bench-verified-technical-report
- https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/
