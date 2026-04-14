### 🚀 VASP 6.5.1 for Windows

This repository contains the **Windows port** of VASP (Vienna Ab initio Simulation Package) version 6.5.1.

> **⚠️ Important Note:**
> VASP is copyrighted software. You must have a valid VASP license to use this software legally. This repository only provides the compilation for Windows users.

---

### 🛠️ Installation & Setup

To use these binaries, you need to configure your environment correctly.

#### 1. Prerequisites
- **Intel oneAPI:** The binaries are compiled using the Intel oneAPI toolkit. It is **highly recommended** to install the [Intel oneAPI Base Toolkit](https://www.intel.com/content/www/us/en/developer/tools/oneapi/base-toolkit.html) to ensure all runtime libraries (MPI, etc.) are available.
- **License Files:** Ensure you have the necessary `potcar` files and a valid license in your working directory.

#### 2. Add to System PATH
For convenience, you should add the directory containing the executables to your Windows **PATH** environment variable.

**How to do it:**
1.  Open the Start menu, search for **"Environment Variables"**, and select **"Edit the system environment variables"**.
2.  Click the **"Environment Variables..."** button.
3.  Under **"System variables"**, find the **`Path`** variable and select **Edit**.
4.  Click **New** and add the full path to the folder where `vasp_std.exe` is located.
5.  Click **OK** to save.

---

### ⚡ Usage

Once the PATH is configured, you can run VASP from the Command Prompt (`cmd`) or PowerShell using `mpiexec`.

#### Standard Calculation (vasp_std)
Used for general purpose calculations (Gamma point and k-points).
```bash
mpiexec -np <number_of_cores> vasp_std
```

#### Gamma-point Only (vasp_gam)
Optimized for calculations using only the Gamma point. Faster and requires less memory.
```bash
mpiexec -np <number_of_cores> vasp_gam
```

#### Non-Collinear Magnetism (vasp_ncl)
Required for non-collinear magnetic calculations and spin-orbit coupling.
```bash
mpiexec -np <number_of_cores> vasp_ncl
```

> **Tip:** Replace `<number_of_cores>` with the number of CPU cores you wish to utilize (e.g., `-np 32`).

---

### 📝 Version Info

- **VASP Version:** 6.5.1
- **Platform:** Windows (x64)
- **Compiler:** Intel oneAPI  mingw64 cygwin

### 📄 License

Please refer to the official [VASP license](https://www.vasp.at) terms.
