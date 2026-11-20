# System Architecture (Proposed)

## High-level components

```text
User
 |-- Web dashboard / text input
 |-- RFQ PDF or image upload
 |-- Future: Tamil / English voice and messaging adapters
 |
 v
API layer (FastAPI)
 |
 v
Workflow Orchestrator
 |-- RFQ & Manufacturing Intelligence Agent
 |-- Smart Procurement & Inventory Agent
 |-- Manufacturing Cost Intelligence Agent
 |-- ProfitGuard Agent
 |-- Negotiation & Business Action Agent
 |
 +--> Deterministic tools
 |     |-- RFQ field validator
 |     |-- Supplier quote normalizer
 |     |-- Landed-cost calculator
 |     |-- Inventory requirement calculator
 |     |-- Manufacturing cost calculator
 |     |-- Margin and quotation calculator
 |
 +--> Data layer
       |-- RFQs and order cases
       |-- Supplier and quotation records
       |-- Inventory records
       |-- Machine / labour cost assumptions
       |-- Estimated and actual job costs
 |
 v
Owner review and approval
 |
 v
Approved quotation / purchasing instruction (manual execution in prototype)
```

## Key design decisions

### Separate AI interpretation from arithmetic

LLMs may extract, classify, explain and coordinate. Financial calculations should use deterministic, tested functions with visible inputs and formulas.

### Human approval gates

The system may draft recommendations, but it must not independently place orders, transfer money, accept customer orders or send binding quotations.

### Data provenance

Each value should be tagged as one of:
- User-provided
- Extracted from a document
- Retrieved from an integration
- Estimated
- Sample / simulated

### Security and privacy

A production version should use authentication, role-based access, encrypted transport and appropriate protection for customer and supplier documents. The hackathon prototype should use synthetic or permissioned data and avoid uploading confidential business records without authorization.

## Initial prototype architecture

For the first demo, a single backend application can orchestrate a small number of focused agent workflows and deterministic tools. The architecture is modular so additional agents can be introduced without requiring five independently deployed services.
