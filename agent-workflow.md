# Agent Workflow

## 1. RFQ & Manufacturing Intelligence Agent

**Input:** Customer RFQ text or supported document.  
**Tasks:** Extract product description, material, quantity, dimensions, tolerance and due date; identify missing fields; request confirmation.  
**Output:** Structured RFQ record and clarification list.

## 2. Smart Procurement & Inventory Agent

**Input:** Confirmed material requirement, inventory record and supplier quotations.  
**Tasks:** Normalize quote units and specifications; calculate landed cost where freight and other charges are available; compare delivery and supplier attributes; calculate net quantity to buy after stock.  
**Output:** Comparison table and explainable supplier recommendation.

## 3. Manufacturing Cost Intelligence Agent

**Input:** Confirmed RFQ, bill of materials, process assumptions and factory cost data.  
**Tasks:** Estimate material usage and wastage; calculate labour, machine, power and other entered costs.  
**Output:** Cost breakdown, unit cost and assumptions.

## 4. ProfitGuard Agent

**Input:** Cost breakdown, proposed selling price and owner target margin.  
**Tasks:** Calculate gross contribution / margin according to the selected definition; compare against target; flag a loss or insufficient margin; calculate a suggested price.  
**Output:** Risk status, calculation and suggested price range.

## 5. Negotiation & Business Action Agent

**Input:** Supplier and quotation recommendations.  
**Tasks:** Draft supplier enquiry / negotiation messages and customer quotation; maintain case status; request owner approval.  
**Output:** Draft documents and approval request.

## Example state flow

```text
NEW_RFQ
  -> NEEDS_CLARIFICATION (if required fields missing)
  -> RFQ_CONFIRMED
  -> FEASIBILITY_REVIEW
  -> PROCUREMENT_ANALYSIS
  -> COST_ESTIMATED
  -> PROFITABILITY_CHECKED
  -> DRAFT_READY
  -> OWNER_APPROVED or OWNER_REJECTED
  -> COMPLETED
  -> ACTUAL_COST_RECORDED
```

The workflow should preserve case state so it can resume after missing information is supplied. Failed extraction or incomplete supplier data should lead to a retry or human review, not fabricated values.
