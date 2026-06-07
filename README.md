# TrustFusion

Anonymous implementation repository for **TrustFusion: Explicit Multi-Dimensional Trust Modeling for Robust Multi-Source Perception**.

This repository accompanies a paper submitted to the **IEEE International Conference on Data Mining (ICDM)**. The code is being prepared for public release and will be open-sourced soon.

## Overview

TrustFusion is a source-reliability layer for V2X cooperative perception. It estimates interpretable source-level trust from communication freshness, temporal stability, and cross-source consistency, then uses the trust scores to reweight multi-agent feature fusion. TrustFusion can be attached to existing cooperative perception backbones without changing their detector-specific internals.

## Main Results

Average Precision (AP) comparison on three V2X cooperative perception benchmarks under clean and corrupted communication/localization settings. `+TF` denotes the backbone enhanced with TrustFusion.

| Dataset | AP | No Fusion | Noise | V2VNet | V2VNet+TF | AttFuse | AttFuse+TF | FuseBEVT | FuseBEVT+TF | F-Cooper | F-Cooper+TF | V2X-ViT | V2X-ViT+TF | CoDynTrust | CoDynTrust+TF |
|---|---:|---:|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| V2XSet | @0.5 | 0.6011 | L0 | 0.8571 | 0.8569 | 0.8031 | 0.8033 | 0.8374 | 0.8372 | 0.8396 | 0.8400 | 0.8801 | 0.8795 | 0.8822 | 0.8829 |
| V2XSet | @0.5 | 0.6011 | L1 | 0.8182 | 0.8180 | 0.7820 | 0.7924 | 0.7979 | 0.7975 | 0.8104 | 0.8274 | 0.8572 | 0.8679 | 0.8616 | 0.8612 |
| V2XSet | @0.5 | 0.6011 | L2 | 0.6837 | 0.7585 | 0.6985 | 0.7714 | 0.6959 | 0.7602 | 0.7252 | 0.7831 | 0.7367 | 0.8086 | 0.7832 | 0.8131 |
| V2XSet | @0.5 | 0.6011 | L3 | 0.5101 | 0.6061 | 0.5259 | 0.6121 | 0.5443 | 0.6219 | 0.5614 | 0.6483 | 0.6120 | 0.6792 | 0.6521 | 0.6857 |
| V2XSet | @0.7 | 0.4072 | L0 | 0.6622 | 0.6624 | 0.6558 | 0.6559 | 0.6651 | 0.6650 | 0.6701 | 0.6709 | 0.7097 | 0.7105 | 0.7134 | 0.7136 |
| V2XSet | @0.7 | 0.4072 | L1 | 0.5729 | 0.6374 | 0.5618 | 0.6408 | 0.5628 | 0.6318 | 0.5457 | 0.6320 | 0.6245 | 0.6859 | 0.6638 | 0.6786 |
| V2XSet | @0.7 | 0.4072 | L2 | 0.4320 | 0.5629 | 0.4419 | 0.5518 | 0.4542 | 0.5494 | 0.4158 | 0.5291 | 0.4818 | 0.5946 | 0.5552 | 0.5855 |
| V2XSet | @0.7 | 0.4072 | L3 | 0.2732 | 0.4125 | 0.2992 | 0.4319 | 0.2817 | 0.4353 | 0.2379 | 0.4122 | 0.3431 | 0.4718 | 0.4213 | 0.4657 |
| OPV2V | @0.5 | 0.6806 | L0 | 0.8981 | 0.8984 | 0.8912 | 0.8910 | 0.9095 | 0.9100 | 0.8281 | 0.8287 | 0.9411 | 0.9415 | 0.9438 | 0.9432 |
| OPV2V | @0.5 | 0.6806 | L1 | 0.8733 | 0.8870 | 0.8562 | 0.8798 | 0.8766 | 0.8754 | 0.7920 | 0.8173 | 0.9078 | 0.9313 | 0.9231 | 0.9325 |
| OPV2V | @0.5 | 0.6806 | L2 | 0.7850 | 0.8601 | 0.7614 | 0.8276 | 0.7863 | 0.8655 | 0.6733 | 0.7335 | 0.7772 | 0.8470 | 0.8434 | 0.8668 |
| OPV2V | @0.5 | 0.6806 | L3 | 0.6217 | 0.7052 | 0.6401 | 0.7254 | 0.6347 | 0.7215 | 0.5277 | 0.6856 | 0.6095 | 0.6901 | 0.6936 | 0.7249 |
| OPV2V | @0.7 | 0.6007 | L0 | 0.8212 | 0.8213 | 0.8118 | 0.8121 | 0.8499 | 0.8503 | 0.7879 | 0.7878 | 0.8493 | 0.8495 | 0.8527 | 0.8530 |
| OPV2V | @0.7 | 0.6007 | L1 | 0.6422 | 0.7043 | 0.6850 | 0.7429 | 0.7161 | 0.7781 | 0.6551 | 0.7376 | 0.7329 | 0.7950 | 0.7702 | 0.7883 |
| OPV2V | @0.7 | 0.6007 | L2 | 0.5236 | 0.6322 | 0.5641 | 0.6750 | 0.5851 | 0.7061 | 0.5426 | 0.6385 | 0.6321 | 0.7229 | 0.6936 | 0.7286 |
| OPV2V | @0.7 | 0.6007 | L3 | 0.3921 | 0.5844 | 0.4309 | 0.5957 | 0.4227 | 0.6052 | 0.3782 | 0.5951 | 0.5053 | 0.6227 | 0.5787 | 0.6139 |
| V2X-Real | @0.3 | 0.3112 | L0 | 0.4270 | 0.4275 | 0.4227 | 0.4226 | 0.4324 | 0.4322 | 0.3936 | 0.3937 | 0.6197 | 0.6193 | 0.6264 | 0.6261 |
| V2X-Real | @0.3 | 0.3112 | L1 | 0.4106 | 0.4101 | 0.4064 | 0.4135 | 0.4122 | 0.4274 | 0.3708 | 0.3884 | 0.5654 | 0.5633 | 0.5639 | 0.5775 |
| V2X-Real | @0.3 | 0.3112 | L2 | 0.2980 | 0.3244 | 0.2903 | 0.3199 | 0.2979 | 0.3342 | 0.2595 | 0.2928 | 0.4782 | 0.5003 | 0.4936 | 0.5127 |
| V2X-Real | @0.3 | 0.3112 | L3 | 0.1629 | 0.2267 | 0.1804 | 0.2396 | 0.1916 | 0.2417 | 0.1243 | 0.2477 | 0.3428 | 0.3842 | 0.3653 | 0.4213 |
| V2X-Real | @0.5 | 0.2243 | L0 | 0.3141 | 0.3140 | 0.3183 | 0.3185 | 0.3218 | 0.3222 | 0.2953 | 0.2961 | 0.5824 | 0.5829 | 0.5848 | 0.5846 |
| V2X-Real | @0.5 | 0.2243 | L1 | 0.2829 | 0.3041 | 0.2827 | 0.3115 | 0.2943 | 0.3102 | 0.2552 | 0.2836 | 0.5265 | 0.5487 | 0.5385 | 0.5556 |
| V2X-Real | @0.5 | 0.2243 | L2 | 0.1654 | 0.2435 | 0.2014 | 0.2613 | 0.2118 | 0.2831 | 0.1982 | 0.2263 | 0.4352 | 0.4655 | 0.4532 | 0.4783 |
| V2X-Real | @0.5 | 0.2243 | L3 | 0.0914 | 0.1993 | 0.1158 | 0.2293 | 0.0897 | 0.1893 | 0.1021 | 0.1923 | 0.2982 | 0.3521 | 0.3301 | 0.3795 |

## Release

The repository currently serves as the anonymous project page for review. Training and evaluation code will be released after the review process.
