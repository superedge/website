---
title: "SuperEdge v0.5.0 Release is Available"
linkTitle: "SuperEdge v0.5.0 Release"
date: 2021-07-23
description: >
    SuperEdge v0.5.0 Release Notes.
---

- [v0.5.0 / 2021-07-23](#v050--2021-07-23)
  - [Features and Enhancements](#features-and-enhancements)
  - [Bug Fixes](#bug-fixes)
  - [Documentation](#documentation)

# v0.5.0 / 2021-07-23

## Features and Enhancements

* Edgeadm: Added `kube-vip` as default HA component support([#186](https://github.com/superedge/superedge/pull/186),[@lianghao208](https://github.com/lianghao208))
* TunnelCloud HPA: Added `tunnel-cloud` metrics for HPA([#187](https://github.com/superedge/superedge/pull/187),[@00pf00](https://github.com/00pf00)), supporting `tunnel-cloud` HPA based on the number of connected edge nodes([#189](https://github.com/superedge/superedge/pull/189),[@00pf00](https://github.com/00pf00)). [Reference](https://github.com/superedge/superedge/blob/main/docs/components/tunnel-cloud-hpa_CN.md)
* Optimized Prometheus support([#189](https://github.com/superedge/superedge/pull/189),[@00pf00](https://github.com/00pf00)).
* TunnelCloud DNS: Separated the synchronization of podIPs and Endpoints([#177](https://github.com/superedge/superedge/pull/177),[@00pf00](https://github.com/00pf00)).
* Edgeadm: Deploy `CoreDNS` on every edge node by `servicegroup`([#185](https://github.com/superedge/superedge/pull/185),[@attlee-wang](https://github.com/attlee-wang)).


## Bug Fixes

* Edgeadm: Fixed X.509 certificate when joining edge nodes([#174](https://github.com/superedge/superedge/pull/174),[@lianghao208](https://github.com/lianghao208))
* Edgeadm: Fixed `tunnel-coredns` address when joining master([#176](https://github.com/superedge/superedge/pull/176),[@attlee-wang](https://github.com/attlee-wang))


## Documentation

* Added Prometheus deployment guide([#189](https://github.com/superedge/superedge/blob/main/docs/components/deploy-monitor_CN.md),[@00pf00](https://github.com/00pf00)).
* Added technical articles related to SuperEdge([#188](https://github.com/superedge/superedge/pull/188),[@neweyes](https://github.com/neweyes)).
* Added proposal template([#199](https://github.com/superedge/superedge/pull/199),[@neweyes](https://github.com/neweyes)).
