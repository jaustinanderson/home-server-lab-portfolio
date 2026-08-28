# Architecture Notes

## Trust and data-flow model

The lab uses four generalized roles:

- An administrative client initiates management sessions over a private,
  encrypted path.
- A compute node runs active workloads against controlled working copies.
- A source archive stores canonical approved material.
- A secondary node pulls a restricted, read-only source into an independently
  versioned backup repository.

The pull direction matters: the source archive does not receive credentials
that can modify the independent recovery copy. The protected scope prioritizes
irreplaceable manifests, annotations, configuration, and database-consistent
exports; reproducible caches and re-downloadable public datasets are excluded.

## Security layers

- No inbound service is intentionally exposed to the public internet.
- Administrative access uses keys and explicitly verified effective policy.
- Service identities are separate from interactive administrator identities.
- Credentials remain outside Git with restrictive local permissions.
- Mounts and data flows are constrained to the minimum required access.
- Public documentation contains abstractions and bounded results, not live
  addressing or configuration.

## Recovery model

Storage redundancy, a local versioned copy, and an encrypted off-site copy
serve different failure modes. A successful job is not treated as proof of
recoverability. The project uses disposable fixtures and checksum comparison to
validate bounded restore claims, while avoiding claims about untested future
datasets or recovery-time objectives.

## Container-service boundary

The first service design places a lightweight monitor on the secondary node so it can remain useful when the compute node is unavailable. The reviewed model keeps application data on local storage, publishes the interface only to host loopback for access through the existing private administrative path, pins the upstream release, defines an explicit health check and restart policy, and excludes daemon-socket access, privileged mode, host-path persistence, and unnecessary capabilities.

Deployment is a separate gate from design. Recovery is also separate: the project will not claim service recoverability until an application-consistent recovery point and isolated restore pass. No public exposure, source-archive change, or backup-scope expansion is implied by the design.

## Portfolio/source-of-truth boundary

The private repository and verified read-only observations govern operational
state. This public repository contains only stable design patterns and
sanitized evidence. A public summary never authorizes or drives a live change.
