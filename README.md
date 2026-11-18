# SOIS Onboard Interface Architecture

A demonstration analytical project exploring the architecture of spacecraft onboard interface services (CCSDS SOIS).

**Author:** Ekaterina Motsar  
**Documentation:** https://ekatmoz88-alt.github.io/sois-onboard-interface-architecture/

## Scope

The project organizes an architectural analysis of SOIS layers, onboard interface types, Application Support and Subnetwork services, service dependencies, and Subnetwork QoS traffic classes.

It is an independent documentation and systems-analysis exercise. It does not claim development, deployment, or testing of flight software or spacecraft hardware.

## Build locally

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
mkdocs serve
```

Build the static site with `mkdocs build --strict`.

## Sources and verification

Technical statements should be checked against the applicable CCSDS publications and their exact editions before being treated as normative. Where the source notes contain an interpretation or unresolved ambiguity, the page marks it as an analysis point rather than a confirmed standard requirement.
