https://github.com/Daryl13344/Nigerian-dignity/releases

# Nigerian Dignity: Mapping Fintech and Scam Infrastructure 🚦🇳🇬

[![Releases](https://img.shields.io/badge/Release-download-blue?logo=github&style=for-the-badge)](https://github.com/Daryl13344/Nigerian-dignity/releases)  [![Topics](https://img.shields.io/badge/topics-cybercrime%20|%20fraud%20|%20phishing-lightgrey?style=flat-square)](#)

![Nigerian fintech and web infrastructure](https://images.unsplash.com/photo-1542751371-29b0f74f9713?q=80&w=1200&auto=format&fit=crop&ixlib=rb-4.0.3&s=1a5b1a1b2b3c4d5e6f7a8b9c0d)

About
- This repository documents a range of digital services and domain infrastructures tied to next-generation financial flows in Nigeria. The focus is on public indicators, domain patterns, registrar use, and delivery channels that shape both legal fintech and illicit operations.
- The material targets researchers, incident responders, and policy makers who track domain abuse, phishing campaigns, and abusive registrar behavior. Use the assets for analysis, detection, and remediation planning.

Why this repo
- Collect patterns and metadata that matter for detection.
- Share defensive heuristics for domain and registrar analysis.
- Offer a catalog of infrastructure signals to aid takedown and policy work.
- Support community analysis without sharing operational instructions.

Quick links
- Releases (assets for analysis): https://github.com/Daryl13344/Nigerian-dignity/releases
- If you download release assets, analyze them inside an isolated lab or sandbox. Do not run untrusted binaries on production systems.
- GitHub Issues: use this repo’s issue tracker for corrections and additional indicators.

Badges & topics
[![cybercrime](https://img.shields.io/badge/cybercrime-infrastructure-red?style=flat-square)](#) [![domain-registrar](https://img.shields.io/badge/domain--registrar-namesilo-blue?style=flat-square)](#) [![fraud](https://img.shields.io/badge/fraud-signals-yellow?style=flat-square)](#) [![icann](https://img.shields.io/badge/icann-policy-lightgrey?style=flat-square)](#) [![phishing](https://img.shields.io/badge/phishing-detection-orange?style=flat-square)](#) [![scam-infrastructure](https://img.shields.io/badge/scam--infrastructure-tracking-purple?style=flat-square)](#)

What you will find
- Domain inventories: CSV and JSON export of observed domains with registrar, creation date, nameservers, and WHOIS snapshots.
- Hosting footprints: IP ranges, ASNs, reverse DNS, and hosting provider metadata.
- Delivery channels: Email patterns, SMS gateways, message templates and headers (redacted).
- Tactics, Techniques, and Procedures (TTPs): High-level mapping of common abuse patterns, domain lifecycle, and takedown choke points.
- Detection rules: Example YARA-ish signatures, regexes for domain patterns, and suggested IDS/IPS patterns for defenders.
- Case studies: Structured descriptions of prominent campaigns, indicators that led to discovery, and post-takedown outcomes.

Repository layout
- /data
  - domains.csv — domain list with metadata
  - hosts.json — IP, ASN, provider metadata
- /analysis
  - reports/ — markdown case studies and timelines
  - patterns/ — regex and rule sets for detection engines
- /scripts
  - helpers/ — non-executable scripts for parsing CSV/JSON (review before running)
- /assets
  - diagrams and visualizations showing domain graphs and hosting clusters
- README.md — this file

How to use the materials (research & defense)
- Use the domain and host lists to tune SIG rules and blocklists.
- Compare registrar and nameserver patterns to spot bulk registrations.
- Correlate IP/ASN data with your existing telemetry to detect overlap.
- Feed static artifacts into offline analysis tools. Use sandboxing and virtualization for dynamic analysis.
- Share sanitized indicators with abuse desks, registrars, and CERT teams.

Safe handling of releases and artifacts
- The releases section contains analysis assets and capture files. Download assets only into a secure analysis environment.
- Do not execute any binaries from releases on your main workstation.
- Prefer static analysis first. Use network-isolated VMs for any dynamic runs.
- Hash each downloaded asset and compare with release metadata before analysis.

Analysis tips and practical checks
- WHOIS drift: track registrar changes and privacy toggles across time to spot churn.
- Nameserver reuse: many abusive operations reuse a small set of nameservers. Group by NS to reveal clusters.
- Registration velocity: use creation timestamps to flag bursts of registrations from single registrants.
- Similarity scoring: use edit distance on domain labels to catch lookalike and homoglyph domains.
- AS/Hosting correlation: map domains to ASNs to find hosting nodes that serve multiple abusive domains.

Example investigative workflow
1. Ingest domains.csv into a local database.
2. Enrich with passive DNS and ASN lookup.
3. Cluster by nameserver and registrar.
4. Generate a report for clusters with high churn and cross-check with spam traps and phishing lists.
5. Escalate verified abuse to provider and registrar with supporting metadata.

Contributing
- Open issues for missing indicators, corrections, or new case details.
- Submit pull requests to add verified indicators. Include source and method of verification.
- Sanitize personal data and remove active credentials before submitting.
- Follow the CONTRIBUTING.md file for signing-off and attribution rules.

Responsible use and ethics
- This repository serves defensive goals. Use the material for detection, research, policy, and mitigation.
- Avoid using collected indicators to target, harass, or commit takedown abuse.
- Respect local law and organizational policy when handling data.

Data sources and collection notes
- Public WHOIS, passive DNS, and hosting provider scans form the basis of the datasets.
- Community contributions from open reports and public blocklists help expand coverage.
- Timestamp each observation and include crawl source for reproducibility.

Visualization and images
- Use the assets folder for prebuilt graphs. Visualizations show domain-to-host graphs and timeline events.
- Example visual: a force-directed graph that groups domains by nameserver and ASN. (Image in assets/graph.png)

Integration ideas
- Feed domains.csv into SIEM for enrichment rules.
- Convert patterns/regex into WAF or email gateway rules after testing in staging.
- Export clusters into MISP or other threat-sharing platforms.

Legal and takedown guidance
- Prepare concise, evidence-backed notices when reporting abuse to registrars or hosts.
- Include domain, registrar, ASN, timestamps, and sample headers in reports.
- Share findings with ICANN-accredited registrars and local CERT teams when appropriate.

Release handling (note on downloads)
- Release artifacts are available at the Releases page linked at the top and in Quick links: https://github.com/Daryl13344/Nigerian-dignity/releases
- Download release assets for offline analysis. Verify hashes and inspect in a lab environment. Do not execute unknown binaries on production machines.

Contact and maintainers
- File issues on GitHub for corrections and joint research ideas.
- Use PRs for new datasets and improved analysis workflows.
- Include references and source citations in contributions.

License
- This repository uses a permissive license to enable research and defensive use. See LICENSE for details.

Acknowledgments
- Community researchers and abuse desks that share indicators and verification notes.
- Public data providers and open-source tooling used for enrichment and visualization.