# Research Report: Use Protocols, Not Services

## Executive Summary

The "use protocols, not services" principle advocates for decentralized communication protocols (like ActivityPub, Nostr, Matrix, XMPP) over centralized platforms (Discord, Twitter, Facebook) to resist censorship and government control. This shift has gained urgency as age verification laws under the UK's Online Safety Act and similar legislation worldwide are forcing platforms to implement invasive identity verification measures, triggering user migration to protocol-based alternatives.

> **Confidence: High** ✅ — Multiple primary sources confirm the regulatory pressures and technical distinctions between protocols and services, with concrete evidence from Discord's implementation and Matrix.org's response.

## Key Findings

### Regulatory Catalyst
- **Discord's Age Verification**: As of July 2025, UK Discord users must complete face scans or government ID verification to access age-restricted content, with expansion planned for March 2026
- **Legal Framework**: UK's Online Safety Act (OSA), along with similar laws in Australia, New Zealand, and the EU, requires platforms to verify user ages
- **Enforcement Reality**: Matrix.org confirmed that even decentralized server operators in affected jurisdictions must comply with age verification laws

### Technical Architecture Differences

**Centralized Services (Discord, Twitter):**
- Single point of failure and control
- Account deletion = permanent loss of access and data
- One government request can affect millions of users
- Cannot migrate accounts or data between providers

**Decentralized Protocols:**
- **ActivityPub (Fediverse)**: Server-based federation where users can migrate between instances, though account portability remains limited
- **Nostr**: Cryptographic key-based identity completely independent of any server; relay-based architecture where users can simply switch relays if banned
- **Matrix**: Federation with end-to-end encryption; working on account portability features
- **XMPP**: Established federated messaging protocol with mature implementations

### Current Migration Patterns
- Matrix.org reported "huge spike of signups" following Discord's age verification announcement
- Users seeking alternatives face feature gaps: Matrix lacks Discord's voice channels, game streaming, custom emoji, and community-oriented features
- Protocol bridges (like Mostr) enable cross-protocol communication between Nostr, ActivityPub, and other networks

## Technical Details

### Censorship Resistance Comparison
1. **Nostr**: Highest resistance - cryptographic identity means no central authority can ban accounts; users simply switch relays
2. **ActivityPub**: Moderate resistance - users lose accounts if banned from their instance but can create new accounts on other instances
3. **Matrix**: Similar to ActivityPub but working on account portability to improve user sovereignty
4. **Centralized Services**: No resistance - single point of control

### Implementation Challenges
- **User Experience Gap**: Protocol-based clients generally lack feature parity with mature centralized platforms
- **Network Effects**: Most users remain on centralized platforms due to existing social connections
- **Technical Literacy**: Self-hosting and managing cryptographic keys requires more technical knowledge
- **Cost Structure**: Free centralized services are subsidized by data collection; protocol implementation often requires users to pay for hosting or premium features

### Practical Migration Strategies
- **Email Analogy**: SMTP demonstrates protocol resilience - even if Gmail bans you, you can still reach Gmail users from other providers
- **Server Selection**: Users can choose instances based on jurisdiction, moderation policies, and feature sets
- **Bridge Technologies**: Cross-protocol bridges maintain connections during migration periods
- **Progressive Adoption**: Users can maintain presence on multiple protocols during transition

## Future Implications

### Regulatory Pressure Spreading
Age verification laws are expanding globally, with movement in the US and Canada following UK/EU implementation. This creates sustained pressure for protocol adoption rather than service migration.

### Technical Development Priorities
- Account portability initiatives in Matrix could set precedent for other protocols
- Bridge development enabling seamless cross-protocol communication
- User experience improvements needed to achieve feature parity with centralized alternatives

### Network Effect Challenges
The core tension remains between protocol benefits (censorship resistance, user sovereignty) and service advantages (ease of use, network effects, zero-cost operation). Success requires either achieving feature parity or providing compelling enough benefits to overcome user friction.

## Sources

---

## Sources Consulted

- https://notnotp.com/notes/use-protocols-not-services/
- https://soapbox.pub/blog/comparing-protocols/
- https://matrix.org/blog/2026/02/welcome-discord/
- https://joinmatrix.org/guide/matrix-vs-discord/
- https://support.discord.com/hc/en-us/articles/33362401287959-What-s-Changing-for-UK-and-Australian-Users
- https://discord.com/safety/adapting-discord-for-the-uk-online-safety-act
- https://arxiv.org/html/2505.22962v1
- https://www.sciencedirect.com/science/article/pii/S2405896325031489
