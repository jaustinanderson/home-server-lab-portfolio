# Sanitized Verification Evidence

The project has completed the following categories of evidence in its private
operational record:

- External verification that password-based remote login is refused
- Recovery after deliberate maintenance reboots
- Clean package and service checks after controlled patching
- Least-privilege storage access tested with disposable synthetic fixtures
- Rejection of unauthorized create, overwrite, rename, and delete operations
- Data-provenance validation exercised with positive and negative synthetic
  fixtures
- A disposable encrypted-backup restore matched its source checksum
- Repository-controlled checks run on proposed changes before merge

## Recent bounded milestones

### Local secondary protection

A repository-controlled backup workflow now pulls an approved read-only synthetic scope into an encrypted local versioned repository. A natural scheduled run, stale-state monitoring, and a checksum-verified isolated restore passed. An earlier integration defect failed closed, was corrected through reviewed changes, and then passed controlled and scheduled verification. Automatic destructive retention remains outside the proven scope.

### Governed public-image pilot

One licensed, nonhuman public image completed the controlled path from quarantine through provenance and license review, manifest and checksum validation, canonical raw archiving, a local working copy, and an independently checksum-verified isolated restore. The pilot did not create an approved release, transform the image, authorize additional downloads, or permit patient, employer, restricted, or uncertain-origin material.

### First container-service gate

The intended ARM64 host passed container-runtime installation and a disposable test. A reviewed first-service design uses a pinned upstream release, local persistence, a dedicated network, a health check, private loopback-only access, and no daemon socket, privileged mode, host-path mount, or added capabilities. Architecture and upstream-image compatibility checks passed, but the application image and service resources remain undeployed. Service health, restart behavior, update/rollback, and isolated recovery are not yet claimed.

These are bounded claims. They do not imply production readiness, regulatory
validation, clinical use, continuous availability, or protection of any data
that has not been included in a verified recovery exercise.

No raw output, operational identifier, private path, address, credential,
schedule, provider account detail, or patient/employer material is published as
evidence here.
