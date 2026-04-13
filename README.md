# 🌌 Data Analysis of Expanding Universe with Redshift Values

> A comprehensive data analysis and visualization project investigating the cosmic expansion of the universe using **redshift (z) spectral measurements**—validating Hubble's Law through analysis of galaxy clusters, constellations, and stars at distances spanning millions of light-years.

---

## 📌 Project Overview

This project analyzes one of the most significant discoveries in modern cosmology: the expanding universe. The work demonstrates that distant astronomical objects are receding from us at velocities proportional to their distance, a foundational principle of cosmology discovered by **Edwin Hubble in 1929**.

**Key Scientific Concept:** When galaxies move away from Earth, the wavelengths of emitted light stretch due to space expansion, causing a **spectral shift toward the red end** of the electromagnetic spectrum. This phenomenon, known as **cosmological redshift**, provides direct evidence of the universe's expansion.

**Analysis Scope:**
- Galaxy clusters and their redshift measurements
- Constellations across the sky and their recession velocities
- Individual stars and their spectral characteristics
- Relationship between redshift (z) and distance (light-years)

---

## ✨ Key Features

| Feature | Description |
|---------|-------------|
| 📊 Multiple Data Sources | Galaxy clusters, constellations, and star catalogs |
| 🔴 Redshift Analysis | Cosmological redshift (z) values from spectroscopy |
| 📐 Hubble's Law Validation | Distance vs. recession velocity relationship |
| 🎨 Rich Visualizations | 6+ plot types (scatter, line, bar, combined) |
| 📈 Comparative Analysis | Cross-analysis between different object types |
| 💾 Data Organization | Structured Excel-based astronomical databases |
| 🌠 Cosmic Perspective | Distances up to millions of light-years |

---

## 🚀 Tech Stack

| Category | Tools |
|----------|-------|
| Language | Python 3.8+ |
| Data Handling | Pandas, NumPy |
| Visualization | Matplotlib |
| Data Format | Excel (.xlsx) |

---

## 📂 Dataset

The project utilizes three distinct astronomical datasets compiled from observational data:

### 1. Galaxy Clusters Dataset

**File:** `galaxy_clusters_final.xlsx`

| Column | Description |
|--------|-------------|
| **Name** | Galaxy cluster designation |
| **Redshift (z)** | Spectral redshift measurement |
| **Distance (Light Years)** | Calculated distance from redshift |

**Scope:** Major galaxy clusters with redshift values ranging from z ≈ 0.01 to z ≈ 0.3

### 2. Constellation Dataset

**File:** `Constellation_redshift_values.xlsx`

| Column | Description |
|--------|-------------|
| **Astronomical Clusters** | Constellation or galaxy cluster name |
| **Redshift Value (z)** | Measured spectral redshift |

**Scope:** Constellation-level analysis across ~30 astronomical regions

### 3. Star Dataset

**File:** `Stars_Redshift.xlsx`

| Column | Description |
|--------|-------------|
| **Redshift** | Star's spectral redshift |
| **Light Year** | Distance in light-years |

**Scope:** Individual star measurements within detectable range

---

## 🌌 Cosmological Background

### Hubble's Law

$$v = H_0 \times d$$

Where:
- **v** = recession velocity (km/s)
- **H_0** = Hubble constant (~70 km/s/Mpc)
- **d** = distance (megaparsecs or light-years)

### Redshift Relationship

$$z = \frac{\Delta \lambda}{\lambda_0} = \frac{\lambda_{observed} - \lambda_{rest}}{\lambda_{rest}}$$

Where:
- **z** = redshift parameter
- **Δλ** = wavelength shift
- **λ₀** = rest wavelength

**Interpretation:**
- z = 0: No shift (stationary object)
- z > 0: Redshift (object receding)
- z < 0: Blueshift (object approaching - rare in cosmology)

---

## 📊 Visualizations Generated

| Plot # | Type | Purpose |
|--------|------|---------|
| **001** | Scatter | Redshift vs. Distance (raw data points) |
| **002** | Line + Scatter | Distance vs. Redshift (blue-red markers) |
| **003** | Line + Scatter (dashed) | Sorted redshift-distance correlation |
| **004** | Bar | Constellation redshift comparison |
| **005** | Line | Constellation redshift behavior |
| **006** | Scatter | Constellation names vs. redshift |
| **007** | Scatter & Line (dashed) | Star redshift and distance analysis |

### Plot Characteristics
- Large figure sizes (12×8 to 18×15) for clarity
- Color-coded markers and lines for distinction
- Grid overlay for precise value reading
- Labeled axes with bold formatting
- Saved as high-resolution PNG files

---

## 🏗️ Data Processing Pipeline

```
Raw Excel Data (galaxy_clusters_final.xlsx)
     ↓
Load via Pandas (pd.read_excel)
     ↓
Extract Columns
├─ Redshift (z)
├─ Distance (Light Years)
└─ Name (Object identifier)
     ↓
Convert to NumPy Arrays
     ↓
┌─────────────────────────────────────┐
│   Exploratory Data Analysis (EDA)   │
│  - Min/Max redshift values          │
│  - Distance range                   │
│  - Redshift-distance correlation    │
└─────────────────────────────────────┘
     ↓
┌─────────────────────────────────────┐
│   Multi-dimensional Visualization   │
│  - Galaxy clusters plot             │
│  - Constellation analysis           │
│  - Star data visualization          │
└─────────────────────────────────────┘
     ↓
Generate Graphs/ Directory Output
```

