# 2603-TANAKA.Mao
2026年3月卒業  田中真央
# Overview
This project investigates the impact of massive concurrent client connections on the Eclipse Mosquitto MQTT broker.
In particular, it focuses on connection-oriented Denial-of-Service (DoS) attacks, where a large number of clients establish connections without actively transmitting messages.
The goal of this study is to clarify how such attacks affect broker memory consumption and runtime behavior, and to identify practical limitations in terms of simultaneous connections.


# Description
This study evaluates how increasing the number of simultaneous publisher connections affects broker memory usage and runtime behavior.
Even when little to no message transmission occurs, a large number of concurrent connections can exhaust connection management and OS resources, potentially leading to a denial-of-service condition.

Memory usage is measured using `/proc/[pid]/smaps`, and broker behavior is observed while gradually increasing the number of connections.



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

# References
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
