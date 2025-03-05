#  Suricata IDS Setup & Configuration  

## Introduction  
In this project, I installed and configured `Suricata` as an IDS (Intrusion Detection System). I also tested its ability to detect alerts by customizing its rule set.

---

 1️⃣ Installation of Suricata  
To install `Suricata` on Ubuntu, I used the following commands:

sudo apt update
sudo apt install -y suricata

#After installation, I verified that Suricata was running:
sudo systemctl status suricata

 2️⃣ Configuring Suricata Rules
I modified the Suricata rules file located at:
/var/lib/suricata/rules/suricata.rules
To add a custom rule, I edited the file and added:
alert http any any -> any any (msg:"Test Alert - HTTP Access Detected"; sid:1000001; rev:1;)
Then, I restarted Suricata:
sudo systemctl restart suricata

3️⃣ Testing Alerts
To test if Suricata was detecting HTTP access, I ran:
curl http://testmyids.com
I checked for alerts in the log file:
sudo tail -f /var/log/suricata/fast.log

✅ Results
Suricata successfully detected the HTTP request and generated an alert in fast.log.
This was my first experience setting up an IDS, and I plan to explore more advanced configurations in the future!

تحرير
