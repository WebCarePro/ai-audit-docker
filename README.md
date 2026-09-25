<div align="center">

# 🐳 WebCarePro • AI & GEO Audit Docker Tool
### Free Self-Hosted Diagnostic Engine for Technical SEO, Core Web Vitals, AI Crawlers & Model Context Protocol (MCP)

[![Docker Pulls](https://img.shields.io/docker/pulls/mirabba/wcp-ai-audit?style=for-the-badge&logo=docker)](https://hub.docker.com/r/mirabba/wcp-ai-audit)
[![Ubuntu](https://img.shields.io/badge/Ubuntu-24.04_LTS_(Noble)-E95420?style=for-the-badge&logo=ubuntu)](https://ubuntu.com/)
[![Nginx](https://img.shields.io/badge/Nginx-Reverse_Proxy-009639?style=for-the-badge&logo=nginx)](https://nginx.org/)
[![Node.js](https://img.shields.io/badge/Node.js-22_LTS-339933?style=for-the-badge&logo=nodedotjs)](https://nodejs.org/)

<p align="center">
  <strong>Pre-built Public Docker Container · Built-in Nginx Reverse Proxy · High Concurrency · Zero Cloud Dependencies</strong>
</p>

</div>

---

## 📌 About The Tool

**WebCarePro AI & GEO Audit Tool** is a self-hosted web application that audits websites for **AI Search Engines** (Perplexity, ChatGPT Search, Claude, Google Gemini/SGE) and **Generative Engine Optimization (GEO)**.

### ✨ Key Features
- 🔍 **44+ Checkpoints**: Tests for AI bot crawlers (`GPTBot`, `ClaudeBot`, `PerplexityBot`), `llms.txt`, JSON-LD Schema, OpenGraph, and Core Web Vitals.
- ⚔️ **Side-by-Side Site Benchmark**: Compare any target URL directly against a competitor's site.
- 📄 **PDF Report Generation**: Export instant downloadable audit reports.
- 🤖 **AI Config Generator**: Interactive tool to build optimized `robots.txt` and `llms.txt` files.
- ⚡ **Built-in Nginx Reverse Proxy**: Pre-configured Gzip compression, static caching, and extended timeouts for long audit streams.

---

## 🚀 How to Download & Run

You do **not** need the source code to run this container. Simply use Docker CLI or Docker Compose.

### Option 1: Quick Run via Docker CLI

Run the pre-built image directly from Docker Hub:

```bash
docker run -d \
  --name wcp-ai-audit \
  -p 80:80 \
  -v wcp_ai_audit_data:/app/data \
  mirabba/wcp-ai-audit:latest
```

After launching, open your browser and navigate to:
👉 **`http://localhost`**

---

### Option 2: Docker Compose Setup

Create a `docker-compose.yml` file anywhere on your server:

```yaml
version: '3.8'

services:
  wcp-ai-audit:
    image: mirabba/wcp-ai-audit:latest
    container_name: wcp-ai-audit
    restart: unless-stopped
    ports:
      - "80:80"
    environment:
      - NODE_ENV=production
      - SCAN_RETENTION_DAYS=365
      # Optional: Google PageSpeed API Key
      - PAGESPEED_API_KEY=
      # Optional: Discord Webhook URL for scan notifications
      - DISCORD_WEBHOOK_URL=
    volumes:
      - ai_audit_data:/app/data
      - ai_audit_pdfs:/app/public/assets/scan

volumes:
  ai_audit_data:
  ai_audit_pdfs:
```

Start the container:

```bash
docker compose up -d
```

To view logs:

```bash
docker compose logs -f
```

To stop:

```bash
docker compose down
```

---

## ⚙️ Data Persistence & Volumes

| Container Path | Host / Volume | Purpose |
|---|---|---|
| `/app/data` | `ai_audit_data` | Persistent local SQLite/JSON database storing audit reports |
| `/app/public/assets/scan` | `ai_audit_pdfs` | Cached generated PDF reports |

---

## 📄 License & Links

- **Maintained by**: [WebCarePro](https://webcarespro.com)
- **Live Demo / Web Tool**: [https://webcarespro.com/ai-audit](https://webcarespro.com/ai-audit)
- **Docker Hub**: [https://hub.docker.com/r/mirabba/wcp-ai-audit](https://hub.docker.com/r/mirabba/wcp-ai-audit)
- **License**: MIT License - Free for personal & enterprise use.
