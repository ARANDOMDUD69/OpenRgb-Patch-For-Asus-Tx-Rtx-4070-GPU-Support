# OpenRGB Patch: ASUS TX GeForce RTX 4070 Gaming OC

An SMBus and Aura GPU controller detection patch for **OpenRGB** that adds RGB control support for the **ASUS TX Gaming NVIDIA GeForce RTX 4070 OC** on Linux.
ENSURE I2C BUS IS ACCESSABLE FOR GPU AFTER OPENRGB INSTALL
## Hardware & Patch Specifications

- **Target Card:** ASUS TX GeForce RTX 4070 Gaming OC
- **PCI Device ID:** `0x2786`
- **Sub-Vendor ID:** `0x8923`
- **I2C / SMBus Target Address:** `0x67`
- **Patched Files:**
  - `Controllers/AsusAuraGPUController/AsusAuraGPUControllerDetect.cpp`
  - `Controllers/ENESMBusController/ENESMBusControllerDetect.cpp`

---

## Building and Applying the Patch on Ubuntu / Debian

### 1. Clone OpenRGB Upstream Source
```bash
git clone [https://gitlab.com/CalcProgrammer1/OpenRGB.git](https://gitlab.com/CalcProgrammer1/OpenRGB.git)
cd OpenRGB
git apply /path/to/asus_tx_rtx4070_smbus.patch

#if using ubuntu based os:

sudo apt update 
sudo apt install build-essential qt6-base-dev qt6-tools-dev libusb-1.0-0-dev libhidapi-dev libmbedtls-dev

qmake6 OpenRGB.pro
make -j$(nproc)

sudo ./OpenRGB
