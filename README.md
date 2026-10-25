# 🦉 OSerial

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OForensics-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
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

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
