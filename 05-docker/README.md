# 🐳 Docker Fundamentals — Day Log

A hands-on learning log documenting my first steps with Docker container management and server deployment.

---

## 📋 What I Learned

### Container Lifecycle Management
| Command | Description |
|--------|-------------|
| `docker run -d --name my-debian debian sleep infinity` | Run a detached Debian container in the background |
| `docker start my-debian` | Start a stopped container |
| `docker stop my-debian` | Gracefully stop a running container |
| `docker ps -a` | List all containers (running + stopped) |
| `docker exec -it my-debian bash` | Open an interactive shell inside the container |

---

## 🛠️ Hands-On Practice

- Launched a **Debian container** in detached mode using the `-d` flag
- Used `sleep infinity` to keep the container alive without a foreground process
- Accessed the container's shell interactively via `exec -it`
- **Built and ran a web server** inside an isolated Docker container
- Practiced stopping, starting, and inspecting container states

---

## 💡 Key Takeaways

> Docker containers are lightweight, isolated environments — perfect for running services like web servers without polluting the host system.

- The `-d` flag runs containers in the **background** (detached mode)
- `docker ps -a` shows **all** containers, not just running ones
- `exec -it` gives you a **live terminal** inside any running container

---

## 🗓️ Date
June 29, 2026

## 🧰 Stack
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Debian](https://img.shields.io/badge/Debian-A81D33?style=flat&logo=debian&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)
