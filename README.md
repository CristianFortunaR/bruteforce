
# 🔑 HTTP Login Bruteforce Script (Python)

A simple proof-of-concept for brute-forcing username and password fields on a vulnerable HTTP login endpoint. This was developed as part of my cybersecurity learning journey and CTF practice.

---

## ⚠️ Disclaimer
> This script is intended **only for educational purposes** and should **never be used on systems without explicit permission**. Unauthorized use may be illegal and unethical.

---

## 📌 Features:
- Character-by-character brute-force for both username and password fields
- Supports full printable ASCII range (except `*`, which is used as a wildcard in this implementation)
- Basic error handling and retry logic for unstable connections
- Works by detecting server-side error messages (e.g., `"No search results."`)

---

## 🚀 How It Works:
The script performs a timing-based character enumeration, using a wildcard (`*`) at the end of each guessed string to probe the server and infer partial correctness.

1. Iterates over printable ASCII characters
2. Sends POST requests with incrementally guessed values
3. Parses HTTP response looking for specific strings that indicate success or partial correctness
4. Continues until both username and password are fully discovered

---

## 🛠️ Usage:

```bash
python3 bruteforce.py
```

Make sure to edit the `url` variable inside the script to match your test target.

---

## ✅ Requirements:

- Python 3.x
- `requests` library (`pip install requests`)

---

## 📄 Important Notes:
- This is **not production-grade code**. It’s designed for controlled lab environments.
- The target server used in the original lab responded with `"No search results."` for partially valid credentials. You’ll need to adjust this logic based on your target’s behavior.

---

## 🧑‍💻 Author:

**Cristian Fortuna Reis**  
[GitHub Profile](https://github.com/cristianfortuna)  
[LinkedIn](https://www.linkedin.com/in/cristianFortunaReis)

---

## 🛡️ Ethical Reminder:
Use responsibly. Always have explicit permission before running any kind of penetration testing tools on live systems.

