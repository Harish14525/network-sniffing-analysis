# Network Sniffing and Analysis

This project demonstrates how network traffic can be captured and analyzed to identify security vulnerabilities in web applications. The task was completed using Wireshark on Kali Linux, focusing on two vulnerable web applications: DVWA (Damn Vulnerable Web Application) and OWASP Juice Shop.

## Project Structure
- `pcap/`: Contains packet capture files (`.pcap`) from network sniffing sessions.
- `screenshots/`: Includes screenshots showing examples of captured HTTP requests containing credentials.
- `analysis_report.md`: Provides detailed observations, identified security issues, and recommendations.
- `README.md`: This file explaining the objective, tools, methodology, and findings.

## Tools Used
- **Wireshark** – for capturing and analyzing network packets.
- **Kali Linux** – operating system used for performing the analysis.
- **DVWA** – a deliberately insecure web application for practicing security testing.
- **OWASP Juice Shop** – a modern, insecure web application that simulates real-world vulnerabilities.

## Approach
1. The vulnerable applications were launched in a controlled environment.
2. Network traffic was captured using Wireshark on the appropriate network interface.
3. Filter such as `http.request` were applied to focus on relevant traffic.
4. Login attempts were performed to simulate user interactions.
5. The captured packets were inspected for sensitive information such as usernames and passwords.

## Observations
- Login credentials were transmitted in plaintext during HTTP requests.
- Even failed login attempts exposed sensitive information over the network.
- The lack of encryption presented significant risks related to credential theft.

## Security Recommendations
- Enforce HTTPS with TLS/SSL encryption to protect data in transit.
- Implement secure authentication mechanisms, including multi-factor authentication.
- Avoid transmitting sensitive information in plain text, and ensure secure handling of user credentials.

## Notes
This is a single task performed across multiple vulnerable applications. TCPDump was not used as it was optional for this assignment. The focus was on learning how network sniffing tools reveal potential threats and understanding how attackers could exploit unencrypted traffic.
