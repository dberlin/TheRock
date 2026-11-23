# ROCm / TheRock SBOM state

## Current result: generated, not version-complete

The latest normal cdxgen CLI scan completed in **22m42s (1362.394 seconds), exit 0**. It saved a **4,308,748,626-byte BOM** and logged successful JavaScript schema validation. **319 software components still lack versions**, plus two data records. The reusable-tool acceptance criteria and nine-minute runtime target are **not met**.

No scan is running. Changes remain in `/home/dannyb/sources/cdxgen-worktrees/remaining-381-integrated`; the requested `/home/dannyb/sources/cdxgen` checkout has **not been promoted**. The successfully scanned frozen tool is `/home/dannyb/sources/therock-sbom/native-closure-three-hour/local-final-output-tool`.

This was a local Bun invocation against the read-only source snapshot, with out-of-tree outputs and six warm provider manifests/caches. It did not consume the classification register or a hand-corrected BOM. **Cold automatic acquisition across every provider family is not established.**

### Actual saved version fields

| Measure                                                   | Count |
| --------------------------------------------------------- | ----: |
| Top-level components                                      | 6,277 |
| Top-level components with a version                       | 5,956 |
| Software components without a version                     |   319 |
| Data records without a version                            |     2 |
| Total top-level records without a version                 |   321 |
| Nested file records without a version, tracked separately | 1,726 |

Recursive software accounting also finds319 missing versions. File inventory records are not software release gaps. Version presence alone does not prove correct ownership or selected-build compatibility.

Graph accounting found **zero duplicate declared refs, dangling dependency refs or dangling candidate refs** across25,903 declared refs. That is structural integrity, not complete dependency/version correctness.

## Why the count changed from210 to319

**319 =115 retained old unversioned refs +204 new unversioned refs.** The204 comprise186 `find_program` tools and18 non-tool identities. The prior completed BOM had zero `find_program` requirement properties; its omission of these dependencies made its lower count misleading as a coverage comparison.

The18 other identities come from previously represented callsites:13 `find_library`, four `find_package`, one external project. Some expose evaluated names; some no longer carry earlier candidate evidence. This is not uniformly improved coverage, and the detailed audit preserves those regressions/uncertainties.

All95 old refs that left the missing-version set disappeared as exact refs. **That is not95 fixes.** The strict previous210 helper reports29 fully-versioned-evidenced,22 partially-versioned-evidenced,115 still-unversioned and44 without demonstrated lineage under its comparison. A subsequent declaration-anchor audit finds additional candidate links in those latter groups, but changed predicates/alternatives prevent an unconditional closure count.

For the original476, **90 exact original refs remain and all90 are unversioned;386 no longer appear verbatim**. Original evidence is mostly filename/manifest/license-level rather than declaration-level. We do **not** have a defensible claim that386 were fixed. See the [transition audit](../therock-sbom/native-closure-three-hour/local-streamed-current-count/failure-analysis/transition-audit.md).

## Fixes implemented and exercised in this phase

- **Wrong nested project versions:** scoped CLI `--project-version` fallback to the scan root. Real LLVM parsing previously inherited TheRock's revision despite recording its independent LLVM revision. The corrected path removes that false fallback while preserving its own conditional version evidence. Failing-before/passing-after parser regression and real LLVM parser smoke were exercised. The704 affected captured input facts are not704 proven BOM fixes.
- **Quadratic provider authentication:** collection-local exact-serialization membership sets replace repeated pairwise export comparison without weakening authentication. A real4,291-export case improved11.839s to0.392s with identical complete graph SHA256. Focused tests and scoped review completed.
- **Output crash:** the preceding full generation reached validation but crashed on one giant `JSON.stringify`. Bounded JSON serialization now writes unsigned CLI file/stdout output without constructing a multi-gigabyte string. A2.15GB serializer smoke, real Bun CLI file/stdout runs, exact-path Node permission/mode checks and focused serializer/filesystem/CLI suites were exercised. The current4.31GB normal output is the end-to-end proof. Signed-output handling retains its existing route; giant signed output is not claimed supported.
- **Earlier exact-input reuse:** source-context and whole-owner reuse remain integrated. Two alternative environment representations regressed actual workloads and were reverted; they are not claimed improvements.

These fixes restore output generation and correct concrete defects. They do not resolve the319 remaining software gaps.

## Performance and output-size findings

The successful scan logged1,170.2s scanning/generation,160.2s postprocessing and12.4s validation. Its main native-provider collection consumed610.054s. Nine-minute performance from the older, narrower result does not establish performance for this coverage.

Saved profiles identify evaluator Map copying/branch bookkeeping; actual provider payload analysis also identifies severe duplication. The captured5,166 provider observations represent only528 distinct refs. Repeated evidence/export payloads and duplicated matching exports multiply again in requirement/canonical-occurrence properties. Final top-level requirement-property values total approximately2.04 billion characters. Streaming avoids the crash but does not fix that amplification.

The next performance work is exact descriptor interning, deduplicated export matches and lossless shared-evidence representation, followed by bounded real-workload profiling and measured evaluator improvements—not another speculative full scan or evidence truncation.

