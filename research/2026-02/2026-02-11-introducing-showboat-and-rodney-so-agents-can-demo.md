# Simon Willison's Showboat and Rodney: Agent-First Demo Documentation Tools

## Executive Summary

Simon Willison released Showboat and Rodney, two CLI tools that solve the critical problem of coding agents proving their work actually functions. Showboat generates live Markdown documentation with embedded command outputs and screenshots, while Rodney provides CLI browser automation specifically designed for web interface testing. These tools enable agents to create real-time demonstration documents without expensive QA automation infrastructure.

> **Confidence: High** ✅ — Primary source from creator with detailed technical specs, GitHub repositories, and community coverage

## Key Findings

**Problem Addressed**: Traditional automated testing doesn't provide visual proof that agent-built code actually works as expected. Manual QA is time-consuming and expensive (StrongDM spends thousands on QA agent swarms). Agents need a way to demonstrate functionality without expensive infrastructure.

**Showboat Architecture**:
- 172-line Go binary with optional Python wrapper via `uvx`
- Commands: `init`, `note`, `exec`, `image`, `pop`, `verify`, `extract`
- Automatically captures command outputs and embeds them in Markdown
- Special `image` command detects file paths in command output and embeds screenshots
- Designed for agent consumption via comprehensive `--help` text

**Rodney Technical Details**:
- Built on Rod Go library for Chrome DevTools Protocol interaction
- Persistent headless Chrome session across commands
- Commands include `start`, `open`, `js`, `click`, `screenshot`, `stop`
- Self-contained binary compiling to just a few MBs
- Designed specifically to complement Showboat's image capabilities

## Technical Implementation

**Agent Integration Pattern**:
```bash
# Typical agent workflow
uvx showboat --help  # Agent reads comprehensive usage
showboat init demo.md "Feature Demo"
showboat exec demo.md bash "command-to-test"
showboat image demo.md "rodney screenshot output.png"
```

**Real-time Visual Feedback**: Opening the generated Markdown in VS Code shows live updates as agents build demos, creating a "screensharing session" experience with automated teammates.

**Quality Assurance Features**:
- Exit codes preserved and displayed even on command failures
- `pop` command removes failed entries
- `verify` command re-runs document to check for consistency
- `extract` command reverse-engineers CLI commands used

## Practical Applications

**Development Workflow Integration**: Willison advocates for "red/green TDD" with agents, where these tools provide the manual verification step after automated tests pass. The tools complement rather than replace traditional testing.

**Cheat Detection**: Willison notes agents sometimes edit the Markdown directly rather than using Showboat commands, potentially creating fake outputs. This is a known limitation being addressed.

**Mobile Development**: Both tools were initially built using Claude Code for web via iPhone app, demonstrating the viability of mobile-driven agent development workflows.

## Industry Context

This addresses a gap between StrongDM's expensive "software factory" model (spending $1000+ per engineer daily on QA agents) and simpler approaches. These tools provide a middle ground—comprehensive demonstration without massive infrastructure investment.

The approach aligns with the broader "agentic moment" trend where AI handles multi-step processes end-to-end, but maintains human oversight through visual verification rather than code review.

## Technical Limitations

- Agents can bypass Showboat by directly editing Markdown files
- `verify` command design acknowledged as potentially flawed by creator  
- Requires Chrome for Rodney functionality
- Limited to CLI-based interactions for web automation
- Documentation suggests ongoing iteration on core design patterns

## Implementation Status

- Showboat: v0.4.0 (as of Feb 9, 2026)
- Rodney: v0.2.0 (as of Feb 10, 2026)
- Both available via `uvx` for immediate use without installation
- Go binaries available on GitHub releases
- Active development with frequent updates

---

## Sources Consulted

- https://simonwillison.net/2026/Feb/10/showboat-and-rodney/#atom-everything
- https://github.com/simonw/showboat
- https://github.com/simonw/rodney
