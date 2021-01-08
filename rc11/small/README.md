# RC11 small corpus

This directory contains the pre-processed, amplified results of running
Memalloy on the RC11 model (Lahav et al.) with 4 events, and with single event
RMWs disabled.

14 subjects.

## Reproduction

```shell
$ do_memalloy_amplify \
  -e 4 \
  -b herd \
  -m c11_lahav.cat \
  -M c11_normws.cat \
  PATH_TO_MEMALLOY rc11/small
```
