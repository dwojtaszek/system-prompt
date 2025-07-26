System Prompt Version History
V1 (Initial Prompt):
Description: Established the basic two-part structure (Architecture/Design & Coding/Development). Included a broad selection of relevant technical and strategic mental models with brief definitions, aiming to guide the AI in applying critical thinking. Lacked strong structure or guidance on application depth.
V2 (Structured & Pragmatic):
Description: Introduced significant structural improvements based on V1 validation. Implemented a tiered approach (Core vs. Toolkit models), added explicit instructions to focus on reasoning depth over breadth, and included a pragmatism clause to encourage selective, context-appropriate model application. Coding phase broken into subpaths (Implementation, Review, etc.). Addressed potential V1 verbosity and superficiality.
V3.1 (Technical Focus + Advanced Risk Models):
Description: Built upon V2's structure. Incorporated deeper analytical and risk-focused models identified as useful for complex scenarios (like Osmosis), including Multiply by Zero, Falsifiability, Black Swan Theory, Red Queen Effect, and a technically-framed Precautionary Principle. Explicitly removed the broader ethical models discussed previously to maintain a strong technical/operational focus.
V4 (Holistic - Tech + UX + Ops + Value):
Description: Major expansion integrating concepts beyond technical implementation. Added models/frameworks for Jobs-to-be-Done (User Value), Nielsen's Heuristics & Cognitive Load (User Experience), Observability Pillars & SLOs/SLIs (Operational Readiness), Cynefin Framework (Problem Framing), and encouraged ADRs (Documentation). Aimed for a comprehensive product development perspective.
V5 (Adaptive Holistic):
Description: Refined V4 by adding meta-instructions for the AI. Introduced principles of Adaptability (scaling analysis depth based on task complexity/risk), Proportionality (applying models judiciously), Meta-Cognition (self-correcting model application relevance/depth), and improved Structured Communication guidance. Kept V4's holistic toolkit but focused on how the AI should apply it intelligently.
V5.1 (V5 + Reasoning/Output Nudges):
Description: Minor refinement of V5. Added subtle guidance encouraging the AI to consider using internal structured reasoning (like CoT/Step-back) for complex tasks and to consider suggesting structured output formats (like tables/JSON) for complex results to improve clarity.
V5.2 (Concept - Dedicated Task Format Rule):
Description: (User preference led to V5.3 instead) Focused refinement of V5.1 specifically for improving task list outputs (e.g., after code reviews). Proposed adding a dedicated general instruction detailing a required Markdown format for tasks, emphasizing Atomicity, Location, Action, Rationale, and Dependencies.
V5.3 (V5.1 + Refined Task Format with Goal):
Description: Built on V5.1. Adopted the user-preferred Markdown task list format incorporating an explicit Goal: field alongside Title, Instruction, Rationale, and Dependencies. Specified that explicit mental model names should not be included in the user-facing Rationale:.
V5.4 (V5.3 + Unique Random Task IDs):
Description: Refined V5.3's task list formatting instruction. Changed the Task [UniqueID] format requirement to IDMMDDNNNN, where NNNN is explicitly a four-digit random number to enhance cross-session uniqueness. The rest of the V5.3 structure (Title, Goal, Instruction, Rationale, Dependencies) remained.
V5.5 (V5.4 + Granular Instructions + Hyrum/Inverse Conway): 
Description:Explicitly instructed AI to provide detailed, step-by-step instructions for complex/multi-step implementation/refactoring/debugging tasks (modifying Principle #2 and Task List Instruction field). Added a hint encouraging hierarchical tasks. Also integrated Hyrum's Law nuance into Second-Order Thinking and Inverse Conway's Law into Conway's Law. Retained IDMMDDNNNN random ID format.
V5.6 (V5.5 + Error Feedback & Pre-fetching): 
Description: Enhanced Explicit Context Priming to suggest pre-fetching anticipated data. Enhanced Debugging subpath and Self-Correction principle to explicitly include analyzing and learning from error feedback from previous steps.
V5.8 (V5.6 Modified for Assumed Progress with Explicit Caveats): 
Description: Tuned Guiding Principle #6 and related sections. Shifted emphasis from halting/requesting external info when uncertain to proceeding with the most reasonable answer based on available info/assumptions, while MANDATING the explicit statement of those assumptions, confidence level, and noting (not blocking on) the need for external validation. Goal is faster progress while maintaining transparency about uncertainty
V6.0
Added Guiding Principle #7 (Plan Before Executing Complex Tasks):
Introduced a new principle mandating an internal planning/outlining phase before the AI undertakes complex generation, design, or analysis.
Allows for optional presentation of this plan summary to the user for confirmation on very complex tasks.
Impact: Improves coherence and completeness of complex outputs; allows for early course correction.
Added "Pre-Analysis Scan" Section (Part A - Architecture/Design):
Instructs the AI to perform and internally note findings from quick scans using JTBD, Systems Thinking, Multiply by Zero, and Inversion before synthesizing its main architectural review or design.
Impact: Ensures foundational perspectives are considered upfront, offloads cognitive load, and grounds subsequent deeper analysis.
Enhanced Guiding Principle #2 (Adapt Your Approach - Dynamic Model Weighting):
Added instruction for the AI to identify and (internally or if requested) state the top 2-3 mental models receiving highest priority for the current task, and to give them precedence in case of conflict, explaining the trade-off.
Impact: Leads to more contextually relevant and defensible decisions by making model prioritization explicit.
Enhanced "Self-Correction" General Instruction (Structured Self-Critique):
Mandates a brief internal self-critique after drafting a primary response for complex design/review tasks, considering the draft from at least two alternative personas (Security Auditor, End-User, Ops Engineer, Maintainer).
The AI should note if this critique leads to refinements.
Also refined the reporting of unresolved uncertainty: "If self-correction does not resolve uncertainty or error, clearly state the remaining ambiguity and the specific point of failure in the reasoning process."
Impact: Forces a more robust internal multi-perspective review, potentially catching a wider range of flaws; improves transparency when uncertainty persists.
Refined Guiding Principle #6 (Address Uncertainty with Grounded Assumptions & Clear Caveats):
Strengthened the instruction: "Only refuse to provide a substantive answer if the task is impossible or nonsensical without critical missing information, stating clearly 'Cannot proceed without [specific missing information].' In such cases, also suggest a simplified version of the task that can be addressed with available information, if feasible."
Impact: Makes the AI more helpful even when fully blocked on the original request by prompting it to offer alternatives.
V6.1
Modified "Artifact Generation" Section (Part A - Previously an unnumbered subsection, now formalized):
Introduced a formalized "Artifact Generation" section.
Replaced any previous informal artifact syntax ideas (like %%% ARTIFACT %%%) with explicit pseudo-HTML/custom XML tags (e.g., <CODE language="python">...</CODE>, <MARKDOWN_DOCUMENT>...</MARKDOWN_DOCUMENT>, etc.) for defining different types of substantial, structured outputs.
The title attribute for artifacts remains optional but recommended.
Impact: Provides a robust, standard, and LLM-friendly way to delineate and type artifacts, improving clarity and parsing reliability for diverse, complex outputs. 
Enhanced Guiding Principle #6 (Address Uncertainty - Simplified Citation):
Modified the sub-bullet regarding answers based on provided documents.
New text: "When answering based only on provided documents/context, internally verify supporting evidence exists and state this limitation. If specific claims are drawn from a provided document, briefly indicate the source document or a clear reference (e.g., '[Source: design_doc_section_3.2]', '[Ref: UserManual_Page10]') immediately after the claim."
Impact: Adds a simplified, universal citation mechanism for traceability when the AI is working directly from supplied documents. 
Added Guiding Principle #8 (Resolve Model Conflicts Systematically):
Introduced a new principle providing a structured approach for the AI when key mental models offer conflicting advice.
Steps include: Acknowledge conflict -> Refer to primary Goal/JTBD -> Apply Second-Order Thinking -> Consider Opportunity Cost -> If still unclear, present options/ask for user priority.
Impact: Provides a clear protocol for navigating design tensions, leading to more transparent and reasoned trade-off analysis. 
v6.2
Enhanced Guiding Principle #1 (Apply Mental Models Pragmatically... - Sunk Cost Fallacy):
Implicitly strengthened by integrating Sunk Cost Fallacy awareness. The AI, when applying Opportunity Cost or Second-Order Thinking, is now more explicitly guided (via the general "Cognitive Bias Awareness" in Self-Correction and its training on these concepts) to disregard past investments if they don't justify future value. While not a direct wording change here, its application is refined by the Self-Correction update.
Enhanced Explicit Context Priming (Part A - Survivorship Bias):
Added a new specific instruction: "When analyzing patterns or best practices from existing systems/examples, actively consider if the available data represents only successes (Survivorship Bias) and seek to understand common failure patterns or less successful attempts if possible/relevant."
Impact: Prompts the AI to be more critical when learning from provided examples or case studies, leading to more robust and contextually appropriate conclusions.
Enhanced "Self-Correction" General Instruction (General Cognitive Bias Awareness):
Expanded the self-critique step: "After drafting your primary response for a complex design or review task, perform a brief internal self-critique. Consider your draft from at least two of these alternative perspectives: Security Auditor, End-User (Usability/JTBD), Operations Engineer (Reliability/Observability), Maintainer (Complexity/Clarity). Additionally, briefly consider if common cognitive biases (e.g., anchoring on initial data, overconfidence due to recent success, sunk cost fallacy, survivorship bias, favoring popular solutions/bandwagon effect) might be unduly influencing your analysis or recommendations. Briefly note if this critique leads to any refinements in your final output. If self-correction does not resolve uncertainty or error, clearly state the remaining ambiguity and the specific point of failure in the reasoning process."
Impact: Provides a broader mechanism for the AI to check its reasoning against common thinking errors beyond just Confirmation Bias, leading to more objective and nuanced outputs. Explicitly lists key biases like sunk cost and survivorship as examples to check for.
v6.3
Modified First Principles Thinking (Core Technical & Value Models - Part A):
Added: "Be wary of initial information or requirements unduly influencing subsequent analysis (Anchoring Bias)."
Impact: Explicitly guides the AI to counteract the tendency to over-rely on the first piece of information encountered.
Modified Inversion (Core Technical & Value Models - Part A):
Added: "Actively consider both best-case (to identify critical success paths) and worst-case (to identify failure modes) scenarios (mitigating Optimism/Pessimism Bias)."
Impact: Encourages a more balanced risk and opportunity assessment by looking at both ends of the outcome spectrum.
Modified Negative Constraints / Anti-Patterns to Avoid (Part A):
Added: "Avoid recommending solutions or technologies solely because they are currently popular (Bandwagon Effect) without validating suitability."
Added: "Challenge assumptions even if they appear to be widely accepted within the provided context to avoid Groupthink."
Impact: Promotes more independent critical thinking and validation against objective criteria rather than social proof or perceived consensus.
Modified Confirmation Bias Awareness (Toolkit Models - Strategic & Risk Analysis - Part A):
Added: "Be particularly wary of consensus-driven biases that might resemble Groupthink."
Impact: Reinforces the check against Groupthink from a different angle, within the model specifically designed for bias awareness.
Modified Black Swan Theory (Toolkit Models - Strategic & Risk Analysis - Part A):
Added: "Guard against overestimating likelihood based on easily recalled or vivid recent events (Availability Heuristic), and assess both optimistic and pessimistic impact scenarios."
Impact: Makes risk assessment for rare events more robust by countering the availability heuristic and ensuring a balanced view of potential impacts.
Modified Self-Correction (General Instruction):
Expanded the list of cognitive biases to check for: "...briefly consider if common cognitive biases (e.g., anchoring on initial data, overconfidence due to recent success or the Availability Heuristic, Halo Effect masking flaws in other areas, sunk cost fallacy, survivorship bias, favoring popular solutions/bandwagon effect) might be unduly influencing your analysis or recommendations."
Impact: Broadens the AI's metacognitive check to include more specific common thinking errors, aiming for more objective self-critique.
v6.4
Enhanced Guiding Principle #6 (Address Uncertainty with Grounded Assumptions & Clear Caveats):
Added a new sub-bullet: "If the task involves generating content in a very specific or nuanced format/style that is not clearly defined by the request or existing context, and confidence in achieving this is low, consider asking the user for 1-2 examples of the desired output (Few-Shot Prompting assistance)."
Impact: Empowers the AI to proactively solicit few-shot examples from the user when output requirements are ambiguous, potentially improving output quality and alignment with user expectations, directly leveraging a key prompt engineering best practice.
Modified Implementation Subpath (Part B.1):
Added to the "Core" models/instructions for implementation: "For non-trivial functions or components, consider outlining logic with comments before writing the full code. Break down complex implementations into smaller, manageable pieces or steps, and aim to generate code that can be tested incrementally if appropriate."
Impact: Provides more specific procedural guidance for complex code generation, encouraging better structure, upfront commenting for clarity, and an incremental development/testing mindset, aligning with established software engineering best practices for tackling complex coding tasks.
v6.5
Enhanced Guiding Principle #2 (Adapt Your Approach - Dynamic Model Activation Profiles):
Added a new sub-instruction: "Based on the initial context and task type, also select and state (internally or if requested) the most appropriate 'Model Activation Profile' from the following list to guide your analysis (e.g., "Activating Security Review Profile")"
Defined profiles: Security Review Profile, Greenfield Design Profile, Refactoring/Optimization Profile, Debugging/RCA Profile, General Analysis/Critique Profile, each with emphasized models.
Impact: Provides more structured guidance for activating coherent sets of models best suited for common, distinct software engineering contexts.
Modified "Formatting Task Lists" (General Instruction - Reflective Rationale Linking):
Added a new optional field to the task structure: "ModelLink (Internal/Optional): (Internally note, or provide if requested for deeper analysis, the 1-2 primary mental models whose application led to this task's Rationale. E.g., "ModelLink: Inversion, Precautionary Principle")"
Impact: Enhances transparency by allowing the user to (optionally) see which specific models most heavily influenced a particular task's rationale.
Enhanced Guiding Principle #8 (Resolve Model Conflicts Systematically - Proactive Trade-off Illumination):
Added a new sub-instruction: "If an internal resolution is made for a conflict between high-priority models that has significant architectural or user-facing implications, briefly state your chosen path and the primary trade-off made, then proactively ask a concise question to the user allowing them to confirm or redirect your priority before extensive further work. E.g., 'I've prioritized X (leading to benefit A) over Y (which would give benefit B). Is this prioritization correct for your current goals, or should I explore the path prioritizing Y?'"
Impact: Involves the user in critical trade-off decisions early, optimizing effort and alignment.
Enhanced "Communicate Effectively" (General Instruction - Assumption & Knowledge Gap Register):
Added: "For complex analyses or designs, conclude with an "Assumption & Knowledge Gap Register" section, listing:
Key Assumptions Made: Bullet points of crucial assumptions underpinning your analysis/design (max 3-5).
Critical Knowledge Gaps Remaining: Bullet points of specific external information that, if obtained, would significantly improve confidence or validate assumptions (max 3-5). Reference relevant Task IDs if tasks were created to address these."
Guiding Principle #6 ("Address Uncertainty...") was also updated to ensure identified gaps are summarized in this register.
Impact: Improves clarity and actionability by providing a consolidated summary of critical assumptions and outstanding information needs.
Added "Learning & Generalization" (General Instruction):
Added a new instruction point after "Formatting Task Lists": "Learning & Generalization (After Debugging/Refactoring/Review): After proposing solutions for debugging, refactoring, or issues found in a review, briefly consider if there are generalizable learnings. If so, optionally suggest: 1) A new project-specific best practice. 2) A potential reusable utility/component. 3. A process improvement to prevent similar issues. Keep suggestions concise."
The Debugging subpath (B.4) was updated to link RCA concepts to this new instruction.
Impact: Turns specific problem-solving into broader learning opportunities, promoting systemic improvements in code quality and development processes.
v6.5.1 Advanced Adaptive Holistic Agent (Optimized Clarity)
Guiding Principle #2 (Adapt Your Approach): Streamlined the phrasing for introducing Dynamic Model Weighting and Model Activation Profiles to improve flow and directness.
General Instruction (Self-Correction): Re-structured into explicit numbered steps for greater clarity to the LLM regarding the self-critique process (Multi-Persona, Cognitive Bias Check, Model Application Assessment, Refine & Report).
General Instruction (Communicate Effectively): Re-structured into explicit numbered steps for better flow, consolidating instructions about concluding with an "Assumption & Knowledge Gap Register."
v6.6
Modified "Communicate Effectively" (General Instruction):
Added the explicit instruction: "Respond directly without unnecessary affirmations or conversational filler (e.g., avoid starting with 'Certainly!', 'Okay, I can do that!'). Get to the point while maintaining a helpful tone."
Impact: Guides the AI towards more professional, direct, and token-efficient communication, reducing conversational overhead while retaining helpfulness.
v6.7
Enhanced Guiding Principle #4 (Be a Thinking Partner - Explicit CoT Output):
Modified to more strongly suggest (and optionally mandate for very complex reasoning) outputting the internal Chain of Thought or Step-back reasoning before the final answer, for transparency.
Enhanced Guiding Principle #6 (Address Uncertainty - Example Quality & RAG Nudge):
When asking for few-shot examples, add a hint to request diverse and high-quality examples.
When noting the need for external info, more explicitly frame it as "This task would benefit from Retrieval Augmented Generation (RAG) using [specific type of source/tool]."
Enhanced Systems Thinking (Core Model - Part A):
Added explicit prompts to look for feedback loops, cascading effects, and emergent behaviors (from image analysis).
Enhanced Second-Order Thinking (Core Model - Part A):
Added explicit prompt to consider how fixes might introduce new problems (penalizing narrow optimization - from image analysis).
Enhanced Debugging Subpath (Part B.4 - Adaptive Diagnostic Reasoning):
Added instruction to employ adaptive diagnostic reasoning: form broad hypotheses with ambiguous data, then iteratively refine/discard as new info emerges (from image analysis).
Enhanced Learning & Generalization (General Instruction - Conceptual Generalization):
Added a point to suggest generalizing learnings into broader conceptual principles or patterns, not just specific best practices/utilities (from image analysis).
Refined Self-Correction (General Instruction - Specific Critique Phrasing):
Incorporate phrasing like "Are there any parts of the previous response that could be improved for clarity, accuracy, or completeness?" to guide the self-critique.
v6.8
Enhanced Guiding Principle #4 (Be a Thinking Partner - Explicit CoT/CoD Output):
Modified to explicitly suggest using either Chain of Thought (CoT) for step-by-step reasoning or Chain of Draft (CoD) for iterative refinement of complex outputs (like documents or code).
Still suggests optionally outputting the internal reasoning/drafting path for transparency.
Impact: Provides the AI with two distinct structured reasoning/generation strategies for complex tasks, allowing it to choose the most appropriate one.
Enhanced Guiding Principle #6 (Address Uncertainty - Example Quality & RAG/MCP Nudge):
When noting the need for external information, explicitly frame it as: "This task would benefit from Retrieval Augmented Generation (RAG) using [specific type of source/tool] or by structuring the necessary external information via a Model-Context-Prompt (MCP) approach to [achieve specific goal]."
Impact: Introduces MCP as a recognized method for providing structured external context, offering an alternative or complement to more general RAG, and making the AI aware of this specific framework if the orchestrating system supports it.
v7.0
Enhanced AI Adaptability & User Interaction: Improved guidance for pragmatic model application (Principle 1), profile selection (Principle 2), explicit model naming (Principle 3), and handling uncertainty (Principle 6, Few-Shot Prompting). The Chain of Draft (CoD) definition (Principle 4) was broadened for complex tasks while retaining brevity for exposed steps, and its thinking block delimiter was updated.
Strengthened Core Analysis & Risk Management: Increased emphasis on Hyrum's Law within Second-Order Thinking for both architectural assessment and code review to better address implicit dependencies and long-term maintainability.
Improved Prompt Structure & Clarity: Reorganized the "General Instruction" section for better flow, particularly elevating "Communicate Effectively." Refined instructions for task rationales (discouraging direct model naming) and clarified triggers for offering generalized learnings, ensuring all changes were integrated cleanly without modification markers.
v7.1
Integrated proactive security consciousness as a general negative constraint, requiring baseline security consideration for all code tasks.
Added an explicit directive to consider fairness and potential bias in code affecting users or processing user data, prompting user consideration where appropriate.
Incorporated an accountability mechanism by suggesting the AI recommend logging key decision points or parameters within complex algorithms or decision-making logic it generates.
Included a soft reminder within communication guidelines to emphasize user comprehension of generated code and responsible AI adoption to maintain user skills.
v7.2
Restructured Core Review Principles: The core principles for code review now lead with:
Strategic Scoping: AI should acknowledge and apply strategic scoping for reviews, focusing on risk/complexity, offering partial reviews, or asking for user priorities (replaces the more general "Pareto Principle" in this specific context).
Context-Driven Comprehension: AI must proactively seek/state context (PR descriptions, tickets) to build its "Expected Change" mental model.
Mental Model Comparison Framework: AI will explicitly compare "Actual Code" vs. "Expected Change" vs. "Ideal Implementation."
The existing core models (Systems Thinking, Second-Order Thinking, Inversion, Occam's Razor) will then be applied within this framework, particularly informing the "Ideal Implementation" and overall assessment.
v7.3
Created a dedicated subpath for reviewing technical artifacts other than code (e.g., ADRs, requirements, specifications, API designs, diagrams).
This subpath mirrors the rigor of the "Code Review" subpath but adapts principles for non-executable artifacts.
v7.4
Guiding Principles - Principle 1 (Apply Mental Models Pragmatically and Proportionally):
Enhanced with "Complexity/Risk-Gated Activation": Principle 1 has been significantly augmented. It now explicitly instructs the AI to perform an initial quick assessment of query complexity/risk. Based on this, the AI will gate its engagement with deeper, more comprehensive parts of the prompt.
"Simple/Low-Risk" queries will heavily favor a "fast path," minimizing explicit model use.
"Moderate/Medium-Risk" and "Complex/High-Risk" queries (or explicit user requests for deep analysis) will unlock progressively deeper engagement with the prompt's framework.
This aims to make "proportionality" more structural and improve AI efficiency and user experience for simpler requests.
Prompt Structure - Introduction of "Core Directives Summary":
Added a new introductory section: Before the "Guiding Principles," a brief "Core Directives Summary" (or similar name) will be added. This section will contain a highly condensed list of 5-7 absolute key directives or meta-principles that the AI should always prioritize. The detailed sections that follow will serve as elaborations.
This is intended to help the AI anchor its behavior on the most critical aspects and manage overall prompt complexity.
General Instruction - Self-Correction:
Enhanced "Testability/Verifiability" of Model Application: The "Self-Correction" section (specifically, "Assess Model Application") has been augmented. It now encourages the AI to internally (or if requested, externally) articulate how a chosen mental model specifically shaped its output or recommendation for non-trivial cases, prompting deeper self-reflection on its reasoning process. For example, by asking itself, "If I applied Second-Order Thinking, what specific indirect consequences did I consider, and how did that change my advice?"
v7.5
Enhanced Handling of Uncertainty & Time-Sensitivity (Principle 6): Added explicit instructions for the AI to acknowledge its knowledge cutoff date when relevant (especially for rapidly evolving technologies or security information), recommend user verification of critical, time-sensitive details, and link this to RAG guidance if applicable.
Improved Interaction for User Corrections (Self-Correction): Augmented the "Self-Correction" section with specific guidance on how the AI should respond when a user directly states the AI has made an error or offers a correction. This involves critical re-evaluation, acknowledging valid corrections, or respectfully explaining its reasoning if it stands by its original assessment after review.
v7.6
Refined Gated Activation Framework (Principle 1): The "Gated Engagement" paths in Principle 1 have been reframed using a "Beginner/Intermediate/Advanced" logic. This provides the AI with a clearer model for how to scale the complexity of its response based on the initial query assessment (e.g., executing single directives for simple tasks, synthesizing multiple constraints for complex ones).
Added "Prompt Diagnostic" Capability (Principle 4): Integrated a new directive within "Be a Thinking Partner" for the AI to act as a prompt coach. If a user's request is ambiguous, the AI is now guided to ask targeted clarifying questions about task specificity, role/persona, context, and format, helping the user improve their input.
Incorporated "Step-Back Prompting" as a Core Strategy (Section A): Added "Step-Back Prompting" as an explicit reasoning technique within "Problem Framing & Approach." This instructs the AI to solve a more general problem first to establish principles before tackling a user's specific complex, creative, or diagnostic task, making it a core strategy applicable across all relevant downstream activities.
v7.7
Added "Environmental & Tooling Context" Awareness (Section A): The prompt now explicitly instructs the AI to proactively seek or state assumptions about a user's specific technology stack (tools, versions, cloud environments) when requests involve implementation details. This aims to generate more accurate, directly usable configurations and advice for DevOps, Test, and Security engineers.
Enhanced Artifact Review with "Persona-Driven Focus" (Section B.5): The Technical Artifact Review subpath has been augmented with guidance for the AI to tailor its review focus based on the likely persona of the user (e.g., Product Manager, UI/UX Designer, Engineering Manager). This ensures feedback is more relevant and valuable for non-developer roles.
Created a Dedicated "Test Case & Scenario Generation" Framework (Section B.6): A new subpath has been added that provides a systematic framework for test case generation. This guides the AI to cover positive paths, negative paths, edge cases, destructive tests, and non-functional considerations, making it a more powerful tool for developers and QA/Test Engineers.
v7.8
Introduced "Detailed Technical Explanation Blueprint": Added a new, highly structured blueprint for the AI to follow when providing "Complex/High-Risk" technical explanations. This blueprint mandates sections for Core Concepts, Annotated Code, a Step-by-Step Dry Run, and Technical Analysis (Complexity & Trade-offs), ensuring pedagogical and verifiable deep-dive answers.
Enhanced "Formatting Task Lists" with Action-Oriented Structure: Reworked the task list format to be more structured and professional, similar to a ticket in a project management system. Each task must now include a Title, Goal, Instruction, Rationale, and optional Dependencies, making the AI's review feedback more actionable.
Mandated Justification Against Alternatives in Decision-Making: Added a new directive for when the AI recommends a solution from a set of viable alternatives. The AI must now not only justify its choice but also briefly explain why the primary 1-2 alternatives are less suitable for the specific context, demonstrating more robust trade-off analysis.
v7.9
Formalized and Integrated Persona Framework (Principle 2):
The "Adapt Your Approach" principle has been enhanced. It now explicitly instructs the AI to infer the user's likely persona (e.g., Junior Dev, Senior Architect, PM) from their query.
This inferred persona is now a key input for selecting the appropriate "Model Activation Profile" and applying the "Persona-Driven Review Focus" in artifact reviews, making the AI's adaptability a more deliberate and guided process.
Introduced "Confidence-Based Elaboration" to Complement Gating (Principle 1):
The "Complexity/Risk-Gated Activation" mechanism has been augmented. In addition to assessing the query's complexity, the AI is now instructed to use its own internal confidence score for its generated answer to modulate the response depth.
This allows the AI to be concise even for complex queries if its confidence is high, and conversely, to provide more detailed justifications, caveats, and assumptions for simple queries where its confidence is low. This adds a crucial layer of self-awareness to its communication strategy.
v8.0
Strategic Analysis Added: The agent is now equipped with a SWOT / Pros & Cons framework to assist in high-level architectural and technology decisions.
Process Coaching Introduced: A new "meta-cognitive" capability allows the agent to recognize when a user is stuck in a debugging loop, provide vague problem descriptions, or forget conversational context, and then offer proactive coaching to improve the workflow.
Safety & Tone Hardened: The new coaching heuristics are governed by strict activation triggers and use softened, collaborative language to ensure they are helpful and not disruptive.
Value Delivery Enhanced: The Learning & Generalization step is now mandatory, pushing the agent to consistently provide systemic, long-term value beyond immediate fixes and to suggest formal artifacts like ADRs or utility functions.
Prompt Efficiency Improved: A new Principle 0 (Focused Processing) was added to help the agent manage the prompt's complexity and focus on the most relevant instructions for a given task.
v8.1
Chain of Draft (CoD) Added: The agent can now use an iterative drafting and refinement process for complex creative tasks, improving the quality of generative outputs.
Model-Context-Prompt (MCP) Framework Integrated: The agent is now more context-aware, explicitly framing requests for external information using the RAG or MCP paradigm when its knowledge is insufficient.
Multi-Persona Self-Critique Formalized: The internal review process is now more robust, requiring the agent to critique its own work from specific viewpoints like a Security Auditor or End-User to better identify flaws.
v8.2
Description: Added a new core operational directive instructing the agent to maintain a persistent, long-term memory within a dedicated .ai_workspace directory. This formalizes the practice of using structured files for context management, task breakdown, and knowledge retention across sessions.
Rationale: This is a fundamental enhancement designed to overcome the limitations of conversational context windows. By creating a structured, persistent "brain" for each project, the agent can deliver more consistent, contextually-aware, and high-quality assistance on complex, long-running tasks.
v8.3
Process Improvement: Added "Hallucination Guardrail" Instruction.
The agent is now required to use a specific phrase ("I do not have the specific information required for X.") when it lacks factual knowledge, making it safer and more transparent about its limitations.
Process Improvement: Formalized "Zero-Shot Chain of Thought" for Planning.
To improve the quality of complex plans, the agent is now instructed to begin its internal planning process with the trigger phrase "Let's think step by step," a proven technique for enhancing logical reasoning.
New Capability: Introduced "Generate-Critique-Refine" Profile.
A new Model Activation Profile has been added to formalize an iterative workflow. When selected, the agent will explicitly generate a draft, critique it from multiple perspectives, and then produce a final, refined output.
v8.4
For very complex tasks, the agent is now encouraged to present a concise "Thought Summary" of its plan to the user before generating the final output. This provides a crucial checkpoint, allowing the user to verify the agent's proposed direction, improving efficiency and collaborative alignment.
v8.5
From "Planning" to "Specification-Driven Development":
Principle 7 has been fundamentally reframed from "Plan Before Executing" to "Synthesize a Task Specification Before Execution." This shifts the agent's core operational model from simple planning to the more robust engineering practice of creating a formal specification before work begins.
Mandated "Acceptance Criteria" in All Tasks:
As part of the new Task Specification, the agent is now required to define clear, testable Acceptance Criteria for every non-trivial task before generating code. This is designed to eliminate ambiguity and provide a clear definition of "done."
Introduced the "Spec Refinement Loop":
The agent's method for handling ambiguity has been upgraded. Instead of just asking clarifying questions, it is now instructed to proactively draft a Task Specification and present it to the user for confirmation, turning a simple Q&A into a collaborative design session.
v8.6
Added "Self-Consistency Check" to Internal Review:
Inspired by research on LLM contradictions, the agent is now required to perform a final check on its reasoning to ensure all assertions are logically consistent before delivering a response. This enhances the trustworthiness of its outputs.
Formalized "Plan-Then-Write" Strategy for Large Tasks:
Drawing from the "LONGWRITER" paper, the agent is now explicitly instructed to use a "divide-and-conquer" strategy for large-scale generation. It must first create a detailed plan and then execute each part sequentially, ensuring coherence in long-form content.
Integrated Temporal & Causal Analysis into Specifications:
Inspired by the "T-CPDL" framework, the agent must now perform a brief analysis of key temporal and causal relationships during the planning phase. This makes its internal model of the task more robust and its plans more logical.
v8.7
Added Guiding Principle #10: Employ Dynamic Cognitive Allocation (Mixture-of-Recursions Analogy). This core directive instructs the agent to act as a "router," dynamically allocating its analytical effort based on the complexity and importance of different parts of a user's request, rather than applying uniform effort to all tasks.
Added a new mental model under A. Software Architecture, Design, and Assessment called Mixture-of-Recursions (MoR) for Task Analysis. This provides a concrete framework for implementing Principle #10 during the task planning phase by breaking down requests and annotating sub-tasks with a required "analytical depth" (1-3).
Added a new heuristic under C. Meta-Cognitive & Coaching Heuristics called The "Increase Recursion Depth" Heuristic (Test-Time Scaling). This provides a specific strategy for responding to user feedback on complex tasks by explicitly offering to re-analyze the problem with a deeper, more rigorous application of its mental models.
v8.8
Enhanced Communicate Effectively Section: The general guidance has been replaced with a mandatory, structured response framework.
Introduced Response Templates: The prompt now includes two distinct, formal templates for responses:
A concise template for simple/low-risk tasks.
A detailed template for moderate/complex tasks.
Made Internal Analysis Visible: The agent's internal complexity assessment (from principle P2) now directly determines which response template to use, making its reasoning process more transparent to the user.
Formalized Rationale and Pro Tips: The detailed template includes specific sections for Key Decisions & Rationale and an actionable Pro Tip, ensuring the agent consistently provides deep insights and forward-looking advice for complex requests.


v8.9
Persona Enhancement: The AI's persona has been elevated to an "expert context engineer" to emphasize its role in managing and optimizing the information flow for superior performance.
Dynamic Context Assembly: A new mechanism for creating task-specific context files (.ai_workspace/TASK[ID].md) has been introduced. This directs the AI to assemble a minimal, focused context for each task, improving efficiency and reducing the risk of context-window limitations.
Explicit Tool Integration: The prompt now explicitly references the use of Model-Context-Prompt (MCP) tools (e.g., context7) for injecting external information, making the process more concrete.
Enhanced Collaborative Interaction (CollabLLM Framework): Principle P5 ("Be a Thinking Partner") has been significantly updated to include proactive and collaborative dialogue patterns:
Proactive Clarification: The AI is now instructed to ask clarifying questions to uncover hidden assumptions, even when a request seems clear.
Hypothesis-Driven Development: For complex design tasks, the AI is encouraged to propose several high-level options and seek user validation before proceeding with a detailed plan.


v9.0
Workspace Redesign (Task-Centric): The .ai_workspace is now fully task-centric. Global files like CHANGELOG.md, TASK_BREAKDOWN.md, and SCRATCHPAD.md have been removed in favor of task-specific files (TASK_[UniqueID]_Knowledge_base.md, TASK_[UniqueID]_TODO.md, TASK_[UniqueID]_notepad.md).
Unified Project Context: PROJECT_BRIEF.md and PROJECT_KNOWLEDGE_BASE.md have been merged into a single, comprehensive file: PROJECT_BLUEPRINT.md.
Permission-Based Writes: The AI's interaction with PROJECT_BLUEPRINT.md is now strictly controlled. It is read-only by default, and the AI must ask for explicit user permission before writing any updates (such as new ADRs or generalizable learnings).
Standardized Task ID: A clear UniqueID format (YYYYMMDDNNNN) has been established as the core of the new task-based file system.


v9.1
NEW: Core Reference Cheatsheet: Added a new, scannable reference section at the top of the prompt. It summarizes key operational details like workspace file structure, response templates, and artifact delimiters in a non-table format for easier parsing.
CONSISTENCY: Standardized PROJECT_KNOWLEDGE.md Naming: All internal references to the project knowledge file (formerly KNOWLEDGE.md) have been updated to the fully qualified name .ai_workspace/PROJECT_KNOWLEDGE.md to eliminate ambiguity.
CLARIFICATION: Defined Model-Context-Prompt (MCP): Added a concise definition for the "Model-Context-Prompt (MCP)" within principle P7, explaining it as an open standard for connecting AI models to external tools and data. This resolves the previously undefined term.
REFACTOR: Consolidated Uncertainty Instructions: Removed redundant text about handling uncertainty from the beginning of Section A (Software Architecture). Replaced it with a single, clear directive pointing to P7 as the single source of truth for this process, making the prompt more concise and robust.
v9.2
Clarified Abstract Concepts with Examples: Added concrete, illustrative examples for complex mental models like Hyrum's Law (unintended dependencies on API behavior) and the Cynefin Framework (problem classification) to make their application more practical and less ambiguous.
Added RAG vs. MCP Decision Heuristic: Introduced a new heuristic in principle P7 to provide clear guidance on when to use a simple Retrieval-Augmented Generation (RAG) search versus proposing a more structured and reusable Model-Context-Prompt (MCP) integration for interacting with external tools and data.
Introduced a Mental Model Application Guide: To improve consistency and focus, a new guide has been added to principle P3. It maps common software development tasks (e.g., Code Review, Greenfield Design) to a prioritized list of primary and secondary mental models, serving as a clear starting point for analysis.
Refined Dynamic Cognitive Allocation: The P10 principle has been updated to replace the abstract concept of "semantic value" with a more concrete, rubric-based system for assigning "Analytical Depth" (Shallow, Moderate, Deep) to tasks based on their architectural impact, risk, and uncertainty.
v9.3
Introduced the <CORE_EXECUTION_FLOW>: Replaced implicit expectations with a mandatory, four-step algorithm (Triage, Grounding, Generation, Review) that the AI must follow for all non-trivial tasks. This is the most significant structural change, designed to enforce procedural discipline.
Formalized Triage with <MANDATORY_TRIAGE_PROTOCOL>: To combat the tendency to misclassify complex tasks as simple, a new protocol forces the AI to explicitly score a request against the P10 rubric and declare its chosen "Analytical Depth" before proceeding.
Upgraded Justification Standards with <RATIONALE_QUALITY_RUBRIC>: To prevent the superficial "name-dropping" of mental models, this new rubric enforces a higher standard for all rationales, requiring them to demonstrate specificity, causality, and trade-off awareness.
Systematized Self-Correction with <SELF_CORRECTION_PROTOCOL>: Replaced the prose-based "Internal Review Process" with a formal, mandatory checklist. This protocol forces the AI to perform consistency checks, persona-based critiques, and conflict resolution before delivering its final response, making self-correction a required action rather than a suggestion.
v9.4
Renamed Response Templates for LLM Clarity: To improve parsing and reduce ambiguity, the response templates have been renamed from "The Swift Response" and "The Blueprint Response" to the more systematic "Template Swift" and "Template Blueprint".
Redesigned "Template Blueprint" for Human-Centric Interaction: The complex response template has been completely redesigned to prioritize the user experience, based on the principle of Progressive Disclosure.
Prioritizes Actionable Summary: The response now leads with scannable Highlights and actionable Next Steps, allowing the user to immediately grasp the core outcome and what to do next.
Re-ordered Artifact Placement: The main deliverable (e.g., code or document) is now placed after the summary and next steps, following a natural user workflow of "understand, then review details."
Conceals Process Details: All internal process information (detailed analysis, rationale logs, triage data) is now neatly tucked away in a collapsible <details> block. This drastically reduces the initial wall of text and cognitive load, while still making the AI's rigorous process fully auditable for users who need to "View Detailed Analysis."
