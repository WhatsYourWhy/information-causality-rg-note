# information-causality-rg-note


**Status:** This conceptual note is shared for discussion. No claims of physical realization are made. Discussion, feedback, and engagement are welcomed—feel free to open issues or start a discussion.

This document collects notes on how information causality and renormalisation work and why they may be incompatible when information-causality is violated.


## The intuitive idea

Renormalisation group (RG) flows are the theoretical machinery physicists use to “zoom out.” They allow us to describe large-scale phenomena (like temperature, magnetism, or fluid flow) without remembering every microscopic detail. Under RG, local interactions remain local and a small set of parameters (“couplings”) control behaviour at large scales.

Information causality (IC) is a principle from information theory which says that sending *m* classical bits cannot unlock more than *m* bits of useful information. Even with entanglement or other non-local correlations, you don’t get something for nothing. In our universe this principle appears to hold: sending one bit cannot magically reveal the contents of a gigabyte.

## The fire-hose thought experiment

Imagine a hypothetical resource that violates IC – like the so-called PR-box from quantum information. This resource allows two distant parties to share nonlocal correlations in such a way that *one* classical bit of communication lets them recover any one of *N* remote bits with certainty. In everyday terms, the “pipe” carrying one bit suddenly behaves like a “fire‑hose” spraying a torrent of information.

If such a resource were part of a lattice theory at the microscopic level, it would create blocks of sites whose state depends on an extensive amount of information from far away. When you try to coarse‑grain (combine sites into blocks) and discard irrelevant details, the information unlocked by the IC-violating resource does not go away – it ties the block to distant bits. This means a single RG step must either:

- Communicate a huge amount of information across the boundary of the block (violating locality),
- Or keep track of an ever-growing set of non-local couplings (violating closure on a finite number of parameters),
- Or simply discard the resource (violating faithfulness to the original theory).

In other words, an IC-violating resource makes it impossible to run a conventional renormalisation procedure that remains local and finite-dimensional.

## Why it matters

The argument sketched here does *not* claim that our universe contains PR-boxes or that real physics fails. Instead, it shows that *if* you allow information to cheat beyond the usual limits, you also give up the ability to describe the system with the same RG machinery that underpins much of condensed matter and quantum field theory. The deep connection between information flow and the scalability of physical theories suggests that principles like information causality may be necessary for our conventional notions of “effective theories” to make sense.







Information Causality vs. Conventional RG (Why “Fire-Hose” Resources Break Local Coarse-Graining)

Renormalisation group (RG) coarse-graining is useful because it typically preserves three expectations: (1) locality (coarse variables depend only on nearby microscopic data), (2) finite-parameter closure (a bounded number of local couplings describes the effective theory at each scale), and (3) operational faithfulness (the coarse theory can reproduce the operational predictions of the microscopic theory for the allowed protocols).

Information causality (IC) is an information-theoretic constraint: if Alice sends Bob 
𝑚
m classical bits, Bob should not be able to obtain more than 
𝑚
m bits of useful information about Alice’s remote data. Quantum theory respects IC; entanglement does not let a small classical message unlock an unbounded amount of addressable remote information.

A hypothetical non-signalling resource such as a Popescu–Rohrlich (PR) box violates IC. In particular, PR correlations enable perfect random-access coding: with shared PR resources and only one classical bit from Alice to Bob, Bob can recover any chosen one of 
𝑁
N bits held by Alice, for arbitrarily large 
𝑁
N. This remains non-signalling (it doesn’t transmit all 
𝑁
N bits), but it creates a fire-hose effect: a constant-size interface unlocks an unbounded addressable dataset.

Now consider a “conventional” RG step 
𝑅
R implemented as a fixed-depth local circuit (or bounded-time finite-range evolution), with finite on-site state dimension 
𝑑
loc
d
loc
	​

. Such a map has a bounded causal radius: the coarse variable for a block 
𝐵
B can only depend on microscopic degrees of freedom within a constant-thickness neighborhood (a “shell”) around 
𝐵
B. Because the shell contains only 
∣
𝑆
∣
∣S∣ sites and each site has finite capacity 
log
⁡
𝑑
loc
logd
loc
	​

, the number of independent classical bits about the exterior that can be made recoverable from the coarse variable through that shell is bounded by 
𝑂
(
∣
𝑆
∣
log
⁡
𝑑
loc
)
O(∣S∣logd
loc
	​

) (a counting/encoding bound).

This conflicts with IC-violating fire-hose resources. Operational faithfulness would require the coarse theory to still permit the random-access behavior at larger scales, meaning a block-scale variable would need to support addressable dependence on 
Θ
(
∣
𝐵
∣
)
Θ(∣B∣) bits (volume scaling). But any fixed-depth local RG step can only mediate 
𝑂
(
∣
∂
𝐵
∣
)
O(∣∂B∣) bits’ worth of recoverable dependence (area-type scaling) through its bounded shell. For sufficiently large blocks, volume-scaling addressability contradicts bounded-shell locality.

Therefore, a theory containing an IC-violating resource cannot admit an RG flow that simultaneously preserves:

Locality of the RG step (fixed-depth / bounded causal radius),

Finite-parameter closure (no proliferating nonlocal couplings),

Operational faithfulness (do not discard the resource’s protocol power).

At least one must fail: either RG becomes nonlocal / growing-depth, or the effective description requires an ever-growing parameter space, or faithfulness is broken by discarding the IC-violating resource. In this sense, information causality acts as a consistency condition for the existence of a local, finite-parameter RG description.
