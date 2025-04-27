# AirDrive-Dashboard (Barebone Laravel Heimdall Fork)

**AirDrive-Dashboard** is a barebone, production-grade fork of the original Heimdall Application Dashboard.  
Unlike most setups which rely on Docker containers, **AirDrive** offers a clean, lightweight, and scalable **bare-metal Laravel installation**.

This project is designed for **real servers**, **VPS deployments**, **dedicated cloud instances**, and integrates natively with **bare metal hosting platforms**.

---

## 🧠 Why AirDrive Instead of Docker Heimdall?

| Feature | AirDrive-Dashboard | Docker Heimdall |
|:---|:---|:---|
| Native PHP Laravel install | ✅ | ❌ |
| Fully configurable server environment | ✅ | ❌ |
| Scalable in cloud & datacenter environments | ✅ | ❌ |
| Instant integration with Cloud Portals | ✅ | ❌ |
| Lower memory usage, faster boot | ✅ | ❌ |
| True system administrator control | ✅ | ❌ |
| Production-ready from first boot | ✅ | ❌ |

---

## 🚀 Key Features

- Lightweight Laravel 10 framework
- No containers, no overhead
- Production `.env` settings ready
- Cloudflare SSL-Proxy ready (green lock on every deployment)
- Native SQLite3 database for easy, fast performance
- Auto-update system via Git cron job
- Manual safe-update script
- Full bare-metal Apache2 + PHP deployment

---

## 📋 Server Requirements

- Ubuntu 24.04 LTS
- Apache2
- PHP 8.3
- Composer
- SQLite3
- Git
- (Optional) Cloudflare account for SSL

---

## 📦 Quick Deployment (Cloud-Init)

When creating a new VM, attach the provided [cloud-init](cloud-init.yml) file:

- Installs all dependencies
- Clones latest GitHub code
- Sets up Laravel `.env`
- Creates SQLite database
- Configures Apache2
- Deploys portal on port 80 (HTTP)

✅ Cloudflare will terminate SSL at the edge automatically.

---

## 🔄 Automatic Update System

- Cron job checks GitHub daily at **3:00AM**
- Pulls new versions
- Installs new dependencies (composer)
- Reloads Apache
- Maintains permissions and security

Manual update possible any time:

```bash
bash /root/airdrive-safe-update.sh
