# AERO Agent Boundaries

Agents may assist with repository planning and implementation, but they must remain auditable and bounded.

## Permitted by default

- inspect source and documentation;
- propose patches;
- implement isolated compiler or runtime features;
- write tests and documentation;
- run local validation commands;
- use read-only external sources when implementation requires them.

## Requires explicit approval

- package or registry publication;
- network-facing services;
- external credentials or identity changes;
- hardware control;
- model downloads or paid inference;
- destructive migration or data deletion;
- GitHub writes beyond the requested change.

## Prohibited

- adding API keys or secrets to files;
- silently changing language semantics;
- replacing tests instead of fixing implementation defects;
- claiming hardware or ML support from documentation alone;
- weakening capability checks or device bounds;
- inventing benchmark or implementation results.

## Agent skill rules

- prefer small, reviewable changes;
- stop and report when repository context is insufficient;
- validate with workspace commands;
- label assumptions as assumptions;
- preserve upstream attribution and license notices.
