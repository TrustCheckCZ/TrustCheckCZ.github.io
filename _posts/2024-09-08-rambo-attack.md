---
layout: post
title: "RAMBO Attack: New Side-Channel Threat Targets Air-Gapped Systems"
categories: 
- privacy
- cybersecurity
author:
- The Trust Check Team
- Bill Toulas (bleeping computer)
---

![Airgapped](https://www.bleepstatic.com/content/hl-images/2024/09/05/Airgapped.jpg)
A groundbreaking side-channel attack, dubbed **RAMBO** (Radiation of Air-gapped Memory Bus for Offense), has emerged, allowing data theft from **air-gapped computers** using electromagnetic radiation emitted by the system's RAM.

Air-gapped systems—those isolated from public networks—are often deployed in highly secure environments such as government facilities, military weapon systems, and nuclear power plants. Their physical isolation aims to prevent external cyber threats. However, these systems can still be compromised by **malicious insiders** or **sophisticated supply chain attacks** that introduce malware through physical devices like USB drives.

Once infected, the malware can covertly manipulate the RAM, transforming the computer into a transmitter that sends sensitive data through controlled electromagnetic emissions to a nearby receiver.

### The RAMBO Attack in Action
The **RAMBO** attack, developed by Israeli researchers led by **Mordechai Guri**, an expert in covert data exfiltration techniques, leverages the **RAM's memory bus** to send encoded information. By altering memory access patterns—specifically, the **read/write operations**—the malware generates precise electromagnetic emissions that contain the stolen data.

![Code to perform the OOK modulation](https://www.bleepstatic.com/images/news/u/1220909/2024/Papers/04/ook-modulation.jpg)
*Code to perform the OOK modulation*  
Source: Arxiv.org

The attack uses **On-Off Keying (OOK)** modulation, where the emissions are modulated to represent binary data, with "1" as "on" and "0" as "off." To ensure accuracy and reduce errors, the researchers employed **Manchester encoding**, which provides better synchronization and error detection.

An attacker can capture these signals using an inexpensive **Software-Defined Radio (SDR)** equipped with an antenna. The SDR decodes the modulated emissions back into usable data.

![Signal of the word "DATA"](https://www.bleepstatic.com/images/news/u/1220909/2024/Papers/04/signal.jpg)
*EM signal of the word "DATA"*  
Source: Arxiv.org

### Transmission Speed and Range
The **RAMBO** attack can achieve transmission speeds of up to **1,000 bits per second** (bps), or **128 bytes per second** (0.125 KB/s). At this rate, exfiltrating **1 MB** of data would take approximately **2.2 hours**. Due to the relatively low data transfer rate, RAMBO is ideal for stealing small but sensitive data, such as passwords, text files, and keystrokes.

The researchers demonstrated real-time **keylogging** capabilities, with a password theft taking anywhere from **0.1 to 1.28 seconds**, while exfiltrating a **4096-bit RSA key** required between **4 and 42 seconds**.

The attack's transmission range depends on the speed and environment. The maximum reliable distance for fast transmissions is **3 meters (10 feet)**, with a **2-4% bit error rate**. Medium-speed transmissions can extend the range to **4.5 meters (15 feet)**, while slow transmissions with near-zero errors can reach up to **7 meters (23 feet)**.

![Data transmission speeds](data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==)
*Data transmission speeds*  
Source: Arxiv.org

The team also experimented with higher transmission speeds up to **10,000 bps** but found that anything above **5,000 bps** drastically reduced the **signal-to-noise ratio**, making the transmission unreliable.

### Mitigating the RAMBO Attack
The researchers outlined several **mitigation strategies** in their [technical paper on Arxiv](https://arxiv.org), although they come with trade-offs. These include:

- **Physical security enhancements**: Stricter zone restrictions to prevent unauthorized access.
- **RAM jamming**: Introducing noise in the RAM to disrupt the malware’s ability to generate signals.
- **External electromagnetic jamming**: Using external devices to interfere with radio signals.
- **Faraday enclosures**: Shielding air-gapped systems to block electromagnetic radiation from leaving the premises.

Tests also showed that RAMBO is effective against virtual machines, although it can be disrupted due to the complex interactions between the host OS and VMs.

### Conclusion
The RAMBO attack highlights the growing sophistication of side-channel attacks on air-gapped systems. While the data transfer rate is relatively slow, the method is ideal for stealing critical information from high-security environments. Organizations using air-gapped systems should take preventive measures to reduce the risk of such covert exfiltration methods.

---

