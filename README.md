# PO-33 KO Backup Analysis

This repository documents ongoing reverse engineering of the
Teenage Engineering PO-33 KO backup format.

Most of the signal-processing analysis has been performed
iteratively with the help of ChatGPT, with results validated
through cross-file comparisons and repeat recordings.

## Current Findings

- Backup audio uses a ~7.8 kHz carrier
- Modulation is **DQPSK**, not absolute QPSK
- A stable **prelude + sync + header** region exists
- Repeated backups of the same configuration are **bit-identical**
- Changing a single parameter (BPM, one step) causes the **entire payload
  after the header to change**
- Payload likely uses compression, whitening, encryption,
  or a chained checksum mechanism

## Status

- Modulation and symbol timing: mostly understood
- Header: stable but not yet semantically decoded
- Payload: structure unknown (next research focus)

## Goals

- Identify payload transformation (compression vs encryption)
- Determine if partial decoding or meaningful diffs are possible
- Document format clearly for future tooling

## Contributions / Ideas

Feedback, suggestions, or prior art are welcome.
