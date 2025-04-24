# system-prompt
an LLM system prompt to have a smart and courious generalist that is all encompassing, you can use it for software architecture, design, code review, etc. Looking for a quality feedback and contributions. especially around evals across various problems.



Just copy and pase the promp.md into your favorite LLM as a system prompt - it taks about 3k tokens.

**System Prompt Version History (V1 through V5.8)**

*   **V1 (Initial Prompt):** Basic structure, flat model list.
*   **V2 (Structured & Pragmatic):** Tiered models (Core/Toolkit), depth/pragmatism guidance, coding subpaths.
*   **V3.1 (Technical Focus + Advanced Risk Models):** Added Mx0, Falsifiability, Black Swan, Red Queen, Precautionary-Tech (technical framing); removed broad ethical models.
*   **V4 (Holistic - Tech + UX + Ops + Value):** Expanded V3.1 with JTBD, Nielsen Heuristics, Observability, SLOs/SLIs, Cynefin, ADR encouragement.
*   **V5 (Adaptive Holistic):** Added meta-instructions to V4 for Adaptability, Proportionality, Meta-Cognition, and Structured Communication.
*   **V5.1 (V5 + Reasoning/Output Nudges):** Added subtle hints for internal CoT & considering structured output.
*   **V5.3 (V5.1 + Refined Task Format with Goal):** Adopted specific Markdown task list format (Task ID, Title, Goal, Instruction, Rationale, Dependencies), omitting explicit model names in Rationale.
*   **V5.4 (V5.3 + Unique Random Task IDs):** Refined task ID format to `IDMMDDNNNN` (4-digit random number).
*   **V5.5 (V5.4 + Granular Instructions + Hyrum/Inverse Conway):** Explicitly required detailed step-by-step instructions for complex/multi-step tasks. Added Hyrum's Law nuance to Second-Order Thinking and Inverse Conway's Law to Conway's Law.
*   **V5.6 (V5.5 + Error Feedback & Pre-fetching & Stronger Hallucination Mitigation):** Added Guiding Principle #6 for stronger hallucination mitigation (state uncertainty, quantify confidence, ground in evidence) and proactive information seeking (identify knowledge gaps, suggest RAG/Tool Use/Search). Enhanced Context Priming, Falsifiability, Debugging, Self-Correction, and Goal statement to align with Principle #6. Emphasized *requesting* external info if needed.
*   **V5.8 (V5.6 Modified for Assumed Progress with Explicit Caveats):** Tuned Guiding Principle #6 and related sections. Shifted emphasis from *halting/requesting* external info when uncertain to **proceeding with the most reasonable answer based on available info/assumptions, while MANDATING the explicit statement of those assumptions, confidence level, and noting (not blocking on) the need for external validation.** Goal is faster progress while maintaining transparency about uncertainty.


**Contributing**
    Fork → clone → create a feature branch.
    Open a Pull Request or Issue—specific questions welcome!
