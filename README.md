<div align="center">

# 監視 KANSHI

**Open-source OSINT platform for target reconnaissance**

![Ruby](https://img.shields.io/badge/Ruby_on_Rails-7.x-CC0000?style=for-the-badge&logo=rubyonrails&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-336791?style=for-the-badge&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-Sidekiq-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

> *KANSHI (監視) — Japanese for "surveillance". A web-based OSINT platform that automates domain, IP, username and email reconnaissance.*

</div>

---

## 📌 Overview

**KANSHI** is a full-stack OSINT platform built with Ruby on Rails. It allows security researchers and analysts to register targets and automatically gather intelligence from multiple public sources — running background jobs, aggregating results, and displaying everything in a clean terminal-styled dashboard.

Built as a portfolio project combining **cybersecurity**, **backend engineering**, and **DevOps**.

---

## ✨ Features

- 🔐 **Authentication** — Secure login and registration via Devise
- 🎯 **Target management** — Register domains, IPs, usernames and emails
- ⚙️ **Background OSINT jobs** — Async reconnaissance powered by Sidekiq + Redis
- 🌐 **WHOIS lookup** — Automated domain registration data
- 🔍 **DNS enumeration** — A, MX, NS, TXT records
- 🛡️ **VirusTotal integration** — Domain and IP reputation check
- 💧 **HaveIBeenPwned** — Email breach detection
- 📡 **Shodan integration** — Open ports and service detection
- 🤖 **Discord Bot** — Run OSINT commands directly from Discord *(coming soon)*
- 🕷️ **Web crawler** — Passive recon and metadata collection *(coming soon)*
- 📊 **Risk score** — Automated 0–100 risk rating per target *(coming soon)*
- 📄 **PDF export** — Full reconnaissance report per target *(coming soon)*

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Backend | Ruby on Rails 7 |
| Database | PostgreSQL 16 |
| Auth | Devise |
| Background jobs | Sidekiq + Redis |
| Containerization | Docker + Docker Compose |
| Dev environment | WSL2 (Ubuntu 22.04) |
| External APIs | Shodan · VirusTotal · HaveIBeenPwned |

---

## 🗂️ Project Structure

```
kanshi/
├── app/
│   ├── controllers/
│   ├── models/
│   │   ├── user.rb
│   │   └── target.rb
│   ├── jobs/
│   │   ├── whois_job.rb
│   │   ├── dns_job.rb
│   │   └── virustotal_job.rb
│   └── views/
├── config/
├── docker-compose.yml
├── Dockerfile
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

- WSL2 (Ubuntu 22.04) or Linux
- Ruby 3.3+
- Rails 7+
- PostgreSQL 16
- Redis
- Docker + Docker Compose *(optional)*

### Installation

```bash
# Clone the repository
git clone https://github.com/Kak3ru/KANSHI.IO.git
cd kanshi

# Install dependencies
bundle install

# Setup database
rails db:create db:migrate

# Start Redis (required for Sidekiq)
redis-server

# Start Sidekiq (background jobs)
bundle exec sidekiq

# Start the server
rails server
```

Access: `http://localhost:3000`

### With Docker

```bash
docker compose up --build
```

---

## ⚙️ Environment Variables

Create a `.env` file at the project root:

```env
# Database
DATABASE_URL=postgresql://postgres:password@localhost/kanshi_development

# APIs
SHODAN_API_KEY=your_key_here
VIRUSTOTAL_API_KEY=your_key_here
HIBP_API_KEY=your_key_here

# Discord Bot (optional)
DISCORD_BOT_TOKEN=your_token_here
```

---

## 🗺️ Roadmap

- [x] Project setup (Rails + PostgreSQL + Devise)
- [ ] Target CRUD + Dashboard
- [ ] WHOIS and DNS background jobs
- [ ] VirusTotal and HIBP integration
- [ ] Shodan integration
- [ ] Docker Compose full setup
- [ ] Discord Bot
- [ ] Web crawler module
- [ ] PDF report export
- [ ] Risk score engine
- [ ] Deploy (Fly.io / Railway)

---

## 🤝 Contributing

This is a portfolio project but contributions are welcome.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

---

<div align="center">

**Built by [Kakero](https://github.com/Kak3ru) · Fortaleza, Brazil**

*"O que não é visto, pode ser encontrado."*

</div>