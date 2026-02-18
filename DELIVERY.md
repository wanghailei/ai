# DELIVERY.md

## Purpose
- This file defines shared delivery, test, staging, and release-validation policy across projects.
- Use this together with `INTEGRATION_WORKFLOW.md` for branch/PR flow and with `DOCUMENTATION.md` for writing quality.

## Test
- Separate validation evidence by mode:
	- common-user dogfooding,
	- local pre-release simulation.
- Do not mix these modes in one claim.
- Every release validation note must label the mode explicitly.
- Common-user dogfooding requires the same install path a normal user uses (published package source and normal install command).
- Local source-built install is simulation evidence only.

## Staging
- Local pre-release simulation must run in a dedicated simulation repository.
- For Butler, use `butler-test/simulation` as the default simulation repository.
- Do not use the product repository itself as the simulation host for release-readiness claims.
- Keep simulation artefacts isolated from product repository state.

## Release
- Do not claim release readiness from simulation evidence alone.
- Release readiness requires at least one successful common-user dogfood run using published package distribution.
- If package publication is pending, release status must be reported as pre-release validation only.
