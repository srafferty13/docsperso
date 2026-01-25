# Robin AI Dark Web OSINT

Robin is an open-source AI-powered tool for legal dark web research, automating searches across Tor onion sites to filter real content from honeypots and law enforcement traps. Created by threat researcher Apurv Singh Gautam after meeting NetworkChuck at DEF CON, it uses LLMs to refine queries, scour 900+ results via 15+ engines, scrape top 20 sites, and generate summaries with next steps.

Most dark web is fake or controlled by authorities, making real threat intel hard to find due to slow Tor relays and sporadic site uptime.

## Dark Web Realities

Tor onion routing bounces traffic through relays for anonymity, but single node failures (like a Raspberry Pi unplug) break circuits, causing disconnects and restarts. Criminal sites operate only 2 days/week unpredictably, forcing constant rescraping.

Much appears "spooky real" but is show—honeypots to catch visitors; real forums require patience to infiltrate.

## Why Use Robin?

Turns 6-8 hour marathons into 30-minute sessions by AI-refining queries, filtering junk, scraping survivors, and suggesting follow-ups like forum monitoring. Exports Markdown for Obsidian; demos showed ransomware builders, Conti crypto addresses (BTC, XMR, LTC).

CLI and Streamlit GUI for queries like "ransomware" or personal emails to check leaks.

## Prerequisites

Docker for containerization; Tor daemon; Git; LLM API keys (OpenAI/ChatGPT, Anthropic, Ollama local). VPN mandatory before Tor to mask traffic—ISPs flag Tor as suspicious.

Linux/Mac native or WSL2 on Windows (install Ubuntu via `wsl --install`).

## Installation Steps

1. Verify/update Docker: `docker --version`; install if missing (links in video description).
2. Install Tor: `sudo apt install tor` (Linux/WSL) or `brew install tor` (Mac).
3. Clone: `git clone https://github.com/apurvsinghgautam/robin.git && cd robin`.
4. Setup env: `cp .env.example .env`; nano edit—add `OPENAI_API_KEY=sk-...` or `OLLAMA_BASE_URL=http://host.docker.internal:11434`.
5. Build: `sudo docker build -t robin .` (downloads BeautifulSoup etc., 2-5 mins).
6. Run GUI: `sudo docker run -p 8501:8501 --network=host -v $(pwd)/.env:/app/.env robin` (wait 1-2 mins for Tor handshake).

Open http://localhost:8501; select model, query.

## Live Demo Insights

NetworkChuck's first run: "ransomware" yielded 910→20 sites, scraped Builders, RCM, Conti forum with $500/hit claims. "Conti" exposed Doge/LTC/BTC/XMR addresses, actor profiles.

Tor browser links sometimes fail—retry; download reports for vaults.

## Safety Protocols

VPN+Tor chain; AI blocks NSFW/illegal (drugs/CSAM/hits)—still avoid. No downloads ever; US searches for CSAM = arrest risk even accidental.

Apurv's rules: guardrails not foolproof; heed GitHub disclaimer.

## Threat Research Workflow

Robin starts leads; lurk days/weeks building trust via sock puppets (burner phones/Telegram, no real recovery email). Maintain personas consistently—no slip-ups like mixing identities; note-take details/accent/slang.

Criminals spot feds via inconsistencies; wait for private Telegram/forum invites.

## Sponsor Context: ThreatLocker

Dark web sells Word/PowerShell exploits bypassing AV; ThreatLocker zero-trust blocks via Ringfencing (e.g., Word can't spawn PS). Learning mode auto-policies; MDR monitors 24/7—free trial at threatlocker.com/networkchuck.

## Homework & Resources

Search your email/name safely; comment findings (safe stuff only). Full Apurv interview: ransomware-as-service, Instagram OpSec fails.

GitHub: https://github.com/apurvsinghgautam/robin; NetworkChuck guide: https://github.com/theNetworkChuck/dark-web-scraping-guide

## Legal Disclaimer

For ethical OSINT/security pros only—no crime, drugs, CSAM. Users liable; build trust patiently as real researchers do.
