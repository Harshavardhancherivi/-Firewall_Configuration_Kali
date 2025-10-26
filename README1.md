# README: Firewall Configuration and Testing

This README provides the steps to configure and test firewall rules on
both Windows and Linux systems.

## Steps to Perform

1.  **Open the firewall configuration tool:**

    -   **Windows:** Open 'Windows Defender Firewall with Advanced
        Security'.
    -   **Linux:** Use the terminal (UFW or iptables).

2.  **List current firewall rules:**

    -   Windows: `netsh advfirewall firewall show rule name=all`
    -   Linux (UFW): `sudo ufw status verbose`

3.  **Add a rule to block inbound traffic on a specific port (e.g., 23
    for Telnet):**

    -   Windows:
        `netsh advfirewall firewall add rule name="Block Telnet" dir=in action=block protocol=TCP localport=23`
    -   Linux (UFW): `sudo ufw deny 23/tcp`

4.  **Test the rule** by attempting to connect to the blocked port
    locally or remotely using Telnet.

5.  **Add rule to allow SSH (port 22)** if on Linux:\
    `sudo ufw allow 22/tcp`

6.  **Remove the test block rule** to restore the original state:

    -   Windows:
        `netsh advfirewall firewall delete rule name="Block Telnet"`\
    -   Linux: `sudo ufw delete deny 23/tcp`

7.  **Document the commands or GUI steps used** for future reference.

8.  **Summarize how firewall filters traffic** based on rules and
    directions (inbound/outbound).

------------------------------------------------------------------------

## Note

Ensure administrative privileges before making firewall changes.
Incorrect configurations may block important network services.

------------------------------------------------------------------------

*Date:* 2025-10-26 18:42:35
