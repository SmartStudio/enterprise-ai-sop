# Security policy

This repository is a **public consulting methodology** (Markdown SOP), not production software. There is no hosted service, installer, or runtime to patch in-tree.

## What to report privately

Use [GitHub private vulnerability reporting](https://github.com/SmartStudio/enterprise-ai-sop/security/advisories/new) when the text could cause harm if discussed in public, including:

- Example credentials, tokens, or keys that look real
- Client names, prompts, or architecture that identifies a customer
- Instructions that would help someone bypass an access/audit control (we describe *what done looks like*, not how to break it)

If the advisory form is unavailable, contact the [SmartStudio organization owners](https://github.com/SmartStudio). Do not open a public issue with the secret or the identifying detail.

## What to file as a public issue

Methodology errors, broken links, and contradictions in the five stages belong in a **Methodology bug** issue. That is not a vulnerability.

## Scope we will not treat as a product CVE

- Missing features (this is not a product)
- “The SOP does not include a demo”
- Third-party sites linked from the README (`fxai.ai` and vendor docs)

We will acknowledge private reports as soon as a maintainer is available and will redact anything that should not have been published.
