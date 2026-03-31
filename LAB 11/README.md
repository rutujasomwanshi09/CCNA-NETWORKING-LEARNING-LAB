# EtherChannel Configuration (Manual Mode - ON)

## 📌 Project Title
Manual EtherChannel Configuration using ON Mode

## 🎯 Objective
To configure EtherChannel manually using ON mode between multiple switches and verify link aggregation.

## 🖥️ Devices Used
- 3 Switches (2960-24TT)
  - S1
  - S2
  - S3

## 🔗 Topology Description

- S1 connected to S2 (Channel Group 2)
- S1 connected to S3 (Channel Group 1)
- S2 connected to S3 (Channel Group 3)

All connections are configured using Manual EtherChannel (ON Mode)

## ⚙️ EtherChannel Mode

- Mode: ON (Manual)
- Protocol: None (Manual EtherChannel)

## 📡 Channel Groups

| Switch | Channel Group | Connected To |
|--------|--------------|--------------|
| S1 | Channel Group 1 | S3 |
| S1 | Channel Group 2 | S2 |
| S2 | Channel Group 2 | S1 |
| S2 | Channel Group 3 | S3 |
| S3 | Channel Group 1 | S1 |
| S3 | Channel Group 3 | S2 |


## 🧪 Verification Commands
- show etherchannel summary
- show running-config
- show interface trunk


## ✅ Expected Result

- EtherChannel formed successfully
- Port-channel interfaces created
- Links bundled successfully

## 📚 Learning Outcome

- Manual EtherChannel Configuration
- Channel Group Configuration
- Trunk Configuration
- Verification Commands
