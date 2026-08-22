# TCTA Evaluation Framework

**Author:** Nicholas Hartman / American Milestone Inc.

## Objective

The TCTA evaluation framework is designed to test the falsifiable core of the architecture: whether trajectory prefixes contain stable, discriminative structure that permits early family resolution and therefore safe reduction of the future transform space.

The primary evaluation tuple is:

\[
\left(k,\epsilon,\Psi_{acc},R,FNR_{prune}\right)
\]

## 1. Critical prefix length

Let a complete trajectory be:

\[
\tau=[T_1,\ldots,T_n]
\]

and a proper prefix:

\[
\tau_{1:k},\qquad k<n
\]

The **critical prefix length** is the earliest \(k\) at which the selected invariant criterion remains stable enough to support family resolution under the evaluation conditions.

Report both:

\[
k
\]

and:

\[
\frac{k}{n}
\]

The supplied Volume 1 identifies a target significance criterion of \(p<0.001\). This must be treated as a target until sufficient data exists to establish it empirically.

## 2. Separability bound

For distinct trajectory families:

\[
\Pr\left[\Gamma(\mathcal{T}_i)=\Gamma(\mathcal{T}_j)\right]<\epsilon
\]

Estimate or bound \(\epsilon\) under the tested noise/domain conditions. Do not report \(\epsilon=0\) unless the experiment actually justifies that result.

## 3. OGSI classification accuracy

Measure:

\[
\Psi_{acc}
\]

as the fraction of evaluated prefixes mapped to the correct trajectory family.

Report confusion between specific families where possible rather than only aggregate accuracy.

## 4. Search reduction factor

Let \(\mathcal{S}(X)\) be the chosen search/effort measure for domain \(X\).

Define:

\[
R=
\frac{\mathcal{S}(\Omega(\mathcal{C}))}
{\mathcal{S}(\mathcal{T}_G)}
\]

The implementation must state what \(\mathcal{S}\) actually measures, for example:

- candidate transform count,
- expanded nodes,
- evaluated trajectory continuations,
- wall-clock computation,
- operations executed,
- another explicitly defined cost quantity.

Do not compare incompatible cost definitions.

## 5. False-negative pruning rate

A critical correctness metric is the rate at which valid continuations are incorrectly removed during constraint/family pruning.

Report:

\[
FNR_{prune}=
\frac{\text{valid ground-truth continuations incorrectly pruned}}
{\text{valid ground-truth continuations evaluated}}
\]

A lower search cost is not useful if the mechanism frequently removes the valid path.

## 6. Ground-truth retention

For each evaluation trajectory, record whether the known valid continuation remains inside the reduced admissible space after pruning.

This should be reported explicitly as a count/rate rather than inferred from classification accuracy.

## 7. Minimum per-run record

Each evaluation record should include:

```text
trajectory_id
trajectory_family
trajectory_length_n
critical_prefix_k
prefix_ratio_k_over_n
signature
predicted_family
correct_family
candidate_count_global_or_preconstraint
candidate_count_after_constraints
candidate_count_after_OGSI
search_cost_before
search_cost_after
search_reduction_R
collision_observed
false_negative_pruned
known_valid_continuation_retained
noise_condition
domain_condition
```

## 8. Synthetic versus empirical data

If synthetic fixtures are used, label them explicitly:

```text
SYNTHETIC VALIDATION FIXTURE
NOT EMPIRICAL REAL-WORLD VALIDATION
```

Synthetic fixtures are useful for verifying implementation mechanics such as branch preservation, prefix recognition, and pruning bookkeeping. They do not independently establish real-world validity of H1 or H2.

## 9. Required benchmark cases

At minimum, an executable evaluation should contain:

### A. Constraint filtering

Start with a known candidate set, apply domain/constraint filtering, and verify expected survivors.

### B. Prefix family resolution

Construct at least two trajectory families with known discriminative prefix structure. Determine the earliest successful \(k<n\).

### C. Branch preservation

Construct a prefix where more than one continuation is valid and verify that the reduction stage preserves all valid branches.

### D. Collision/noise case

Introduce a condition in which signatures become less separable and measure the resulting classification/pruning error rather than hiding it.

## 10. Acceptance discipline

The evaluation harness must never convert a successful synthetic test into a universal theorem. Results should be reported as measurements tied to:

- dataset/fixture,
- invariant implementation,
- family partition,
- domain constraints,
- noise regime,
- cost definition.
