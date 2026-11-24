<div align="center">

# Jaime Muñoz Sánchez 👋

### Cloud & DevOps Engineer · Madrid, España

**Infraestructura, automatización y seguridad para entornos Cloud y Edge.**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Perfil-0A66C2?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/jaime-mu%C3%B1oz-0780032b4/)
[![Portfolio](https://img.shields.io/badge/Portfolio-Notion-334155?style=for-the-badge&logo=notion&logoColor=white)](https://app.notion.com/p/Jaime-Mu-oz-S-nchez-13edfd61a87280e3bb64c6231fe66f37)
[![Email](https://img.shields.io/badge/Email-Contactar-475569?style=for-the-badge&logo=gmail&logoColor=white)](mailto:jaimemunz03@gmail.com)

</div>

---

## 👋 Sobre mí

Soy **Técnico Superior en Administración de Sistemas Informáticos en Red (ASIR)** y curso el **Máster de Ingeniería MultiCloud & DevOps en Tajamar**, becado por la Fundación Alfonso Martín Escudero. Entre marzo y mayo de 2026 trabajé como **Técnico de SecOps e Infraestructura en CDS, an HPE Company**.

Mi experiencia combina automatización de infraestructura, bastionado de sistemas y seguridad perimetral. Ahora estoy ampliando esa base hacia **Cloud, DevOps y Edge Computing**, con interés en construir entornos seguros y operables.

---

## 🧰 Tecnologías

**Cloud · DevOps · Automatización**

![Kubernetes](https://img.shields.io/badge/Kubernetes-k3s-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-AWX-EE0000?style=flat-square&logo=ansible&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-CI-2088FF?style=flat-square&logo=githubactions&logoColor=white)

- **Cloud** — **Profesional:** Kubernetes (k3s), Traefik Ingress. **Proyecto personal:** Edge sobre Orange Pi Zero 3 / ARM64. **En formación:** AWS y Microsoft Azure.
- **DevOps** — **Profesional:** automatización de infraestructura con Ansible y AWX. **Proyecto personal:** GitHub Actions; Docker Compose solo para QA/simulación. **En formación:** preparación de GH-200.
- **Automatización** — **Profesional:** Ansible, AWX e infraestructura como código. **Proyecto personal:** Python, Bash y Makefile.

**Sistemas · Ciberseguridad**

![Debian](https://img.shields.io/badge/Debian-13-A81D33?style=flat-square&logo=debian&logoColor=white)
![Suricata](https://img.shields.io/badge/Suricata-IDS%2FIPS-1F4E79?style=flat-square)

- **Sistemas** — **Profesional:** Linux y Debian 13. **Proyecto personal:** DietPi sobre ARM64, systemd y SQLite/WAL.
- **Ciberseguridad** — **Profesional:** OPNsense, Suricata IPS, UFW, Fail2Ban y Auditd. **Proyecto personal:** Nginx, TLS 1.2/1.3, Cowrie y Tailscale; Kali Linux, Nmap, Wireshark y otras herramientas en laboratorio.

---

## 🌟 Proyecto destacado

### 🛡️ [Edge Security Agent](https://github.com/jqime/edge-sec-agent)

**Appliance de seguridad self-hosted para Orange Pi Zero 3 · ARM64 · DietPi**

Edge Security Agent reúne hardening perimetral, observabilidad, telemetría de honeypot, informes con IA local y tareas de recuperación en un nodo de bajos recursos. La administración y la inferencia local no dependen de un servicio cloud.

**Arquitectura**

```mermaid
flowchart TB
    client["Cliente / operador"] -->|"HTTPS :8443"| proxy["Nginx · TLS · Basic Auth · rate limit"]
    proxy -->|"loopback :5000"| api["Gunicorn + Flask API"]
    api --> db[("SQLite / WAL")]
    api -->|"inferencia local"| ollama["Ollama · loopback :11434"]
    tailnet["Tailscale"] --> admin["Administración · Dropbear :2222"]
    tailnet --> cowrie["Cowrie honeypot · :2223"]
    cowrie -->|"eventos agregados"| api
```

- **Perímetro:** Nginx con TLS 1.2/1.3, autenticación, limitación de peticiones y cabeceras de seguridad; reglas de firewall persistentes y Fail2Ban.
- **API y observabilidad:** Flask detrás de Gunicorn, endpoints de salud y métricas Prometheus, y persistencia SQLite/WAL.
- **Operación:** Ollama local, copias de seguridad y restauración, watchdog y actualizaciones seguras opcionales.
- **Tecnologías:** Python, Flask, Gunicorn, Nginx, SQLite, Ollama, Cowrie y Tailscale. Docker Compose está limitado al entorno de QA/simulación.

El honeypot no se expone a Internet por defecto. Consulta el [repositorio](https://github.com/jqime/edge-sec-agent) para ver el código, la documentación y el estado del proyecto.

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

## 🎓 Formación & certificaciones

### Formación

- **Máster de Ingeniería MultiCloud & DevOps** · Tajamar · Septiembre 2026 – Presente
  Beca de la Fundación Alfonso Martín Escudero.
- **Técnico Superior en Administración de Sistemas Informáticos en Red (ASIR)** · DigitechFP · 2024–2026.
- **Bachillerato** · IES Jaime Ferrán · 2024.

### Certificaciones obtenidas

- **IBM:** Cybersecurity Professional Certificate; Incident Response and Systems Forensics.
- **Google:** Google Cybersecurity Professional Certificate; IA & Productividad.
- **Cisco:** Introduction to Cybersecurity.

### En preparación

- **Microsoft Azure:** AZ-104 / AZ-500.
- **AWS:** Solutions Architect Associate (SAA-C03).
- **GitHub Actions:** GH-200.

---

## 📊 GitHub

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=jqime&show_icons=true&theme=transparent&hide_border=true" alt="Estadísticas de GitHub de Jaime" />

<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=jqime&layout=compact&theme=transparent&hide_border=true" alt="Lenguajes más utilizados" />

</div>
