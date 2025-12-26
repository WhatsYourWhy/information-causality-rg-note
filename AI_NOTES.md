# Information Causality, Scale Separation, and Why Some AI Coordination Claims Fail to Close

## Why this note exists

This document is an interpretive bridge between the renormalisation group (RG) insight about information‑causality (IC) and the world of artificial intelligence and multi‑agent coordination. It does **not** assert that current AI systems violate IC, nor that quantum PR‑boxes lurk inside neural networks. Instead, it uses the RG–IC result as a lens for reasoning about scalability, bounded interfaces and stable abstractions in AI. If the analogy is helpful, use it; if not, ignore it.

## Translating the physics language

- **Locality** – In physics: finite‑range interactions and finite propagation speed.  
  In AI: bounded interfaces, bandwidth limits, permissions, budgets and rate‑limited APIs.

- **Renormalisation‑group (RG) coarse‑graining** – In physics: integrating out microscopic degrees of freedom and describing behaviour with a small set of couplings.  
  In AI: building high‑level evaluations, metrics and policies that summarise behaviour with a finite set of parameters.

- **Information causality** – In physics: sending `m` classical bits cannot unlock more than `m` independent bits.  
  In AI: you cannot extract unbounded global knowledge or control from a bounded interface.

- **PR‑box / fire‑hose resource** – In physics: a non‑signalling correlation that lets one bit of communication reveal any of `N` remote bits.  
  In AI terms: a “magic unlock” or jailbreak that turns a single prompt or instruction into reliable, unbounded global access or control.

## The core structural claim (AI version)

> **Any AI system that appears to let bounded interface actions reliably unlock unbounded global information or control must be hiding either:**
>
> – non‑local coupling (shared secret channels, hidden state);  
> – unbounded internal complexity (infinitely many couplings / exceptions); or  
> – failure of stable coarse‑grained description (evaluations that don’t close).

This is an analogy, not a theorem about AI. It says that claims of “tiny prompt → unlimited, stable capability” are structurally suspect.

## Prompting, jailbreaks and “magic unlock” narratives

Jailbreaks and prompt injections show that large models can be coaxed into behaviours outside the intended eval domain. That does **not** mean a single prompt unlocks everything; it means there are **unmodelled couplings**. Real systems show brittle, domain‑specific failure, not true “fire‑hose” amplification. A universal “one‑bit key” that reliably reveals all secrets would imply hidden nonlocality or exploding complexity.

## Alignment and “small rule fixes everything”

Efforts to align AI often look for simple patches: one constitutional rule to ensure honesty, one reward tweak to ensure safe behaviour. The RG–IC lens says: if alignment were truly achieved by a single knob that scales across domains, the complexity hasn’t disappeared – it’s hidden elsewhere. Scalable alignment requires scalable structure (datasets, oversight, infrastructure) rather than purely local patches.

## Tool‑using agents and real fire‑hose analogues

The closest practical analogue to a fire‑hose is an agent with access to external tools. A small prompt can trigger chain‑of‑thought planning, web search, API calls and data exfiltration. The “pipe” (agent interface) is small, but the tool graph is huge. Security practices like least privilege, compartmentalisation and auditing are how we prevent bounded prompts from unlocking unbounded damage. This shows the value of thinking about information flow through boundaries.

## What this does not claim

- It does **not** assert that AI systems violate information causality.  
- It does **not** prove alignment impossible or markets unstable.  
- It does **not** imply that quantum non‑locality exists in AI.  
- It does **not** predict financial value.

This is a structural analogy to discipline reasoning, not a doom claim or a revenue model.

## Why this lens is still useful

Even without being literal physics, the RG–IC analogy offers a way to test narratives. When a proposal promises scalable coordination or capability with almost no communication or complexity, the question becomes: **Where does the information live? Through which channels does it flow? What grows with scale?** If the answer is “nowhere,” the claim may be glossing over hidden channels or unbounded couplings. This lens encourages careful thinking about evaluation closure, safety boundaries, and the limits of shortcut coordination in AI.

---

*Feel free to open an issue or start a discussion if you have thoughts, objections or alternative mappings. The hope is that this note provides a useful conceptual tool, not a dogma.*          
