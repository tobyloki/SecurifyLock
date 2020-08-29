# SecurifyLock
CodeDay Summer 2020

### Communication Scheme
Lock <---> Receiver <---> Azure Sphere

### Arduino Lock/lock/lock.ino
- code for the actual lock with RFID and RF capabilities to open/close a lock via a relay
- forwards/receives data by the receiver over RF communication

### Arduino Lock/receiver/receiver.ino
- receives data sent by the lock indicating whether it is open/close
- also sends data to lock to open/close
- forwards/receives data by Azure Sphere over SPI communication

### Azure Sphere/azure-sphere-samples/Samples/AzureIoT/main.c
- receives data sent by the receiver indicating wheter it is open/close
- also sends data to receiver to open/close
- forwards/receives data by Azure IoT Cloud over WiFi
- (based on original sample, but added/removed code for SPI, GPIO control, timers, etc.)

### Wix Website
- web-based app to control/monitor lock
- communicates to Azure IoT Cloud over internet