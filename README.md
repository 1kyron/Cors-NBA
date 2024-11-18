# Vulnerability in nba.com Server
A security vulnerability has been identified in the server __nba.com__ related to __misconfigured CORS (Cross-Origin Resource Sharing) or SSL/TLS (Insecure Renegotiation)__. This flaw may lead to sensitive data exposure and communication security issues. Experts can exploit these vulnerabilities to perform unauthorized actions such as data theft or code execution.

## Summary
The vulnerability stems from the server's improper handling of __CORS and insecure SSL/TLS renegotiation__, which has been disabled by default in newer OpenSSL versions due to known security risks. The server attempts to use __unsafe legacy SSL renegotiation which exposes it to potential Denial of Service (DoS)__ attacks or __remote code execution__.
###  Vulnerability Details
##### __CORS Misconfiguration__:A flaw in the CORS policy can allow malicious websites to access sensitive API resources without proper authentication.
##### __Insecure SSL/TLS Renegotiation__: The server’s failure to properly configure SSL/TLS renegotiation exposes it to __DoS attacks and remote code execution__, depending on other system vulnerabilities.
##### __Observed Error__: The error message code  ```SSLError: UNSAFE_LEGACY_RENEGOTIATION_DISABLED ``` indicates that the server is attempting to use deprecated and insecure SSL renegotiation protocols.

# Tools Used to Identify Vulnerability

the following tools were used to identify the vulnerability in the server:

##### __Spyhunt__: (Where the vulnerability was discovered)
##### __Dirsearch__: Directory and file brute forcing tool to identify sensitive endpoints.
##### __Nmap__: Network scanning tool to identify open ports, services, and vulnerabilities.
##### __SQLMap__: Automated SQL injection tool to test for database vulnerabilities.
##### __Nuclei__: Template-based vulnerability scanner for common security issues.
##### __Paramspider__: Automated tool for discovering parameters on web applications

# Steps to Reproduce
##### __Run a directory brute force scan__ using Dirsearch to identify exposed resources.
##### __Perform an SSL scan__ using Nmap to check for weak or outdated SSL/TLS configurations.
##### __Test CORS configurations__ to verify if sensitive API endpoints are improperly exposed to cross-origin requests.
##### __Use Nuclei__ to scan for common vulnerabilities related to SSL/TLS misconfigurations.
##### __Check for SSL/TLS renegotiation errors__ by observing the server’s SSL handshake behavior using tools like Nmap or OpenSSL.
# Potential Impact
The impact of this vulnerability could be significant:

##### __Sensitive Data Exposure__: If the CORS flaw is exploited, attackers could access sensitive API resources without proper authentication.
##### __Insecure SSL/TLS Renegotiation__: This could lead to DoS attacks or, in some cases, remote code execution if additional vulnerabilities exist in the server's configuration.
# Example Scenario
An attacker could use the insecure SSL renegotiation to exploit this flaw, potentially leading to __Denial of Service (DoS)__ or other security breaches. The SSL/TLS renegotiation should be updated to use more secure protocols, as the legacy method is no longer safe.

# Recommendations
##### __Fix CORS Configuration__: Ensure that only trusted domains are allowed to access API resources.
##### __Update SSL/TLS Configuration__: Disable insecure SSL/TLS renegotiation and ensure the use of up-to-date protocols.
##### __Regular Security Audits__: Conduct regular vulnerability assessments using tools like Nmap, SQLMap, and Nuclei.
# Screenshot 

![Screenshot_7](https://github.com/user-attachments/assets/e0d8daae-512b-446b-a61d-592220b9b73b)

