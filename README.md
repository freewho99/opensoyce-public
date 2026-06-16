# opensoyce-public

**OpenSoyce** is a trust record system for open source software. It produces signed evidence bundles — called packets — that let vendors show buyers exactly what is known about a component's risk, remediation, and deployment, without overclaiming.

This repo is the **public sample and reference layer**. The product code is private. What you see here is:

- Sanitized sample artifacts showing the shape and doctrine of each artifact type
- - The non-claim doctrine that makes every OpenSoyce artifact honest
  - - Links to the live public credibility layer
   
    - ---

    ## What OpenSoyce does

    OpenSoyce lets a vendor publish a signed trust record for a software component. The record includes:

    - **Observation** — what was seen in the dependency manifest, with provenance
    - - **Vulnerability context** — what intelligence was recorded (not a claim of absence)
      - - **Remediation questions and resolutions** — the trust-decision chain
        - - **Attestation** — a signed officer or vendor statement over the packet
          - - **Deployed-artifact binding** — linking the packet to a declared artifact digest
            - - **Non-claims** — explicit statements of what the packet does NOT prove
             
              - A buyer can open the packet in the viewer, verify the signature, review the chain, and download a verification receipt — all without trusting OpenSoyce to vouch for the software.
             
              - ---

              ## Public credibility layer

              Live verified proof and public key information:

              - [opensoyce.vercel.app/trust](https://opensoyce.vercel.app/trust)
              - - [opensoyce.vercel.app/opensource-trust](https://opensoyce.vercel.app/opensource-trust)
               
                - These pages show what OpenSoyce actually proved in production — signed artifacts, verification receipts, and the public half of the signing key.
               
                - ---

                ## Sample files

                All files in `/samples` are sanitized for public reference. Signature values, digests, and identifiers are redacted. They show structure and doctrine — not real production data.

                | File | What it shows |
                |------|---------------|
                | `samples/signed-packet.json` | The shape of a signed evidence bundle |
                | `samples/attestation.json` | A vendor/officer attestation over a packet |
                | `samples/verification-receipt.json` | A buyer-generated verification receipt (VERIFIED case) |
                | `samples/deployment-observation.json` | A CI deployment observation artifact |
                | `samples/non-claims.json` | The full non-claim doctrine — what OpenSoyce does NOT assert |

                ---

                ## Non-claim doctrine

                Non-claims are not disclaimers. They are load-bearing doctrine printed on every artifact:

                - OpenSoyce does not certify that software is safe, secure, or production-ready
                - - A packet does not prove the absence of vulnerabilities
                  - - Signature validity proves packet integrity only — not software quality
                    - - A signed packet does not prove what is currently deployed or running in production
                      - - OpenSoyce does not verify attester identity beyond what is self-asserted
                        - - A buyer verification receipt is buyer-generated and OpenSoyce-unsigned
                         
                          - See `samples/non-claims.json` for the full set with explanations.
                         
                          - ---

                          ## What is NOT here

                          The product source code, CLI, verifier logic, share store, runtime reader, architecture docs, and lane manifests are private. This repo is the public face — not the implementation.

                          ---

                          *OpenSoyce — the nutrition label for open source projects.*
