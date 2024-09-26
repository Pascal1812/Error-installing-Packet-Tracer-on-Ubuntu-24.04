# Fixing Packet Tracer Installation Errors on Ubuntu 24.04

This guide provides steps to fix the dependency issues encountered when installing **Packet Tracer** on Ubuntu 24.04. The error typically relates to missing dependencies like `libgl1-mesa-glx`.

### Issue

When attempting to install `Packet_Tracer822_amd64_signed.deb`, you may encounter the following error due to unmet dependencies:

```bash
packettracer depends on libgl1-mesa-glx; however:
  Package libgl1-mesa-glx is not installed.
```

## Solution

Follow these steps to resolve the issue and successfully install Packet Tracer:

### 1. Update Your System

First, ensure that your system's package list is up to date:

```bash
sudo apt update
```

### 2. Download the Missing Package

You can download the missing package (`libgl1-mesa-glx`) from the following GitHub repository:

[Download Missing Package](https://github.com/PetrusNoleto/Error-in-install-cisco-packet-tracer-in-ubuntu-23.10-Dependency-is-not-satisfiable-libgl1-mesa-glx/releases/tag/Dependency-is-not-satisfiable-libgl1-mesa-glx)

### 3. Install the Missing Package

Once downloaded, use `dpkg` to install the missing dependency:

```bash
sudo dpkg -i <path_to_downloaded_libgl1-mesa-glx_package>
```

### 4. Fix Broken Dependencies (if needed)

If any issues remain after installing Packet Tracer, you can resolve them by running the following command:

```bash
sudo apt --fix-broken install
```
### 5. Install Packet Tracer

After resolving the missing dependency, install Packet Tracer using the `.deb` installer:

```bash
sudo dpkg -i Packet_Tracer822_amd64_signed.deb
```


### Additional Notes

If you continue encountering issues or missing dependencies, check for any additional packages needed or refer to online support communities for further assistance.