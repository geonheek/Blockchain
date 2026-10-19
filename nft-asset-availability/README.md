# NFT Asset Availability

This directory contains code used for the NFT asset availability study published in *Computer Networks*.

## Overview

NFT ownership is recorded on-chain, while image assets are frequently stored outside the blockchain.

This project measures whether NFT image resources remain accessible and examines how availability differs across storage systems.

The analysis covers:

- Web2-hosted resources
- IPFS
- Arweave

The dataset contains approximately:

- 5 million NFT mint transactions
- 2.5 million image URIs

## Accessibility Verification

A failed HTTP request was not immediately treated as permanent asset loss.

Resources were checked using a staged verification process:

1. HEAD request
2. Partial GET request
3. Full GET request

For IPFS resources, additional validation was performed when a gateway failed.

The CID was rechecked and the asset was queried through alternative gateways.

`ar://` URIs were normalized before requesting resources through an Arweave gateway.

This process was used to distinguish temporary network or gateway failures from actual asset unavailability.

## Storage Categories

Assets were grouped into three storage categories:

- Web2
- IPFS
- Arweave

Web2 includes project domains and CDN-hosted resources.

IPFS includes both public and project-specific gateways.

## Results

During revalidation, resources initially classified as inaccessible were recovered:

- 2020 cohort: 11,493 assets
- 2024 cohort: 5,222 assets

After the full verification procedure, the final inaccessible rate was approximately 4.21%.

## Repository Structure

```text
scripts/
    Research scripts used for URI normalization,
    accessibility checks, retry logic, and aggregation.

sample/
    Small examples of the processed data format.

results/
    Summaries and derived statistics.
