# 🌐 Network Reconnaissance & Security Assessment — Home Network Lab

> Proyek network scanning dan security assessment terhadap jaringan pribadi menggunakan Nmap, dengan analisis risiko berdasarkan standar keamanan jaringan umum.

---

## ⚠️ Disclaimer

Seluruh aktivitas scanning dalam proyek ini dilakukan **secara eksklusif terhadap jaringan pribadi milik penulis sendiri**. Tidak ada sistem, jaringan, atau perangkat milik pihak ketiga yang menjadi target. Proyek ini dibuat untuk keperluan **edukasi dan portofolio semata**.

---

## 📋 Project Overview

| Item | Detail |
|------|--------|
| **Target** | Home Network (192.168.1.0/24) |
| **Environment** | Jaringan pribadi terkontrol |
| **Tool** | Nmap 7.98 |
| **Tipe Scan** | Service Version Detection & Aggressive Scan |
| **OS Penguji** | macOS (Apple MacBook Air, ARM) |
| **Tanggal** | 19 Februari 2026 |

---

## 🔍 Findings Summary

| Host | Device | Open Ports | Risk Level |
|------|--------|------------|------------|
| 192.168.1.1 | Router (Cisco-Linksys E4200) | 80, 49152 | 🟠 Medium |
| 192.168.1.5 | MacBook (Penguji) | 80, 5000, 7000 | 🟢 Low |

---

## 🛠️ Command yang Digunakan

```bash
# Scan seluruh subnet — deteksi host aktif dan service version
nmap -sV 192.168.1.0/24

# Aggressive scan terhadap router
nmap -A 192.168.1.1
```

---

## 📌 Temuan Utama

### 192.168.1.1 — Router Cisco-Linksys E4200 (🟠 Medium)
- **Port 80** terbuka — admin panel router dapat diakses via HTTP tanpa enkripsi
- **Port 49152** terbuka — layanan UPnP aktif, berpotensi dieksploitasi untuk modifikasi konfigurasi firewall

**Rekomendasi:** Ubah kredensial default router, nonaktifkan UPnP jika tidak digunakan.

### 192.168.1.5 — MacBook Penguji (🟢 Low)
- **Port 80** — DVWA berjalan di Docker (lab environment yang disengaja)
- **Port 5000 & 7000** — AirPlay macOS, normal dan tidak berbahaya

---

## 📚 Referensi

- [Nmap Documentation](https://nmap.org/docs.html)
- [OWASP Top 10 2021](https://owasp.org/Top10/)
- [CVE Database — UPnP Vulnerabilities](https://cve.mitre.org)

---

## 👤 Author

**[ALIZHA TIARA SYAFAHIRA]**  
[Sistem Informasi] — [Telkom University]  
[www.linkedin.com/in/alizhatiara | lizha.tiara@gmail.com]
