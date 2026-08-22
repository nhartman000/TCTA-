# Orthogonal Gestalt Symmetry Identification (OGSI)

**Author:** Nicholas Hartman / American Milestone Inc.

## Purpose

**Orthogonal Gestalt Symmetry Identification (OGSI)** is the TCTA trajectory-family resolution operator. It acts on invariant structure extracted from an incomplete trajectory prefix and maps that structure to a candidate trajectory family.

The canonical sequence is:

\[
\tau_q\xrightarrow{\Gamma}G\xrightarrow{\Psi}\mathcal{T}_G
\]

where:

- \(\tau_q=\tau_{1:k}\) is an incomplete trajectory prefix,
- \(\Gamma\) extracts the invariant signature,
- \(G\) is the resulting signature representation,
- \(\Psi\) is OGSI,
- \(\mathcal{T}_G\) is the resolved trajectory family.

## Prefix-stability dependency

OGSI relies on the TCTA prefix-stability hypothesis:

\[
\exists k<n:\quad \Gamma(\tau_{1:k})=\Gamma(\tau)
\]

for the family/domain under evaluation.

This is **Hypothesis H1**, not a universal theorem. A family may require a longer prefix, may fail to stabilize under noise, or may not admit a useful invariant at all.

## Family separability dependency

For distinct trajectory families \(\mathcal{T}_i\) and \(\mathcal{T}_j\), the current formal core uses the bounded collision condition:

\[
\Pr\left[\Gamma(\mathcal{T}_i)=\Gamma(\mathcal{T}_j)\right]<\epsilon
\]

This is **Assumption H2 / an empirical separability requirement**. When \(\epsilon>0\), OGSI resolution is bounded-risk rather than logically infallible.

## Effect on admissible continuation

Before OGSI resolution, continuation operates over the admissible trajectory space:

\[
\Omega(\mathcal{C})
\]

After a family is resolved, continuation can be restricted to:

\[
\mathcal{T}_G\subseteq\Omega(\mathcal{C})
\]

or to the transform set associated with that family.

Conceptually:

```text
admissible transforms before OGSI
T1 T2 T3 T4 T5 T6
          ↓
prefix invariant Γ
          ↓
OGSI Ψ
          ↓
resolved family
          ↓
remaining transforms
T1 T4
```

The eliminated transforms are those incompatible with the resolved family under the current model and error assumptions.

## Branch preservation

OGSI is not required to collapse every prefix to a single next transform. A resolved family may still contain multiple admissible continuations:

```text
T_G
├── T_a
├── T_b
└── T_c
```

Additional observations or constraints may be required before the branch resolves further.

## Quantities to measure

A serious OGSI evaluation should report at minimum:

- full trajectory length \(n\),
- critical prefix length \(k\),
- prefix ratio \(k/n\),
- family classification accuracy \(\Psi_{acc}\),
- collision/separability error \(\epsilon\),
- candidate count before and after family resolution,
- false-negative pruning rate,
- ground-truth trajectory retention.

## Scope

This document specifies the role and formal dependencies of OGSI. It does not claim that a universal invariant operator \(\Gamma\) or universally separable trajectory-family partition has already been established across all domains.
