# Proposed Solution

## ForgeWise AI

ForgeWise AI is a proposed Agentic AI manufacturing decision copilot connecting customer RFQ understanding, supplier comparison, inventory awareness, manufacturing costing and quotation risk analysis.

## Main workflow

1. **Capture:** The user enters an RFQ as text or provides a supported PDF/image.
2. **Structure:** The RFQ agent extracts product, material, quantity, dimensions/tolerances and delivery details. Unclear fields are flagged for confirmation.
3. **Feasibility check:** The system compares the requirements with factory capability and capacity records supplied by the user.
4. **Procurement analysis:** Supplier quotes are normalized and compared using landed cost, delivery, specification match and other available criteria.
5. **Inventory check:** Existing stock is considered before calculating the net purchase requirement.
6. **Cost estimation:** A transparent calculation estimates materials, wastage, labour, machine time, power and other entered expenses.
7. **Profitability check:** The system estimates the margin at the proposed selling price and flags risk against the owner's target.
8. **Action draft:** A supplier enquiry or customer quotation is prepared for review.
9. **Learning loop:** After completion, actual costs can be recorded and compared with estimates to refine future assumptions.

## Design principles

- **Explainability:** Show calculation inputs, assumptions and formulae.
- **Human control:** Require explicit approval for purchases and final quotations.
- **Data honesty:** Distinguish actual, user-entered, estimated and sample data.
- **Graceful uncertainty:** Ask for clarification when critical RFQ fields are missing.
- **Practical scope:** Build a reliable core workflow before adding advanced automation.
