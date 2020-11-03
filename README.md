# JumpCloudTest

JumpCloud Test Application Refuses Inbound/Outbound Connections:

Steps to recreate- 1) Unzip the .tz file into a folder of your choice
                   2) Follow the instructions to port the application to a random, yet available port on the operating system
                   3) Execute the Post command and grant the aplication permission to access the folder it is running from.
                   
                   Expected result - The application should retuen a password that is consistent with the format in the PDF example.
                   Actual result - The application refuses connections with the following output for each command - 
                   
s-iMac:broken-hashserve viks$ export PORT=8088Vs-iMac:broken-hashserve viks$ curl -X POST -H "application/json" -d '{"password":"angrymonkey"}' http://127.0.0.1:8088/hash 
curl: (7) Failed to connect to 127.0.0.1 port 8088: Connection refused
Vs-iMac:broken-hashserve viks$ curl -H "application/json" http://127.0.0.1:8088/hash/1
curl: (7) Failed to connect to 127.0.0.1 port 8088: Connection refused
Vs-iMac:broken-hashserve viks$ curl http://127.0.0.1:8088/stats
curl: (7) Failed to connect to 127.0.0.1 port 8088: Connection refused
Vs-iMac:broken-hashserve viks$ curl -X POST -d ‘shutdown’ http://127.0.0.1:8088/hash
curl: (7) Failed to connect to 127.0.0.1 port 8088: Connection refused

Operating/CLI system used - MacOSX Cataline 10.15.7, Mac Terminal.
