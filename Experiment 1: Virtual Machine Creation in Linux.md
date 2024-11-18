## **Experiment 1: Virtual Machine Creation in Linux**



### **AIM:**
To create and configure a virtual machine (VM) on a Linux system using VirtualBox, and install a guest operating system (e.g., Ubuntu) on the VM.



### **EQUIPMENT REQUIRED:**

1. **Hardware:**
   - A computer running a Linux distribution (e.g., Ubuntu, Fedora, CentOS).
   - Minimum 4 GB of RAM (8 GB recommended for better performance).
   - At least 20 GB of free disk space for VM storage.

2. **Software:**
   - **VirtualBox** (Hypervisor for creating and managing virtual machines).
     - Download from: [https://www.virtualbox.org/](https://www.virtualbox.org/).
   - **Operating System Image (ISO):**
     - Example: Ubuntu ISO file (download from [https://ubuntu.com/download/desktop](https://ubuntu.com/download/desktop)).

3. **Optional:**
   - **VirtualBox Extension Pack** (for additional features like USB support, RDP, etc.).



### **THEORY:**

**Virtualization** is the process of creating a virtual version of a physical system, such as a virtual machine (VM). This allows you to run multiple operating systems (OS) on a single physical machine by using software called a **hypervisor**.

There are two types of hypervisors:
- **Type 1 (Bare-metal):** Runs directly on the physical hardware, such as **KVM** or **Xen**.
- **Type 2 (Hosted):** Runs on top of an existing operating system, such as **VirtualBox**, **VMware**, or **Parallels**.

**VirtualBox** is a Type 2 hypervisor, which means it runs on top of the host operating system and manages virtual machines. Each virtual machine operates as if it is running on its own physical hardware, but it shares resources from the host system (CPU, RAM, storage).



### **ALGORITHM / PROCEDURE:**

1. **Install VirtualBox:**
   - Open the terminal and update the package list:
     ```bash
     sudo apt update
     ```
   - Install VirtualBox:
     ```bash
     sudo apt install virtualbox
     ```

2. **Download OS ISO:**
   - Download the desired operating system ISO (e.g., Ubuntu) from the official website:
     - Example: [Ubuntu](https://ubuntu.com/download/desktop).

3. **Launch VirtualBox:**
   - Open VirtualBox by searching it in the application menu or running the command:
     ```bash
     virtualbox
     ```

4. **Create a New Virtual Machine (VM):**
   - In VirtualBox, click on **New**.
   - Provide a name for your VM (e.g., "Ubuntu-VM").
   - Select the operating system type as **Linux** and the version (e.g., **Ubuntu 64-bit**).
   - Click **Next**.

5. **Allocate RAM:**
   - Assign memory (RAM) for the VM (e.g., 2GB or more).
   - Click **Next**.

6. **Create a Virtual Hard Disk:**
   - Choose **Create a virtual hard disk now** and click **Create**.
   - Choose the disk format (VDI is recommended).
   - Select whether you want a **Dynamically allocated** or **Fixed size** disk.
   - Set the size of the virtual hard disk (e.g., 20GB or more).
   - Click **Create** to finalize.

7. **Configure VM Settings:**
   - Go to **Settings** for the VM, adjust the following:
     - **Storage:** Attach the ISO file (e.g., Ubuntu ISO) to the VM.
     - **Network:** Configure network adapter settings (e.g., NAT or Bridged Adapter).
     - **System:** Adjust boot order if necessary, to ensure it boots from the ISO.

8. **Start the VM:**
   - Select the VM in the VirtualBox Manager and click **Start**.
   - The system will ask you to choose a startup disk; select the ISO file (Ubuntu ISO).
   
9. **Install the Guest Operating System:**
   - The VM will boot from the ISO and start the OS installation process.
   - Follow the on-screen instructions to install the operating system (e.g., Ubuntu):
     - Choose language, time zone, and keyboard layout.
     - Set up a username, password, and disk partitioning (usually automatic).
   
10. **Finish Installation:**
    - Once the installation is complete, the system will prompt you to restart the VM.
    - Remove the ISO file from the virtual CD/DVD drive after reboot.

11. **Log in and Configure the OS:**
    - After rebooting, you can log in using the credentials you created.
    - You now have a fully functioning virtual machine running the guest operating system.



### **OUTPUTS:**

- **[Leave blank]**



### **RESULT:**

The virtual machine was successfully created, and the guest operating system (e.g., Ubuntu) was installed and is running properly. The VM is fully functional for further use.
