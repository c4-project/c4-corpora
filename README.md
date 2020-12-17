# c4-corpora

This repo contains input corpora for
[c4f](https://github.com/MattWindsor91/c4f).  These contain C litmus tests
generated using Memalloy, with the postconditions replaced ('amplified', in C4
speak) with ones listing all states seen through exhaustive Herd7 simulation.

## The corpora

We organise the corpora based on generation model and size:

### Models

- **rc11**: produced against `c11_lahav` (Memalloy), amplified against `rc11`
  (Herd), with `c11_normw` used to forbid certain types of RMW.  These were
  the original corpora we used for testing `c4f`, but predate handling of 
  compare-exchanges in our tooling, and so don't have any.  Note that `rc11`
  is theoretically stronger than some architectures, and using these inputs
  against a simulator _may_ cause false positives.
- **partialSC**: newer corpora produced and amplified against `c11_partialSC`.
  These corpora are smaller and less well-tested, but contain compare-exchanges
  and should be suitable for using against a simulator.

### Sizes

- **small**: 2 events;
- **large**: 4 events for rc11, 5 events for partialSC.

## Reproduction

These corpora were produced using the `do-memalloy-amplify` script in
[c4-scripts](https://github.com/MattWindsor91/c4-scripts).  For full
compare-exchange support, we use a
[Memalloy fork](https://github.com/MattWindsor91/memalloy) (`dev` branch) and
a [Herd7 fork](https://github.com/MattWindsor91/herdtools7).

## Licence

These corpora are considered to be in the public domain, under the Creative
Commons CC0 waiver version 1.0; see `LICENSE`.

