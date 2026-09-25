# Contributing

Thank you for helping keep this **public consulting SOP** accurate. This repository is a blueprint, not a product. Client teams execute. Do not send patches that invent a product, a hosted demo, a trading system, or an “AI agent army” kit.

## Before you write

1. Read the first screen of [README.md](README.md). The locked category lines must keep their meaning:
   - zh: 企业 AI 落地 SOP——先写清边界，再自动化。
   - en: Public SOP for enterprise AI: write the boundary before you automate.
2. Read [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md).
3. Search [existing issues](https://github.com/SmartStudio/enterprise-ai-sop/issues) so we do not duplicate a thread.

## What we want

- Corrections to a stage, exit test, or “Do not” line
- Broken-link fixes (`fxai.ai` notes, anchors, tables)
- Clarifications that keep Diagnose → Access → Engineer → Deliver → Compound in that order
- Community hygiene (templates, labels, translations of **tables only**)

## What we will close

- Customer names, prompts, or architecture that identifies a client
- Vendor account-sharing instructions
- Fake screenshots, demo GIFs, or “install the product” copy
- Trading / forex / agent-army material
- Rewrites that skip Access or treat seats as a diagnosis

## Good first issues

Look for the [`good first issue`](https://github.com/SmartStudio/enterprise-ai-sop/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22) label, or open one with the **Good first issue** template if you are proposing a small, self-contained docs fix. Typical first contributions:

- Typo or bilingual heading drift (English / 中文 labels on the five stages)
- A dead URL
- One extra row on the one-page check, with a reason
- A clearer “Do not” sentence that does **not** change the stage meaning

If the change would alter an exit test, it is **not** a good first issue—open a methodology bug instead.

## How to propose a change

1. Open an issue (bug or good-first-issue template) unless the fix is a one-line typo.
2. Fork or branch from `main`. Keep the PR scoped to one concern.
3. Edit Markdown only unless you are changing a workflow on purpose.
4. Fill in `.github/pull_request_template.md`.
5. Wait for review. Maintainers may ask you to restore the consulting boundary if the text starts to sound like a product.

There is no local test suite. The review is the test: meaning, honesty, and the five-stage order.

## Reporting security or private incidents

See [SECURITY.md](SECURITY.md). Do not file a public issue for leaked example secrets or client-identifying text.
