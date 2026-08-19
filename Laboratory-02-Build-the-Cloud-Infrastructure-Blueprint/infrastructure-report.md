## 🐧1. Operating System

The cloud server is running **Ubuntu 24.04.4 LTS**, with the release codename **Noble**. The operating system information is shown below.

| Information    | Result             |
| -------------- | ------------------ |
| Distributor ID | Ubuntu             |
| Description    | Ubuntu 24.04.4 LTS |
| Release        | 24.04              |
| Codename       | noble              |

> **Note:** The terminal displayed `No LSB modules are available.` However, the operating system information was still displayed correctly.

---

## 🔧2. Kernel Version

The server is running **Linux kernel version 6.8.0-136-generic**.

| Information    | Result            |
| -------------- | ----------------- |
| Kernel Version | 6.8.0-136-generic |

The kernel manages the system's hardware resources and provides the connection between the operating system and the underlying hardware.

---

## 🧠3. CPU Model

The server uses an **Intel Xeon E312xx (Sandy Bridge, IBRS update)** processor. The BIOS also reports the virtual machine configuration as **RHEL-9.6.0 PC (Q35 + ICH9, 2009) CPU @ 2.0GHz**.

| Information | Result                                        |
| ----------- | --------------------------------------------- |
| CPU Model   | Intel Xeon E312xx (Sandy Bridge, IBRS update) |
| BIOS Model  | RHEL-9.6.0 PC (Q35 + ICH9, 2009) CPU @ 2.0GHz |

---

## ⚙️4. Number of CPU Cores

The server has **1 CPU core** available.

| Information | Result |
| ----------- | -----: |
| CPU Cores   |      1 |

This CPU resource provides the processing capacity used by the operating system, applications, and running processes.

---

## 🧮5. Total RAM

The server has **1.9 GiB of total RAM**. At the time the system information was recorded, **460 MiB** was being used, while **743 MiB** was free and **1.4 GiB** was available.

| Memory Information |  Result |
| ------------------ | ------: |
| Total RAM          | 1.9 GiB |
| Used               | 460 MiB |
| Free               | 743 MiB |
| Shared             | 1.1 MiB |
| Buff/Cache         | 871 MiB |
| Available          | 1.4 GiB |
| Swap Total         | 1.0 GiB |
| Swap Used          |     0 B |
| Swap Free          | 1.0 GiB |

The server also has **1.0 GiB of swap space**, which was not being used at the time.

---

## 💿6. Disk Capacity

The main filesystem, `/dev/vda1`, has a total capacity of **19 GB**. It has **5.4 GB** of used space and **13 GB** of available space.

| Filesystem  |  Size |   Used | Available | Usage | Mount Point |
| ----------- | ----: | -----: | --------: | ----: | ----------- |
| `/dev/vda1` | 19 GB | 5.4 GB |     13 GB |   30% | `/`         |

The root filesystem `/` contains the main operating system files, directories, and installed applications.

---

## 🗂️7. Mounted File Systems

The server has several mounted filesystems that support different parts of the Linux environment.

| Filesystem   |   Size |   Used | Available | Usage | Mounted On  |
| ------------ | -----: | -----: | --------: | ----: | ----------- |
| `tmpfs`      | 191 MB | 996 KB |    190 MB |    1% | `/run`      |
| `/dev/vda1`  |  19 GB | 5.4 GB |     13 GB |   30% | `/`         |
| `tmpfs`      | 952 MB |  84 KB |    952 MB |    1% | `/dev/shm`  |
| `tmpfs`      | 5.0 MB |    0 B |    5.0 MB |    0% | `/run/lock` |
| `/dev/vda16` | 881 MB | 117 MB |    703 MB |   15% | `/boot`     |
| `/dev/vda15` | 105 MB | 6.2 MB |     99 MB |    6% | `/boot/efi` |

The `/` filesystem serves as the main root filesystem. The `/boot` and `/boot/efi` partitions contain files needed during the system startup process, while the `tmpfs` filesystems provide temporary storage used by the system.

---

## 🖥️8. Hostname

The hostname of the server is **`ubuntu`**.

| Information | Result |
| ----------- | ------ |
| Hostname    | ubuntu |

The hostname is used to identify the server within its environment.

---

## 🌐9. IP Address

The server has the following IP addresses:

| Address      | Result       |
| ------------ | ------------ |
| IP Address 1 | `172.30.1.2` |
| IP Address 2 | `172.17.0.1` |

Both addresses were returned by the `hostname -I` command.

