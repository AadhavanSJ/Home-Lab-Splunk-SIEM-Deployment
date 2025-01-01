# **Detection Lab Project: A Hands-On Approach to Cybersecurity**

## **Objective**
The Detection Lab project aimed to establish a controlled environment for simulating and detecting cyber attacks. The primary focus was to ingest and analyze logs within a Security Information and Event Management (SIEM) system, generating test telemetry to mimic real-world attack scenarios. This hands-on experience was designed to deepen understanding of network security, attack patterns, and defensive strategies.

## **Skills Learned**
- Advanced understanding of SIEM concepts and practical application.
- Proficiency in analyzing and interpreting network logs.
- Ability to generate and recognize attack signatures and patterns.
- Enhanced knowledge of network protocols and security vulnerabilities.
- Development of critical thinking and problem-solving skills in cybersecurity.

## **Tools Used**
- **Splunk** for log ingestion and analysis.
- **Sysmon** for capturing detailed system activity on the Windows machine.
- **Metasploit** for generating attacks.
- **Windows Event Viewer** for monitoring event logs in real-time.
- **Nmap** for scanning and discovering open ports and services on the target machine.

## **Steps**

### **1. Setting Up the Environment**
The first step in the project was creating the lab environment. I used virtualization software to set up two machines:

- **Windows 10**: Configured as the victim system to simulate a corporate endpoint.
- **Kali Linux**: Used as the attacker system to simulate attacks on the Windows machine.

#### Key Tools and Configurations:
- **VirtualBox**: Used to create and manage the virtual machines.
- **Splunk**: Installed to capture and analyze logs from the Windows machine.
- **Sysmon**: Used to capture detailed system activity.

![Network Diagram](imgsrc)  
*Ref 1: Network Diagram*  
*Screenshot of the network layout used in the Detection Lab, showing the interconnected systems and components used to simulate attacks.*

### **2. Simulating the Attack**
With the environment set up, I moved on to the attack phase. Using **Kali Linux**, I leveraged **Metasploit** to simulate an attack on the **Windows 10** machine.

#### Steps I Followed to Attack the Windows Machine:
1. **Identifying the Target's IP Address:**
   - I used **Nmap** to scan the network and discover open ports and services on the Windows machine.
   - Example Nmap command:  
     ```bash
     nmap -A <target_ip>
     ```

2. **Launching Metasploit Framework:**
   - I launched the **Metasploit console** in Kali Linux and searched for an exploit based on the open ports and services found during the Nmap scan.
   - Example Metasploit command:  
     ```bash
     msfconsole
     ```

3. **Configuring the Payload:**
   - I selected a **reverse TCP payload** to establish a reverse shell connection with the target machine.

4. **Launching the Exploit:**
   - After configuring the payload, I executed the exploit. Upon success, **Metasploit** gave me access to the **Windows 10** machine via a **Meterpreter shell**.

![Nmap Scan](imgsrc)  
*Ref 2: Nmap Scan Screenshot*  
*Screenshot showing the results of the Nmap scan on the Windows machine, revealing open ports and services.*

### **3. Generating and Capturing Telemetry Data**
Once the attack was executed, I focused on generating and capturing telemetry data from the **Windows 10** machine. I configured **Windows Event Viewer** and **Sysmon** to capture relevant logs and system activity.

#### Key Tools and Configurations:
- **Windows Event Viewer**: Used to monitor event logs, including authentication attempts and system events.
- **Sysmon**: Configured to capture detailed system activity, such as process creation and network connections.

![Telemetry Data](imgsrc)  
*Ref 3: Telemetry Data Screenshot*  
*Screenshot of telemetry data showing failed login attempts and other suspicious activities.*

### **4. Analyzing Data in Splunk**
The final phase involved setting up **Splunk** to ingest and analyze the telemetry data from the **Windows 10** machine. I used **Splunk**'s powerful features to identify attack patterns, correlate events, and generate visualizations.

#### Key Configurations in Splunk:
- **Data Inputs**: Configured **Splunk** to receive logs from the **Sysmon**.
- **Search Queries**: I used **SPL (Search Processing Language)** to query logs and identify suspicious activities, such as failed login attempts and unauthorized access.
- **Dashboards**: Created visualizations to represent attack patterns and system behavior, making it easier to detect and respond to threats.

![SIEM Dashboard](imgsrc)  
*Ref 4: SIEM Dashboard Screenshot*  
*Screenshot of the Splunk dashboard, displaying visualizations of detected attack patterns and anomalies.*

### **5. Reporting and Reflection**
After analyzing the data, I generated a report summarizing the findings. The report discussed the detected attack patterns, insights into system vulnerabilities, and proposed defensive strategies to mitigate similar attacks in the future.

![Report Screenshot](imgsrc)  
*Ref 5: Report Screenshot*  
*Screenshot of a report summarizing the attack findings, analysis, and proposed defensive measures.*

## **Lessons Learned**
This project was a fascinating dive into the world of cybersecurity. Here are some key takeaways:

- **Importance of Logging**: Comprehensive logging is essential for detecting and understanding security incidents.
- **SIEM Tools Are Powerful**: **Splunk**'s capabilities in data aggregation, visualization, and anomaly detection make it invaluable in security operations.
- **Hands-On Practice is Crucial**: Setting up a home lab provided me with practical experience that goes beyond theoretical knowledge.

## **Final Thoughts**
Building this home lab was an enriching experience that deepened my understanding of cybersecurity concepts and tools. It’s a testament to how much one can learn by experimenting and challenging themselves. For anyone looking to break into cybersecurity, I highly recommend starting with a project like this to build foundational skills and confidence.

If you have any questions or want to share your own experiences, feel free to comment below. Let’s learn and grow together in this exciting field!
