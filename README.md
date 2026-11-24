# 🦉 OSerial

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OForensics-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OSerial** — Insecure Deserialization Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview


OSerial is an offline insecure-deserialization auditor that statically inspects serialized blobs and source trees without ever deserializing untrusted data. It recognises Java, Python pickle, PHP, .NET, ViewState, Ruby, YAML and Node formats, unwraps base64/hex/url/gzip/zlib layers, and flags known gadget chains. Findings are graded A+ to F with CWE-502 and MITRE tags and can be exported as TXT, Markdown, JSON, CSV or SARIF for CI pipelines.

---

## ✨ Features


- Offline blob inspector for Java, Pickle, PHP, .NET, ViewState, Ruby, YAML and Node payloads (never calls loads/unserialize)
- Layer unwrapper (base64 / hex / url / gzip / zlib) with automatic format detection
- Gadget-chain detection modelled on ysoserial, phpggc, ysoserial.net and RubyGems
- Source-code sink scanner across Python, Java, PHP, C#, Ruby and JavaScript
- A+..F grading with CWE-502 and MITRE tags; severity filtering and CI gating via --fail-on
- Exports to TXT, Markdown, JSON, CSV and SARIF, plus a --demo self-test with synthetic blobs

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage


```bash
./OSerial --scan ./src --format sarif -o deser.sarif
./OSerial --blob payload.bin --show-opcodes
./OSerial --data "$B64_BLOB" --format-hint java --min-severity high
./OSerial --demo
./OSerial --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 275+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

Proprietary — © 2026 Owlsec LLC. All rights reserved.

*Tools are distributed as pre-built executables. Source code is proprietary.*

---

## 🔍 Verification & Transparency

This tool is closed-source. These files let you see exactly what is inside it,
without the source:

- [`SBOM.cdx.json`](SBOM.cdx.json) — CycloneDX inventory: SHA-256 of this
  binary, bundled CPython version, and every bundled library with its exact
  version and license. Feed it to Grype, Trivy or Dependency-Track to audit
  our dependencies for CVEs yourself.
- [`THIRD-PARTY-NOTICES.md`](THIRD-PARTY-NOTICES.md) — the full license text
  of every third-party component, extracted from this binary.

**No telemetry, no analytics, no licence check-in.** This tool does not phone
home. Verify that claim yourself:

```bash
sudo strace -f -e trace=network ./OSerial --help   # watch every network call
firejail --net=none ./OSerial --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)
