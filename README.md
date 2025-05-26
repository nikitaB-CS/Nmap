# Nmap

What is Nmap?

Nmap (Network Mapper) is a powerful open-source tool used for network discovery, port scanning, and vulnerability assessment.

Official site: https://nmap.org

Scanning Techniques-

1.TCP SYN Scan (-sS)

  This is a stealthy scan that sends SYN packets to determine if ports are open, closed, or filtered without completing the TCP handshake.

Type: Stealth/half-open scan

Use Case: Avoiding detection by intrusion detection systems (IDS)

Example:

nmap -sS 192.168.1.1

 2. Version Detection(-sV)-

 Probes open ports to determine service versions running on the target.

Type: Service interrogation

Use Case: Identifying vulnerable versions of services

Exmaple-

nmap -sV 192.168.1.1

3. Combined Usage-(-sS -sV)-
   
   Combining -sS and -sV allows you to stealthily detect open ports and get detailed information about the services running on them.

   Exmaple-

   nmap -sS -sV 192.168.1.1

4. Saving the scan results

This section demonstrates how to run Nmap scans (specifically with -sS and -sV flags) and save the output in a clean, readable HTML report for documentation, reporting, or analysis purposes

Command:

nmap -sS -sV -oX scan.xml 192.168.1.1

-sS: TCP SYN Scan

-sV: Version Detection

-oX scan.xml: Save output as XML (used for HTML conversion)

5.  Convert XML to HTML

Nmap provides a tool called xsltproc to convert the XML output into an HTML file.

xsltproc scan.xml -o scan.html

This generates a user-friendly scan.html report you can open in any web browser.








