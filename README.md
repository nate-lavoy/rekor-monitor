# Rekor Monitor

An auditing system for Sigstore signatures.

![Build Status](https://github.com/nate-lavoy/supply-chain-security/actions/workflows/cd.yml/badge.svg)
[![OpenSSF Scorecard](https://api.scorecard.dev/projects/github.com/nate-lavoy/supply-chain-security/badge)](https://scorecard.dev/viewer/?uri=github.com/nate-lavoy/supply-chain-security)
[![OpenSSF Best Practices](https://www.bestpractices.dev/projects/9764/badge)](https://www.bestpractices.dev/projects/9764)

## Project Description

Rekor Monitor provides tools for verifying inclusion and consistency of log entries in the Sigstore Transparency Log. It helps ensure the integrity of signed artifacts using Cosign.

## Installation

You can install Rekor Monitor directly from PyPI:

```bash
pip install rekor-monitor
```

## Using the Code

1. **Fetch the Latest Checkpoint:**

   Retrieve the latest checkpoint from the Rekor server with:

   ```bash
   rekor-monitor -c

2. **Verifying Log Inclusion:**

   To confirm that a specific log entry exists in the transparency log and verify the artifact's signature stored in Rekor:

   ```bash
   rekor-monitor --inclusion <logIndex> --artifact <artifactFilePath>
   ```
- Replace <logIndex> with the index of the log entry.

- Replace <artifactFilePath> with the path to your artifact file.

3. **Verifying Checkpoint Consistency:**

   To ensure an older checkpoint is consistent with the current Rekor checkpoint:

   ```bash
   rekor-monitor --consistency --tree-id <treeID> --tree-size <treeSize> --root-hash <rootHash>
   ```

- Replace <treeID> with the ID of the Merkle tree.

- Replace <treeSize> with the size of the previous tree.
   
- Replace <rootHash> with the root hash of the previous checkpoint.
