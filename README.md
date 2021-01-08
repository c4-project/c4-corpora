# c4-corpora

This repo contains input corpora for
[c4f](https://github.com/c4-project/c4f).  These contain C litmus tests
generated using Memalloy, with the postconditions replaced ('amplified', in C4
speak) with ones listing all states seen through exhaustive Herd7 simulation.

**Have an interesting C litmus test that you think might be a good fuzzer
input?** Feel free to open a pull request to add it to the corpus (so long as
it can be placed under the CC0 waiver).

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

There are up to three sizes for each model: `tiny`, `small`, and `large`.
The sizes are relative; for example, `rc11/small` is much smaller than
`partialSC/small`.

These names may change to something more systematic later on.

## Reproduction

These corpora were produced using the `do-memalloy-amplify` script in
[c4-scripts](https://github.com/c4-project/c4-scripts).  For full
compare-exchange support, we use a
[Memalloy fork](https://github.com/c4-project/memalloy) (`dev` branch) and
a [Herd7 fork](https://github.com/c4-project/herdtools7).

## Licence

These corpora are considered to be in the public domain, under the Creative
Commons CC0 waiver version 1.0; see `LICENSE`.
