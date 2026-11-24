<div align="center">

# Jaime Muñoz Sánchez 👋

### Cloud & DevOps Engineer · Madrid, España

ASIR · Máster de Ingeniería MultiCloud & DevOps en Tajamar · Becado por la Fundación Alfonso Martín Escudero

**Infraestructura, automatización y seguridad para entornos Cloud y Edge.**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Perfil-0A66C2?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/jaime-mu%C3%B1oz-0780032b4/)
[![Portfolio](https://img.shields.io/badge/Portfolio-Notion-334155?style=for-the-badge&logo=notion&logoColor=white)](https://app.notion.com/p/Jaime-Mu-oz-S-nchez-13edfd61a87280e3bb64c6231fe66f37)
[![Email](https://img.shields.io/badge/Email-Contactar-475569?style=for-the-badge&logo=gmail&logoColor=white)](mailto:jaimemunz03@gmail.com)

</div>

---

## 👋 Sobre mí

Mi base es la administración de sistemas y redes. Trabajé como **Técnico de SecOps e Infraestructura en CDS, an HPE Company**, donde realicé tareas de automatización, bastionado y seguridad perimetral.

Me interesa construir y operar infraestructura **Cloud y Edge** con Linux, automatización, seguridad y observabilidad. Mi experiencia incluye monitorización de Kubernetes y trabajo en entornos distribuidos de telemetría con conectividad 5G.

---

## 🌟 Proyecto destacado

<div align="center">

### 🛡️ [Edge Security Agent](https://github.com/jqime/edge-sec-agent)

**Appliance de seguridad self-hosted · Orange Pi Zero 3 · ARM64 · DietPi**

</div>

Edge Security Agent es un appliance self-hosted para un nodo ARM64 de bajos recursos. Reúne hardening perimetral, monitorización y telemetría de honeypot, manteniendo la API y los datos operativos en el dispositivo.

**Arquitectura**

```mermaid
flowchart TB
    client["Cliente"] -->|"HTTPS :8443"| nginx["Nginx · TLS · Basic Auth"]
    nginx -->|"proxy a 127.0.0.1:5000"| api["Gunicorn + Flask"]
    api -->|"genera informe"| agent["sec-agent CLI"]
    api -->|"health e histórico"| db[("SQLite · WAL")]
    api -->|"lee en GET /api/honeypot/summary"| log["cowrie.json"]
    agent -->|"persiste métricas"| db
    api -->|"health check · 127.0.0.1:11434"| ollama["Ollama"]
    tailnet["Tailscale · interfaz restringida"] -->|"SSH :2222"| dropbear["Dropbear"]
    tailnet -->|"SSH :2223"| cowrie["Cowrie honeypot"]
    cowrie -->|"escribe eventos"| log
    rag["CLI RAG · entorno aislado"] -->|"lee"| log
    rag -->|"embeddings / consulta"| ollama
    rag --> vectors[("sqlite-vec · cowrie_vec.db")]
```

- **Perímetro y acceso:** Nginx en `:8443` aplica TLS 1.2/1.3, Basic Auth y rate limiting. El firewall restringe Dropbear `:2222` y Cowrie `:2223` a la interfaz Tailscale; Gunicorn solo escucha en `127.0.0.1:5000`.
- **API y observabilidad:** Flask ofrece health checks y métricas Prometheus; SQLite/WAL conserva las métricas. El endpoint de resumen de Cowrie lee sus eventos JSON sin exponer credenciales ni comandos.
- **Análisis local:** Ollama escucha en `127.0.0.1:11434`. Flask comprueba su disponibilidad; `/v1/chat/completions` ejecuta `sec-agent` para generar un informe, no un chat LLM general. El RAG de Cowrie es una CLI separada que usa Ollama y `sqlite-vec`.
- **Automatización y ARM64:** systemd ejecuta el watchdog y las copias horarias; las actualizaciones seguras son opt-in. El proyecto está dirigido a Orange Pi Zero 3 / ARM64 con DietPi; el bootstrap documenta Debian 13 ARM64 y compatibilidad con DietPi. Docker Compose es solo para QA/simulación.

El honeypot escucha en `:2223`, pero el firewall solo permite tráfico desde Tailscale; no se expone a Internet por defecto.

---

## 🧰 Tecnologías

**Cloud y plataformas**

![Kubernetes](https://img.shields.io/badge/Kubernetes-k3s-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-AWX-EE0000?style=flat-square&logo=ansible&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-CI-2088FF?style=flat-square&logo=githubactions&logoColor=white)

- **Profesional:** Kubernetes (k3s), Traefik Ingress.
- **Proyecto personal:** Orange Pi Zero 3 / ARM64.
- **En formación:** AWS y Microsoft Azure.

**DevOps y automatización**

- **Profesional:** Ansible, AWX e infraestructura como código.
- **Proyecto personal:** GitHub Actions para CI; Docker Compose solo en QA/simulación.
- **En preparación:** certificación GitHub Actions GH-200.

**Sistemas y redes**

![Debian](https://img.shields.io/badge/Debian-13-A81D33?style=flat-square&logo=debian&logoColor=white)

- **Profesional:** Linux y Debian 13.
- **Proyecto personal:** DietPi, systemd y Tailscale sobre ARM64.
- **Otros entornos y redes:** Ubuntu y WireGuard.

**Seguridad y observabilidad**

![Suricata](https://img.shields.io/badge/Suricata-IDS%2FIPS-1F4E79?style=flat-square)

- **Profesional:** OPNsense, Suricata IPS, UFW, Fail2Ban y Auditd.
- **Proyecto personal:** Nginx, TLS 1.2/1.3, Cowrie, métricas Prometheus y SQLite/WAL.
- **Laboratorio:** Kali Linux, Nmap, Hping3, Tcpdump, Wireshark, Netcat, Hack The Box y Elastic Stack.

**Programación y scripting**

- **Proyecto personal:** Python, Bash y Makefile.

---

## 💼 Experiencia profesional

### Técnico de SecOps e Infraestructura · CDS, an HPE Company

**Marzo 2026 – Mayo 2026** · Las Rozas de Madrid, España

- Automatización de infraestructura con **Ansible y AWX** para el bastionado de servidores Debian 13.
- Configuración de reglas perimetrales en **OPNsense** e inspección de tráfico con **Suricata IPS**.
- Bastionado y auditoría local mediante **UFW, Fail2Ban y Auditd**.
- Mantenimiento y monitorización de clústeres **Kubernetes (k3s)** con Traefik Ingress.
- Trabajo en entornos distribuidos de telemetría con conectividad **5G**.

---

## 🎓 Formación y certificaciones

- **Máster de Ingeniería MultiCloud & DevOps** · Tajamar · Septiembre 2026 – Presente · Beca de la Fundación Alfonso Martín Escudero.
- **Técnico Superior en Administración de Sistemas Informáticos en Red (ASIR)** · DigitechFP · 2024–2026.
- **Bachillerato** · IES Jaime Ferrán · 2024.

**Certificaciones obtenidas**

- **IBM:** Cybersecurity Professional Certificate; Incident Response and Systems Forensics.
- **Google:** Google Cybersecurity Professional Certificate; IA & Productividad.
- **Cisco:** Introduction to Cybersecurity.

**En preparación**

- **Microsoft Azure:** AZ-104 / AZ-500.
- **AWS:** Solutions Architect Associate (SAA-C03).
- **GitHub Actions:** GH-200.

---

## 📊 GitHub

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=jqime&show_icons=true&theme=transparent&hide_border=true" alt="Estadísticas de GitHub de Jaime" />

<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=jqime&layout=compact&theme=transparent&hide_border=true" alt="Lenguajes más utilizados" />

</div>
