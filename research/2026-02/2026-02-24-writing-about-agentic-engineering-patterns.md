# Agentic Engineering Patterns: A New Professional Framework for AI-Assisted Development

## Executive Summary

Simon Willison has launched a structured documentation project called "Agentic Engineering Patterns"—a collection of professional practices for working with coding agents like Claude Code and OpenAI Codex. The project distinguishes between "vibe coding" (unstructured AI prompting) and "agentic engineering" (professional software development using autonomous coding agents with human oversight), providing practical patterns like treating code as cheap-to-generate and leveraging TDD workflows.

> **Confidence: High** ✅ — Primary source documentation from the creator, corroborated by multiple technical sources and recent industry adoption patterns

## Key Findings

### Defining Agentic Engineering
Willison defines "agentic engineering" as professional software development using coding agents that can both generate and execute code independently, testing and iterating without turn-by-turn human guidance. This contrasts with "vibe coding"—the reckless approach of accepting all AI output without review—which Willison considers appropriate only for prototypes and personal scripts.

### First Documented Patterns

**"Writing Code is Cheap Now"** - The foundational challenge of agentic engineering is adapting to the reality that generating initial working code costs almost nothing. This disrupts traditional engineering intuitions about trade-offs, planning, and what features are "worth building." However, producing *good code*—working, tested, documented, maintainable code—still requires substantial human oversight.

**"Red/Green TDD"** - Using test-driven development as a prompt instruction ("red/green TDD") significantly improves agent results by forcing them to write failing tests first, then implement code to pass them. Both Claude and ChatGPT understand this shorthand and can execute the full test-first workflow autonomously.

**"First Run the Tests"** - Starting AI coding sessions with "First run the tests" forces agents to discover and understand existing test suites, making them significantly more likely to write and run tests for future code changes.

### Technical Implementation Details

The patterns are being published using a new "guide" format—collections of continuously updated chapters rather than static blog posts. Willison notes that nearly all the implementation code for this system was written by Claude Opus 4.6 running in Claude Code, demonstrating the meta-application of these patterns.

### Industry Context and Adoption

Multiple industry sources confirm the growing distinction between casual AI prompting and professional agentic workflows. Addy Osmani's analysis reinforces that "agentic engineering" is becoming the preferred term for disciplined, agent-assisted development with human oversight, while "vibe coding" remains useful for prototyping but inadequate for production systems.

Current coding agents mentioned include:
- Claude Code (Anthropic) - emphasizes reasoning and iteration
- OpenAI Codex - focuses on core edit/execute loops  
- Various GitHub integrations through Agent HQ platform
- Apple's integration into Xcode 26.3

## Technical Details

### Workflow Characteristics
Agentic engineering requires:
1. **Planning before prompting** - Writing specs and breaking work into well-defined tasks
2. **Code review discipline** - Reviewing agent output with the same rigor as human PRs
3. **Comprehensive testing** - Using test suites to enable agent iteration loops
4. **Human oversight of architecture** - AI handles implementation, humans own design decisions

### Failure Modes and Limitations
- Agents excel at assembling known techniques but struggle with open-ended generalization
- Context loss during processing can override safety constraints
- Junior developers risk skill atrophy by relying on agents before building fundamentals
- Cache hit rates are critical for agent viability due to cost and rate limit constraints

### Economic Impact
The cost shift from writing code to reviewing code fundamentally changes development economics. Features previously dismissed as "not worth the time" become viable for asynchronous agent exploration, potentially expanding the scope of what teams choose to build.

## Sources

- https://simonwillison.net/2026/Feb/23/agentic-engineering-patterns/
- https://simonwillison.net/guides/agentic-engineering-patterns/code-is-cheap/
- https://addyosmani.com/blog/agentic-engineering/
- https://simonwillison.net/guides/agentic-engineering-patterns/first-run-the-tests/#atom-everything
- https://simonwillison.net/guides/agentic-engineering-patterns/red-green-tdd/#atom-everything

---

## Sources Consulted

- https://simonwillison.net/2026/Feb/23/agentic-engineering-patterns/
- https://simonwillison.net/guides/agentic-engineering-patterns/code-is-cheap/
- https://addyosmani.com/blog/agentic-engineering/
- https://simonwillison.net/guides/agentic-engineering-patterns/first-run-the-tests/#atom-everything
- https://simonwillison.net/guides/agentic-engineering-patterns/red-green-tdd/#atom-everything
