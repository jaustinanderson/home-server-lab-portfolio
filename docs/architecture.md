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

## Portfolio/source-of-truth boundary

The private repository and verified read-only observations govern operational
state. This public repository contains only stable design patterns and
sanitized evidence. A public summary never authorizes or drives a live change.
