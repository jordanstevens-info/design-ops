# Data Handling

Use this before processing user-provided artifacts, evidence, screenshots,
research, analytics, session replay, tickets, source code, or external data.

## Classification

The `design` plugin uses generic classes. Team variants can map these to local
policy names and approved destinations.

- **Class 1: Public** - approved for public disclosure.
- **Class 2: Internal** - internal business data with minimal disclosure impact.
- **Class 3: Confidential** - limited recipients; disclosure could harm the
  business, reputation, customers, or partners.
- **Class 4: Restricted** - extremely sensitive, private, regulated, or named
  individual access only.

Unknown classification is sensitive until confirmed.

## Hard Rule: Never C4

Never process C4 with AI. No upload, analysis, generation, summarization,
deduction, inference, transformation, or redaction pass.

If material is known or suspected C4:

- Stop the run as `Prohibited`.
- Do not quote or summarize the source.
- Do not ask the model to redact the source.
- Record only minimal lineage: source reference, reason category, and safe
  rerun conditions.

C4 examples can include payment card data, credentials, secret tokens, legal
material, security incidents, medical data, biometric data, government IDs,
precise geolocation, protected characteristics, and sensitive personal
information. Do not rely on this list as exhaustive.

## AI-Specific Prohibitions

Do not use AI for:

- C4 Sensitive Personal Information
- call recordings
- deepfakes
- manipulative systems
- workplace emotion recognition
- third-party or non-company IP without confirmed rights

User-authored async demo recordings are allowed only when they do not contain
C4, call recordings, meeting recordings, or unapproved third-party IP.

## C3 Defaults

Keep C3 source material in the source system by default. Link to the source and
summarize only when the user has confirmed the destination and persistence
expectation.

Do not copy screenshots, transcripts, analytics, session replay, research
notes, or confidential customer/business material into local artifacts unless
the user explicitly approves the destination.

## Prohibited-Run Report

Use `../templates/prohibited/prohibited-run-report.md` when a workflow has
already started and must stop. Minimum report:

- Stop condition: `Prohibited`
- Reason category: C4, rights, unapproved AI tool, forbidden AI use, or unknown
  classification with possible C4
- Minimal source reference, without sensitive content
- What was not processed
- Required non-AI confirmation or governance owner
- Safe rerun conditions
