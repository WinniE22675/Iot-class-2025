# 📄 Debian Installation Report for IoT, MQTT, Kafka Course

> Students must complete all sections of this form during Debian installation and submit it upon completion.

---

## 🔧 General Information

| Title                  | Value                                               |
| -----------------------| --------------------------------------------------- |
| Full Name              | Pitipat Assanurak|
| Student ID             | 6510301007 |
| Installation Date      | 11 Jun 2025 |


---

## 🖥️ Device Information

- 💻 **Device Model / Type**: Dell Gateway Edge 5000 
- 🧬 **Firmware Type**:  
  - [ ] UEFI  
  - [x] BIOS  
- 🏷️ **Installation Type**:  
  - [x] Physical PC  
  - [ ] Virtual Machine (VM)

---

## 🗂️ Custom Partitioning

| Partition     | Size   | Filesystem | Mount Point       | Notes                                       |
|---------------|--------|------------|--------------------|----------------------------------------------|
| `udev`        | 1.9G   | devtmpfs   | `/dev`             | อุปกรณ์ virtual สำหรับ device files         |
| `tmpfs`       | 379M   | tmpfs      | `/run`             | พื้นที่หน่วยความจำชั่วคราว (RAM)          |
| `/dev/sda1`   | 29G    | ext4       | `/`                | พาร์ติชันหลักของระบบ                       |
| `tmpfs`       | 1.9G   | tmpfs      | `/dev/shm`         | ใช้สำหรับ shared memory                     |
| `tmpfs`       | 5.0M   | tmpfs      | `/run/lock`        | สำหรับเก็บ lock files (RAM)                |
| `tmpfs`       | 379M   | tmpfs      | `/run/user/1000`   | tmpfs เฉพาะ user ที่ใช้งาน (UID 1000)       |


---

## 🌐 Network Configuration (Static IP)

| Title                   | Value                                               |
| ------------------------| --------------------------------------------------- |
| Network Interface Name  | enp1s0     |
| IP Address              | 172.30.15.25 |
| Netmask                 | 255.255.255.0 |
| Gateway                 | 172.30.15.254 |
| DNS                     | 8.8.8.8 |

---

## 🖧 Hostname

- 🖥️ **Hostname Set**: FPT6510301007

---

## 👤 User Account

- 👨‍💻 **Username Created**: u6510301007
- 🔐 **Is a Root Password Set?**:  
  - [X] Yes  
  - [ ] No

---

## ✅ Additional Problems Notes (if any)

> _____________________________________________________________________  
> _____________________________________________________________________  
> _____________________________________________________________________

