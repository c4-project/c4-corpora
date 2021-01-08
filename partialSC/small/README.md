# PartialSC small corpus

This directory contains the pre-processed, amplified results of running
Memalloy on the 'Overhauling SC atomics in C11 and OpenCL' model with 4 events.

150 subjects.

## Reproduction

```shell
$ do_memalloy_amplify \
  -e 4 \
  -b herd \
  -m c11_partial.cat \
  PATH_TO_MEMALLOY partialSC/tiny
```
