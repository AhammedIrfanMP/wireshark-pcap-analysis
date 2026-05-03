# Wireshark PCAP Analysis — PurpleFox Exploit Kit Infection

> **Tool:** Wireshark | **Source:** malware-traffic-analysis.net  
> **Malware Family:** PurpleFox EK + NuggetPhantom | **Verdict:** ✅ Confirmed Infection + C2

---

## Summary

Analyzed a real-world PurpleFox Exploit Kit infection PCAP (10,389 packets, ~21 minutes). The victim machine visited a malicious landing page triggering a drive-by download. Malware performed check-ins, downloaded cabinet file payloads, established C2 beaconing to three servers, and began SMB lateral movement scanning.

---

## Key Findings

| Finding | Detail |
|---|---|
| Victim IP | 10.1.5.101 |
| Exploit Kit | www.nationalbiminitops.shop |
| Fake CDN | rawcdn.githack.cyou (typosquatted GitHub domain) |
| Payload | M0021.cab + M002.jpg (malware disguised as image) |
| C2 Servers | 60.12.109.73 · 59.45.79.40 · 58.64.128.29 |
| C2 Pattern | .moe URI beaconing on non-standard ports |
| Lateral Movement | SMB port 445 scanning — worm behavior |
| Fake User-Agent | MSIE 6.0 KewGad (PurpleFox identifier) |

---

## Wireshark Filters Used

```
dns
http
http.host contains "githack"
ip.addr == 58.64.128.29
tcp.port == 445
```

---

## Tools Used
Wireshark · VirusTotal · malware-traffic-analysis.net

## Full Write-up
Read the complete analysis on Medium → *https://medium.com/p/e7c267466e47?postPublishedType=initial*

