# npx skills add https://github.com/kroegha/kali-docker-pentesting --skill kali-docker-pentesting

# 🚀 Cómo Usar (Quick Start)

Este repositorio es una **Skill para Agentes IA** (como Gemini Code o Claude). Permite ejecutar herramientas de pentesting de forma ultra eficiente.

### 🤖 Con un Agente IA (Gemini/Claude)
Si estás usando este proyecto con un agente, simplemente dale órdenes en lenguaje natural. **Yo me encargo del resto.**
- *"Escaneá la IP 10.0.4.125 con nmap buscando puertos y versiones."*
- *"Corré un nikto contra http://10.0.4.125 para buscar vulnerabilidades web."*
- *"Usá gobuster para encontrar directorios en 10.0.4.125."*

### 💻 Uso Manual (Terminal)
Si preferís tirar los comandos vos, asegurate de tener el contenedor corriendo (`docker-compose up -d`) y ejecutá:
```bash
docker exec kali-pentest [herramienta] [opciones]
```
*Ejemplo:* `docker exec kali-pentest nmap -sV 10.0.4.125`

---

# Herramientas en kali-docker-pentesting

Este documento contiene la lista de herramientas incluidas en el contenedor de Kali Docker para pentesting, organizadas por categorías.

## 🔍 Network Discovery & Scanning (Descubrimiento y Escaneo de Red)
* **nmap**: Network Mapper para descubrimiento de hosts y auditoría de seguridad.
* **masscan**: Escaneador de puertos TCP de alto rendimiento.
* **netdiscover**: Herramienta de reconocimiento de direcciones ARP activa/pasiva.
* **arp-scan**: Escaneador ARP para descubrir hosts IPv4 en redes locales.

## 🌐 Web Application Testing (Pruebas de Aplicaciones Web)
* **nikto**: Escaneador de servidores web para encontrar archivos peligrosos y vulnerabilidades.
* **dirb**: Analizador de contenido web mediante fuerza bruta basado en diccionarios.
* **gobuster**: Herramienta para enumerar URIs (directorios y archivos) y subdominios DNS.
* **wfuzz**: Herramienta de fuzzing para aplicaciones web.
* **sqlmap**: Herramienta automática para detección y explotación de inyecciones SQL.
* **wpscan**: Escaneador de vulnerabilidades para sitios basados en WordPress.
* **whatweb**: Identificador de tecnologías web (CMS, plataformas de blogs, etc.).

## 🔐 Password Attacks (Ataques de Contraseña)
* **john**: John the Ripper, craqueador de contraseñas rápido.
* **hashcat**: Herramienta de recuperación de contraseñas basada en GPU y CPU.
* **hydra**: Herramienta de inicio de sesión paralelo muy rápida que soporta numerosos protocolos.
* **medusa**: Craqueador de login modular, paralelo y rápido.
* **crunch**: Generador de listas de palabras (wordlists) personalizadas.

## 📡 Wireless Security (Seguridad Inalámbrica)
* **aircrack-ng**: Suite completa para evaluar la seguridad de redes WiFi.
* **wifite**: Herramienta automatizada para ataques a redes inalámbricas.
* **reaver**: Implementación de ataque de fuerza bruta contra el PIN WPS.

## 🕵️ Information Gathering (Recopilación de Información)
* **theharvester**: Herramienta para obtener correos, subdominios, nombres de host e IPs de fuentes públicas.
* **dnsrecon**: Herramienta de enumeración de DNS.
* **sublist3r**: Herramienta de enumeración de subdominios mediante OSINT.
* **enum4linux**: Herramienta para enumerar información de sistemas Windows y Samba.
* **dmitry**: Deepmagic Information Gathering Tool para recopilación profunda de datos.

## 🛡️ Exploitation Frameworks (Frameworks de Explotación)
* **metasploit-framework**: Plataforma para pruebas de penetración y desarrollo de exploits.
* **msfvenom**: Combinación de msfpayload y msfencode para generar payloads.
* **social-engineer-toolkit (SET)**: Framework para ataques de ingeniería social.

## 🔬 Forensics & Analysis (Forense y Análisis)
* **binwalk**: Herramienta para analizar, realizar ingeniería inversa y extraer archivos de firmware.
* **foremost**: Programa para recuperar archivos basado en sus encabezados y estructuras.
* **volatility**: Framework para análisis forense de memoria RAM.
* **strings**: Utilidad para extraer cadenas de caracteres imprimibles de archivos binarios.
* **exiftool**: Librería y aplicación para leer y escribir información meta (Exif) en archivos.

## 🔄 Reverse Engineering (Ingeniería Inversa)
* **ghidra**: Suite de ingeniería inversa desarrollada por la NSA.
* **radare2**: Framework avanzado de ingeniería inversa y análisis de binarios.
* **gdb**: El depurador estándar del proyecto GNU.

## 🎯 Vulnerability Assessment (Evaluación de Vulnerabilidades)
* **lynis**: Herramienta de auditoría de seguridad para sistemas basados en Unix/Linux.
* **openvas**: Escaneador de vulnerabilidades de red con funciones completas.

## 📊 Network Analysis (Análisis de Red)
* **tcpdump**: Analizador de paquetes de red de línea de comandos.
* **tshark**: Analizador de protocolos de red (versión de terminal de Wireshark).
* **ettercap**: Herramienta para ataques "Man-in-the-Middle" en redes locales.
