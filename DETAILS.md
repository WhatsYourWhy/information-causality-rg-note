# Full details: Information Causality and Renormalisation

This document expands on the notes in the README by providing a more detailed, technical summary of the argument that information‑causality‑violating resources break conventional renormalisation group (RG) flows. It includes definitions, a formal theorem, and a sketch of the proof with corrections applied.

## Background

Renormalisation group flows describe how a physical theory changes under coarse‑graining – combining small regions into blocks and discarding microscopic details. RG relies on three key expectations:
- **Locality**: interactions remain local under coarse‑graining.
- **Finite dimensionality**: only a finite set of coupling constants (“relevant parameters”) needs to be tracked.
- **Faithfulness**: coarse‑grained variables reproduce all operational predictions of the microscopic theory.

Information causality (IC) is a principle from information theory: sending `m` classical bits should not unlock more than `m` bits of useful information about a remote system. Quantum mechanics honours this: entanglement alone does not let you transmit more information than the bits you communicate. In our universe, IC appears to hold.

A hypothetical non‑local resource (such as a Popescu–Rohrlich box) violates IC. It allows two parties to use one bit of classical communication to recover any one of `N` remote bits with certainty. We call this the “fire‑hose” effect: a narrow interface can deliver an arbitrarily large amount of information.

## Definitions

* **Localizable channel**: A channel implementable by a fixed‑depth circuit of local gates (or, equivalently, by evolving for a bounded time under a finite‑range Hamiltonian). Localizable channels have a finite causal radius – they cannot make one region depend on degrees of freedom outside a bounded neighbourhood.

* **RG transformation**: A physical coarse‑graining map from microscopic degrees of freedom (spacing `a`) to coarse degrees of freedom (spacing `b a`). It is a completely positive trace‑preserving (CPTP) map (classical/GPT: stochastic map) and is translation invariant.

* **Operational faithfulness**: The RG map must preserve all operational predictions of the microscopic theory. If the microscopic theory allows an agent to perform a protocol, the coarse theory must allow the same protocol (possibly with different variables) with the same success probability.

* **IC‑violating resource**: A bipartite, non‑signalling resource that violates the information‑causality bound. A Popescu–Rohrlich (PR) box is the standard example. The resource is assumed to be available between any pair of sites and is part of the microscopic theory’s operational content.

* **Finite‑dimensional relevance**: After each RG step, the effective theory should be describable by finitely many coupling constants with local or rapidly decaying interactions. The number of couplings should not grow with system size or RG depth.

## Theorem (RG impossibility with IC violation)

**Assumptions**:

1. **Finite‑range dynamics**: The microscopic theory has finite‑range interactions; hence time evolution obeys a Lieb–Robinson bound with finite velocity `v_{\mathrm{LR}}`.  
2. **Bounded local capacity**: Each site has finite state dimension `d_{\mathrm{loc}}`; thus it can store at most \(\log d_{\mathrm{loc}}\) bits of information.  
3. **Ubiquitous IC‑violating resource**: A PR‑box (or any IC‑violating non‑signalling resource) is available between any two sites, and its use is part of the operational content of the theory.  

**RG desiderata**:

A renormalisation‑group map `R` is said to be **conventional** if it satisfies:

- **Locality**: `R` is localizable with depth independent of the lattice size.  
- **Physicality**: `R` is CPTP (or stochastic) and translation invariant.  
- **Finite‑dimensional relevance**: Repeated application of `R` yields effective theories with a finite number of relevant couplings.  
- **Faithfulness**: `R` reproduces all operational predictions of the microscopic theory, including protocols that use the IC‑violating resource.

**Conclusion**:

> **No conventional RG transformation exists under these assumptions.** In other words, if a theory contains an information‑causality‑violating resource, one must abandon locality, finite‑dimensional relevance, or faithfulness. The RG flow cannot remain within a finite set of couplings or within a local channel.

## Proof sketch

The proof has three ingredients:

1. **Boundary‑shell information bound**. A localizable channel of fixed depth `D` can only make a block’s coarse variable \(\Sigma_B\) depend on microscopic degrees of freedom within a boundary shell of thickness \(R_* = D k\). With bounded on‑site dimension `d_{\mathrm{loc}}`, the amount of classical information that can enter the block through this shell is at most \(O(|\partial B|\, \log d_{\mathrm{loc}})\), i.e., it scales like the surface area of the block. This is a consequence of Lieb–Robinson‑type causal cones, not of spectral gaps or equilibrium.

2. **Fire‑hose protocol**. With a PR‑box and one classical bit, one can implement a random‑access code: a block of `b^d` sites encodes `N = \Theta(L^d)` remote bits by feeding each bit into a PR‑box shared with a distinct remote site. Sending the parity of those bits across the boundary allows the remote region to recover any chosen bit. The operational information accessible to the block’s complement scales with the volume \(L^d\), despite only one bit crossing the boundary. The PR resource thus amplifies information across a local interface.

3. **Contradiction by faithfulness**. If the RG map is faithful, the coarse theory must still permit the fire‑hose protocol at the coarse scale. But the boundary‑shell bound forbids a fixed‑depth local channel from injecting \(\Theta(L^d)\) bits into \(\Sigma_B\) across a boundary of size \(\Theta(b^{d-1})\). To encode the fire‑hose dependence, the RG step would need unbounded depth (violating locality), or it must introduce couplings with support that grows without bound (violating finite‑dimensional relevance), or it must discard the PR‑boxes altogether (violating faithfulness). Thus no conventional RG flow exists.

## Remarks

- This argument does **not** assume a spectral gap or equilibrium, and does **not** rely on the entanglement area law. It uses only causal locality and finite information capacity per site.

- Replacing the mutual‑information claim with an **operational random‑access claim** avoids overstating raw mutual information. The fire‑hose protocol ensures that the coarse block’s state can depend on an extensive number of remote bits operationally.

- A key correction is that the RG map must be **localizable** rather than just CPTP. Complete positivity alone does not limit information flow; only finite‑depth locality and bounded `d_{\mathrm{loc}}` do.

- This no‑go theorem applies equally to classical, quantum, or more general GPT systems, provided they admit an IC‑violating resource as part of their operational content.

## Conclusion

Information‑causality‑violating resources are incompatible with conventional renormalisation group flows. The fire‑hose effect shows that a small boundary can unlock extensive remote information, contradicting the assumption that coarse‑graining should reduce the description to a finite number of local couplings. To reconcile such resources with coarse‑graining, one must either allow non‑local RG steps, accept an ever‑growing parameter space, or drop faithfulness by discarding the resource. Thus information causality emerges as a necessary consistency condition for the existence of a local, finite‑parameter RG description.
