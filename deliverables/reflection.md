# Module 7 Lab 2

Maintaining Secure Systems with SBOMs and Patching

## Part 1: Generate Baseline System Information

Linux Version:
```
Linux codespaces-ce95bd 6.8.0-1030-azure #35~22.04.1-Ubuntu SMP Mon May 26 18:08:30 UTC 2025 x86_64 x86_64 x86_64 GNU/Linux
```

Ubuntu Version:
```
PRETTY_NAME="Ubuntu 22.04.5 LTS"
NAME="Ubuntu"
VERSION_ID="22.04"
VERSION="22.04.5 LTS (Jammy Jellyfish)"
VERSION_CODENAME=jammy
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=jammy
```

## Part 2: Generate Baseline SBOM and Vulnerability Report

Syft detected 2,191 packages from 3,117 executables.

Grype detected 369 vulnerabilities:
- 9 Critical
- 49 High
- 1529 Medium
- 198 Low
- 24 Negligible

For example, a High severity Go standard library (stdlib) vulnerability found [here](https://nvd.nist.gov/vuln/detail/cve-2023-44487) in the NVD database allows an attacker to cause a denial of service by cancelling many requests.

## Part 3: Identify and Apply System Updates

The system is already fully up-to-date.

## Part 4: Post-Update Analysis

No packages were updated or removed. The diff is empty.

## Part 5: Reflection

Maintaining updated packages ensures that every safeguard that's intended to be in place is actually in place. When a vulnerability is discovered, that usually means one (or more) such safeguard(s) are missing or broken. By updating packages, these vulnerabilities are patched, ensuring that shortcuts through security measures are closed off.

Generating a new SBOM after patching allows you to verify that the patches actually fixed the vulnerabilities. CVEs generally include information about which versions are affected by the vulnerability and which versions are patched, so a new SBOM allows you to confirm that the system is no longer running the vulnerable versions.

When organizations delay system updates, these known vulnerabilities (in the form of CVEs) are exploitable for longer. This increases the chance that an attacker finds and exploits one of these vulnerabilities, potentially leading to a security breach. Regularly applying patches minimizes this risk by reducing the window of opportunity for attackers.

The exercise fills in the later parts of the secure design lifecycle, by ensuring that systems remain secure after deployment. Once a system is deployed, it must be continually monitored and updated to ensure that the newest vulnerabilities are patched, keeping the system secure over time.
