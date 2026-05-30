# OPENCLAW MULTI-AGENT ORCHESTRATION SPEC (FINAL v2)

**1. MODEL SOURCE RULE (MANDATORY)**

ALL models MUST be referenced via OpenRouter format:

provider/model-name

No exceptions.

**2. MODEL REGISTRY (FINAL CORRECT SET)**
🟦 GENERAL / ORCHESTRATOR
- openrouter/openai/gpt-oss-120b:free
- openrouter/openai/gpt-oss-120b:free
- openrouter/nvidia/nemotron-3-super-120b-a12b:free

🟥 CODING AGENT (IMPORTANT FIXED ORDER)
- Primary (best reasoning): deepseek/deepseek-v3.2-speciale
- Fallback 1 (best coding specialist - FREE): qwen/qwen3-coder-480b-a35b-instruct:free
- Fallback 2 (paid version = higher reliability, SAME model family): qwen/qwen3-coder-480b-a35b-instruct

🟩 STUDY / RESEARCH AGENT
- deepseek/deepseek-v3.2-speciale
- deepseek/deepseek-v3.2
- nvidia/nemotron-3-super-120b-a12b:free

🟨 GENERAL AGENT
- Uses orchestrator stack only:
  - openai/gpt-oss-120b:free
  - openai/gpt-oss-120b:free
  - nvidia/nemotron-3-super-120b-a12b:free

**3. ROUTING SYSTEM (IMPROVED + SAFE)**
❗️ PRINCIPLE
Routing must be based on the overall intent and structural cues of the request, not merely on the presence of isolated keywords. Classification should analyse the purpose, context, and format of the user’s query, using deeper semantic understanding rather than simple keyword matching.

🟥 CODING INTENT
Requests whose primary purpose is software development, debugging, code manipulation, or system architecture. Typical signals include code snippets, references to programming languages, repository operations, or detailed technical descriptions. The classification should consider the overall goal (e.g., building, fixing, or improving code) rather than just keyword presence.

🟩 STUDY / RESEARCH INTENT
Requests whose primary purpose is academic learning, explanations, essays, document summarization, or exam preparation. Typical signals include:
- Academic explanations requested
- Essays, writing, or structured reports
- PDFs or document summarization
- School/college exam preparation (SAT, etc.)
- Concept teaching ("explain how X works")
- Scientific or theoretical comparisons
- General learning requests
Classification should focus on the educational intent rather than keyword presence.

🟨 GENERAL INTENT
Answer if:
- Business ideas
- Casual questions
- Advice
- Productivity or life planning
- Unclear or mixed intent
- Non-technical, non-academic questions

**Non‑specialized Task Routing**
Tasks that do not satisfy the Coding or Study intent criteria are automatically routed to the General Agent, which uses the orchestrator model stack for fast, efficient handling of everyday queries.

**3.1 AMBIGUITY RULE (CRITICAL)**
If classification is unclear:
Priority:
- If ANY technical/system element → CODING
- If ANY educational element → STUDY
- Otherwise → GENERAL
If still uncertain → default to GENERAL (safest fallback)

**4. CODING AGENT BEHAVIOR (IMPORTANT)**
1. **TASK CLASSIFICATION**
   - SIMPLE TASK: small scripts, syntax fixes, basic functions
   - DEBUG TASK: fixing errors, runtime issues, broken logic
   - COMPLEX TASK: system design, multi‑step logic, algorithms
   - REPOSITORY TASK: multi‑file projects, GitHub workflows, cloning, large codebases
2. **EXECUTION STRATEGY**
   - Analyze the full context before writing code
   - Identify dependencies and hidden constraints
   - Break the problem into steps before solving
   - Avoid rushing to output code immediately
3. **OUTPUT QUALITY REQUIREMENTS**
   - Provide complete, runnable code with all required imports and dependencies
   - No placeholders or TODOs; fully fleshed sections
   - Ensure consistent end‑to‑end logic
   - Handle relevant edge cases
   - Maintain clean, readable structure
4. **DEBUGGING RULE**
   - Explain the root cause clearly
   - Propose the fix
   - Provide corrected code
   - Verify logic mentally before output
5. **REPOSITORY HANDLING RULE**
   - Map project structure first
   - Identify file relationships
   - Avoid editing isolated files without context
   - Ensure changes are consistent across the system
6. **COMPLEXITY ADAPTATION RULE**
   - SIMPLE → fast, minimal explanation
   - DEBUG → detailed reasoning
   - COMPLEX → step‑by‑step breakdown
   - REPO → architecture‑first thinking
7. **ERROR PREVENTION RULE**
   - Mentally simulate execution
   - Check for missing variables or imports
   - Verify logic consistency
   - Ensure no broken references exist
8. **FAILURE HANDLING RULE**
   - Re‑evaluate problem if solution uncertain
   - Restructure approach if needed
   - Do NOT output low‑confidence code
   - Prefer correctness over speed
9. **FINAL BEHAVIOR GUARANTEE**
   - Ensure correctness, completeness, execution safety, and clarity
   - Never guess without reasoning, output partial solutions, or ignore edge cases

**5. STUDY AGENT BEHAVIOR**
structured output:
- simple explanation
- deeper explanation
- summary
prioritize clarity over complexity
for PDFs → extract + summarize + organize

**6. GENERAL AGENT BEHAVIOR**
- Stay concise; keep responses short and to the point.
- Avoid over‑explaining; give only what’s needed for the user.
- Do not adopt coding‑agent or study‑agent styles unless the request explicitly requires technical or academic depth.
- Provide practical answers without unnecessary structure.

**7. FALLBACK SYSTEM (CRITICAL EXECUTION ORDER)**
Each agent MUST follow this exact deterministic fallback chain:
1. **Attempt primary model** – try once.
2. **Retry primary model** – if the first attempt fails (e.g., timeout, error), retry the same primary model once before moving on.
3. **First fallback** – if both primary attempts fail, switch to the FIRST fallback model and try once.
4. **Retry first fallback** – if that attempt fails, retry the first fallback once.
5. **Second fallback** – if both attempts on the first fallback fail, switch to the SECOND fallback model and try once.
6. **Retry second fallback** – if that fails, retry the second fallback once.
7. **Failure handling** – if all attempts (primary ×2, fallback 1 ×2, fallback 2 ×2) fail, return a structured partial response with an error state.

This ensures a deterministic order (primary → first fallback → second fallback) with a single retry for each level and no skipping of fallback levels.

**9. SAFETY AGAINST WRONG ROUTING**
Before final routing, always enforce the following safety rule:
- If code exists in the request → route to **CODING AGENT**.
- If an academic explanation is present → route to **STUDY AGENT**.
- Otherwise → route to **GENERAL AGENT**.
This rule supersedes keyword‑only heuristics; always examine the content structure first.
Never rely on single keywords alone.

**10. FINAL SYSTEM BEHAVIOR**
🧠 Intelligent router (fast classification)
⚙️ Specialized execution agents
🔁 deterministic fallback chain
📦 OpenRouter‑only model execution layer
