# 🦈 Capturing Plain Text Credentials Using Wireshark

## 📝 Overview
This document guides you through the process of logging into an application and capturing requests using Wireshark to verify whether credentials are transmitted in plain text.

---

## ✅ Prerequisites
1. **Wireshark**: Ensure Wireshark is installed on your system. Download it from [https://www.wireshark.org/](https://www.wireshark.org/) if not already installed.
2. **Application Access**: You should have access to the application where login credentials will be tested.
3. **Network Interface**: Identify the correct network interface to capture traffic.
4. **Administrative Privileges**: Ensure you have admin privileges to capture network traffic.
5. **Demo Website**: Use the demo HTTP website [http://altoro.testfire.net/](http://altoro.testfire.net/) for testing purposes.

---

## 🛠️ Steps

### 1️⃣ Start Wireshark
1. Open Wireshark.
2. Select the network interface you want to capture traffic from (e.g., Ethernet, Wi-Fi).
3. Click the **Start Capture** button (shaped like a shark fin 🦈).

### 2️⃣ Filter for HTTP or HTTPS
1. In the **Capture Filter** box, enter:
   - `http` for non-secure web traffic.
   - `ssl || tls` for secure web traffic (optional for encrypted requests).
2. Press **Enter** to apply the filter.

### 3️⃣ Log in to the Application
1. Open the demo website [http://altoro.testfire.net/](http://altoro.testfire.net/) in your web browser.
2. Navigate to the login page.
3. Enter your username and password (use test credentials provided by the website if available).
4. Submit the credentials by clicking the login button 🖱️.

### 4️⃣ Analyze Captured Traffic
1. Stop the capture in Wireshark after completing the login process.
2. Look for HTTP POST requests (if using HTTP) or inspect decrypted HTTPS traffic (if applicable).
   - To filter HTTP POST requests, use the display filter: `http.request.method == "POST"`.
3. Check the request details in the **Packet Details** pane.
4. Inspect the payload for the presence of plain text username and password.

### 5️⃣ Verify Findings
- If credentials are transmitted in plain text, they will appear unencrypted in the payload.
- For HTTPS, ensure decryption is set up (requires private keys or appropriate certificates).

---

## ⚠️ Notes and Precautions
- **Ethical Considerations**: Ensure you have proper authorization to test the application.
- **Encryption**: If HTTPS is used and credentials are encrypted, ensure the server implements strong security protocols.
- **Legal Compliance**: Follow all applicable laws and organizational policies when testing.

---

## 🔍 Conclusion
Using Wireshark, you can verify whether credentials are transmitted securely. If credentials are found in plain text, the application is vulnerable to interception attacks, and immediate remediation is recommended.

---
