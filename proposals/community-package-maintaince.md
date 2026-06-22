# Community package maintaince

This proposal about exteding PVP enforcement to full-fledged maintance
of a problem package by maintainers of dependent packages.

Rules/conditions:

- Hackage gets new GHC version.
- Compilation of problem package P breaks on new GHC version.
- Hackage discovers all directly dependent well maintained projects
  (DP) of P (buildable with previous GHC version and registered at
  least N month ago) and emails all their maintainers about the
  problem and a link for submitting PR for a community review. It is
  assumed that P maintainer had time to fix issues while pre-release
  GHC version was available.
- A maintainer of DP project prepares patch and submits for review by
  maintiners of other DPs.
- If no vetoes have been received after X weeks then the PR is
  approved and newer version is released with suffix "C".

- If no action happened from maintainers of any DP package within Y weeks then
  DP set is extendended with maintainers of packages depedenent on P
  transitively.

- After K consecutive community releases of package P - these
  community contributors could start elections of a new maintainer for
  package P among themselves to reduce "democratic overhead" in the
  future.
