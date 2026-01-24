# Angry IP Scanner Guide

Angry IP Scanner is a free, open-source tool for scanning IP addresses and ports on local networks or public ranges. This guide transcribes a YouTube tutorial on its use for discovering devices and open services to "win arguments online" by gathering network facts.

## Download and Install

Open your web browser and go to angryip.org.

Downloads are available for Windows, Linux, Mac, and others. Click the Windows installer (includes Java runtime, recommended).

During installation, check "Run Angry IP Scanner" and uncheck options like password access if concerned about security; skip the built-in tutorial.

## IP Basics

Your subnet (e.g., 192.168.x.x) shows local IPs for devices inside your network like phones, laptops, smart TVs, or fridges.

Local IPs are only accessible within the network; public IPs (router's external address) are reachable worldwide.

The tool auto-fills your subnet range on launch.

## Basic Local Scan

Press **Start** to scan. Scanning completes quickly.

Colors indicate status:

- **Green**: Online, responds to pings, has open ports.
- **Red**: No ping response (offline or blocked).
- **Blue**: Online but no open ports.

Hostnames help identify devices (e.g., router). Many reds make lists messy.

## Filter Views

Click the **settings icon** (preferences). Under **Display**, select "Live hosts only" or "Hosts with open ports only".

Rescan: Now shows only blue/green (online devices), hiding reds.

## Port Scanning

Useful ports: 21 (FTP), 22 (SSH), 23 (Telnet), 80/443/8080 (HTTP/HTTPS), 445 (SMB), 3389 (RDP), 5900 (VNC).

In preferences > **Ports**, add ports (e.g., 80,443). Set "Hosts with open ports only" for greens. Rescan.

Right-click a host:

- **Open > Web browser** for port 80/443 (e.g., router login page).
- **Open > Windows shares** for 445 (SMB) to browse file systems—fast local file sharing without cloud.

Ping test confirms if still online.

## Public IP Scanning

Enter public ranges (not subnet). Add ports like 443, 8080.

For ranges, visit nearoft.net/net/country-ip (or similar IP lookup sites). Select country (e.g., China), copy first/last IP in range.

Scan large ranges takes time (e.g., 8.5 minutes for 70 hosts)—grab food or vacation.

## Public Results and Access

Open 80/443 in browser: May show login pages or downloads.

Port 21 (FTP): Copy IP, command prompt `ftp <IP>`—may prompt login (defaults often weak).

Port 22 (SSH): `ssh <IP>`—defaults vulnerable to brute-force if exposed.

**Warning**: Exposed SSH/Telnet/FTP to world risks attacks from unchanged defaults. Use VPN to hide your scans.

To avoid being scanned: Close unnecessary ports on router.

## Tips

Results vary by network/firewalls. Export or CLI for advanced use. Free, cross-platform, no install needed for portables.
