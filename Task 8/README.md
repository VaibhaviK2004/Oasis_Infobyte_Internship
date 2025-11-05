Network Traffic Capture and Analysis Using Wireshark
Objective
The objective of this task is to capture network traffic on a selected network interface using Wireshark, filter traffic based on HTTP protocol, and analyze the captured packets to understand network communication patterns.

Tools Used
Wireshark: A network protocol analyzer for capturing and inspecting network packets.

Capture Process
Wireshark was installed on the system.

The appropriate network interface (e.g., Wi-Fi or Ethernet) was selected to monitor live traffic.

Packet capture was started while normal network activities (such as web browsing) were performed.

Capture was stopped after enough traffic was collected.

The captured packets were saved to a file named wiresharkcapture.pcap.

Filtering and Analysis
Applied display filter http to extract and view only HTTP traffic.

Analyzed HTTP request and response packets.

Inspected details such as source/destination IP addresses, TCP ports, request methods (GET/POST), status codes, and headers.

Observed the sequential request-response communication confirming normal HTTP operations.

Observations
The captures revealed standard HTTP traffic exchanged between client and server.

Packet details allowed verification of protocol operation and data flow, useful for network troubleshooting, performance analysis, or security assessments.

Deliverables Included
The packet capture file wiresharkcapture.pcap.

Screenshots demonstrating the capture interface, filter application, and details of selected packets.

A demo video showcasing the capture and filtering process along with explanations.