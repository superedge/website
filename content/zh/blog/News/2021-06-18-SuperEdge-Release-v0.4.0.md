---
title: "SuperEdge v0.4.0 Release is Available"
linkTitle: "SuperEdge v0.4.0 Release"
date: 2021-06-18
description: >
    SuperEdge v0.4.0 Release Notes.
---

- [v0.4.0 / 2021-06-18](#v040--2021-06-18)
  - [Features and Enhancements](#features-and-enhancements)
  - [Bug Fixes](#bug-fixes)
  - [Documentation](#documentation)

# v0.4.0 / 2021-06-18

## Features and Enhancements

* Introduced `Penetrator` to batch add and reload edge nodes from the cloud([#121](https://github.com/superedge/superedge/pull/121),[@00pf00](https://github.com/00pf00)). User submits `nodetask`, a Kubernetes CRD, and then penetrator batch adds and reloads edge nodes in the background even if the nodes can only be accessed one-way. [Reference](https://github.com/superedge/superedge/blob/main/docs/installation/addnode_via_penetartor.md)
* Supported SSH login to edge nodes from cloud, even if the nodes can only be accessed one-way([#140](https://github.com/superedge/superedge/pull/140),[@00pf00](https://github.com/00pf00)). [Reference](https://github.com/superedge/superedge/blob/main/docs/components/edge-node-ops.md)
* `Servicegroup` supported multi-cluster application distribution([#139](https://github.com/superedge/superedge/pull/139),[@chenkaiyue](https://github.com/chenkaiyue)). `Nodeunits` under the same `nodegroup` can be distributed in different clusters in `Clusternet`. [Reference](https://github.com/superedge/superedge/blob/main/docs/components/serviceGroup_CN.md#%E4%BD%BF%E7%94%A8%E7%A4%BA%E4%BE%8B)
* Supported SuperEdge add-on mode([#129](https://github.com/superedge/superedge/pull/129),[@lianghao208](https://github.com/lianghao208)). [Reference](https://github.com/superedge/superedge/blob/main/docs/installation/addon_superedge.md)
* Moved the `NewInitNodePhase()` function directly into an `init-node.sh` script([#138](https://github.com/superedge/superedge/pull/138),[@k2let](https://github.com/k2let)).
* Upgraded `klog` from v1 to v2([#136](https://github.com/superedge/superedge/pull/136),[@attlee-wang](https://github.com/attlee-wang)).


## Bug Fixes

* Modified `edgeadm` to disable SELinux([#132](https://github.com/superedge/superedge/pull/132), [@k2let](https://github.com/k2let)).
* Lite-apiserver: Added `modify-request-accept` param([#126](https://github.com/superedge/superedge/pull/126), [@Beckham007](https://github.com/Beckham007)).
* Added node name parameter check to avoid unsupported the IPv4 format([#125](https://github.com/superedge/superedge/pull/125), [@zhhray](https://github.com/zhhray)).

## Documentation

* Added hostname requirements to deployment docs([#150](https://github.com/superedge/superedge/pull/150), [@jasine](https://github.com/jasine)).
* Added `edge-health` deploy docs([#141](https://github.com/superedge/superedge/pull/141), [@attlee-wang](https://github.com/attlee-wang)).
