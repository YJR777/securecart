# SecureCart – CI/CD Security Pipeline for Django

SecureCart is a prototype e-commerce application built using Django 3.12, designed to demonstrate secure software delivery through integrated static and dynamic testing. This repository accompanies the report for WM240-24: *The Cyber Context of Software Engineering (Coursework 2)*.

## 🔒 Project Overview

SecureCart supports core e-commerce functionality including user registration, product browsing, and order placement. The system has been evaluated using:

- **Snyk CLI** for Static Application Security Testing (SAST)
- **OWASP ZAP** for Dynamic Application Security Testing (DAST)
- **GitHub Actions** for CI/CD automation
- **Render** for cloud deployment

Security is embedded into the development lifecycle, aligning with DevSecOps principles and promoting early detection of vulnerabilities.

---

## 🛠️ Local Setup

To run the project locally:

```bash
git clone https://github.com/YJR777/securecart.git
cd securecart
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