## Complete remaining-failure plan

All **319 current software refs are classified exactly once**, across41 mechanism families. Independent coverage checking found zero missing, extra, duplicate or incomplete rows. Both data records have separate repair contracts.

| External-information class                 | Current rows | Meaning                                                                             |
| ------------------------------------------ | -----------: | ----------------------------------------------------------------------------------- |
| No confirmed external input needed         |           79 | Local/source/cache evidence and generic tool corrections first; not79 already fixed |
| Public information acquired by the tool    |          239 | Public metadata/source/package research and acquisition, not user homework          |
| Demonstrated authorized-input prerequisite |            1 | simpenrose                                                                          |

The implementation order is:

1. **Separate known owner/version from unknown selection.** Preserve genuine versioned candidate owners despite HINTS, paths, ABI/platform or build uncertainty; retain unresolved predicates and all original occurrences.
1. **Index executable/script exports.** Add actual CMake executable/installed-program, wrapper, Cargo and script entry-point ownership. Fix literal `.exe`/platform aliases. This addresses the shared mechanism behind many of the186 new tool gaps.
1. **Automate missing public acquisition.** Derive executable package queries from discovered `find_program` alternatives; inspect authenticated package, wheel, source and SDK inventories. Prove empty-cache acquisition and offline warm reuse separately.
1. **Complete the133 library/helper contracts.** Scoped finders, generated configs, literal/static/platform material, coherent ABI/header/library/tool sets, exact source selectors, historical APIs and helper role corrections. Use bounded out-of-tree configure only where data-only evidence is insufficient.
1. **Canonicalize true same-release alternatives.** The current BOM still has two json@3.12.0 archive identities; numeric `v` normalization alone has not satisfied the user's deduplication request. Merge only authenticated same-upstream releases while retaining distinct material provenance. Handle data content revisions honestly.
1. **Remove measured payload/evaluator amplification**, then run the integrated acceptance gate. No package/version override table, manual BOM edits, suppressed requirements or invented versions.

Full plan: [failure-analysis/plan.md](../therock-sbom/native-closure-three-hour/local-streamed-current-count/failure-analysis/plan.md). It links the186-tool and133-library plans and the machine-readable319-row register. Each row names source evidence, remaining blocker, concrete tool files/APIs, acceptance and public-information URLs where applicable. The register is not a runtime input. This supersedes the old210-row repair plan.

### Information actually needed from the user

**Only simpenrose has a demonstrated restricted prerequisite.** Mesa's `docs/drivers/vc4.rst:298–303` documents NDA access. An authorized source/package or NDA-permitted immutable owner/export manifest must establish the genuine release/revision and `simpenrose.pc` ownership. Do not provide credentials or material you cannot share. All other work is independent.

`v3d_hw`, private-framework/legacy SDK and site profiler cases remain public-research-first. `hip_raw_trace` is an unidentified optional workload, not established private/NDA software. A missing local cache entry is not evidence the user must supply information. No ROCm repository edits are currently required by this repair plan.

The two data records are `machine-readable-isa` and `embed.tracy`; both already carry declared content hashes. The plan calls for automatic acquisition/hash validation and embedded/content revision metadata, not invented software releases or silent removal.

## Microsoft sbom-tool

**No new implementation or run during this phase.** Its last recorded generation completed in319.984s with3,568 packages and211 native identities. SHA256/SHA1 validation runs reported zero errors across779,054 files. However, unresolved/conflicting native projects were omitted, and the output had211 root-to-native attachments but zero native-to-native edges. Nonblank versions among emitted packages are therefore not coverage closure. Its original476 mapping was only29 name-level/unattributed overlaps and447 nonmatches—not29 fixes.

The requested AutoMapper upgrade to15.1.1 was previously made; its RPL1.5/commercial licensing remains unapproved for production use. Evidence: `~/sources/therock-ms-sbom-native/final2/resolution-report.json`.

## Reproduction and evidence

All current artifacts are under:
`~/sources/therock-sbom/native-closure-three-hour/local-streamed-current-count/`

- `config.json`: exact command/environment/cache configuration.
- `metrics.json`, `scan.log`, `phase-trace.ndjson`: exit, duration and phase evidence.
- `bom.json`: unchanged tool-generated deliverable,4,308,748,626 bytes.
- BOM SHA256: `71a684f13e1cf503070fe99054fb04472debadd086fd8572ba2b6d89d852e6b2`.
- `failure-analysis/state.json`, `coverage.json`: measured state and classification coverage.
- `failure-analysis/current-319-classification.json`, `plan.md`: exhaustive repair register and implementation plan.
- `failure-analysis/transition-audit.json` and `.md`: count reconciliation and historical occurrence evidence.
- `failure-analysis/prior-summary.md`: preserved historical chronology; its old latest-state claims are superseded by this file.

**Bottom line:** a normal CLI BOM now exists; the tool is still incomplete. Remaining work is generic owner/export discovery, automatic evidence acquisition, scoped resolution/canonicalization and measured performance repair. Classification/planning is complete for the current residuals; implementation closure and checkout promotion are not.
