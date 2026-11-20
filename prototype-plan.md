# Prototype Development Plan

## Goal

Demonstrate a complete, understandable decision-support workflow for one sample manufacturing RFQ using clearly labelled synthetic data.

## Minimum viable demonstration

1. Enter a sample RFQ.
2. Extract and confirm material, quantity and delivery details.
3. Load three sample supplier quotations.
4. Compare total landed cost using available freight and charge fields.
5. Check sample inventory and calculate net material purchase quantity.
6. Calculate production cost from explicit material, wastage, labour, machine and power assumptions.
7. Compare a proposed selling price with estimated cost and target margin.
8. Generate a draft customer quotation and supplier recommendation.
9. Require an owner approval action before marking the draft approved.
10. Record illustrative actual costs and show estimated-versus-actual variance.

## Suggested staged implementation

### Stage 1 – Reliable calculations
- Define input schemas.
- Implement landed-cost, inventory, manufacturing-cost and margin functions.
- Add unit tests and validation for missing or inconsistent units.

### Stage 2 – RFQ and supplier document handling
- Support text input and simple PDF extraction.
- Add OCR only if image/scanned document support is feasible.
- Show extracted fields for user confirmation.

### Stage 3 – Agent workflow and dashboard
- Connect the focused agent workflow to deterministic tools.
- Build a dashboard showing RFQ, supplier comparison, cost breakdown and risk flag.
- Add owner approval state.

### Stage 4 – Learning record and polish
- Record estimated and actual costs.
- Display variance and update user-reviewed assumptions.
- Test with several synthetic scenarios and document limitations.

## Demo acceptance criteria

- The same inputs produce the same calculation outputs.
- Supplier comparison shows the formula and included charges.
- Inventory reduces the net quantity to purchase.
- The cost breakdown exposes all assumptions.
- A below-cost or below-target-margin order is clearly flagged.
- No purchase or binding quotation is executed without owner approval.
- Sample data is visibly labelled as synthetic.

## Out of scope for the first prototype

- Guaranteed live supplier price feeds
- Autonomous purchasing or payment
- Guaranteed supplier negotiation outcomes
- Full ERP integration
- Production-grade offline synchronization
- Claims of measured savings without field testing
