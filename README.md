###  VASP 6.5.1 for Windows (Binaries)

This repository provides pre-compiled binaries for **VASP 6.5.1** on Windows. We offer three different builds to suit your specific computational needs and system environments.

> **️ Important Note:**
> VASP is copyrighted software. You must have a valid VASP license to use these binaries legally. This repository only provides the Windows compilation binaries.

---

###  Versions & Requirements

Please select the version that best fits your workflow:

#### 1. Standard - oneAPI Version (Recommended for Performance)
- **Compiler:** Intel oneAPI (ifx/icc).
- **Description:** The standard build optimized for Intel architectures.
- **Requirements:** Requires **Intel oneAPI Base Toolkit** (specifically MPI libraries) to be installed and initialized.
- **Best For:** Users seeking maximum performance on Intel CPUs and who already have the Intel environment configured.

#### 2. Standard - MinGW64 Version (Standalone)
- **Compiler:** GCC (gfortran) via MinGW64.
- **Description:** A portable build that does not rely on Intel's heavy runtime libraries.
- **Requirements:** Minimal dependencies. Usually works out-of-the-box.
- **Best For:** Users who want a simple setup without installing the Intel oneAPI suite.

#### 3. VTST - MinGW64 Version (With Transition State Tools)
- **Compiler:** GCC (gfortran) via MinGW64.
- **Description:** Includes the **VTST (Transition State Tools)** scripts and source modifications.
- **Features:** Supports **NEB** (Nudged Elastic Band), **Dimer** method, and other advanced geometry optimization algorithms provided by the Henkelman group.
- **Requirements:** Same as the standard MinGW64 version.
- **Best For:** Users performing reaction path finding, transition state searches, or requiring VTST-specific functionalities.

---

### ️ Installation

1.  **Download:** Choose your preferred version from the releases and extract the archive.
2.  **Add to PATH:**
    To run VASP commands globally, add the extracted folder's `bin` directory to your Windows **Environment Variables**.
    -   Search for **"Environment Variables"** in the Windows Start menu.
    -   Under **"System variables"**, edit the **`Path`** variable.
    -   Add the full path to the folder containing `vasp_std.exe`.

---

###  Usage

Open **Command Prompt** (`cmd`) or **PowerShell** in your working directory.

#### Standard Execution
```bash
mpiexec -np <cores> vasp_std
```

#### Gamma-point Only (Optimized)
```bash
mpiexec -np <cores> vasp_gam
```

#### Non-Collinear / SOC
```bash
mpiexec -np <cores> vasp_ncl
```

> **Note:** Replace `<cores>` with the number of CPU threads (e.g., `-np 16`).

#### VTST Specifics (For VTST Version Users)
If you are using the **VTST version**, you can utilize additional scripts like `nebmake.pl` for setting up NEB calculations. Ensure the script directory is also in your PATH.

---

###  Version Comparison

| Feature | oneAPI Version | MinGW64 Version | **VTST (MinGW64)** |
| :--- | :--- | :--- | :--- |
| **Compiler** | Intel (ifx) | GCC (gfortran) | **GCC (gfortran)** |
| **Dependencies** | High (Intel Runtime) | Low (Standalone) | **Low (Standalone)** |
| **Performance** | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ |
| **VTST Tools** |  No |  No |  Yes |
| **Use Case** | Heavy Production | General Use | **Transition States/NEB** |

---


