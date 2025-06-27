## Module 2 – Optimized Allocator: 5-Sprint Plan

| Sprint      | Goal                  | Key Tasks                                                                                                      |
|-------------|-----------------------|-----------------------------------------------------------------------------------------------------------------|
| **Sprint 1**| **Model & Design**    | - Formalize allocation as a mathematical program (objective, variables, constraints)<br>- Select solver/approach (LP, MIP, heuristic)<br>- Draft unit-test plan for core functions |
| **Sprint 2**| **Prototype Implementation** | - Code initial optimizer module<br>- Implement objective-function for price-error minimization<br>- Write unit tests for error calculation and constraint checks |
| **Sprint 3**| **Integration**       | - Embed optimizer into the Base Allocator pipeline<br>- Wire up market-data inputs and target proportions<br>- Verify end-to-end data flow with mock datasets |
| **Sprint 4**| **Performance & Scenario Testing** | - Benchmark runtime and memory (target < 2 s/batch)<br>- Run on historical and edge-case datasets<br>- Profile and optimize bottlenecks |
| **Sprint 5**| **Validation & Handover** | - Produce validation report (accuracy, edge-cases)<br>- Finalize developer/user documentation<br>- Demo to stakeholders and gather sign-off |
