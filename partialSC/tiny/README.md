# PartialSC tiny corpus

This directory contains the pre-processed, amplified results of running
Memalloy on the 'Overhauling SC atomics in C11 and OpenCL' model with 2 events.
This number of events produces a comparable number of subjects to the RC11 model
on 4 events, but produces fairly uninteresting interactions between threads.

9 subjects.

## Reproduction

```shell
$ do_memalloy_amplify \
  -e 2 \
  -b herd \
  -m c11_partial.cat \
  PATH_TO_MEMALLOY partialSC/tiny
```
