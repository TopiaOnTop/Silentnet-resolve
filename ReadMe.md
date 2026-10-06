# SilentNet - Blockchain C2 Domain Resolver

An interactive, single-page web dashboard designed for security researchers and SOC analysts to resolve and monitor Command and Control (C2) domains hidden within smart contracts on the Polygon network.

🌐 **Live Demo:** [topiaontop.github.io/silentnet-resolve](https://topiaontop.github.io/silentnet-resolve)

---

## 🔍 Overview

Certain malware strains leverage public Ethereum-compatible smart contracts (such as on Polygon mainnet) as a decentralized dead-drop resolver to dynamically fetch their active C2 domain. Since smart contract storage is publicly accessible, this tool allows defenders to:

1. **Extract Active C2 Domains:** Directly query the target contract's `getDomain()` function (`0xce6d41de`) via public RPC nodes.
2. **Proactive Blacklisting:** Identify newly updated C2 domains before malware endpoints pull the updated configuration.
3. **Export IoCs:** Download key indicators of compromise in JSON format for SIEM/SOAR integration.

---

## 🚀 Key Features

* **Client-Side Resolution:** Zero backend requirements—queries public Polygon RPC endpoints directly from the browser using standard JSON-RPC (`eth_call`).
* **Multi-Node Fallback:** Automatically cycles through public RPC nodes to ensure reliable response times and bypass rate limits.
* **ABI Hex Decoder:** Native JavaScript parser that decodes raw EVM dynamic string responses (`offset` + `length` + `data`).
* **Threat Intel & Code Inspection:** Includes threat metadata, contract analysis, and a reconstructed Solidity implementation (`C2Resolver.sol`) of the target contract.
* **IoC Export:** One-click JSON export for quick sharing and blocking.

---

## 🛠️ Usage

1. Open the web interface at [topiaontop.github.io/silentnet-resolve](https://topiaontop.github.io/silentnet-resolve).
2. Click **Execute Live RPC Query** to query the smart contract.
3. Review the extracted C2 domain and status logs across the RPC endpoints.
4. Click **Export IoCs (JSON)** to save the indicators for your security ecosystem.

---

## ⚠️ Disclaimer

This tool is created strictly for educational, defensive, and threat intelligence research purposes. It helps security personnel identify and mitigate malicious infrastructure.
