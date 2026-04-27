# LUXFI-FORK

This is a luxfi-maintained fork of [supranational/blst](https://github.com/supranational/blst).

## Pin

* Upstream tag: `v0.3.15`
* Commit SHA: `6d960cd05d6fe2b5bc9ba161edf0c1a131b87c4c`
* License: Apache-2.0 (see `LICENSE`)

## Why this fork exists

`blst` is the BLS12-381 reference. luxfi consumes it as a TEST-ORACLE-ONLY
dependency at `luxcpp/crypto/bls/test/cmake/blst.cmake`. The LP-137 invariant
forbids any blst symbols in production link graphs; first-party host/Metal/GPU
BLS bodies live under `luxcpp/crypto/bls/{host,gpu,metal}/`.

Owning the fork pins the test-oracle commit and prevents upstream HEAD drift
from silently changing differential test vectors.

## Sync policy

* Track upstream stable releases only. Never track HEAD.
* Pull upstream tags into a `sync/<tag>` branch. Audit the diff. Merge to
  `master` only after `luxcpp/crypto/bls` differential tests pass against the
  new pin.
* Security advisories: hot-cherry-pick fixes onto `master`, tag as
  `<upstream-tag>-luxfi.<n>`.

## Maintainer

luxfi crypto team. Contact via the `luxfi/crypto` repo.
