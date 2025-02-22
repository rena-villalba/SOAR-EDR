# SOAR-EDR Lab

## Project Overview

The purpose of this project is to automate security operations by integrating Tines (SOAR) and LimaCharlie (EDR). The goal is to enhance threat detection and response by reducing manual intervention and streamlining security workflows.

## Objective
The project involves simulating an infected machine executing a malicious file designed to extract system passwords. By leveraging LimaCharlie as the EDR, we will monitor and analyze system events in real-time. Once the EDR detects the malicious process, an alert will be generated.

Following this, Tines (SOAR) will automate the incident response by executing predefined actions based on the detected threat.


### Skills Learned

- Creating automated incident response playbooks.
- Monitoring and analyzing endpoint security events in real-time.
- Detecting malicious activity and responding to security threats.
- Understanding how security tools detect and log security incidents.
- Learning how to reduce manual intervention by automating repetitive SOC tasks.
- Evaluating risk levels and deciding on the appropriate security response.

### Tools Used

- Security Orchestration, Automation and Response (SOAR) software to build workflows.
- Endpoint Detection and Response (EDR) that collects and analyzes data from endpoints.

## Process Workflow

Pre-Conditions:
- Disable real-time protection from Windows Security to download and run the Lazagne application from its official github repository.

1. Threat Simulation & Detection

- Deploy an infected machine with a malicious executable designed to steal system passwords.
- Monitor system events using LimaCharlie to detect suspicious activity.
- Generate an alert when the malicious process is identified.

2. Automated Response via Tines

- Notification Phase:
Send an alert notification via Slack and Email containing details of the detected event.

- User Decision Point:
Prompt the user with event details, including the affected endpoint.
Ask if the infected machine should be isolated.

- Isolation or Warning Response:
If the user selects "Yes", LimaCharlie isolates the machine from the network, and a confirmation message is sent via Slack.
If the user selects "No", a Slack message is sent, warning that the machine was not isolated and requires further investigation.

*Img 1: Network Diagram*<br>
![1 SOAR_EDR_Project drawio](https://github.com/user-attachments/assets/9f5b9e8c-db95-4d8c-a896-e7bb6c42b6a8)

*Img 2: Create a new Organization for the project*<br>
<img width="569" alt="2 organization_name" src="https://github.com/user-attachments/assets/ef6c5742-b7e5-4f4b-9c86-8e3f889daf84" />

*Img 3 & Img 4: New Installation Key created and the sensor executable downloaded*<br>
![3 sensor_key](https://github.com/user-attachments/assets/9d275610-93c0-4971-85fc-1378e89f000d)
![4 sensor_download](https://github.com/user-attachments/assets/ac1351cc-7121-4116-a15f-80a81ab79e9d)

*Img 5: Running the sensor executable with the sensor key as option to enroll correctly the machine*<br>
<img width="434" alt="5 sensor_executable" src="https://github.com/user-attachments/assets/d8d6a51c-7e7b-4cd8-9b6a-6308961c1c3c" />

*Img 6: Confirm that LimaCharlie is correctly installed and running*<br>
<img width="444" alt="6 confirm_lc" src="https://github.com/user-attachments/assets/5ae12316-1b4d-456d-ba7d-17766fdd966d" />

*Img 7: Download the Lazagne application from the github repository (https://github.com/AlessandroZ/LaZagne)*<br>
![7 lazagne](https://github.com/user-attachments/assets/8f943c76-1d1f-4e5a-b3dc-c6a5dfa01a9b)

*Img 8: Running the Lazagne application to generate some telemetry*<br>
<img width="425" alt="8 lzagne_executed" src="https://github.com/user-attachments/assets/3f1e345b-fb6f-4012-8096-3faa411e97cf" />

*Img 9: Searching for the event at the Timeline section*<br>
<img width="820" alt="9 timeline_detect" src="https://github.com/user-attachments/assets/e21a01b2-7b12-4723-906a-315c5ea2ec82" />

*Img 10 & Img 11: Creating a new rule at the Automation/D&R section*<br>
<img width="427" alt="10 detection_rule" src="https://github.com/user-attachments/assets/d917579e-541b-4b51-999a-bf23853785d2" />
<img width="228" alt="11 respond_rule" src="https://github.com/user-attachments/assets/d04c24f4-fcfe-46a2-8281-e0ea4805b150" />

*Img 12 & Img 13: Testing the rule with the raw data using the "NEW PROCESS" and checking at the "Detection" section the event get caught*<br>
<img width="665" alt="12 testing_rule" src="https://github.com/user-attachments/assets/6750cd2e-8ddd-40b5-af79-840c8e79e30b" />
<img width="817" alt="13 detection_caught" src="https://github.com/user-attachments/assets/d4e76892-6e02-4fa0-93ba-52e7d88b021f" />

*Img 14 & Img 15: Tines workflow generated*<br>
![14 Tines](https://github.com/user-attachments/assets/a5d45724-5f50-478b-8595-1550f16d356e)
![15 Tines](https://github.com/user-attachments/assets/3534d388-0f6c-485d-a0a4-67ac4a31bc05)

*Img 16: Slack message with the detection caught and the case where the user didn't isolate the machine*<br>
<img width="503" alt="16 slack_mssg" src="https://github.com/user-attachments/assets/c7522924-0fb2-4b13-8a78-e9062ed29987" />

*Img 17: Email alert*<br>
<img width="448" alt="17 email_alert" src="https://github.com/user-attachments/assets/e4130667-ec6f-45ae-aaa3-dad067ece1f9" />

*Img 18: Case where the machine has been isolated*<br>
![18 isolated_machine](https://github.com/user-attachments/assets/155fe2c6-8bcf-43cf-956a-2a31fbce7d6d)
