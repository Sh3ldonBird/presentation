I just ended up deploying the InsightVM platform within my homelab to play around with  
[Home-lab-VMs.png](https://github.com/Sh3ldonBird/presentation/blob/main/Environment/Rapid7/Home-lab-VMs.png)  
[Rapid7-InsightVM.png](https://github.com/Sh3ldonBird/presentation/blob/main/Environment/Rapid7/Rapid7-InsightVM.png)  
The pairing key kept messing up though. I'm going to have to return to it.  
# What I believe they're using going off of the job description
## [InsightVM](https://docs.rapid7.com/insightvm/)
https://docs.rapid7.com/insightvm/insightvm-quick-start-guide/
- Is this the system they're using to track their network vulnerabilities or are they using their network vendors solution?

## Network Sensor
- How many network sensors do they have deployed?
- How are they strewn about the network? Are they integrated with our current network vendor?


## Agent deployment
### Token
- How many organizations do we have and how many tokens do we have deployed?
	- Do we have different tokens depending on OS and/or region?
https://docs.rapid7.com/insight-agent/linux-installation/


#### Installation using .deb token no proxy
sheldonbird@Edge-Jumpbox:/opt/rapid7/ir_agent/components$ sudo -i
root@Edge-Jumpbox:~# cd /opt/rapid7/ir_agent/components/insight_agent/4.0.13.32/
root@Edge-Jumpbox:/opt/rapid7/ir_agent/components/insight_agent/4.0.13.32# ./configure_agent.sh --token=us3:6ab28401-6caf-4540-8f39-98d010633365 -v --start
[INFO] This is the latest version of this script available on this machine
[INFO] Configuring agent with token method
[INFO] 
[INFO] Retrieved configuration files using the provided token.
[INFO] The "disable-updates" argument is "", skipping configuration file creation.
[INFO] The "desired group" argument is empty and there is no file to delete.
[INFO] Getting proxy settings for connectivity test...
[INFO] Running connectivity tests...
[INFO] Running connectivity without proxy configurations
[INFO] No Proxy URL detected.                                                                                                                                                                                                                                                                                                                [INFO]
All Connectivity Tests Passed                                                                                                                                                                                                                                                                                                         [INFO]
[INFO] Connectivity Tests Passed
[INFO] Copying configuration file to --> /opt/rapid7/ir_agent/components/insight_agent/common
[INFO] Copying ssl files to --> /opt/rapid7/ir_agent/components/bootstrap/common/ssl
[INFO] Copying ./cafile.pem --> /opt/rapid7/ir_agent/components/bootstrap/common/ssl
[INFO] Copying ./client.crt --> /opt/rapid7/ir_agent/components/bootstrap/common/ssl
[INFO] Copying ./client.key --> /opt/rapid7/ir_agent/components/bootstrap/common/ssl
[INFO] Starting the ir_agent service...
[INFO] Checking on status: systemd
-- completed --
[INFO] Started ir_agent via systemctl
[INFO] Checking on status: systemd
-- completed --
● ir_agent.service - Rapid7 Insight Agent
     Loaded: loaded (/etc/systemd/system/ir_agent.service; enabled; preset: enabled)
     Active: active (running) since Sun 2024-12-15 01:02:36 PST; 1s ago
   Main PID: 588909 (ir_agent)
      Tasks: 36 (limit: 9217)
     Memory: 71.6M (peak: 75.1M)
        CPU: 731ms
     CGroup: /system.slice/ir_agent.service
             ├─588909 /opt/rapid7/ir_agent/ir_agent
             ├─588919 /opt/rapid7/ir_agent/components/agent_core/1.2.1.3/rapid7_agent_core
             ├─588920 /opt/rapid7/ir_agent/components/endpoint_broker/1.8.1.0/rapid7_endpoint_broker
             ├─588930 /opt/rapid7/ir_agent/components/insight_agent/4.0.13.32/ir_agent
             └─588956 /opt/rapid7/ir_agent/components/insight_agent/4.0.13.32/ir_agent -S -E -c "from multiprocessing.resource_tracker import main;main(9)"

Dec 15 01:02:36 Edge-Jumpbox systemd[1]: Started ir_agent.service - Rapid7 Insight Agent.
root@Edge-Jumpbox:/opt/rapid7/ir_agent/components/insight_agent/4.0.13.32# exit
logout
