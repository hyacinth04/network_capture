# Internship Project: Wireshark Network Traffic Analysis

This repository contains the deliverables and supporting files for a networking internship task focused on **capturing, filtering, and analyzing network traffic** using Wireshark. The project demonstrates proficiency in identifying core protocols, analyzing their packet structures, and summarizing communication flows.


## Repository Contents

The following files constitute the submission for this project:
* **`MyNetworkCapture.pcapng`**: The raw packet capture file. This file contains the complete, unfiltered dataset of network traffic recorded during the analysis session. It should be opened using Wireshark.
* **`Network_Traffic_Analysis.pdf`**: The formal report summarizing all technical findings, including detailed protocol analysis and packet characteristics.


##  Tools and Technologies

* **Packet Analyzer:** **Wireshark** (Used for live capture, precise filtering, and deep packet inspection.)
* **Operating System:** [**Your Specific OS (e.g., Windows 11 / macOS Sonoma)**]
* **Protocols Analyzed:** TCP, UDP, DNS, TLS (HTTPS)

---

## Summary of Findings and Protocol Details

The capture was filtered to provide detailed evidence of protocols operating across the Transport and Application Layers.

### A. Transport Layer Protocols

These protocols manage data transfer between endpoints, focusing on reliability or speed.

* **TCP (Transmission Control Protocol):**
    * **Function:** Provides a **reliable, connection-oriented** service, guaranteeing ordered delivery.
    * **Packet Details:** The **full connection lifecycle** was confirmed through key flags:
        * **Establishment:** Identified the **three-way handshake** using the sequential flags: `[SYN]`, `[SYN, ACK]`, and `[ACK]`.
        * **Termination:** Observed the graceful closing of the session via the **`[FIN, ACK]`** (Finish, Acknowledge) flag packets.

* **UDP (User Datagram Protocol):**
    * **Function:** Provides a **fast, connectionless** service with minimal overhead; ideal where speed is critical.
    * **Packet Details:** UDP was confirmed as the carrier for rapid **DNS** queries, identifiable by its simple header structure lacking sequencing or acknowledgment fields.

### B. Application and Security Layer Protocols

These protocols handle application-specific data and encryption.

* **DNS (Domain Name System):**
    * **Function:** Translates human-readable domain names into numerical IP addresses.
    * **Packet Details:** The transaction was observed as a **"Standard query"** sent from the host, immediately followed by the server's **"Standard query response,"** confirming successful name resolution.

* **TLS (Transport Layer Security):**
    * **Function:** Provides **encryption, integrity, and authentication** for securing web traffic (HTTPS).
    * **Packet Details:** The initiation of the security layer was verified by the **"Client Hello"** message, which begins the cryptographic handshake necessary to establish a secure channel.


## Conclusion

This project successfully fulfilled the objective by providing a thorough, packet-level analysis of core networking protocols. The findings confirm proficiency in using Wireshark to capture, filter, and interpret live network traffic data for technical analysis.

---

## How to View and Verify the Analysis

1.  **Requirement:** Ensure **Wireshark** is installed on your system.
2.  **Access:** Open the **`MyNetworkCapture.pcapng`** file directly within Wireshark.
3.  **Verification:** Apply the protocol filters mentioned above (e.g., `tcp`, `tls`, `dns`) to isolate and verify the specific packet flag details documented in the report.
