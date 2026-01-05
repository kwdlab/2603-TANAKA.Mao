# 2603-TANAKA.Mao
2026年3月卒業  田中真央
# Overview
This repository contains experimental code and scripts used to evaluate the impact of massive concurrent connections on the Eclipse Mosquitto MQTT broker, focusing on concurrent-connection-based DoS attacks.

# Description
This study investigates how an increasing number of simultaneous publisher connections affects Mosquitto’s memory usage and stability.  
Even without significant message transmission, a large number of concurrent connections may exhaust broker-side or OS-level resources and lead to service disruption.

Memory usage is measured using `/proc/[pid]/smap

# Requirements
- OS: Linux
- MQTT Broker: Eclipse Mosquitto
- Protocol: MQTT v5.0
- Measurement: procfs (`smaps`)

# Install / Usage
```bash
git clone https://github.com/kwdlab/2603-TANAKA.Mao.git
```


# Author
Mao Tanaka

References
- MQTT Version 5.0 Specification
https://docs.oasis-open.org/mqtt/mqtt/v5.0/os/mqtt-v5.0-os.html
- Eclipse Mosquitto
https://github.com/eclipse-mosquitto/mosquitto
- procfs smaps documentation
https://man7.org/linux/man-pages/man5/proc_pid_smaps.5.html
- RFC 9431
https://www.rfc-editor.org/rfc/rfc9431.html

# License
- Eclipse Public License 2.0
- Eclipse Distribution License 1.0
