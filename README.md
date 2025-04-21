# 🐳 Multi-Arch Docker Python App

This project demonstrates how to build and push a **multi-platform Docker image** using `docker buildx`, based on a simple **Python Flask web app**.

It supports:
- `linux/amd64`
- `linux/arm64`

---

## 🚀 App Overview

This is a minimal Python web app that responds with:

" 🚀Hello from a Multi-Arch Python App!"

You can view it at `http://localhost:5000` after running the container.

---
## 📁 Files in This Project

- `app.py` – A simple Python Flask web app that responds on `/`
- `requirements.txt` – Declares Flask dependency
- `Dockerfile` – Used to build a multi-arch image with Buildx
- `README.md` – You're reading it!

You can view the source code in this repo directly.
---

## Docker Buildx Commands

To build and push this image for multiple platforms:

```bash
docker buildx create --name mybuilder --use
docker buildx inspect --bootstrap

docker buildx build \
  --platform linux/amd64,linux/arm64 \
  -t yourdockerhubusername/multi-arch-python-demo:latest \
  --push .


Replace yourdockerhubusername with your Docker Hub username.

## Test the Image

```bash
docker run -p 5000:5000 yourdockerhubusername/multi-arch-python-demo:latest

Then visit: http://localhost:5000

Verify Supported Platforms
```bash
docker buildx imagetools inspect yourdockerhubusername/multi-arch-python-demo:latest

## Summary

This project shows how to:

Use Docker Buildx for multi-architecture builds

Package a Python app into a cross-platform container image

Run it on Intel, ARM, or any supported architecture


---
