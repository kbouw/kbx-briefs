# AI is Destroying Open Source: Sustainability Under Assault

## Executive Summary

Jeff Geerling's analysis reveals a critical tension: AI development is undermining the open source ecosystem it depends on by flooding maintainers with low-quality submissions, creating unsustainable workloads, and devaluing human contributions. Empirical evidence from the curl project and controlled studies demonstrates that AI tools are not only failing to improve developer productivity but actively making open source maintenance harder.

> **Confidence: High** ✅ — Multiple independent sources confirm the trend, with concrete data from major projects like curl, peer-reviewed research from METR, and widespread GitHub policy changes in response.

## Key Findings

### AI Tools Slow Experienced Developers Down
A rigorous randomized controlled trial by METR involving 16 experienced open source developers working on 246 real issues found that **AI tools made developers 19% slower**, contradicting both developer expectations (24% speedup predicted) and post-task perceptions (20% speedup reported). This gap between perception and reality is particularly concerning for decision-making around AI adoption.

### Bug Bounty Programs Collapse Under AI Slop
The curl project, maintained by Daniel Stenberg, shut down its bug bounty program in January 2026 after AI-generated reports caused the rate of legitimate vulnerability reports to plummet from 15% to below 5%. The program had successfully identified 87 confirmed vulnerabilities over five years, but became unsustainable when maintainers were spending more time debunking AI-generated false positives than fixing real issues.

### GitHub Considers Drastic Measures
GitHub is exploring a "kill switch" for pull requests—the core collaboration feature that made the platform popular—because maintainers report being overwhelmed by AI-generated contributions. This represents a fundamental threat to open source development workflows, with some projects like Godot reporting "demoralizing" impacts on maintainer morale.

### Automated Harassment at Scale
Jeff Geerling describes "agentic AI" instances automatically filing bug reports and pull requests without human oversight, creating a new form of automated harassment for maintainers. The creator of OpenClaw, an agent framework enabling this behavior, was subsequently hired by OpenAI to "bring agents to everyone."

## Technical Details

### The Economics of Unsustainability
- **60% of open source maintainers work unpaid** according to 2024 Tidelift data
- **44% report burnout** as a major issue
- Critical infrastructure projects depend on volunteer maintainers who lack infinite resources to review AI-generated submissions

### Quality vs. Quantity Problem
The curl project data shows a stark pattern:
- **2019-2024**: ~15% of security reports were legitimate vulnerabilities
- **2025**: Rate dropped to 5% as AI submissions increased
- **Volume increase**: curl received significantly more reports than peer projects (Ruby, Node.js, Rails) which remained flat

### Detection and Response Challenges
Current mitigation efforts include:
- Anti-slop GitHub Actions (claiming 98% effectiveness on one project)
- Restricting contributions to collaborators only
- Manual review burden that scales poorly
- Repository owners considering closing external contributions entirely

### The Plateau Problem
Jeff Geerling notes that while AI slop generation is getting easier, "it's not getting smarter." Code generation quality has plateaued while the volume of submissions continues growing, creating an increasingly unfavorable signal-to-noise ratio for maintainers.

## Broader Implications

### Infrastructure Risk
Open source software forms critical digital infrastructure, with the failure of key projects potentially causing "catastrophic, cascading effects across the entire digital economy." The concentration of dependencies means a small number of maintainer departures could have outsized impact.

### The Training Data Paradox
AI systems depend on open source code for training data, yet their deployment is making open source maintenance unsustainable. This creates a self-defeating cycle where AI could ultimately destroy the very foundation it relies on for continued improvement.

### Ecosystem Fragmentation
Projects are beginning to close off the open collaboration that defines open source:
- Disabling pull requests entirely
- Restricting contributions to known collaborators
- Abandoning bug bounty programs
- Moving to private vulnerability reporting

This represents a fundamental shift away from the open development model that enabled the software ecosystem's growth.

## Unanswered Questions

1. **Scale of Impact**: While curl and other high-profile projects report significant AI slop problems, the full extent across the open source ecosystem remains unmeasured.

2. **Effectiveness of Countermeasures**: It's unclear whether automated detection tools can keep pace with improving AI generation capabilities.

3. **Economic Solutions**: Whether sustainable funding models can emerge fast enough to support the increased maintenance burden.

4. **Long-term Trajectory**: If the AI "bubble" deflates as Geerling suggests, will the damage to open source collaboration norms be reversible?

The evidence suggests we're witnessing a critical juncture where the success of AI development may be undermining the collaborative foundations that made it possible.

---

## Sources Consulted

- https://www.jeffgeerling.com/blog/2026/ai-is-destroying-open-source/
- https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/
- https://daniel.haxx.se/blog/2026/01/26/the-end-of-the-curl-bug-bounty/
- https://www.theregister.com/2026/02/03/github_kill_switch_pull_requests_ai
- https://opensourcepledge.com/blog/the-open-source-sustainability-crisis/
- https://byteiota.com/open-source-maintainer-crisis-60-unpaid-burnout-hits-44/
