# 📱 Mobile Security Analysis — Snaptube APK
### Using MobSF (Mobile Security Framework) with Docker on Windows

---

## 🔍 About This Project

This project demonstrates a **static security analysis** of the **Snaptube APK** using **MobSF (Mobile Security Framework)** — an automated, all-in-one mobile application pen-testing and malware analysis framework.

> **Tool Used:** MobSF (mobsf.live)  
> **Platform:** Windows  
> **Analysis Type:** Static Analysis  
> **APK Analyzed:** Snaptubes.NET_20230822.apk (20.28 MB)

---

## 🚀 How to Run MobSF using Docker

### Prerequisites
- Docker Desktop installed on Windows
- Any APK file to analyze

### Steps

**Step 1 — Pull MobSF Docker Image**
```bash
docker pull opensecurity/mobile-security-framework-mobsf:latest
```

**Step 2 — Run MobSF Container**
```bash
docker run -it --rm -p 8000:8000 opensecurity/mobile-security-framework-mobsf:latest
```

**Step 3 — Open Browser**
```
http://localhost:8000
```
Default credentials: `mobsf / mobsf`

**Step 4 — Upload APK**
- Click "Upload & Analyze"
- Drag & Drop your APK file
- Wait for analysis to complete

---

## 📊 Analysis Results — Snaptube APK

### 🔐 Security Score
| Metric | Result |
|--------|--------|
| Security Score | **35 / 100** ⚠️ |
| Trackers Detected | **12 / 428** |
| Activities | 146 |
| Services | 34 |
| Receivers | 35 |
| Providers | 11 |

---

### ⚠️ Dangerous Permissions Found

| Permission | Risk Level | Description |
|------------|-----------|-------------|
| ACCESS_COARSE_LOCATION | 🔴 Dangerous | Access approximate network-based location |
| ACCESS_FINE_LOCATION | 🔴 Dangerous | Access precise GPS location |
| CAMERA | 🔴 Dangerous | Take pictures and videos anytime |
| GET_TASKS | 🔴 Dangerous | Retrieve running applications |

> These permissions can be misused to track user location and monitor device activity.

---

### 🕵️ Trackers Detected (12 total)

| Tracker | Category |
|---------|----------|
| AppLovin (MAX and SparkLabs) | Analytics, Profiling, Advertisement |
| Facebook Analytics | Analytics |
| Google AdMob | Advertisement |
| Google Firebase Analytics | Analytics |
| Google CrashLytics | Crash Reporting |
| IAB Open Measurement | Identification, Advertisement |
| Pangle | Advertisement |
| PubNative | Advertisement |
| Sensors Analytics | Analytics |
| Bugly | — |

> 12 trackers found — App heavily tracks user behavior for advertising purposes.

---

### 🌍 Server Locations
- App communicates with servers in **USA** and **Europe/China**
- App may communicate with **OFAC sanctioned countries**

---

### 📜 Signer Certificate
| Field | Value |
|-------|-------|
| Signed | ✅ Yes |
| Signature Type | v1 only (v2/v3/v4 missing — weak!) |
| Organization | wandoulabs |
| Location | Beijing, China |
| Valid From | 2010-09-07 |
| Valid To | 2060-08-25 |

> ⚠️ Only v1 signature — modern Android security recommends v2/v3/v4

---

## 🔎 Key Security Findings

1. **Low Security Score (35/100)** — App has multiple security issues
2. **Dangerous Permissions** — Location, Camera access without clear justification
3. **Heavy Tracking** — 12 trackers including Facebook, Google, AppLovin
4. **Weak Signing** — Only v1 signature scheme used
5. **Server Communication** — Connects to servers in China and USA
6. **High Tracker Count** — Privacy risk for users

---

## 🛠️ Tools & Technologies Used

- **MobSF** — Mobile Security Framework
- **Docker** — Container platform
- **Windows** — Host OS
- **Static Analysis** — APK reverse engineering

---

## 👤 Author

**Hepisha**  
GitHub: [@hepisha](https://github.com/hepisha)  
Cybersecurity Enthusiast | Mobile App Security

---

## 📄 License

This analysis is for **educational purposes only**.  
MobSF is licensed under GPL-3.0.
