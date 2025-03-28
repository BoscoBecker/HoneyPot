# PHP Honeypot - Protection against bots and intruders

This is a simple PHP honeypot script designed to detect and log suspicious access and malicious access attempts to a web application. It stores valuable information about each attempt, such as the IP address, visitor's geolocation, user agent, and other headers, helping to protect your system against bots and intruders.

🍯 **What is a Honeypot?**

A honeypot is a security technique used to trick bots and attackers into interacting with fake or unusable resources, while the real system remains secure and monitored. In the case of this script, it logs information about visitors trying to access critical areas of the website.

---

### Features:
- **IP Logging:** Stores the IP address of each access attempt.
- **Geolocation:** Obtains information about the visitor's geographic location, such as country and city.
- **Proxy and VPN Detection:** Identify if the visitor is using a proxy or VPN.
- **Attempt Count:** Count how many times an IP attempted to access the page.
- **Detailed Logs:** Records the user agent and HTTP headers for analysis.

---

### How it works:

1. **Page Accesses:** The script is configured to monitor accesses to the `/wp-admin.php` page (but can be adapted to other URLs).
2. **IP Geolocation:** Using the `ip-api.com` API, the script tries to discover the visitor's location.
3. **Proxy and VPN Check:** Also checks if the visitor is using proxy or VPN services.
4. **Access Count:** Keeps a record of how many times the same IP attempted to access the monitored page.

---

### How to use:

1. **Create the log file:** Make sure the path to the log file (`honeypot_log.txt`) is secure and outside the `public_html` directory (if possible).

2. **Place the script on your server:** Place this PHP code on a page of your website that you want to monitor. In the example above, it is set to monitor the `/wp-admin.php` page.

3. **Check the logs:** The generated log file (`honeypot_log.txt`) will store all access attempts with detailed information about each visitor.

---

### Example log entry:

Page: /wp-admin.php 2025-03-28 10:00:00 - IP: 192.168.1.1 - Country: Brazil - City: São Paulo - ISP: Vivo - Proxy: NO - VPN: NO - Accesses: 2 - Agent: Mozilla/5.0 (...) - Headers: { "Header1": "Value1", "Header2": "Value2" }

---

### Considerations:
- **Security:** This script helps identify behavior patterns and can be useful to protect your system from bots and other threats.
- **Data Storage:** Keep in mind that the storage of personal information, such as IP addresses, may be subject to local privacy regulations, such as GDPR.
- **Improvements:** You can expand the script to add more layers of verification, such as captchas or automatic blocking for suspicious IPs.

---
### Emojis: 🍯🐝

Use this honeypot as a "sweet trap" to catch bots and intruders while keeping your system secure!

---
### License:
This script is provided free of charge for educational and security purposes, without warranty of any kind.