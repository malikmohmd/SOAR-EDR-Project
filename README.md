# SOAR-EDR Project Using Tines and LimaCharlie

## Introduction

As the cybersecurity landscape continues to evolve, **Security Orchestration Automation and Response (SOAR)** tools have become a crucial part of modern **Security Operations Centers (SOC)**. SOAR platforms help automate repetitive security tasks, enhance incident response, and streamline workflows with structured playbooks, allowing SOC teams to focus on more complex and high-priority incidents.

This project demonstrates the integration of **Tines**, a SOAR platform, with **LimaCharlie**, an Endpoint Detection and Response (EDR) system. The objective was to automate responses to security detections, such as the execution of password recovery tools, and escalate actions based on user input. Importantly, this project focused on mastering core SOAR concepts, ensuring that the skills are vendor-agnostic and transferable across different platforms.

## Project Objectives

- **Automate Detection and Response**: Detect password recovery tools on Windows machines using LimaCharlie and respond to these incidents with Tines.
- **Design and Implement Playbooks**: Create a custom playbook (called “stories” in Tines) that integrates detection alerts with communication tools like Slack and email.
- **User Interaction for Incident Response**: Enable users to provide input on critical actions, such as isolating machines upon detecting malicious activity.
- **Hands-On SOAR and EDR Experience**: Gain practical experience with SOAR and EDR platforms by setting up detection rules, generating events, and automating responses.
  
## Tools Used:


| Tool             | Description                                                 |
|------------------|-------------------------------------------------------------|
| **Tines**        | SOAR platform for automating security workflows.             |
| **LimaCharlie**  | EDR platform for detecting security events and vulnerabilities. |
| **Slack**        | Communication tool for receiving security alerts.            |
| **Windows Server**| A virtual machine used to simulate a real network environment. |
| **LaZagne**      | Password recovery tool used for testing detection capabilities. |




## Project Workflow

### **1. Preparation**

- **Tools Setup**: Installed and configured **Tines** as the SOAR platform and **LimaCharlie** as the EDR solution.
- **Windows VM**: Deployed a Windows Server 2022 VM in VirtualBox as the test environment. It was essential that this VM had an active internet connection to communicate with both SOAR and EDR platforms.

### **2. Detection Setup**

- **Custom Detection Rules**: Created custom detection rules in LimaCharlie to monitor password recovery tools, specifically focusing on **LaZagne**.
- **Data Collection**: The Windows Server 2022 VM began generating event data sent to LimaCharlie, where the telemetry was stored and analyzed.

### **3. Playbook Creation (Tines Story)**

- **Automated Responses**: Built a playbook in Tines that automates responses when detection is triggered:
  - An alert is sent via **Slack** and **email** when a detection occurs.
  - The user is prompted to decide whether the machine should be isolated.
  - Based on the user’s input, LimaCharlie can automatically isolate the machine.

### **4. Slack and Email Integration**

- **Incident Notifications**: Integrated Slack and email with the Tines playbook to receive real-time notifications about detected incidents.
- **Testing**: Verified that alerts were correctly sent to both platforms upon detection.

### **5. User Interaction**

- **Prompting User Decisions**: Upon detecting suspicious activity, Tines prompts the user to confirm whether the machine should be isolated.
- **Automation Based on Input**: If the user selects "Yes," LimaCharlie automatically isolates the machine.

## Challenges Encountered

1. **Playbook Design Iterations**: Building a functional playbook required multiple iterations, as some configurations didn't work as expected.
2. **Integration and Data Handling**: Ensuring smooth integration between LimaCharlie and Tines required troubleshooting, especially around passing alerts and data between platforms.
3. **Handling User Inputs**: Designing the logic for user inputs (e.g., whether to isolate the machine) required adjustments to avoid incorrect incident responses.

## Results

By the end of the project, I successfully:

- **Created a Detection Rule**: Monitored and alerted on the use of the LaZagne password recovery tool with a custom detection rule in LimaCharlie.
- **Integrated Slack and Email**: Developed a fully automated playbook that notifies users in real-time and enables incident response directly through **Slack** and **email**.
- **User-Driven Automation**: Enabled manual user intervention in key security workflows, such as machine isolation based on real-time detection.

## Lessons Learned

1. **Vendor-Agnostic Skills**: While I used Tines and LimaCharlie, the underlying principles of SOAR and EDR can be applied across many different platforms {I have used Shuffle for a SOAR project as well}. SOC teams should design processes with flexibility in mind.
2. **Iterative Playbook Development**: Playbooks evolve with operational needs and new threats. It's important to refine them continuously.
3. **Hands-On Experience Matters**: This project reinforced the importance of practical, hands-on experience with SOAR and EDR tools to better understand their capabilities and workflows.

## Conclusion

This project demonstrated the immense value of integrating SOAR platforms like Tines with EDR tools such as LimaCharlie to automate SOC workflows. Automating detection and response not only enhances incident management but also improves efficiency by allowing SOC teams to focus on critical threats.

By following this project, I gained valuable real-world experience and developed a practical understanding of orchestrating automated responses to security threats in a streamlined and structured way. The skills learned here will serve as a solid foundation for future SOC automation and security orchestration endeavours.


