# Analysis Report – Network Sniffing and Analysis

## Objective
The purpose of this task was to capture and analyze network traffic to identify security vulnerabilities, specifically the exposure of sensitive data during network communication. The analysis aimed to demonstrate how attackers could intercept credentials transmitted over unprotected channels.

## Tools and Environment
- **Wireshark**: Used to capture and inspect network packets in real time.
- **Kali Linux**: The operating system where the analysis was conducted.
- **DVWA (Damn Vulnerable Web Application)** and **OWASP Juice Shop**: Used as test environments for simulating vulnerable web applications.

## Methodology
1. The applications were launched within the Kali Linux environment.
2. Wireshark was used to capture network traffic by selecting the appropriate network interface.
3. Filters such as `http.request` and `ip.addr == <target_ip>` were applied to isolate traffic associated with login attempts.
4. Login actions were performed on both DVWA and Juice Shop to generate HTTP requests containing user credentials.
5. The captured packets were examined to identify whether sensitive data was exposed.

## Findings
- Login credentials, including usernames and passwords, were transmitted in plaintext using HTTP POST requests.
- These credentials were visible in Wireshark even when login attempts failed, meaning that network attackers could potentially intercept information without needing successful authentication.
- The absence of encryption makes it easier for attackers to perform credential theft, session hijacking, and other network-based attacks.

## Security Issues Identified
- Sensitive data is exposed during transmission over unsecured channels.
- Applications without HTTPS encryption are highly susceptible to network sniffing attacks.
- Plaintext transmission of credentials increases the likelihood of unauthorized access.

## Recommendations
- All web applications should enforce HTTPS using TLS/SSL to ensure secure communication.
- Secure authentication mechanisms, such as multi-factor authentication and token-based systems, should be implemented.
- Sensitive data must not be transmitted in plaintext. Proper encryption methods should be applied at both the transport and application layers.

## Conclusion
This task helped in understanding the importance of encrypted communication in protecting user credentials and data. By analyzing network traffic using Wireshark, it was possible to observe how easily attackers could intercept and exploit unsecured information. The findings reinforce the need for robust security practices in web applications.
