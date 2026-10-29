# Related work — complementary boundaries

| Area | Public upstream examples | CQF's scope |
| --- | --- | --- |
| Agent coordination | [LangGraph](https://github.com/langchain-ai/langgraph), [CrewAI](https://github.com/crewAIInc/crewAI) | Contract for evaluated outputs, not agent execution |
| Durable workflows | [Temporal](https://github.com/temporalio/temporal), [n8n](https://github.com/n8n-io/n8n) | Gate obligations, not scheduling or retries |
| LLM evaluation | [Promptfoo](https://github.com/promptfoo/promptfoo), [DeepEval](https://github.com/confident-ai/deepeval) | Guard evolution, scope, policy enforcement, provenance |
| Evaluation platforms | [Opik](https://github.com/comet-ml/opik), [Phoenix](https://github.com/Arize-ai/phoenix) | Portable policy semantics rather than observability storage |
| Interoperability | [A2A](https://github.com/a2aproject/A2A), [MCP](https://github.com/modelcontextprotocol) | Acceptance evidence rather than transport protocol |

CQF is deliberately narrow: a domain-neutral quality contract linking defect reports, verified guards and release gates. Other tools may already support overlapping features; this document is a statement of intended boundaries, not a feature-by-feature superiority claim.
