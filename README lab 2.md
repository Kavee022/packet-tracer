# Lab Sheet 01 - VLAN Configuration (Switching)

This repository contains the configuration steps and notes related to **Lab Sheet 01** and **Lab Sheet 02** from the **National School of Business Management** networking curriculum.

---

## 📋 Lab 01 Objectives

* Create a VLAN and assign it a name based on your group number.
* Assign an IP address to the VLAN interface.
* Connect two PCs to the VLAN via switch ports.
* Configure IP addresses on PCs and verify connectivity using `ping`.

## 🔧 Lab 01 Tasks Breakdown

### 1. Create VLAN

```bash
Switch> enable
Switch# config t
Switch(config)# vlan 5
Switch(config-vlan)# name VL0105
```

### 2. Assign IP Address to VLAN Interface

```bash
Switch(config)# interface vlan 5
Switch(config-if)# ip address 10.1.5.254 255.255.255.0
Switch(config-if)# no shutdown
```

### 3. Assign Ports to VLAN

```bash
Switch(config)# interface fastEthernet 0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 5

Switch(config)# interface fastEthernet 0/2
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 5
```

### 4. Test Configuration

* Connect two PCs to Fa0/1 and Fa0/2 using UTP cables.
* Manually assign IP addresses:

  * **PC1:** `10.1.5.1`
  * **PC2:** `10.1.5.2`
* Use `ping 10.1.5.2` from PC1 to test.

---

## 📋 Lab 02 Objectives

* Reset the switch using `write erase`.
* Create **two VLANs**.
* Assign IP addresses to each VLAN interface.
* Assign different ports to each VLAN.
* Test PC-to-PC connectivity across VLANs.

## 🔧 Lab 02 Tasks Breakdown

### 1. Create Two VLANs

```bash
Switch(config)# vlan 5
Switch(config-vlan)# name VL0105

Switch(config)# vlan 6
Switch(config-vlan)# name VL0205
```

### 2. Assign IP Addresses to VLAN Interfaces

```bash
Switch(config)# interface vlan 5
Switch(config-if)# ip address 10.1.5.254 255.255.255.0
Switch(config-if)# no shutdown

Switch(config)# interface vlan 6
Switch(config-if)# ip address 10.2.5.254 255.255.255.0
Switch(config-if)# no shutdown
```

### 3. Assign Ports to VLANs

```bash
Switch(config)# interface fastEthernet 0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 5

Switch(config)# interface fastEthernet 0/2
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 6
```

### 4. Test Configuration

* PC1 connected to VLAN 5 port: `10.1.5.1`
* PC2 connected to VLAN 6 port: `10.2.5.2`
* Test connectivity with `ping`.

---

## 🧰 Cisco Command Summary

| Task                         | Command                       |
| ---------------------------- | ----------------------------- |
| Enable mode                  | `enable`                      |
| Enter configuration mode     | `config t`                    |
| Create VLAN                  | `vlan <ID>`                   |
| Name VLAN                    | `name <VLAN_NAME>`            |
| Interface config             | `interface FastEthernet 0/x`  |
| Assign VLAN to port          | `switchport access vlan <ID>` |
| Set access port mode         | `switchport mode access`      |
| VLAN interface IP assignment | `interface vlan <ID>`         |
| Assign IP to VLAN interface  | `ip address x.x.x.x y.y.y.y`  |
| Reset switch config          | `write erase`                 |

---

## 📂 Files

* `Lab Sheets01- Switchng.docx` – Lab 01 instruction file
* `Lab Sheets02- Vlan INterface.docx` – Lab 02 instruction file

---

## 🧑‍💻 Author

**Kaveesha Nethmini** &#x20;
Group 05 &#x20;
National School of Business Management (NSBM)

---

## 🔗 Repository Link

Feel free to clone this repository:

```bash
git clone https://github.com/Kavee022/packet-tracer.git
```

