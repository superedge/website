---
title: "edge-health"
linkTitle: "edge-health"
description: >
  A distributed health check to detect edge nodes liveness within the same NodeGroup.
---


`edge-health` provides an additional layer of health check, which does't affect by the unstable of cloud-to-edge network. It runs on every edge node by default to check the actual status of edge nodes with the same NodeGroup at the edge so as to keep the healthy edge nodes running while temporary losing connection to the cloud.

## Configurations
### For health check
   - healthcheckperiod: detection period (unit is second, and the default value is 10)
   - healthcheckscoreline: The score line to determine the node is normal (the default value is 100)
   - The following parameters are supported in the plugin:
     - timeout: specify the timeout period for a request
     - retrytime: specify the number of retries for probe failure
     - weight: specify the proportion of the detection method to the detection score, the maximum is 1
     - port: specify the port for detection
   - Two plugins currently supported:
     - Detcet kubelet security authentication port: `--kubeletauthplugin=timeout=5,retrytime=3,weight=1,port=10250`
     - Detcet kubelet non-secure authentication port: `--kubeletplugin=timeout=5,retrytime=3,port=10255,weight=1`

### For communication
- communicateperiod: specify the interaction period (in seconds, and the default value is 10)
- communicatetimetout: specify the timeout period for sending interactive information (unit is seconds, and the default value is 3)
- communicateretrytime: specify the number of retries when sending interactive information fails (the default value is 1)
- communicateserverport: the port for receiving and sending interactive information (the default port is 51005)

### Others
- voteperiod: specify the voting period (unit is seconds, and the default value is 10)
- votetimeout: specify the valid time for voting, invalid voting is longer than this time (unit is second, and the default value is 60)

## Multi-region Detection
- To enable
  - Label the nodes according to the region with `superedgehealth/topology-zone:<zone>`
  - Create a ConfigMap named `edge-health-zone-config` in the `edge-system` namespace and set `TaintZoneAdmission` to `true`.

  Sample config:
   ```yaml
   apiVersion: v1
   kind: ConfigMap
   metadata:
     name: edge-health-zone-config
     namespace: edge-system
   data:
     TaintZoneAdmission: true
   ```
- To disable
  - Change the value of `TaintZoneAdmission` to `false` or delete `edge-health-zone-config` ConfigMap

> Note: Nodes without `superedgehealth/topology-zone:<zone>` label will not detect other nodes even if multi-region detection is enabled.
