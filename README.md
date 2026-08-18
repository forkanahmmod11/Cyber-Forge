# CyberForge v6.2 — Adaptive Technology Website Security Analyzer

CyberForge is an authorized defensive assessment toolkit. It performs passive and low-impact checks only and requires explicit scope for network actions.

## Core capability
CyberForge now uses **Adaptive Technology Intelligence**. It first fingerprints the target stack, then selects relevant passive checks for the detected technologies. Unknown stacks still receive generic HTTP/TLS/API/configuration analysis.

### Technology coverage
- CMS/e-commerce: WordPress, WooCommerce, Drupal, Joomla, Magento/Adobe Commerce, Shopify, PrestaShop
- Frontend: React, Next.js, Vue, Nuxt, Angular, Svelte/SvelteKit, Astro, Ember, Backbone, jQuery, Bootstrap, Tailwind, TypeScript
- Backend: Node/Express, NestJS, Django, Flask, FastAPI, Laravel, Symfony, Rails, Spring Boot, ASP.NET/.NET, PHP, Go, Rust
- API/realtime: GraphQL, WebSocket, gRPC
- Cloud/CDN/edge: Cloudflare, AWS, Azure, Google Cloud, Vercel, Netlify, Render
- Web servers: Nginx, Apache, IIS, Caddy

Detection is evidence-based; a fingerprint is not treated as proof of a backend implementation.

## Adaptive analysis
```bash
./cyberforge --scope scope.txt adaptive-analysis https://YOUR-AUTHORIZED-DOMAIN
```

The adaptive engine:
1. Fetches the authorized target.
2. Detects technologies from HTML, script paths, cookies and response headers.
3. Records evidence for every fingerprint.
4. Selects technology-specific, scope-safe paths where applicable.
5. Falls back to generic analysis when the stack is unknown.

## Deep analysis
```bash
./cyberforge --scope scope.txt deep-audit https://YOUR-AUTHORIZED-DOMAIN
```

Deep analysis now includes the adaptive technology layer alongside web, TLS, DNS, GeoIP, Nmap/builtin fallback and port analysis.

## Module health
```bash
./cyberforge --scope scope.txt module-health
```

Current registry: **35/35 modules active**.

## Interactive mode
```bash
./cyberforge --scope scope.txt
```

Use option **35** for Adaptive Technology / Stack Analysis and **36** for Module Health Check.

## Scope
Create `scope.txt` with only assets you are authorized to assess:
```text
example.com
*.example.com
192.168.1.0/24
```

## Safety
CyberForge does not add credential attacks, brute force, exploitation, persistence, destructive actions or unauthorized access. Use it only on systems you own or have explicit permission to assess.


## Article-style text summaries
After `deep-audit` or `adaptive-analysis`, CyberForge automatically generates a readable Bengali text summary in `reports/` describing:
- overall risk and severity counts
- detected technology stack
- exactly what problem was found
- analysis module/area
- target/location where it was observed
- evidence
- recommended remediation
- prioritized remediation plan

You can also generate it manually:
```bash
./cyberforge article-summary --target https://YOUR-AUTHORIZED-DOMAIN
```


## Final result model
Every finding includes evidence, confidence, verification status, module/area, and remediation. Risk is independently recalculated per analysis and the article summary explains the score and finding contributions.


## Startup Safety Warning
CyberForge displays an authorization and limitations warning before every run. Use it only on assets you own or are explicitly authorized to assess. Automated findings require appropriate verification.

## URL-First Analysis

Run `./cyberforge` with no arguments. Choose a tool and enter its target
website URL. CyberForge creates a temporary host-only scope automatically,
so you do not need to create `scope.txt` for each website.

Persistent `--scope scope.txt` mode remains available for explicitly
authorized multi-host or wildcard assessments.

## Compliance Framework Gap Assessment

CyberForge 6.8 adds a technical compliance mapping engine for:

- **NIST CSF 2.0**
- **ISO/IEC 27001:2022 Annex A**
- **SOC 2 Trust Services Criteria**
- **PCI DSS 4.0.1**
- **EU GDPR — technical security controls**
- **HIPAA Security Rule — technical safeguards**
- **OWASP ASVS 5.0**
- **CIS Critical Security Controls v8.1**

Run all frameworks:
```bash
./cyberforge --scope scope.txt compliance-audit https://YOUR-AUTHORIZED-DOMAIN
```

Run selected frameworks:
```bash
./cyberforge --scope scope.txt compliance-audit https://YOUR-AUTHORIZED-DOMAIN --frameworks nist,iso27001,soc2,pci
```

Use the latest saved JSON report instead of rescanning:
```bash
./cyberforge compliance-audit --frameworks all
```

The engine maps observable technical evidence to framework controls and returns:
- control-by-control status: `OBSERVED_OK`, `PARTIAL`, `GAP`, or `NOT_ASSESSED`
- technical score per framework
- related findings and high-risk finding counts
- mapped CyberForge modules
- machine-readable JSON in `reports/`

**Important:** this is a technical gap-assessment aid, not a legal opinion, certification, SOC 2 attestation, PCI ROC/AOC, ISO certification, or proof of GDPR/HIPAA compliance. Organizational policies, governance, contracts, physical safeguards, evidence retention, privacy/legal review, and independent auditors remain necessary.

