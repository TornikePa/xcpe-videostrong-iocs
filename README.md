XCPE / Videostrong IOC Collection
Curated indicators for defensive hunting related to the XCPE Android backdoor and the Videostrong device ecosystem.

Last updated: 2026-11-03
Contents
- [`xcpe_iocs.txt`](./xcpe_iocs.txt) - consolidated, raw IOC feed with source and context comments.
The feed separates core XCPE command-and-control infrastructure from related module and affiliate infrastructure. It also includes file hashes, Android package names, persistence artefacts, and device fingerprints reported by the cited research.
Hunting notes
- Prioritize outbound connections to the core XCPE IP addresses and domains. For MQTT-related activity, correlate the broker destinations with TCP ports 3885-3887.
- Treat ports as contextual indicators. A port match by itself is not evidence of XCPE activity; correlate it with the destination IP/domain, protocol, device identity, and connection history.
- Affiliate and module endpoints are listed separately from core XCPE C2. A match to one of these endpoints should be investigated in the context of the source device and observed traffic.
- Android package names, filesystem paths, certificate fingerprints, and device model strings are investigation pivots. A single match does not independently confirm compromise.
- Review historical DNS, firewall, and NetFlow records as well as current telemetry. Infrastructure disruption does not remove an implant already present in device firmware.
- Device model strings are not proof that every unit of a listed model is compromised.
Hash reputation
VirusTotal URLs in the feed are lookup links for the listed hashes. Current VirusTotal detection counts and verdicts were not retrieved for this publication; no detection ratio is asserted.
Sources
- Google Threat Intelligence Group, Shutting the Door on the XCPE Botnet, 2026-11-03.
- Synthient, The Internals of a Badbox Operation, 2026-11.
- BleepingComputer, Google disrupts million-device XCPE Android malware botnet, bans TV box maker, 2026-11.
Scope and handling
This is an analyst-curated collection based on the public sources above. It is not a claim of original discovery, and the indicators have not been independently observed in a specific environment. Some infrastructure may be historical or inactive following disruption activity.

Use the indicators for authorized defensive monitoring and investigation. Validate matches before blocking, especially for affiliate endpoints, generic ports, shared hosting, and model/package-name pivots.
