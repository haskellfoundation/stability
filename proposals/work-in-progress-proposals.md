# Work In Progress Proposals

This serves to collect proposals as rough idea sketches that have been brought up in working group meetings. As such this is not a complete proposal that the community could act on, but rather a collection of items that could become many proposals in the future.

The ideas are roughly grouped where possible.

## Extend Hackage

Many ideas are extensions to Hackage in some form.

- Allow maintainers to be notified when a dependency has been uploaded that falls out of range.
- Show consumers of a particular export of a given package.
  This allows maintainers to see the impact of a change they wish to make and give information for more informed changes.
- Allow for opt-in PVP enforcement and display if packaage has opted-in.

## GHC Releases

Several ideas on GHC release scheduling have been discussed and could be more formally proposed.

- Yearly GHC releases
- A dependable release cycle with a set release month or months

## Other Ideas
- Introduce language and compiler features to facilitate evolution of libraries without breaking users.
- State formally a goal of evolution and breaking changes
  >Write in some official place (Haskell.org or at least haskell.foundation) something like "One of the Haskell goals is to constantly evolve and this implies having breaking changes from time to time". This statement helps to align community expectations with common goals and values. Additionally, this reduces burnout of maintainers because they at least know what to expect (to some degree).
- Support Stackage LTS in some fashion
