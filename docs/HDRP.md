# Hartman Dual-Register Predictor (HDRP)

**Author:** Nicholas Hartman / American Milestone Inc.

## Purpose

The **Hartman Dual-Register Predictor (HDRP)** is the localized predictive layer used downstream of TCTA trajectory-family resolution. It implements the retained-state “extra digit” mechanism through two explicit registers:

- present state register: \(R_0\)
- previous state register: \(R_{-1}\)

HDRP is not the entirety of TCTA and is not a global planner. It performs short-horizon continuation inside a trajectory family already constrained by TCTA/OGSI.

## Dual-register state

At time \(t\), retain both:

\[
R_0
\]

and

\[
R_{-1}
\]

The localized trajectory delta is:

\[
\mathbf{T}_t=R_0-R_{-1}
\]

## Forward projection

The canonical bounded projection is:

\[
\mathbf{O}_t=\tanh\left(R_0+g_t\alpha\mathbf{T}_t\right)
\]

where:

- \(\alpha\) is the momentum coefficient,
- \(g_t\) is the adaptive gate,
- \(\mathbf{O}_t\) is the predicted successor state.

## Error

Given observed successor state \(\mathbf{I}_{t+1}\), instantaneous tracking error is:

\[
E_t=\left\|\mathbf{O}_t-\mathbf{I}_{t+1}\right\|_2
\]

with error delta:

\[
\Delta E_t=E_t-E_{t-1}
\]

## Gate adaptation

The supplied HDRP gate dynamics are:

\[
\Delta g_t=-\eta\Delta E_t\operatorname{sgn}\left(\mathbf{T}_t\cdot\mathbf{O}_t\right)
\]

and:

\[
g_{t+1}=\Pi_{[0,1]}\left(g_t\lambda_{\mathrm{rec}}+\Delta g_t\right)
\]

where:

- \(\eta\): gate update rate,
- \(\lambda_{\mathrm{rec}}\): recovery coefficient,
- \(\Pi_{[0,1]}\): projection into the stable gate interval.

## Relationship to TCTA

The canonical hierarchy is:

\[
\Omega(\mathcal{C})
\rightarrow
\tau_q
\xrightarrow{\Gamma}
G
\xrightarrow{\Psi}
\mathcal{T}_G
\xrightarrow{\Phi}
\text{localized continuation}
\]

with \(\Phi\) denoting HDRP.

The distinction matters:

1. TCTA bounds the admissible trajectory space.
2. \(\Gamma\) extracts trajectory-prefix invariant structure.
3. OGSI \(\Psi\) resolves the trajectory family \(\mathcal{T}_G\).
4. HDRP predicts only inside that reduced family.

## Implementation status discipline

This document specifies the current canonical equations. If executable code in this repository differs from them, the discrepancy must be reported explicitly rather than silently changing either the specification or implementation.
