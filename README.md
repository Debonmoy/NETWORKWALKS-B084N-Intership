# My First Week Internship Task: Setting Up Kali Linux on VirtualBox

## Introduction

For my first-week internship task, I set up **Kali Linux on Oracle VM VirtualBox**. I wanted to prepare a virtual environment where I could practise Linux commands, explore networking, and work on cybersecurity tasks without changing my main operating system.

In this write-up, I have documented the steps I followed and the configuration I used while setting up my Kali Linux virtual machine.

## 1. Tools and requirements

Before starting, I made sure I had the following:

- A Windows host machine.
- Oracle VM VirtualBox installed.
- The Kali Linux ISO image downloaded from the [official Kali Linux website](https://www.kali.org/get-kali/).
- Enough available RAM and disk space to run the virtual machine.

I downloaded VirtualBox from the [official VirtualBox website](https://www.virtualbox.org/).

## 2. Creating a new virtual machine

I opened **Oracle VM VirtualBox Manager** and clicked on **New** to create a virtual machine.

I used the following details:

| Option | Value |
|---|---|
| VM name | Kali |
| Operating system type | Linux |
| Version | Debian (64-bit) |

I then created a virtual hard disk for the machine. I used a **60 GB virtual disk**, named `Kali.vdi`.

## 3. Configuring the system

After creating the VM, I selected it in VirtualBox Manager, opened **Settings**, and went to the **System** section.

I configured the resources as follows:

| Setting | Value |
|---|---:|
| Base memory (RAM) | Approximately 6055 MB |
| Processors | 4 |
| Boot order | Floppy, Optical, Hard Disk |
| Acceleration | Nested Paging, KVM Paravirtualization |

I allocated around 6 GB of RAM and 4 processors to give Kali enough resources for my initial practice. These settings depend on the host machine, so I made sure to leave enough resources for Windows as well.

## 4. Configuring the display

Next, I opened **Settings → Display** and checked the display configuration.

I used:

| Setting | Value |
|---|---|
| Graphics controller | VMSVGA |
| Video memory | 128 MB |
| Remote desktop server | Disabled |
| Recording | Disabled |

I kept the VMSVGA graphics controller for the Linux virtual machine and assigned 128 MB of video memory.

## 5. Configuring storage

I went to **Settings → Storage** to check the virtual machine's storage devices.

My configuration showed:

- An IDE controller with an optical drive.
- A SATA controller.
- A virtual hard disk named `Kali.vdi`.
- A virtual disk capacity of **60.00 GB**.

I used the optical drive to attach the Kali Linux ISO during installation. Once Kali was installed, the virtual machine could boot from its virtual hard disk.

## 6. Configuring the network

One of the important parts of the setup was configuring the virtual machine's network connection.

I opened **Settings → Network → Adapter 1**, enabled the network adapter, and used the following configuration:

| Setting | Value |
|---|---|
| Enable Network Adapter | Enabled |
| Attached to | NAT |
| Adapter type | Intel PRO/1000 MT Desktop (82540EM) |
| Promiscuous mode | Deny |
| Cable Connected | Enabled |

I selected **NAT (Network Address Translation)** so that Kali could access the internet through my host machine's network connection.

For this initial setup, NAT was sufficient. I can explore other networking modes, such as Bridged Adapter and Host-only Adapter, when I need them for specific lab exercises.

## 7. Starting Kali Linux

After checking the VM settings, I returned to VirtualBox Manager, selected **Kali**, and clicked **Start**.

I used the Kali Linux installation media to boot the VM and followed the installer prompts to complete the installation. After installation, I restarted the virtual machine and logged in to Kali.

> The screenshots I captured show the Kali VM running in VirtualBox and the terminal being used. They do not include every installation screen, so I have documented the installation flow here in summary.

## 8. Opening the terminal and creating my workspace

Once Kali was running, I opened the terminal and checked my current location:

```bash
pwd
```

The terminal showed that I was in:

```text
/home/debonmoy
```

I wanted to keep my internship-related work organised, so I created a separate directory named `internship` inside my home directory.

I ran:

```bash
mkdir internship
```

Then I moved into the newly created directory:

```bash
cd internship
```

To confirm that I was in the correct location, I ran:

```bash
pwd
```

The path was now:

```text
/home/debonmoy/internship
```

## 9. Creating my first text file

Inside the `internship` directory, I created a file named `mydetails.txt` using Nano:

```bash
nano mydetails.txt
```

I added my basic details to the file:

```text
name - Debonmoy Pal
location: India
```

After saving and exiting Nano, I used the `cat` command to check the contents:

```bash
cat mydetails.txt
```

The terminal displayed the information I had entered, confirming that the file was created successfully.

## 10. Commands I used

Here is a quick summary of the terminal commands I used during this task:

| Command | Purpose |
|---|---|
| `pwd` | Displays the current working directory. |
| `mkdir internship` | Creates the internship directory. |
| `cd internship` | Moves into the internship directory. |
| `nano mydetails.txt` | Creates or edits the text file using Nano. |
| `cat mydetails.txt` | Displays the contents of the text file. |

## 11. Final Virtual Machine Configuration

After completing the setup, my Kali Linux VM had the following configuration:

| Component | My configuration |
|---|---|
| Virtualization software | Oracle VM VirtualBox |
| VM name | Kali |
| Guest OS type | Debian (64-bit) |
| RAM | Approximately 6055 MB |
| CPU | 4 processors |
| Virtual hard disk | `Kali.vdi` |
| Disk capacity | 60 GB |
| Graphics controller | VMSVGA |
| Video memory | 128 MB |
| Network mode | NAT |
| Network adapter | Intel PRO/1000 MT Desktop (82540EM) |
| Promiscuous mode | Deny |
| Cable connected | Enabled |
| Working directory | `/home/debonmoy/internship` |
| Created file | `mydetails.txt` |

## 12. What I learned

Through this task, I got familiar with creating a virtual machine and configuring its basic resources. I also learned how to configure a virtual network adapter, work with the Kali Linux terminal, navigate directories, and create files using Nano.

Most importantly, I now have a dedicated Kali Linux environment ready for my upcoming cybersecurity practice and internship tasks.

## Conclusion

I successfully completed my first-week internship task by setting up Kali Linux on Oracle VM VirtualBox and preparing my initial workspace.

This is my first step towards getting more comfortable with Linux and practical cybersecurity tools. I look forward to learning more, experimenting in authorised lab environments, and taking on the upcoming internship tasks.

## Useful Resources

- [Kali Linux Downloads](https://www.kali.org/get-kali/)
- [Kali Linux Documentation](https://www.kali.org/docs/)
- [Oracle VM VirtualBox](https://www.virtualbox.org/)
- [VirtualBox User Manual](https://www.virtualbox.org/manual/)

---

*Documented by Debonmoy Pal — Week 1 Internship Task.*
