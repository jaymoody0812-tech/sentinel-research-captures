# Sentinel Research Captures

Threat intelligence captures from the Sentinel Defense System live research honeypot.

**System:** [sentinel-defense-system.onrender.com](https://sentinel-defense-system.onrender.com)  
**Research program:** HALO — SUNY Oswego  
**Operator:** Jacob D. Moody

---

## Structure

```
captures/
  YYYY-MM-DD/
    {ip_underscored}/
      sentinel_dossier.json   — raw dossier: threat score, CVEs, behavioral timeline, Shodan data
      sentinel_report.html    — formatted TI report, opens in browser, prints to PDF
```

## What's captured here

Each entry represents a threshold capture (threat score ≥ 70) observed by the Sentinel honeypot.
Every dossier includes:
- IP address, geolocation, ISP
- Shodan threat tags, open ports, CVE count
- Behavioral timeline (endpoint sequence, lure hits, user agent)
- Intent classification (RECON / VULN_SCAN / CRED_HARVEST / EXPLOIT / MIXED)
- CCT behavioral signals: escalation velocity, co-regulatory response, micro-pacing, DCR flag
- Paradox score (UA class vs. navigation depth divergence)
- Swarm cluster membership

## How to push a new capture

After exporting from the Sentinel dashboard, run `push-capture.ps1` from the Desktop.
The script reads the most recent `sentinel_dossier_*.json` from Downloads, finds the matching HTML report, and commits both here.

## Research use

This data is published for academic and security research purposes.
All captures are from a live research honeypot operated under the HALO research program at SUNY Oswego.
See the companion invention disclosure (SUNY RF Portal, 2026) for the theoretical framework.

---
*Built on Cascade Compression Theory (CCT) — Moody, J.D., 2026, SUNY Oswego*
