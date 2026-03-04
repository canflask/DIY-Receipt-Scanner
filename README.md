# DIY Receipt Scanner

[![License: AGPL-3.0](https://img.shields.io/badge/License-AGPL--3.0-blue.svg)](https://www.gnu.org/licenses/agpl-3.0.en.html)

**DIY Receipt Scanner** is a stripe receipt scanner with automatic filing and a local web server.  
The project is completely open-source and combines 3D printing, electronics, computer vision and web development.

---

## 🎯 Project goal

Create **an accurate and affordable receipt scanner** that can be assembled at home or in a makerspace.  
Main functions:

- Automatic receipt submission via a roller mechanism
- Band-pass scanning for high-precision OCR
- Local web interface for text viewing and basic analytics
- The ability to integrate with mobile applications and future ML-analysis of receipts

---

## 🧩 Architecture

```
[Receipt tray]
      ↓
[Capture rollers]
      ↓
[Illuminated tunnel]
      ↓
[Camera]
      ↓
[Raspberry Pi]
      ↓
[Python OCR + FastAPI]
      ↓
[Web UI + Analytics]
```

---

## ⚙️ Required skills of participants

- **Mechanics / Electronics:** Auto-feed assembly, stepper motor control, sensors  
- **Python / Computer Vision:** stripe image processing, OCR, stripe gluing  
- **Frontend / Web:** local interface, receipt analytics  
- **ML (optional):** check classification, improved recognition

---

## 🛠 Minimum set of components

- Raspberry Pi 5 + microSD 32–64 GB  
- Raspberry Pi Camera Module 3  
- NEMA 17 stepper motor + DRIVER (A4988 or TMC2208)  
- Rubber rollers, shafts, bearings  
- IR break-beam sensors (receipt availability/output)  
- LED strip 12V (4000–5000K) + power supply  
- Printed parts (PLA/PETG): housing, tunnel, roller holders, camera mount, trays

*(For a full list of components and upgrades, see [BOM.md ](./BOM.md ))*  

---

## 🖥 Software installation and launch

1. Install **Raspberry Pi OS** on microSD  
2. Connect the camera and motor drivers  
3. Install dependencies:

```
sudo apt update
sudo apt install python3-pip tesseract-ocr
pip install fastapi uvicorn opencv-python pytesseract sqlalchemy
```
Start the server:
```
uvicorn api:app --host 0.0.0.0 --port 8000
```
Open the web interface: http://<IP_RaspberryPi>:8000

The structure
of the repository
```
scanner/
 ├── motor.py # stepper motor control
 ├── camera.py # Image capture
 ├── ocr.py # OCR processing
 ├── parser.py # text extraction
 ├── database.py # receipt storage
 ├── api.py # FastAPI server
 ├── web/             # frontend
 └── 3D_models/       # STL print files
```
# Road map

[-] Band-pass scanning

[-] Automatic receipt submission

[-] FastAPI local server

[-] Web interface with analytics

[-] Classification of receipts with ML

[-] Export to CSV/Excel

[-] Integration with mobile applications

# Contacts and participation

- If you want to join:

- Forks and Pull Requests are welcome

- Issues for bugs and suggestions

- Discussions on GitHub Discussions

- [Discord](https://discord.gg/3ASMKt9b)

# Roles:

- Mechanics / Electronics

- Python / Computer Vision

- Frontend / Web

- ML / Analytics

# 📄 License

The project is licensed under the GNU Affero General Public License v3.0 (AGPL)

(requires opening the source code if used over the network)
