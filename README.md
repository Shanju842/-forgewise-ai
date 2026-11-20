# ForgeWise AI
### An Agentic Manufacturing Intelligence Copilot for Smart Procurement and Profit-Safe Quoting

ForgeWise AI is a proposed Agentic AI-powered decision-support platform for small manufacturing businesses. It aims to help factory owners understand customer enquiries, assess manufacturing feasibility, compare supplier quotations, estimate production costs and identify potentially loss-making orders.

> **Project status:** Idea-stage / proposed prototype. The workflows and sample data in this repository are illustrative. No live supplier integrations, deployed product, customer adoption or measured savings are claimed.

## The problem

Small manufacturers often manage customer RFQs, supplier quotations, inventory and costing through phone calls, messaging apps, paper records and spreadsheets. This can make it difficult to compare the true landed cost of materials and account for wastage, labour, machine time, electricity and other production expenses. As a result, businesses may overpay for materials or quote orders below their actual cost.

## Proposed solution

ForgeWise AI coordinates specialized agents and deterministic calculation tools to support a complete workflow:

1. Read and structure a customer RFQ.
2. Check available factory capability and inventory information.
3. Compare supplier quotations using total landed cost and other relevant factors.
4. Estimate manufacturing expenses.
5. Flag potentially loss-making orders and suggest a target quotation.
6. Prepare drafts and recommendations for owner review.

## Proposed agents

| Agent | Responsibility |
|---|---|
| RFQ & Manufacturing Intelligence | Extract product, material, quantity, tolerance and delivery details; identify missing information and check capability data. |
| Smart Procurement & Inventory | Read supplier quotes, compare landed costs, review stock and recommend purchasing quantities. |
| Manufacturing Cost Intelligence | Estimate bill of materials, wastage, labour, machine time, power and other costs. |
| ProfitGuard | Calculate estimated margins, identify loss risks and recommend a minimum viable price. |
| Negotiation & Business Action | Prepare supplier enquiries and customer quotations, maintain case records and request human approval. |

The first prototype is intended to prioritize RFQ extraction, supplier comparison, transparent cost calculations and profitability checks. Additional agents and integrations are planned for later iterations.

## Example workflow

A factory receives an RFQ for a batch of components and uploads three supplier quotations. ForgeWise extracts the material and quantity requirements, checks sample inventory records, compares supplier landed costs, estimates production expenses and calculates the expected margin. If the proposed selling price is below the estimated cost or the owner's target margin, the system flags the risk and suggests a revised price for review.

All numbers in the sample dataset are fictional and provided only to demonstrate the workflow.

## Proposed technology

- Frontend: React
- Backend: Python and FastAPI
- Database: SQLite for a prototype; PostgreSQL may be considered for later deployment
- AI: LLM with tool calling and an agent orchestration framework such as LangGraph
- Document processing: PDF text extraction and OCR for scanned documents
- Voice: Speech-to-text and text-to-speech for Tamil and English, subject to prototype feasibility
- Costing: deterministic Python calculation functions, not free-form LLM arithmetic

## Trust, safety and reliability

- Supplier recommendations should explain the data and assumptions used.
- Cost calculations should be reproducible and auditable.
- Missing or ambiguous RFQ details should trigger clarification rather than guessed specifications.
- The owner must approve purchases, supplier commitments and final customer quotations.
- Local records and later synchronization are a proposed offline-friendly direction; actual offline behavior must be implemented and tested before it is claimed as available.

## Prototype plan

See [`docs/prototype-plan.md`](docs/prototype-plan.md). The initial demo will use clearly labelled sample data and demonstrate:

1. RFQ input and structured extraction.
2. Supplier quotation comparison and landed-cost calculation.
3. Manufacturing cost estimation.
4. Profitability and margin-risk analysis.
5. A draft quotation requiring owner approval.

## Repository structure

```text
forgewise-ai/
├── README.md
├── LICENSE
├── docs/
│   ├── problem-statement.md
│   ├── proposed-solution.md
│   ├── system-architecture.md
│   ├── agent-workflow.md
│   ├── prototype-plan.md
│   └── technology-stack.md
└── sample-data/
    ├── supplier-quotations.csv
    └── manufacturing-costs.csv
```

## Important note

This repository documents a proposed hackathon concept and prototype plan. Sample supplier records and costs are fictional. Do not describe planned features as implemented or sample results as real-world performance.

## License

See [`LICENSE`](LICENSE).
