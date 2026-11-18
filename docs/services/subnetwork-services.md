# Subnetwork services

Subnetwork services expose common communication and device-access functions above a selected onboard subnetwork.

## Service catalogue

| Service | Function | Access pattern |
|---|---|---|
| Packet Service | Transfers packets over a subnetwork and supports multiplexing and QoS | Packet-oriented |
| Get Parameter Service | Reads a parameter value from a locally accessible device | Asymmetric; local user node |
| Set Parameter Service | Writes a parameter value to a locally accessible device | Asymmetric; local user node |
| Read Location Service | Reads a word or block from device memory/register space | Asymmetric; local user node |
| Write Location Service | Writes a word or block to device memory/register space | Asymmetric; local user node |
| Time Distribution Service | Distributes time from a source node to consumers | Producer/consumer |
| Device Discovery Service | Detects devices that become active after a hardware-configuration change | Discovery/event-oriented |

## Parameter and location access

Parameter services operate on values associated with devices. Location services operate on memory or register locations and may support single-word or block operations.

The study notes distinguish local device access from access to a device attached to a remote node. Remote interaction is expected to use higher-level communication capabilities rather than treating a local Subnetwork service as a remote procedure call.

## Time distribution

The Time Distribution Service is described as asymmetric: a master/source node provides time and other nodes consume it. The exact synchronization mechanism, accuracy, and fault behavior depend on the selected standard and implementation.

## Device discovery

Device Discovery Service concerns detecting devices that become active due to a change in hardware configuration. Do not conflate this with a complete plug-and-play lifecycle unless the applicable specification defines those additional behaviors.

## Implementation checklist

- Identify which services are supported natively by the selected link.
- Define convergence functions for unsupported capabilities.
- Specify local versus remote access boundaries.
- Define error handling and parameter representation.
- Verify service names and required/optional status against the selected CCSDS edition.
