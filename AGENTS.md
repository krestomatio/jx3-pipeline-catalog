# Repository guidance

Before working, read these optional instruction files in order,
resolving these paths from this repository's root:

1. `.agents/organization/AGENTS.md`
2. `.agents/workspace/AGENTS.md`

Read each file if it resolves to a readable regular file.
Skip absent files; report broken or unreadable links.
Read each resolved file only once to avoid duplicate loading and cycles.

Resolve references inside imported files relative to their real target
directory after following symlinks.

Apply organization guidance, then workspace guidance, then the repository
instructions below. More specific applicable instructions take precedence.

Follow this repository's documentation and any more specific instructions for
the files being changed.

## Repository scope

- This repository owns reusable Jenkins X 3/Tekton tasks under `tasks/`.
  `kio-jx` directly consumes the Git-clone tasks; the multi-architecture builder
  tasks remain infrastructure-capable even when no current pipeline references
  them visibly.
- Task parameters, workspace names, environment contracts, images, and result
  paths are public pipeline interfaces. Preserve compatibility or coordinate every
  consumer update.

## Validation

- Lint YAML and validate changed objects against the intended Tekton API/CRDs in
  a non-production context. Review embedded shell with strict quoting and failure
  handling.
- Deployment/undeployment tasks can create or destroy AWS builders. Do not apply
  tasks or run their Terraform operations as a validation shortcut.
