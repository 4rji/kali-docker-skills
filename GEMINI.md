# Project Overview
This project contains an AI agent skill, `kali-docker-pentesting`, designed to provide token-efficient, direct access to a comprehensive Kali Linux Docker container equipped with over 200 pentesting tools. By using direct `docker exec` commands rather than MCP server protocols, it achieves ~70% token savings for the AI agent. The repository structure holds the skill configuration (`SKILL.md`), setup documentation (`QUICK-START.md`), a main `README.md` outlining categorized tools, and the necessary files for the Docker setup.

# Building and Running
The primary environment is managed via Docker.
- **Build Container:**
  - `docker-compose build` (recommended) or `docker build -t kali-comprehensive .`
- **Start Container:**
  - `docker-compose up -d` or `docker run -d --name kali-pentest -v $(pwd)/workspace:/workspace -v $(pwd)/results:/results --network host kali-comprehensive`
- **Stop Container:**
  - `docker-compose down` or `docker stop kali-pentest`
- **Execution Strategy for AI (Shell Commands):**
  - Use `docker exec kali-pentest <tool> [options]` directly via shell execution (e.g., `nmap`, `gobuster`, `nikto`, `sqlmap`).
- **File Management:**
  - Upload files: `docker cp ./local-file kali-pentest:/workspace/`
  - Download results: `docker cp kali-pentest:/results/file ./`
  - Mount paths typically include `/workspace` (working files) and `/results` (scan outputs).

# Development Conventions & Usage Rules
- **Direct Shell Execution:** Always prefer running tools via `docker exec kali-pentest ...` to preserve context efficiency instead of spawning separate persistent interactive shells, unless interactivity is strictly required.
- **Save Results Extensively:** Always utilize the output flags of the tools (e.g., `-oA`, `-w`, `-o`) to redirect outputs into the `/results/` directory inside the container to ensure persistence.
- **Ethical Testing Only:** Strictly adhere to scope boundaries, verify authorization for targets, and practice responsible disclosure. Only execute tools against authorized targets.
- **Token Efficiency:** The overarching goal of this setup is token-efficient execution. Use precise, scoped parameters for security tools to prevent bloated text outputs that consume excessive context.
- **Key Tool Categories included:** 
  - Network Scanning (nmap, masscan, netdiscover)
  - Web Application Testing (nikto, dirb, gobuster, sqlmap, wpscan)
  - Password Attacks (john, hashcat, hydra, crunch)
  - Wireless Security (aircrack-ng, wifite, reaver)
  - Info Gathering (theharvester, dnsrecon, enum4linux)
  - Forensics & Reversing (binwalk, volatility, ghidra, radare2)
