# Subnetwork QoS traffic classes

The study notes model Subnetwork QoS as a combination of a traffic class, a priority, and (where applicable) a channel identifier associated with reserved resources.

## Traffic classes

| Class | Delivery behavior in the study notes | Resource reservation |
|---|---|---|
| Best-Effort | Makes one delivery attempt; successful delivery is not confirmed | No |
| Assured | Delivery is confirmed; inability to provide the service is reported to the sender | No |
| Reserved | Best-effort-like delivery behavior with resources associated with a channel | Yes |
| Guaranteed | Confirmed delivery plus resources associated with a channel | Yes |

These descriptions are a working summary of the material studied. Exact guarantees, failure reporting, and service parameters must be checked against the relevant CCSDS specification.

## Priority models

The notes distinguish two priority interpretations:

- **Unreserved classes:** priority indicates the relative importance of data for transmission.
- **Reserved classes:** priority indicates importance within the resources allocated to the reserved channel.

## Ordering terminology: an open analysis point

The source material contains a potential ambiguity:

- Best-Effort describes packet order as not necessarily preserved.
- Another statement says packets received out of sequence may be discarded for Best-Effort and Reserved classes.

These statements may refer to different meanings or scopes of “order” and “in-sequence”, or to conditions under which sequence preservation is expected. The available notes do not resolve the issue.

**Do not silently normalize this into a definitive requirement.** Resolve it by consulting the exact normative text, definitions, and relevant service clauses in the selected CCSDS edition.

## General constraints recorded in the notes

- An SDU derived from an erroneous PDU is not delivered.
- A submitted SDU must not exceed the applicable MTU.
- Ordering behavior may depend on channel and priority boundaries and on the capabilities of the underlying data-link service.

## Questions for verification

1. Is “order” defined as submission order while “in-sequence” refers to sequence-number validation?
2. Under what conditions are out-of-sequence packets discarded?
3. Does the behavior differ by traffic class, channel, or priority?
4. Which guarantees are normative and which are implementation-dependent?
