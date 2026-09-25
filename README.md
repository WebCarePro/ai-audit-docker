<div align="center">

# 🚀 WebCare Pro • AI & GEO Readiness Audit Tool
### Enterprise Diagnostic Engine for Technical SEO, Core Web Vitals, AI Crawlers & Model Context Protocol (MCP)

[![Ubuntu](https://img.shields.io/badge/Ubuntu-26.04_LTS-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)](https://ubuntu.com/)
[![Nginx](https://img.shields.io/badge/Nginx-Reverse_Proxy-009639?style=for-the-badge&logo=nginx&logoColor=white)](https://nginx.org/)
[![Node.js](https://img.shields.io/badge/Node.js-26-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)](https://nodejs.org/)
[![Next.js 16](https://img.shields.io/badge/Next.js-16.3.3_Standalone-black?style=for-the-badge&logo=next.js&logoColor=white)](https://nextjs.org/)
[![React 19](https://img.shields.io/badge/React-19.2.8-61dafb?style=for-the-badge&logo=react&logoColor=black)](https://react.dev/)
[![Docker Pulls](https://img.shields.io/docker/pulls/mirabba/wcp-ai-audit?style=for-the-badge&logo=docker&logoColor=white)](https://hub.docker.com/r/mirabba/wcp-ai-audit)

<p align="center">
  <strong>Self-Hosted · 42+ Technical Checkpoints · Embedded Nginx Reverse Proxy · Local JSON Database · Zero Vendor Lock-In</strong>
</p>

</div>

---

A complete, self-hosted web application and automated diagnostic engine for evaluating websites across **AI Search Engines** (ChatGPT Search, Perplexity, Claude, Google Gemini/SGE), **Generative Engine Optimization (GEO)**, **Model Context Protocol (MCP)**, and **Google Core Web Standards**.

Powered by **Next.js 16 (App Router with Turbopack)** running securely on **Ubuntu 26.04.1 LTS** with an embedded **Nginx Reverse Proxy** delivering high-speed gzip compression, static chunk caching, and deep crawler proxy buffering.

---

## ✨ Key Features & Audit Capabilities

### 🔍 1. Deep AI & Search Engine Evaluation (42+ Rules)
- **12+ AI Crawlers Audited**: Evaluates real-time crawl permissions for GPTBot, OAI-SearchBot, PerplexityBot, ClaudeBot, Google-Extended, Applebot, Bytespider, Amazonbot, and more.
- **Generative Engine Optimization (GEO)**: Analyzes unstructured LLM readiness, `llms.txt`, `/llms-full.txt`, semantic markdown structure, and AI discovery protocols.
- **Model Context Protocol (MCP)**: Detects MCP server descriptors (`mcp.json`, `ai-plugin.json`) and agent discoverability.
- **Technical SEO & Structured Data**: Validates Schema.org JSON-LD (Organization, WebSite, FAQPage, BreadcrumbList), canonical tags, robots headers, and OpenGraph/Twitter social cards.
- **Google Standards & Core Web Vitals**: Integrated PageSpeed Insights analysis checking LCP, INP, CLS, TTFB, and responsive viewport geometry.

### 📊 2. Competitive Site Comparison (`/compare`)
- Direct side-by-side benchmark comparing two domains across all 5 technical scoring categories.
- Real-time delta score indicators with granular checkpoint breakdowns.

### 📄 3. Enterprise PDF Report Generation
- Native PDF rendering using **PDFKit** with branded headers, category scorecards, visual badges, and complete technical findings.
- One-click print-to-PDF layout with dedicated executive print stylesheets.

### 🛡️ 4. Turnkey Production Stack
- **Embedded Nginx Reverse Proxy**: Pre-configured for port `80`, handling client request buffering, gzip compression, and caching for Next.js static assets (`/_next/static/*`).
- **No External Database Required**: Uses a high-speed local filesystem JSON storage system with automated directory initialization.
- **Fast Domain Scans**: Direct scan execution with optional benchmark leaderboard indexing.

---

## ⚡ Quick Start

### Option A: Run via Docker CLI (Recommended)

Run the container exposing port `80` with persistent storage:

```bash
docker run -d \
  --name ai-audit-tool \
  -p 80:80 \
  -v ai_audit_data:/app/data \
  --restart unless-stopped \
  mirabba/wcp-ai-audit:latest
```

Open your browser at:
- **`http://localhost`** (or `http://your-server-ip`)

---

### Option B: Run with Docker Compose

Create a `docker-compose.yml` file:

```yaml
services:
  ai-audit:
    image: mirabba/wcp-ai-audit:latest
    container_name: wcp-ai-audit
    restart: unless-stopped
    ports:
      - "80:80"
    volumes:
      - ./data:/app/data
      - ./scans:/app/public/assets/scan
    environment:
      - NODE_ENV=production
      - PORT=3000
      - HOSTNAME=127.0.0.1
```

Start the service:

```bash
docker compose up -d
```

View real-time logs:

```bash
docker compose logs -f
```

---

## ⚙️ Persistent Data & Volume Mounts

| Container Path | Purpose |
|---|---|
| `/app/data` | Persistent storage for all audit scan records (`./data/scans/*.json`) |
| `/app/public/assets/scan` | Cached PDF audit reports |

---

## 🛠️ WebCare Pro Infrastructure Services

WebCare Pro provides elite, direct 1-on-1 Linux server engineering, performance optimization, and infrastructure management by **Mir Alamin** without agency overhead or middlemen.

| Service | Focus & Deliverables |
|---|---|
| 🖥️ **[Managed Linux Server Administration](https://webcarespro.com/services/managed-server-administration)** | Dedicated sysadmin, OS hardening, kernel updates, security patching, Docker/container operations, and 24/7 proactive monitoring. |
| ⚡ **[Website Speed & Core Web Vitals](https://webcarespro.com/services/website-speed-optimization)** | 90–100 Google PageSpeed scores, LCP/INP optimization, advanced server caching (Redis, Varnish, FastCGI), and database query tuning. |
| 🛡️ **[Website Hack Recovery & Security Hardening](https://webcarespro.com/services/website-hack-recovery-security)** | Emergency malware removal, blacklist removal, WAF deployment, DDoS mitigation, and server-level intrusion prevention. |
| 🔄 **[Zero-Downtime Server Migration](https://webcarespro.com/services/website-transfer)** | Seamless server-to-server and cloud migrations (AWS, DigitalOcean, Hetzner, Vultr, Linode) with zero loss of data or downtime. |
| 🌐 **[Domain, DNS & Cloudflare Architecture](https://webcarespro.com/services/domain-dns-setup)** | Enterprise Cloudflare setup, DNSSEC, SSL/TLS full strict configuration, email deliverability records (SPF, DKIM, DMARC), and edge routing. |
| 🔧 **[Server Troubleshooting & Error Resolution](https://webcarespro.com/services/website-server-troubleshooting)** | Immediate diagnosis and resolution of 500 Internal Server Errors, 502/504 Bad Gateways, high CPU/RAM bottlenecks, and database deadlocks. |
| 🤝 **[White-Label Agency Support](https://webcarespro.com/services/white-label-agency-support)** | Invisible tier-3 server engineering and technical maintenance for web design and marketing agencies. |
| 📚 **[Operations Knowledge Hub](https://webcarespro.com/operations-hub)** | In-depth technical guides, sysadmin architectures, and DevOps benchmarks. |

👉 **[Explore All 12+ Professional Services](https://webcarespro.com/services)**

---

## 👨‍💻 About WebCare Pro & Mir Alamin

**WebCare Pro** is founded and operated by **Mir Alamin**, a senior Linux systems administrator and web infrastructure engineer with **10+ years of hands-on experience**.

- 🏆 **Upwork Top-Rated Freelancer**: Rated **4.9 / 5.0** across **528+ verified client reviews**.
- 📜 **40+ Verified Professional Certifications & Skill Badges** ([View Credly Profile](https://www.credly.com/users/miralamin/badges/credly)).
- 🚀 **680+ Completed Web Infrastructure & Optimization Projects**.
- 🌍 **100% Remote Global Operations**: Worldwide direct technical support without agency bureaucracy.

---

## 🔗 Connect & Direct Channels

| Channel | Contact & Link |
|---|---|
| 🌐 **Main Website** | [https://webcarespro.com](https://webcarespro.com) |
| 🔍 **Live AI Audit Engine** | [https://webcarespro.com/ai-audit](https://webcarespro.com/ai-audit) |
| 💬 **WhatsApp Direct** | [+880 1322-691090](https://wa.me/8801322691090) |
| 👥 **Microsoft Teams** | [Connect on Teams](https://teams.live.com/l/invite/FEAI60zv48mwbIKhA?v=g1) |
| 📧 **Direct Email** | [hello@webcarespro.com](mailto:hello@webcarespro.com) |
| 💼 **Upwork Profile** | [Mir Alamin on Upwork](https://www.upwork.com/freelancers/~0162afa9a578170c67) |
| 👔 **LinkedIn** | [linkedin.com/in/miralamin](https://www.linkedin.com/in/miralamin/) |
| 🐙 **GitHub** | [github.com/WebCarePro](https://github.com/WebCarePro) |
| 🐦 **X (Twitter)** | [@WebCarePro](https://x.com/WebCarePro) |
| 📘 **Facebook** | [facebook.com/WebCareProHQ](https://facebook.com/WebCareProHQ) |
| 🤖 **AI Agent Protocol** | [https://webcarespro.com/llms.txt](https://webcarespro.com/llms.txt) |

---

<div align="center">

### ⚙️ Build better infrastructure. Ship faster. Stay secure.

**WebCare Pro**  
*Infrastructure • Security • Performance • AI-Ready Web*

</div>
