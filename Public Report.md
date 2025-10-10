# Email Data Extraction Agent – Public Report

**Date:** October 9, 2025  
**Authors:** Iago Tavares & Engineering Team  

---

## 1. Executive Summary

The **Email Data Extraction Agent** project successfully automates the extraction and validation of financial information from unstructured email content.  
Over the course of development, the team implemented a multi-agent pipeline combining natural language understanding and validation logic to ensure reliable, structured data from noisy text inputs.

The system is now fully functional and integrated, achieving:

- **Accurate JSON extraction** from heterogeneous email formats  
- **Full pipeline orchestration** between Extractor, Verifier, and Orchestrator agents  
- **Resilience to human error**, inconsistent formatting, and multilingual data  
- **Structured and auditable results** ready for downstream financial systems  

---

## 2. Completed Sprint Summary

| Sprint      | Goal                                  | Status      | Key Achievements                                                                 |
|--------------|---------------------------------------|-------------|----------------------------------------------------------------------------------|
| **Sprint 1** | Architecture Design                   | ✅ Completed | Defined multi-agent structure (Extractor / Verifier / Orchestrator). |
| **Sprint 2** | ExtractorAgent Implementation          | ✅ Completed | Implemented TinyLlama model for entity recognition and JSON schema extraction. |
| **Sprint 3** | VerifierAgent Development              | ✅ Completed | Added validation routines for numeric normalization, schema validation, and consistency checks. |
| **Sprint 4** | Orchestration & Fallbacks             | ✅ Completed | Built the `Orchestrator` class coordinating agents, error handling, and recovery logic. |
| **Sprint 5** | Testing, Documentation & Optimization | ✅ Completed | Validated pipeline with real-world emails; finalized README, diagrams, and user examples. |

---

## 3. Quality & Reliability

- **Functional Coverage:** All agent layers tested for extraction, validation, and recovery.  
- **Resilience:** Handles inconsistent patterns (commas, missing labels, mixed languages).  
- **Security Measures:** Anti–prompt-injection rules and numeric coercion for safe parsing.  
- **Auditability:** Clear JSON output and layered validation ensure transparency.  

---

## 4. Technical Highlights

1. **Agent-Based Architecture**  
   - Three-layer system: Extractor → Verifier → Orchestrator.  
   - Modular design enables maintainability and scalable future integration.

2. **AI-Powered Parsing**  
   - Uses **TinyLlama** for natural language understanding.  
   - Capable of identifying structured financial data even in human-written, messy text.

3. **Verifier Logic**  
   - Ensures numerical consistency and field validity (e.g., quantity > 0).  
   - Automatically corrects decimal and separator inconsistencies.

4. **Orchestration Flow**  
   - Central control via the `Orchestrator` class.  
   - Executes fallback and re-verification steps to guarantee final output integrity.

---

## 5. Deployment & Usage

1. **Clone the repository**
   ```bash
   git clone https://github.com/Inteli-College/2025-1A-T03-G28-PUBLICO.git
   cd email-data-extraction-agent


2. **Create a Virtual Environment**
   ```pytbashhon
      python -m venv .venv
      source .venv/bin/activate
      pip install -r requirements.txt

3. **Run the Orchestrator**
   ```python
      from orchestrator import Orchestrator
      from agents import ExtractorAgent, VerifierAgent

      email = """
      COMPRA: NTN-B 15/08/2026
      QTDE: 320.000
      PU: 4.374,14
      FIN: R$ 999.999,45
      """

      orchestrator = Orchestrator(ExtractorAgent(), VerifierAgent())
      result = orchestrator.run(email)
      print(result)

## 6. Future Work

Multi-language fine-tuning for English, Portuguese, and Spanish emails.

Integration with corporate inbox APIs (e.g., Outlook, Gmail).

Confidence scoring for extracted entities.

Automatic classification of email types (purchase, sale, correction).

