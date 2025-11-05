Task 2: Configuring a Basic Firewall with UFW Goal

 Use UFW (Uncomplicated Firewall) to set up a simple firewall on a Linux system that will permit SSH traffic on port 22 and block HTTP traffic on port 80.
 UFW: What is it?

 On Linux computers, UFW (Uncomplicated Firewall) is an intuitive interface for controlling firewall rules.  By offering simple commands for permitting or prohibiting traffic on particular ports or services, it makes network security configuration easier.
 
==== Steps Performed ====

    1] Installed UFW

    Command:

    bash
    sudo apt update && sudo apt install ufw

    This ensures UFW is available on the system.

    2] Allowed SSH (port 22)

    Command:

    bash
    sudo ufw allow ssh

    This rule allows incoming SSH connections, which are essential for remote server management. Allowing SSH before enabling the firewall prevents accidental lockout.

    ​

    3] Denied HTTP (port 80)

    Command:

    bash
    sudo ufw deny http

    This rule blocks incoming HTTP traffic, which is useful if the server should not be accessible as a website or to reduce the attack surface.

    4] Enabled UFW

    Command:

    bash
    sudo ufw enable

    This activates the firewall and applies all configured rules.

    5] Checked Firewall Status

    Command:

    bash
    sudo ufw status numbered

    This displays all active rules and their order. A screenshot of this output is included in the repository.
    
Why These Rules?

    Allowing SSH ensures you can connect to and manage your server remotely.

    Denying HTTP prevents unauthorized web access, which is important if the server is not intended to host web services or to minimize exposure to web-based attacks.
     
    Commands : 
    
    sudo ufw default deny incoming
    sudo ufw default allow outgoing


Files Included

    ufw_configuration.sh: Shell script containing all commands used for configuration.

    README.md: This documentation file.

    screenshot.png: Screenshot showing the active UFW rules.


