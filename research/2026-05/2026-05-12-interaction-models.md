# AI Interaction Models: Evolution Toward Real-Time Collaborative Systems

## Executive Summary

The field of AI interaction models is experiencing a fundamental shift from turn-based, prompt-response patterns to real-time, multimodal collaboration systems. Thinking Machines has introduced the first production-scale "interaction model" that handles voice, video, and text simultaneously with 200ms response times, while recent research reveals growing sophistication in agentic workflows that help users navigate the inherent ambiguity in conversational AI interfaces.

> **Confidence: High** ✅ — Multiple independent technical sources, including published research papers and official model releases from established AI labs, with concrete technical specifications and benchmarking data.

## Key Findings

### 1. Real-Time Multimodal Interaction Models Are Production-Ready

Thinking Machines has launched the first large-scale "interaction model" that processes audio, video, and text in continuous 200ms micro-turns rather than traditional turn-based exchanges. Their system uses a dual-architecture approach:
- **Interaction model**: Maintains real-time presence and handles immediate responses
- **Background model**: Performs complex reasoning, tool use, and longer-horizon tasks asynchronously

The technical breakthrough is scaling this architecture to DeepSeek V4-Flash size (40x larger than previous fully-duplex models like Moshi), enabling sophisticated reasoning while maintaining conversational fluency.

### 2. OpenAI's GPT-Realtime-2 Advances Voice Interaction Patterns

OpenAI has identified three core voice interaction patterns and released GPT-Realtime-2 to support them:
- **Voice-to-action**: Users speak requests, systems complete tasks
- **Systems-to-voice**: Software provides spoken guidance based on context
- **Voice-to-voice**: AI maintains natural conversation flow while reasoning

The new model introduces "stay quiet" behavior where it can listen silently during side conversations and re-engage on command—a genuinely novel interaction pattern that moves beyond simple turn-taking.

### 3. Agentic Workflows Address Conversational AI's Core Problems

Recent research from universities has identified two fundamental challenges in conversational human-AI interaction (CHAI):
- **Ambiguity**: Users often have unclear goals and don't understand AI capabilities
- **Transience**: Interactions are brief and rarely revisited, limiting design opportunities

Proposed solutions include structured agentic workflows with three stages:
1. **Contextualization**: Automated data gathering with minimal user effort
2. **Goal formulation**: AI-generated personalized recommendations based on user persona
3. **Prompt articulation**: AI assistance in crafting effective prompts

### 4. The Four-Model Framework Remains Relevant But Evolving

The original Thinking Machines framework of four interaction models (command-based, conversational, assistant-based, collaborative) continues to provide useful categorization, but the boundaries are blurring:
- **Command-based** systems are incorporating more natural language understanding
- **Conversational** interfaces are becoming more proactive and context-aware  
- **Assistant-based** models are developing genuine collaborative capabilities
- **Collaborative** systems are emerging as the new frontier, with shared problem-solving in real-time

## Technical Implementation Details

### Architecture Innovations

**Time-aligned micro-turns**: Instead of waiting for complete user inputs, modern systems process 200ms chunks continuously, enabling:
- Natural interruptions and overlapping speech
- Simultaneous tool use while maintaining conversation
- Real-time visual cue recognition (e.g., detecting bugs in code as you type)

**Encoder-free early fusion**: Rather than using separate large encoders for different modalities, new systems use lightweight embedding layers:
- Audio processed as dMel spectrograms
- Video split into 40x40 patches with hMLP encoding  
- All modalities co-trained from scratch with the transformer

**Streaming sessions**: Custom inference optimizations for frequent small prefills, avoiding the overhead typical of LLM inference libraries designed for longer contexts.

### Safety and Control Mechanisms

Real-time interaction poses unique safety challenges requiring:
- **Modality-appropriate refusals**: Natural-sounding voice rejections rather than text-based responses
- **Long-horizon robustness**: Automated red-teaming for extended speech conversations
- **Context preservation**: Maintaining conversation state across interruptions and background task delegation

## Practical Implications

### For Developers
- Traditional voice interfaces using voice-activity-detection (VAD) will likely be outpaced by end-to-end trained models
- New architectures require inference optimization specifically for real-time constraints
- Safety considerations must account for spontaneous, multi-turn conversations across modalities

### For Product Teams
- User research methods need updating for real-time, multimodal interactions
- Design patterns from text-based chat may not transfer to voice/video systems
- Agentic workflows can help bridge the gap between user intent and AI capabilities

### For Enterprise Applications
- Collaborative interaction models show promise for complex workflows requiring sustained human-AI partnership
- Voice-first interfaces may become viable for professional use cases previously limited to text
- Integration challenges around real-time systems and existing enterprise infrastructure

## Open Questions and Limitations

1. **Scalability concerns**: Current real-time systems require significant computational resources—unclear how costs scale with simultaneous users
2. **Privacy implications**: Always-listening systems raise new questions about data handling and consent
3. **Cognitive load**: Whether users can effectively manage simultaneous communication across multiple modalities
4. **Enterprise readiness**: Most demonstrations focus on consumer use cases—enterprise deployment patterns remain unclear


---

## Sources Consulted

- https://thinkingmachines.ai/blog/interaction-models/
- https://arxiv.org/html/2501.18002v1
- https://openai.com/index/advancing-voice-intelligence-with-new-models-in-the-api/
- https://www.mindstudio.ai/blog/openai-3-new-realtime-voice-models-api-access
- https://developers.openai.com/api/docs/models/gpt-realtime-2
