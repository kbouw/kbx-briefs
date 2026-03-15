# Simon Willison's Agentic Engineering Patterns from Pragmatic Summit

## Executive Summary

Simon Willison shared practical agentic engineering patterns from his Pragmatic Summit fireside chat, demonstrating mature approaches to working with AI coding agents. Key insights include using "red-green TDD" as a 5-token prompt that dramatically improves code quality, treating AI agents like trusted external teams rather than scrutinizing every line, and employing "conformance-driven development" to reverse-engineer standards from multiple implementations.

> **Confidence: High** ✅ — Based on direct source content from Willison's blog post and supporting documentation of his tools and methodologies.

## Key Findings

### Practical Prompting Patterns
- **"Use red-green TDD"** - A 5-token prompt that significantly improves agent success rates by forcing test-first development
- Willison starts every coding session by specifying the test framework (`uv run pytest`) and instructing agents to use red-green TDD
- Despite personally disliking TDD throughout his career, he finds it extremely effective for agents since "tests are effectively free now"

### Trust Models for AI Output
Willison advocates treating AI agents like external teams rather than code reviewers:
- Similar to trusting professional teams' services without examining their code
- Claude Opus 4.5 was the first model to earn his trust for routine tasks like JSON APIs with database pagination
- Trust is task-specific: "for classes of problems that I've seen it tackle before, it's not going to do anything stupid"

### Conformance-Driven Development
A novel pattern for implementing standards:
1. Instruct the agent to build test suites that pass across multiple existing implementations (Go, Node.js, Django, Starlette)
2. Use those tests as the specification for implementing the feature in your own framework
3. "Reverse engineer six implementations of a standard to get a new standard"
- Willison successfully used this to add multipart file uploads to Datasette

### Testing and Validation Tools
Willison developed two complementary tools for agent workflow validation:

**Showboat**: Creates executable Markdown documents demonstrating agent work
- CLI tool (172 lines of Go) that builds demo documents with embedded command outputs
- Commands: `init`, `note`, `exec`, `image` for structured documentation
- Prevents agent "cheating" by capturing actual command outputs rather than fabricated results

**Rodney**: CLI browser automation designed to work with Showboat
- Built on Go's Rod library for Chrome DevTools protocol
- Enables agents to capture screenshots and demonstrate web interfaces
- Session example: `start`, `open`, `js`, `click`, `screenshot`, `stop`

## Technical Architecture Insights

### Code Quality Philosophy
- Quality requirements are "completely context dependent"
- For disposable tools: "800 lines of complete spaghetti" is acceptable if it works
- For maintained codebases: "Having poor quality code from an agent is a choice that you make"
- Agents excel at refactoring tasks that humans avoid due to time constraints

### Security Framework: The Lethal Trifecta
Willison identified three combined capabilities that create severe security vulnerabilities:
1. **Access to private data** (API keys, emails, environment variables)
2. **Exposure to untrusted content** (web pages, user inputs, documents)
3. **Exfiltration vectors** (external communication capabilities)

When combined, these enable prompt injection attacks where malicious instructions in untrusted content can steal private data. The attack vector is structural—LLMs cannot reliably distinguish instruction source, making everything "glued together into a sequence of tokens."

### Development Workflow Evolution
Willison's current approach represents a significant productivity shift:
- Most code now ships to GitHub written by agents driven via iPhone Claude app
- Agents can handle complex multi-language projects (he released 3 Go projects in 2 weeks despite not being fluent in Go)
- Mental exhaustion limits sessions to 2-3 hours managing multiple concurrent agent projects

## Industry Implications

### Paradigm Shift in Engineering Careers
- Engineers should "be so much more ambitious" due to agent capabilities
- Language barriers dissolving: "don't learn it, just start writing code in it"
- Pattern consistency means agents follow existing codebase conventions "almost to a tee"

### Reliability Threshold Reached
- "November 2025 inflection point" marked when agents became reliably predictable
- Current state: "oneshotting basically everything" with 2-sentence prompts
- Key insight: "we can predict what they're going to do" enables trust-building

### Model Capability Exploration
Willison emphasizes that exploration of current model boundaries is more important than waiting for future models: "The most interesting question is what can the models we have do right now."

## Sources

---

## Sources Consulted

- https://simonwillison.net/2026/Mar/14/pragmatic-summit/
- https://simonwillison.net/2026/Feb/10/showboat-and-rodney/
- https://simonw.substack.com/p/the-lethal-trifecta-for-ai-agents
