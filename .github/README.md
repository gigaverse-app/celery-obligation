# Celery, checked by pytest-obligation

[![pytest-obligation](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/gigaverse-app/celery-obligation/main/.github/obligation-badge.json)](#what-the-contract-finds-in-celerys-main)

This is [Celery](https://github.com/celery/celery) with one addition: a
[pytest-obligation](https://github.com/gigaverse-app/pytest-obligation) contract for Celery's
worker, in [`t/due_work`](../t/due_work). Celery's own README is [`README.rst`](../README.rst).

The contract sends one task, with a link and an error callback, through a real `celery worker`,
and a chord of two such tasks. It fails each run at one of Celery's stages: the worker's pool
child is lost as the task starts, before or after its result is stored, the task's `on_success`
hook raises, or the broker refuses the next publish. Then it restarts the worker and compares
what each run leaves with a normal run: the task's state, the messages sent, and which of the
link and the error callback ran.

Every night it runs against Celery's current `main`, and the report below is updated whenever
what it finds changes.

- [celery/celery#10726](https://github.com/celery/celery/pull/10726) proposes this contract to Celery.
- [celery/celery#10724](https://github.com/celery/celery/issues/10724) came from it, and is fixed on
  `main` by [celery/celery#10752](https://github.com/celery/celery/pull/10752) and
  [celery/celery#10759](https://github.com/celery/celery/pull/10759). The contract saw both fixes without being told about them.
- [celery/celery#10725](https://github.com/celery/celery/issues/10725) and
  [celery/celery#10954](https://github.com/celery/celery/issues/10954) are still open.

## What the contract finds in Celery's main

<!-- pytest-obligation:start -->
> [!CAUTION]
> **The test step failed.**
>
> A count shown as ? is not known.
>
> Contract counts cover only obligation checks; inspect the run log for other failures.

> [!WARNING]
> **Evidence unavailable.**
>
> Expected 1 report; found 0. Check the JSON artifacts and pytest logs.

<a href="https://github.com/gigaverse-app/pytest-obligation"><picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/sticky-banner-dark.svg"><img alt="pytest-obligation: what passed, what is missing, what to fix" src="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/sticky-banner-light.svg" width="640"></picture></a>

### Obligation contract checks

Other pytest tests and workflow steps are not included in these counts.

<p><picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/neutral-5-dark.svg"><img src="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/neutral-5-light.svg" width="18" height="36" alt="5 applications" align="middle"></picture><picture><img src="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/space.svg" width="69" height="36" alt="" align="middle"></picture><picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/warning-unknown-dark.svg"><img src="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/warning-unknown-light.svg" width="18" height="36" alt="contract checks passed: unknown" align="middle"></picture><picture><img src="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/space.svg" width="75" height="36" alt="" align="middle"></picture><picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/divider-dark.svg"><img src="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/divider-light.svg" width="1" height="36" alt="" align="middle"></picture><picture><img src="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/space.svg" width="12" height="36" alt="" align="middle"></picture><picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/warning-unknown-dark.svg"><img src="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/warning-unknown-light.svg" width="18" height="36" alt="contract failures: unknown" align="middle"></picture><picture><img src="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/space.svg" width="68" height="36" alt="" align="middle"></picture><picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/warning-unknown-dark.svg"><img src="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/warning-unknown-light.svg" width="18" height="36" alt="blocked checks: unknown" align="middle"></picture><picture><img src="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/space.svg" width="75" height="36" alt="" align="middle"></picture><picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/warning-unknown-dark.svg"><img src="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/warning-unknown-light.svg" width="18" height="36" alt="coverage gaps: unknown" align="middle"></picture><picture><img src="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/space.svg" width="72" height="36" alt="" align="middle"></picture><picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/warning-unknown-dark.svg"><img src="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/warning-unknown-light.svg" width="18" height="36" alt="rejected bindings: unknown" align="middle"></picture><picture><img src="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/space.svg" width="73" height="36" alt="" align="middle"></picture><picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/warning-unknown-dark.svg"><img src="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/warning-unknown-light.svg" width="18" height="36" alt="skipped tests: unknown" align="middle"></picture><picture><img src="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/space.svg" width="69" height="36" alt="" align="middle"></picture><br><picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/captions-with-skips-dark.svg"><img src="https://raw.githubusercontent.com/gigaverse-app/pytest-obligation/main/docs/assets/report-glyphs/captions-with-skips-light.svg" width="640" height="34" alt="applications · contract checks passed · contract failures · blocked checks · coverage gaps · rejected bindings · skipped tests" align="middle"></picture></p>

<details>
<summary>Application inventory and skipped tests</summary>

**0** applications with results · **0** applications not run · **5** unknown
Checks skipped: **unknown**. Applications without a report have no measured test count.

No application contract checks ran.

- **test&#95;DefaultConfiguration**: Unknown: reports incomplete.
- **test&#95;RequeuedWithAKey**: Unknown: reports incomplete.
- **test&#95;RequeuedWithoutAKey**: Unknown: reports incomplete.
- **a worker runs it with a link**: Unknown: reports incomplete.
- **celery: the worker running a task**: Unknown: reports incomplete.

Static declarations only; dynamically generated suites may be absent. No application code was imported.
Application name unresolved: t.due&#95;work.test&#95;application&#95;contract.test&#95;DefaultConfiguration; showing its suite name.
Application name unresolved: t.due&#95;work.test&#95;application&#95;contract.test&#95;RequeuedWithoutAKey; showing its suite name.
Application name unresolved: t.due&#95;work.test&#95;application&#95;contract.test&#95;RequeuedWithAKey; showing its suite name.

</details>




---

<details>
<summary><strong>What do these numbers mean?</strong></summary>

- **Failures:** an executed assertion failed unexpectedly or was an application-declared expected failure. Expected failures still permit successful CI; the visible breakdown distinguishes them.
- **Rejected bindings:** repair the connection to production code; these checks provide no supporting evidence.
- **Blocked checks:** checks could not establish a result, including missing execution, setup/cleanup errors, binding-debt or unclassified expected failures, and unexpected passes requiring declaration review.
- **Coverage gaps:** guarantees not assessed, missing scenarios, or with declared gaps. Each affected guarantee counts once. Deliberate exclusions are shown separately.

Pass/fail/blocked/rejected counts partition unique checks. Gaps count guarantees, not extra tests. Declined and not-applicable declarations remain separate and do not establish passing coverage. Graphics color contract results: passing checks and zero issues are green, failures and rejected bindings are red, blocked checks and gaps are amber. Missing reports never show green zeroes. The workflow status above is separate from these contract counts.

Elapsed time covers the pytest session. Summed check time includes setup, execution and cleanup; parallel work overlaps.
Application totals include discovered declarations and reported suites. Skipped checks count known deselections and explicit pytest skips; incomplete selected checks are not skips. Uncollected applications have unknown check counts. Zero recorded outcomes do not certify passing coverage.

Application names, quoted reasons and diagnostic values come from application code. Guarantee labels come from pytest-obligation. Results cover collected suites only; passing checks do not rate every test's quality.

Test step (reported): **failure**
Source: <code>nightly run of t/due&#95;work against Celery&#x27;s current main</code>

</details>

[Report guide](https://github.com/gigaverse-app/pytest-obligation/blob/main/package/docs/github-action-report.md)
<!-- pytest-obligation:end -->
