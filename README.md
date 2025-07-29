<<<<<<< HEAD
# FDIA Detection in Smart Grids Using PMU Data

Developed by **AOUF Nihed**  
Networks & Electrical Student @ ESGEE | Open to PFE Internship & Research Opportunities  
Inspired by KAUST & IEEE research on cybersecurity in energy systems

---

## Project Overview

This project explores the detection of **False Data Injection Attacks (FDIA)** in power systems by leveraging **Phasor Measurement Unit (PMU)** data, unsupervised learning techniques, and digital twin logic mimicking the decision-making of digital relays.

We use real PMU measurement data and simulate sophisticated attacks that mimic faults while remaining stealthy to traditional protection systems.

---

## Objectives

- Inject stealthy FDIA into real PMU measurements
- Train unsupervised models to detect anomalous patterns
- Simulate a basic digital relay decision logic
- Build a lightweight dashboard to visualize impact and detection

---

## Project Structure

```bash
smartgrid-fdia-ml/
│
├── 01_data_cleaning.ipynb          # Convert xlsx → CSV, clean + EDA
├── 02_fdia_simulation.ipynb        # Inject False Data into Normal PMU samples
├── 03_ml_fdia_detection.ipynb      # Train ML model for anomaly detection
├── 04_digital_relay_twin.ipynb     # Relay mimic logic + performance simulation
│
├── data/
│   ├── raw/
│   │   └── PMU_data.xlsx            # Original data
│   ├── processed/
│   │   ├── pmu_clean.csv            # Cleaned version
│   │   ├── pmu_fdia_only.csv        # FDIA-injected rows
│   │   └── pmu_with_fdia.csv        # Combined dataset (normal + FDIA)
│
└── README.md                       # Project documentation
```

---

## Dataset Info

**Source**: PMU Data from EPFL, available on [Mendeley](https://data.mendeley.com/datasets/ydcz98ky28/1)

**Size**: ~86,000 normal samples + 15,000 labeled fault samples  
**Resolution**: One measurement every 0.02s  
**Features**: Includes voltage/current magnitude & angle for all 3 phases, frequency, ROCOF, delay

### Fault Injection Simulation

We add synthetic FDIA based on known fault logic, e.g.:

- SLG Fault: `Ia ↑`, `Ib = Ic = 0`
- LL Fault: `Ia = 0`, `Ib = -Ic`, `Vb = Vc`
- LLG Fault: `Ia = 0`, `Vb = Vc = 0`
- FDIA: Modified voltage angles or frequency drift without violating physical models

---

## Model Architecture

We use an **Autoencoder Neural Network** to reconstruct normal PMU signal behavior. Samples with high reconstruction error are flagged as anomalous (FDIA or Fault).

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/5/5f/Autoencoder_structure.png" alt="Autoencoder Diagram" width="500"/>
</p>

---

## Digital Relay Twin Logic

We simulate the internal logic of a simple digital relay by:

- Thresholds on `Ia`, `Va_angle`, and `frequency`
- Delay logic and tripping simulation
- Compare decisions on clean, fault, and FDIA data

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/f5/Relay_logic_diagram.svg/1200px-Relay_logic_diagram.svg.png" alt="Relay Logic Diagram" width="400"/>
</p>

---

## Dashboard (Planned)

We plan to use **Streamlit** or **Dash** to create a simple web interface:

- Display raw vs. FDIA-injected PMU data
- Show detection results and thresholds
- Simulate digital relay decision outcomes

---

## Tech Stack

| Layer          | Tools Used                          |
| -------------- | ----------------------------------- |
| Data Analysis  | Python, Pandas, Seaborn, Matplotlib |
| ML/DL          | scikit-learn, joblib                |
| Relay Logic    | NumPy, thresholding                 |
| Dashboard (UI) | Streamlit / Dash                    |

---

## References & Reading

The project was inspired by recent works in power system cybersecurity:

1. S. Ghosh & C. Konstantinou,  
   *A Bi-Level Differential Game-Based Load Frequency Control With Cyber-Physical Security*, IEEE TSG, 2024.
2. J. D. de Hoz Diego et al.,  
   *CMXsafe: A Proxy Layer for Securing IoT Communications*, IEEE TIFS, 2024.
3. A. Intriago et al.,  
   *Residual-Based Detection of Attacks in Inverter-Based Microgrids*, IEEE TPWRS, 2024.
4. I. Zografopoulos et al.,  
   *Cybersecurity Outlook for Distributed Energy Resources*, IEEE Systems J., 2023.
5. I. Zografopoulos & C. Konstantinou,  
   *Detection of Malicious Attacks in Autonomous Microgrids*, IEEE TII, 2022.
6. S. Lakshminarayana et al.,  
   *Load-Altering Attacks in Low-Inertia Power Grids*, IEEE OAJPE, 2022.

---

## About the Author

AOUF Nihed  
Student in Electrical & Networks Engineering at ESGEE  
Passionate about energy systems, cyber-physical security, and applied AI  
Always open to research collaboration, PFE internships, and CPS security challenges

---

## License

This project is released under the MIT License.  
Data is for academic purposes only.
=======

>>>>>>> 86382c6e53726f159c35a20a974515bc693ce79c
