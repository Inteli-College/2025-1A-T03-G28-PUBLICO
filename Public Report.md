# KapAloca Public Report – Module 2: Optimized Allocator

**Date:** June 26, 2025  
**Authors:** Iago Medeiros Tavares & KapAloca Team  

---

## 1. Executive Summary

Over the last five sprints, the KapAloca team successfully designed, implemented, and delivered the **Optimized Allocator** module. This component replaces our baseline allocator with a high-performance, mathematically driven engine that automatically distributes trade orders across funds and custodians, respecting both target proportions and lot-size constraints. All planned deliverables have been completed on schedule, resulting in:

- **100% test coverage** for core allocation logic  
- **Sub-2-second** batch processing for typical order volumes  
- **Auditable, transparent** allocation reports  
- **Seamless integration** with market data feeds and the Base Allocator pipeline  

---

## 2. Completed Sprint Summary

| Sprint      | Goal                                    | Status      | Key Achievements                                                                                   |
|-------------|-----------------------------------------|-------------|----------------------------------------------------------------------------------------------------|
| **Sprint 1**| Model & Design                          | ✅ Completed | - Formalized optimization as an MIP problem<br>- Selected commercial solver<br>- Defined unit-test plan |
| **Sprint 2**| Prototype Implementation                | ✅ Completed | - Developed initial optimizer module in `core/allocator.py`<br>- Implemented price-error objective and basic constraints |
| **Sprint 3**| Integration with Base Allocator         | ✅ Completed | - Embedded optimizer into Base Allocator pipeline<br>- Wired up live market-data and target proportions<br>- Validated end-to-end flow with mocks |
| **Sprint 4**| Performance & Scenario Testing          | ✅ Completed | - Benchmarked runtime: **1.7 s** per 1 k orders on average hardware<br>- Profiled hotspots and optimized bottlenecks<br>- Verified stability on edge-case datasets |
| **Sprint 5**| Validation & Handover                   | ✅ Completed | - Published validation report detailing accuracy and edge-case coverage<br>- Finalized user and developer documentation<br>- Conducted stakeholder demo and gathered sign-off |

---

## 3. Quality & Reliability

- **Test Coverage:** 100% for all new functions, including edge-case scenarios for lot-size constraints.  
- **Error Handling:** The function `realizar_picking_das_boletas_por_preco_medio()` now raises clear `ValueError`s when allocation quantities violate predefined lot multiples.  
- **Performance:** Average allocation time of **1.7 s** per 1,000 order lines, well below the 2 s target.  

---

## 4. Technical Highlights

1. **Mathematical Model**  
   - Mixed-Integer Programming (MIP) formulation minimizing price-error deviation.  
2. **Modular Codebase**  
   - `scs/alocator/` for optimization logic  
   - `data/` for market data adapters  

3. **Quantity-Restriction Verification**  
   - Validates that each asset’s allocated quantity is an exact multiple of its lot size before proceeding  
   - Prevention of invalid allocations via early exception raising  

---

## 5. Deployment & Usage

1. **Clone the repo**

   ```bash
   git clone https://github.com/Inteli-College/2025-1A-T03-G28-PUBLICO.git
   cd kapaloca 

2. Create a virtual environment

    ```bash
    python -m venv .venv
    source .venv/bin/activate  
    pip install -r requirements.txt 

3. Run the optimizer
    ```bash
    jupyter notebook src/alocator/Allocation_Algorithm.ipynb

