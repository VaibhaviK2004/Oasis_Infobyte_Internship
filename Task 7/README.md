Nikto Vulnerability Scan Report
===============================
Introduction
This report presents the results of a vulnerability scan performed on the target web server at IP address 15.197.225.128 using Nikto, an open-source web server vulnerability scanner. The purpose of this scan is to identify potential security issues, misconfigurations, and vulnerabilities that could be exploited by attackers.

Scan Details
Target Host: 15.197.225.128

Target Port: 80 (HTTP)

Scan Date: 01-11-2025

Tools Used: Nikto

Summary of Findings
The scan revealed several security concerns that should be reviewed and addressed:

Server Banner Information Disclosure:

The server banner changed indicated dynamic server naming (e.g., from 'ip-100-74-5-17.eu-west-2.compute.internal' to 'ip-100-74-4-66.eu-west-2.compute.internal').

This information disclosure can aid attackers in fingerprinting the server environment.

Missing Security Headers:

The X-Frame-Options header is not present, which exposes the site to clickjacking attacks.

The X-Content-Type-Options header is missing, allowing browsers to sniff content types and potentially execute malicious scripts.

Uncommon Headers:

A custom header x-request-id with a unique ID was found; this is likely used for request tracing.

Another header wafrule was found, possibly indicating Web Application Firewall rules in effect.

Recommendations
Configure the web server to include the following security headers:

X-Frame-Options: DENY``````SAMEORIGIN

X-Content-Type-Options: nosniff

Review and minimize server banner information to limit exposure of internal environment details.

Investigate custom headers to ensure they do not leak sensitive information.