# information-causality-rg-note

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
