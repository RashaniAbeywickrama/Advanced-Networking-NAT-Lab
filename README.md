# Network Address Translation (NAT) Configuration Lab

## Advanced Networking

---

## 📌 Project Overview

This laboratory exercise focuses on the implementation and verification of Network Address Translation (NAT) using Cisco routers.

The lab demonstrates three NAT techniques:

1. Static NAT
2. Dynamic NAT
3. Port Address Translation (PAT / NAT Overload)

The configurations were implemented in Cisco Packet Tracer and verified using connectivity tests and Cisco IOS commands.

## 🎯 Objectives

- Understand the operation of Network Address Translation.
- Configure Static NAT.
- Configure Dynamic NAT using a public IP address pool.
- Configure Port Address Translation (PAT).
- Verify and troubleshoot NAT configurations using Cisco IOS commands.

## 🖥️ Network Topology

The network consists of two internal networks connected to Router1, which communicates with Router2 through a serial connection.

## 🌐 IP Addressing Scheme

| Device | Interface | IP Address | Subnet Mask |
|---|---|---|---|
| PC1 | FastEthernet0 | 192.168.100.1 | 255.255.255.0 |
| PC2 | FastEthernet0 | 192.168.101.1 | 255.255.255.0 |
| Router1 | FastEthernet0/0 | 192.168.100.254 | 255.255.255.0 |
| Router1 | FastEthernet0/1 | 192.168.101.254 | 255.255.255.0 |
| Router1 | Serial0/3/0 | 210.10.10.1 | 255.255.255.248 |
| Router2 | Serial0/3/0 | 210.10.10.2 | 255.255.255.248 |

## ⚙️ Lab Implementation

### Part A – Static NAT Configuration

Static NAT establishes a permanent one-to-one mapping between a private IP address and a public IP address.

**Implementation:**
- Configured static NAT translation on Router1.
- Associated an internal private IP address with a public IP address.
- Tested communication between internal and external networks.
- Verified the NAT translation table.

**Verification commands:**

```bash
show ip nat translations
show ip nat statistics
```

### Part B – Dynamic NAT Configuration

Dynamic NAT automatically assigns public IP addresses from a predefined address pool when internal devices initiate communication with external networks.

**Implementation:**
- Configured an access list to identify internal addresses.
- Created a public IP address pool.
- Configured dynamic NAT mapping.
- Tested address translation.
- Verified dynamically allocated translations.

**Verification commands:**

```bash
show ip nat translations
show ip nat statistics
```

### Part C – Port Address Translation (PAT)

PAT, also known as NAT Overload, allows multiple internal devices to share a single public IP address by using different port numbers to identify individual connections.

**Implementation:**
- Configured PAT on Router1.
- Enabled NAT overload.
- Tested communication from internal devices.
- Verified translated addresses and port information.

**Verification commands:**

```bash
show ip nat translations
show ip nat statistics
```

## 🔍 Verification and Troubleshooting

The following Cisco IOS commands were used to inspect and verify NAT operations.

| Command | Purpose |
|---|---|
| `show ip nat translations` | Displays active NAT translations |
| `show ip nat statistics` | Displays NAT statistics |
| `show ip interface brief` | Checks interface status and IP addresses |
| `show running-config` | Displays the router configuration |
| `ping` | Tests network connectivity |

## 📊 Observations

- **Static NAT:** Provided a permanent one-to-one mapping between private and public IP addresses.
- **Dynamic NAT:** Allocated public IP addresses from a predefined pool when internal hosts initiated communication.
- **PAT:** Allowed multiple internal devices to share one public IP address by using different port numbers.

NAT translation tables and statistical outputs were used to confirm the operation of the configured translation methods.

## ✅ Conclusion

This laboratory exercise provided practical experience in configuring and verifying Static NAT, Dynamic NAT and Port Address Translation using Cisco routers.

The exercise demonstrated how NAT translates private IP addresses into public addresses, enabling communication with external networks while helping conserve public IPv4 address space.

It also improved practical understanding of NAT translation tables, IOS verification commands and network troubleshooting.

## 🧰 Technologies Used

- Cisco Packet Tracer
- Cisco IOS CLI
- Network Address Translation
- IPv4 Addressing
- Static NAT
- Dynamic NAT
- PAT (NAT Overload)

*University Networking Laboratory | BICT Undergraduate Portfolio*
