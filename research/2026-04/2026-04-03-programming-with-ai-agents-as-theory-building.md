# Programming (with AI Agents) as Theory Building: Validating Naur's 1985 Framework

## Executive Summary

A developer's experience with AI coding agents validates Peter Naur's 1985 insight that programming's core output is the engineer's mental theory, not the code itself. The developer reports rejecting 90% of AI agent output based on their internal theory understanding, while agents can build working theories for normal codebases but must rebuild them from scratch each session—highlighting the persistent centrality of human mental models in software development.

> **Confidence: High** ✅ — Multiple corroborating sources from academic research, recent industry studies, and the original detailed developer report provide consistent evidence.

## Key Findings

### Core Theory Validation
- **AI-Human Theory Gap**: Despite advanced AI coding capabilities, developers still reject ~90% of agent-generated code based on their internal mental models of system architecture and requirements
- **Theory Persistence Problem**: AI agents must rebuild system theories from scratch each session, lacking the continuity that human developers maintain across projects
- **Quality Filter Role**: Strong mental models serve as essential quality filters—developers with deeper system understanding are more selective about AI output acceptance

### Modern Research Alignment
Recent 2024-2025 studies corroborate these findings:
- **Context Pain Increases with Experience**: Senior engineers (52%) report more context-related pain with AI tools than juniors (41%) because "senior engineers have deeper mental models of their codebase, and they expect AI to reflect that nuance"
- **Trust-Quality Correlation**: Only 3.8% of developers report both low AI hallucinations and high confidence in shipping AI code—the "sweet spot" where theory-building and AI assistance align effectively
- **Paradigm Shift Evidence**: New development approaches like "Chat-Oriented Programming" (CHOP) and "vibe coding" represent shifts from direct code writing to theory-guided AI orchestration

## Technical Details

### Naur's 1985 Framework
Peter Naur's "Programming as Theory Building" argued that:
1. **Primary Artifact**: The programmer's knowledge/theory is the main output, not the code
2. **Implicit Knowledge**: Mental models contain understanding that "cannot be written down"—including system context, design rationale, and modification strategies  
3. **Theory Transmission**: Requires mentorship and collaborative work, not just documentation

### AI Agent Theory-Building Capabilities
**What AI Agents Can Do**:
- Build functional theories for "normal-ish applications like CRUD servers, proxies" that are well-represented in training data
- Demonstrate explicit theory-building in logs through hypothesis formation and testing
- Successfully debug complex codebases (sometimes outpacing human developers)

**Critical Limitations**:
- **Session Amnesia**: Must reconstruct system theories from scratch each interaction
- **Context Boundaries**: Struggle with truly novel or unusual system architectures
- **Theory Persistence**: Cannot retain and refine mental models across development cycles

### Developer Workflow Impact
Modern AI-assisted development follows this pattern:
1. Developer spins multiple AI agents for parallel work
2. Continuous filtering based on internal mental model (~90% rejection rate)
3. Detailed review of remaining ~10% against system theory
4. Further refinement reducing viable code to ~5% final adoption

This validates that **mental model strength directly correlates with AI tool effectiveness**—the better the developer's theory, the more precisely they can guide and filter AI output.

## Implications

### For Development Practice
- **Mental Model Investment**: Strong system understanding remains the bottleneck for effective AI-assisted development
- **Theory-First Approach**: Developers should focus on building comprehensive mental models before delegating implementation to AI
- **Quality Assurance**: Mental models serve as the primary quality gate for AI-generated code

### For AI Tool Design
- **Context Persistence**: Major opportunity for tools that can retain and refine codebase theories across sessions
- **Theory Visualization**: Tools that help externalize and share mental models could bridge the human-AI theory gap
- **Incremental Learning**: Systems that learn from developer corrections to build better theories over time

### For Software Engineering Education
Reinforces the importance of teaching theory-building skills alongside coding—developers need strong mental modeling capabilities to effectively leverage AI tools rather than being replaced by them.

## Sources

---

## Sources Consulted

- https://seangoedecke.com/programming-with-ai-agents-as-theory-building/
- https://emptysqua.re/blog/programming-as-theory-building/
- https://arxiv.org/html/2510.10819v1
- https://www.qodo.ai/reports/state-of-ai-code-quality/