---

## ⚙️ Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/singularity-14/Data-Analysis-of-Expanding-Universe.git
cd Data-Analysis-of-Expanding-Universe
```

### 2. Install dependencies
```bash
pip install pandas numpy matplotlib openpyxl
```

### 3. Verify data files exist
```bash
# The following data files should be in the Data/ directory:
# - galaxy_clusters_final.xlsx
# - Constellation_redshift_values.xlsx
# - Stars_Redshift.xlsx

ls Data/
```

### 4. Run the notebook
```bash
jupyter notebook Expanding_Universe.ipynb
```

### 5. View results
```bash
# Generated plots are saved in the Graphs/ directory
ls Graphs/
```

---

## 💻 Usage Example

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# Load galaxy cluster data
df = pd.read_excel("Data/galaxy_clusters_final.xlsx")

# Extract key columns
redshift = np.array(df["Redshift"])
distance = np.array(df["Light Years Distance"])
names = np.array(df["Name"])

# Analyze redshift-distance relationship (Hubble's Law)
plt.figure(figsize=(12, 7))
plt.scatter(redshift, distance, color="black")
plt.title("Hubble's Law: Redshift vs. Distance", fontsize=20)
plt.xlabel("Redshift (z)", weight="bold")
plt.ylabel("Distance (Light Years)", weight="bold")
plt.grid()
plt.show()

# Statistical analysis
print(f"Redshift range: {redshift.min():.4f} to {redshift.max():.4f}")
print(f"Distance range: {distance.min():.0f} to {distance.max():.0f} light-years")
print(f"Correlation coefficient: {np.corrcoef(redshift, distance)[0,1]:.4f}")
```

---

## 📂 Project Structure

```
Data-Analysis-of-Expanding-Universe/
│
├── Expanding_Universe.ipynb            # Main analysis notebook
├── Data/                               # Input data directory
│   ├── galaxy_clusters_final.xlsx      # Galaxy cluster dataset
│   ├── Constellation_redshift_values.xlsx # Constellation data
│   └── Stars_Redshift.xlsx             # Star data
├── Graphs/                             # Output visualization directory
│   ├── Expanding_Universe_001.png      # Redshift vs. Distance scatter
│   ├── Expanding_Universe_002.png      # Distance vs. Redshift line
│   ├── Expanding_Universe_003.png      # Sorted correlation plot
│   ├── Expanding_universe_004.png      # Constellation line plot
│   ├── Expanding_universe_005.png      # Constellation bar chart
│   ├── Expanding_universe_006.png      # Constellation scatter
│   └── Expanding_universe_007.png      # Star redshift analysis
├── Project_Report/                     # Detailed findings report
├── README.md                           # This documentation
└── LICENSE                             # MIT License
```

---

## 🔬 Key Findings & Interpretations

### Hubble's Law Confirmation

The analysis demonstrates a **strong linear positive correlation** between redshift values and distance:
- As redshift (z) increases, distance increases proportionally
- This validates the fundamental principle that the universe is expanding uniformly

### Redshift Distribution

**Galaxy Clusters:**
- Typical z values: 0.01 to 0.3
- Higher redshift indicates faster recession velocity
- Distant clusters show higher redshift values

**Constellations:**
- Redshift varies by direction (spatial isotropy)
- Some regions show higher redshift concentrations
- Indicates non-uniform local expansion rates

**Stars:**
- Smaller z values due to relatively closer distances
- Fine detail in nearby universe structure
- Individual stellar motions blend with cosmic expansion

---

## 💡 Key Learnings & Takeaways

- **Hubble's Law is Universal:** Redshift-distance relationship holds across all observable galaxy populations
- **Cosmological Redshift:** Results from space expansion, not Doppler effect alone (key distinction)
- **Distance Metrics:** Redshift (z) provides a direct, measurable distance indicator in cosmology
- **Data-Driven Cosmology:** Large-scale astronomical surveys confirm Einstein's universe models
- **Visualization Impact:** Multiple plot types reveal different aspects of cosmic expansion
- **Statistical Validation:** Linear correlation analysis confirms proportional relationship
- **Precision Measurement:** Spectroscopic redshift provides precise distance determination to millions of light-years
- **Cosmic Perspective:** The universe expands homogeneously, with no special central location

---

## 📖 Scientific References

1. **Hubble, E.P.** (1929). "A Relation between Distance and Radial Velocity among Extra-Galactic Nebulae." *PNAS* 15(3): 168-173.

2. **Standard Cosmological Model (ΛCDM)**
   - Accelerating expansion driven by dark energy
   - Hubble constant H₀ ≈ 70 km/s/Mpc

3. **Redshift and Cosmological Distance**
   - Comoving distance calculations
   - Luminosity distance determinations

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

*A data-driven exploration of the expanding universe, demonstrating how spectroscopic observations and statistical analysis reveal the large-scale structure and dynamics of the cosmos.*
