# Lab Sheet 01 - VLAN Configuration (Switching)

This repository contains the configuration steps and notes related to **Lab Sheet 01** from the **National School of Business Management** networking curriculum.

## 📋 Lab Objectives

* Create a VLAN and assign it a name based on your group number.
* Assign an IP address to the VLAN interface.
* Connect two PCs to the VLAN via switch ports.
* Configure IP addresses on PCs and verify connectivity using `ping`.

## 🔧 Lab Tasks Breakdown

### 1. Create VLAN

Use the following command format to create a VLAN and give it a name:

```bash
Switch> enable
Switch# config t
Switch(config)# vlan 5
Switch(config-vlan)# name VL0105
```

---

### 2. Assign IP Address to VLAN Interface

```bash
Switch(config)# interface vlan 5
Switch(config-if)# ip address 10.1.5.254 255.255.255.0
Switch(config-if)# no shutdown
```

---

### 3. Assign Ports to VLAN

Assign two switch ports (e.g., FastEthernet 0/1 and FastEthernet 0/2) to VLAN 5:

```bash
Switch(config)# interface fastEthernet 0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 5

Switch(config)# interface fastEthernet 0/2
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 5
```

---

### 4. Test Configuration

* Connect two PCs to Fa0/1 and Fa0/2 using UTP cables.
* Manually assign IP addresses:

  * **PC1:** `10.1.5.1`
  * **PC2:** `10.1.5.2`
* Verify connectivity using:

```bash
ping 10.1.5.2
```

(on PC1)

---

## 🧰 Cisco Command Summary

| Task                    | Command                       |
| ----------------------- | ----------------------------- |
| Enter config mode       | `config t`                    |
| Create VLAN             | `vlan <ID>`                   |
| Set VLAN name           | `name VL01XX`                 |
| Interface config        | `interface FastEthernet 0/x`  |
| Assign port to VLAN     | `switchport access vlan <ID>` |
| Set port mode to access | `switchport mode access`      |

---

## 📂 Files

* `Lab Sheets01- Switchng.docx` – Original lab instruction file

---

## 🧑‍💻 Author

**Kaveesha Nethmini**
Group 05
National School of Business Management (NSBM)

---

## 🔗 Repository Link

Feel free to clone this repository:

```bash
https://github.com/Kavee022/packet-tracer
```





