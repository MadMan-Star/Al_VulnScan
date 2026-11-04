# 🔐 AI-VulnScan

![banner](https://img.shields.io/badge/AI%20Network%20Scanner-AI%20+%20Nmap%20+%20CVE%20Lookup%20+%20LLM-blueviolet?style=for-the-badge)

**AI-VulnScan** is an AI-powered network vulnerability scanner that uses **Nmap** to detect open ports and services, searches for known **CVEs**, and uses a **local LLM (like Mistral or LLaMA3)** for AI-based vulnerability analysis.

---

## 🚀 Features

- 🔍 Scan open ports with version detection (`nmap -sV`)
- 📜 Lookup known CVEs using NVD (offline)
- 🧠 Local LLM-based AI analysis and remediation (no API key needed!)
- 📄 Markdown report generated after every scan
- 🎨 Rich CLI output with beautiful banners

---

## 📦 Installation Guide

### 🛠 Prerequisites

- Python 3.8+
- [nmap](https://nmap.org/) installed on your system:
    ```bash
    sudo apt update && sudo apt install nmap
    ```
- [Ollama](https://ollama.com/) for running local LLMs (Linux/macOS/Windows supported)
- [Virtualbox](https://www.virtualbox.org/wiki/Downloads) (Linux/macOS/Windows supported)
- [Kali](https://www.kali.org/get-kali/#kali-virtual-machines) download the virtual box version
- [Metasploitable](https://www.rapid7.com/products/metasploit/metasploitable/)

---

## 🐉 Step-by-step Setup of Kali and Metasploitable

### 1. Extract virtual box and start it

### 2. Click machine on the top bar and then add on virtual box

### 3. Find kali wherever you extracted to and click to add it to virtual box

### 4. The username and password is kali

### 5. Installing metasploitable; go back to virtual box and on the top bar click machine and then new

### 6. Name it metasploitable and then click next until you see the virtual hard disk page

### 7. On the virtual hard disk page, select adduse an existing virtual hard disk file

### 8. Click add then find the Metasploitable.vmdk file in your extracted metasploitable folder, then choose it. Then click next and finish.

```bash
msfadmin # This is the username and password for logging into Metasploitable
```
### 9. For metasploitable and kali go to settings, then network, and in adapter 1, set both to host-only network adapter.

## 🧪 Step-by-step Setup

### 1. Clone the Repository

```bash
git clone https://github.com/Rjkumarkumawat/Al-VulnScan.git
cd Al-VulnScan
```

### 2. Create a Virtual Environment (Recommended)

```bash
python3 -m venv venv # For Windows: py -m venv venv
source venv/bin/activate  # For Windows: venv\Scripts\activate
```

### 3. Install Python Dependencies

```bash
pip install -r requirements.txt
```

---

## 🤖 Install and Run Local LLM (Ollama)

### Step 1: Install Ollama

Visit: https://ollama.com/download  
Or run on Linux (with curl):

```bash
curl -fsSL https://ollama.com/install.sh | sh
```

Start the Ollama server:

```bash
ollama serve
```

### Step 2: Pull a Model (llama3 recommended)

```bash
ollama pull llama3
```

Other supported models:

```bash
ollama pull mistral
ollama pull codellama
```

You can customize the model used in your code inside `ai_analyzer.py` like:

```python
response = ollama.chat(model="mistral", messages=[...])
```

---

## ✅ Run the Scanner

```bash
python main.py
```
```Powershell
py -X utf8 main.py
```

- Enter the **target IP**
- Choose to scan specific ports or all
- It will scan, lookup CVEs, ask the LLM for suggestions, and update `report.md`

---

## 🔍 Sample Output

<sample output omitted for brevity>

---

## 📄 Output File

All findings are saved to `report.md` in Markdown format – perfect for sharing or documenting a pentest.

---

## 📜 License

MIT License

---

## 👨‍💻 Created By

**Rajkumar Kumawat**

---

## 🔗 Links

- Original Project Repository: [github.com/Rjkumarkumawat/Al-VulnScan](https://github.com/Rjkumarkumawat/Al-VulnScan.git)
- LLM Engine: [ollama.com](https://ollama.com)
- CVE Database: [nvd.nist.gov](https://nvd.nist.gov)
