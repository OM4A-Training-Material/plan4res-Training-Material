# 🧰 plan4res – Training Section

## 📘 Introduction

**plan4res** is an electricity system optimisation and simulation tool composed of three integrated models:

- **CEM** – *Capacity Expansion Model*: optimizes new generation, storage, and interconnection investments to meet demand while minimizing total system costs.
- **SSV** – *Seasonal Storage Valuation Model*: computes “water values” to optimize the use of seasonal storage during high-demand periods.
- **SIM** – *Simulation Model*: performs hourly system dispatch and unit commitment across a full year.

The plan4res ecosystem includes:
- 🔧 `p4r-env`: execution environment developed by CRAY & HPE ([GitLab](https://gitlab.com/cerl/plan4res/p4r-env))  
- 📦 Core models built using the `SMS++` library by the University of Pisa ([GitLab](https://gitlab.com/smspp/smspp-project))  
- 🛠️ Python tools for data treatment and visualization ([plan4res-scripts](https://github.com/plan4res/plan4res-scripts))  
- 🔁 Workflow management scripts ([include](https://github.com/plan4res/include))  

---

## 📚 Training Materials

You can access all documentation and tutorials for installing and using plan4res:

- 📄 [User Manual (PDF)](https://github.com/plan4res/documentation/blob/main/plan4resUserManual.pdf)  
  Includes:
  - Installation for Linux and Windows
  - Module descriptions and workflows
  - Input/output structure and file format
  - Tutorials on running modules and interpreting outputs

- 📊 [Introduction to plan4res](https://github.com/OM4A-Training-Material/plan4res-Training-Material/blob/main/plan4resIntroduction.pdf)  
  Overview of mathematical models and implementation

- 🛠️ [Installation Slide Guide](https://github.com/OM4A-Training-Material/plan4res-Training-Material/blob/main/plan4resInstall.pdf)  
  Walk-through of the installation steps

- 🧪 [How to Run plan4res](https://github.com/OM4A-Training-Material/plan4res-Training-Material/blob/main/plan4resRun.pdf)  
  Practical guide to executing models

---

## 💾 Installation

- Recommended system: **Linux** (or Windows Subsystem for Linux)
- Disk space required: **min. 3 GB**

### 🔧 Steps:
1. Clone the install repo:
   ```bash
   git clone https://github.com/plan4res/install
   cd install
   ./plan4res_install.sh
   ```
   > Use `./plan4res_install.sh -H` for help and options.

2. If using a server or external repo, configure your user:
   ```bash
   ./user_init_plan4res -D P4R_INSTALL_DIR
   ```
   > Use `./user_init_plan4res.sh -H` for more info.

---

## 🚀 Running plan4res

You can use the [toyDataset](https://github.com/plan4res/toyDataset) as an example.

1. **Create dataset** from IAMC inputs and time series:
   ```bash
   p4r CREATE toyDataset
   ```

2. **Format NetCDF data** for SSV (required by SMS++) out of plan4res csv data for each module - Seasonal Storage Valuation (SSV), simulation (SIM) and capacity expansion (CEM):
   ```bash
   p4r FORMAT toyDataset -M optim    # for SSV
   p4r FORMAT toyDataset -M simul    # for SIM
   p4r FORMAT toyDataset -M invest   # for CEM
   ```

3. **Run individual modules**:
   ```bash
   p4r SSV toyDataset     # Seasonal storage
   p4r SIM toyDataset     # Simulation
   p4r CEM toyDataset     # Capacity expansion
   ```

4. **Run full workflow**:
   ```bash
   p4r SSVandSIM          # Combined SSV + SIM
   p4r SSVandCEM          # Combined SSV + CEM
   ```

## 🎥 Step-by-step Video Support

You can find all tutorials on <a href="https://www.youtube.com/playlist?list=PLHN93NPePQ1IWXjwSWkLIyo6tAc0xT9Rd" target="_blank" style="text-decoration: none;">
  <img src="https://cdn.simpleicons.org/youtube/FF0000/16" alt="YouTube" height="16" style="vertical-align: text-bottom; margin-left: 4px;">
</a>

## ❓ Need Help?

Check our [Questions & Answers](docs/faq.md) page for common issues and guidance.

---

## 📬 Contact

For support and inquiries, please use the [plan4res contact form](https://plan4res.github.io/contact/contact.html).

---

References:  
Official repo: [https://github.com/plan4res](https://github.com/plan4res)  
