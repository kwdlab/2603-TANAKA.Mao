# 2603-TANAKA.Mao
2026年3月卒業  田中真央
# Overview
This project investigates the memory consumption characteristics of the Eclipse Mosquitto MQTT broker under a large number of concurrent client connections.
Rather than generating malformed traffic or high message rates, this study focuses on scenarios in which many legitimate MQTT clients establish and maintain connections simultaneously.

The objective of this work is to clarify how the number of concurrent connections affects broker memory usage and to estimate the scalability limits of Mosquitto in terms of connection management, which is an important consideration for large-scale IoT systems.



# Description
In this study, multiple MQTT publisher clients are launched concurrently to increase the number of simultaneous connections to a single Eclipse Mosquitto broker.
Each client establishes a connection, sends a minimal message once, and then keeps the connection open without further message transmission. This allows the evaluation to focus on the memory overhead associated with connection management rather than message processing.

Broker memory usage is measured by comparing the resident set size (RSS) at broker startup with the RSS observed immediately after all client connections are established.
Memory statistics are collected using `/proc/[pid]/smaps`, enabling detailed observation of the broker’s memory consumption behavior as the number of concurrent connections increases.

# Requirements
- OS: Linux
- MQTT Broker: Eclipse Mosquitto
- Protocol: MQTT v5.0
- Measurement: procfs (`smaps`)

# Install / Usage
```bash
git clone https://github.com/kwdlab/2603-TANAKA.Mao.git
```
To build Eclipse Mosquitto listed in the References section, first clone the official Mosquitto repository.
Next, download this repository and replace the corresponding source files in the Mosquitto source tree with the files provided here if files with the same names already exist.
After replacing the files, compile Mosquitto using the standard build commands.


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
