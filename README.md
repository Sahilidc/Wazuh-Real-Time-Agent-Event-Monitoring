# Wazuh Real-Time Agent Event Monitoring
This project demonstrates real-time monitoring of events on a Wazuh agent and how they are displayed in the Wazuh manager. The setup involves configuring both the agent and manager to ensure that file addition events and configuration changes are captured and reported correctly.

### Screenshots
###### File Added Event: Screenshot of a file addition event detected by the Wazuh agent.
![fileaddedtoroot](https://github.com/user-attachments/assets/e3c06d35-c021-4cab-9eb4-20d1dc598ad7)

###### ossec.conf Configuration Changes:
![loc for file config](https://github.com/user-attachments/assets/9cce9833-1e05-49c1-98c5-e8ce8aa70b0d)

###### Agent: Configuration changes to enable real-time monitoring on the Wazuh agent.
![wazuh agent changes](https://github.com/user-attachments/assets/13113519-5025-473a-bf1a-77e52b2bb9d8)

###### Manager: Configuration changes on the Wazuh manager to handle and display agent events.
![wazuh manager change](https://github.com/user-attachments/assets/9c59d175-b200-4295-a5f0-e3480c9bd372)

###### Event Logs: Logs showing the real-time event details as captured by the Wazuh manager.
![realtim2](https://github.com/user-attachments/assets/932af064-3379-468f-9e1d-b584d0523651)


### Setup and Configuration
#### Prerequisites
Wazuh Manager deployed on Ubuntu using Docker.
A Windows VM set up as a Wazuh agent.

##### Step 1: Configure the Wazuh Agent
Modify the ossec.conf file on the Wazuh agent to enable the required monitoring modules.
```yaml
nano /var/ossec/etc/ossec.conf
```
`
Ensure the <localfile> entries are configured to monitor the necessary directories and file changes.

##### Step 2: Configure the Wazuh Manager
Modify the ossec.conf file on the Wazuh manager to accept and display real-time events from the agent.

```yaml
nano /var/ossec/etc/ossec.conf
```

##### Step 3: Start the Wazuh Services

```yaml
# On the Wazuh Manager
systemctl restart wazuh-manager

# On the Wazuh Agent
systemctl restart wazuh-agent

```

### Viewing Real-Time Events

Log into the Wazuh manager interface.
Navigate to the "Events" section to view real-time events captured from the agent.

    Screenshots
    Include the following screenshots:
    
    File Added Event.
    ossec.conf Changes for Agent.
    ossec.conf Changes for Manager.
    
	Event Logs.
