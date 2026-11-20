# Proposed Technology Stack

| Layer | Proposed technology | Purpose |
|---|---|---|
| Frontend | React.js | Owner dashboard and review screens |
| Backend | Python + FastAPI | API and workflow services |
| Database | SQLite initially; PostgreSQL later | RFQs, suppliers, inventory and cost history |
| Agent orchestration | LangGraph or equivalent | Stateful multi-step workflow |
| LLM | Selected model with tool calling | Extraction support, reasoning and explanations |
| Document processing | PDF text extraction; OCR when needed | Supplier quotes and RFQs |
| Voice (later scope) | Speech-to-text and text-to-speech | Tamil and English interaction |
| Calculations | Python functions | Auditable cost, landed-cost and margin calculations |

## Implementation principle

Use AI for interpreting unstructured information and coordinating steps. Use deterministic code for all financial calculations. Every recommendation should show its inputs and assumptions.

Technology choices are proposed and may change during prototype development based on availability, cost and evaluation.
