# Wazuh EDR - File Integrity Monitoring(FIM)

# Project Overview

This project demonstrates the implementation of File Integrity Monitoring (FIM) using Wazuh. The objective is to monitor critical system files and directories, detect unauthorized changes, and generate real-time security alerts.

  * Technologies Used

  * Wazuh Manager 4.14.5

  * Wazuh Agent

  * Ubuntu 24.04.4 LTS

  * Linux File System Monitoring (Syscheck)

  * Wazuh Dashboard


# Objective

 * Monitor sensitive directories and files.

  * Detect file creation, modification, and deletion.

  * Generate security alerts in the Wazuh Dashboard.

  * Validate real-time monitoring capabilities.



# Wazuh Agent Deployment

Before File Integrity Monitoring can take place, the Wazuh agent must be installed and enrolled on the target endpoint. Wazuh provides a streamlined, single-command installation script based on the parameters selected in the dashboard.

![Email Header Analysis](https://github.com/sudu-13/Wazuh-EDR---File-Integrity-Monitoring-FIM-/blob/38eb967e5e81aa38d95b39aefbb9eaabb44fd675/2.png)

# Agent Verification & Status Check

To confirm that the Wazuh agent successfully registered and established a secure channel with the manager, we verify its real-time telemetry from the Endpoints inventory.

![Email Header Analysis](https://github.com/sudu-13/Wazuh-EDR---File-Integrity-Monitoring-FIM-/blob/9217ccfe27e1ddb28126b063d8493effc8ed098a/3.png)

# Configuring the Agent Local Configuration (ossec.conf)

To instruct the Wazuh agent to actively audit changes within sensitive system boundaries, the main configuration file must be modified on the target endpoint.

* Real-time Triggering (realtime="yes"):

 Utilizes the Linux kernel's file monitoring systems to immediately catch operations.

* Context Capturing (report_changes="yes"):

 Tells the system to track exact delta modifications to file interiors, ensuring unauthorized code injection or parameter adjustments can be quickly parsed in a security investigation.

![Email Header Analysis](https://github.com/sudu-13/Wazuh-EDR---File-Integrity-Monitoring-FIM-/blob/abd5346014d78b5aa99a87a0a8bfcc31f8523523/4.png)


# Simulating a Security Event (File Creation)

To verify that the File Integrity Monitoring (FIM) subsystem actively captures modifications, an administrative action was simulated to trigger a file creation alert.

![Email Header Analysis](https://github.com/sudu-13/Wazuh-EDR---File-Integrity-Monitoring-FIM-/blob/cf01b83711b7391b0ab2b42e1dbc1bb53cf98111/5.png)

# Analyzing FIM Dashboard Alerts

After simulating file operations on the monitored endpoint, the File Integrity Monitoring dashboard provides a visual breakdown of the security events ingested by the Wazuh manager.

![Email Header Analysis](https://github.com/sudu-13/Wazuh-EDR---File-Integrity-Monitoring-FIM-/blob/86cc64d287825ffa8348354bdcd9cdf445653694/6.png)

# Granular Forensic Analysis & Metadata Mapping

When clicking on a specific file event within the Wazuh dashboard, the system provides an exhaustive metadata breakdown. This allows security analysts to perform rapid forensic triage without needing direct terminal access to the affected endpoint.

![Email Header Analysis](https://github.com/sudu-13/Wazuh-EDR---File-Integrity-Monitoring-FIM-/blob/e8d360bb510b0eb25e666af3b0dc4b28db44e173/7.png)

# Conclusion

This project successfully demonstrates File Integrity Monitoring (FIM) using Wazuh EDR. By configuring the Syscheck module with real-time monitoring enabled, the system detected file additions and modifications within the monitored /root directory. Wazuh generated alerts containing detailed metadata such as hashes, permissions, ownership, and timestamps, allowing security analysts to quickly identify unauthorized changes and potential security incidents. This capability is essential for SOC operations, threat detection, compliance monitoring, and incident response.
