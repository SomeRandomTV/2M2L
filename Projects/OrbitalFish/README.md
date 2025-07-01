# 🚀 OrbitalFish

OrbitalFish is a Machine Learning algorithm (part of **2M²L**) built to classify Kepler Objects of Interest (KOIs) as **Planets** or **False Positives**.

Data sourced from the [NASA Exoplanet Archive](https://exoplanetarchive.ipac.caltech.edu/).

---

## 🔭 Features Used

### 1. Transit Shape & Timing
| Feature            | Unit      | Description                                                 |
|--------------------|-----------|-------------------------------------------------------------|
| **`koi_period`**   | days      | Orbital period of the candidate                             |
| **`koi_duration`** | hours     | Duration of the transit dip                                 |
| **`koi_depth`**    | ppm       | Transit depth (planet-to-star area ratio)                    |
| **`koi_impact`**   | —         | Impact parameter (0 = central, 1 = grazing)                  |

### 2. Planetary Properties
| Feature            | Unit          | Description                                                    |
|--------------------|---------------|----------------------------------------------------------------|
| **`koi_prad`**     | Earth radii   | Inferred planet radius                                         |
| **`koi_teq`**      | K             | Equilibrium temperature estimate                               |
| **`koi_insol`**    | Earth flux    | Incident stellar flux relative to Earth                        |

### 3. Signal Quality & False-Positive Flags
| Feature                | Type  | Description                                                        |
|------------------------|-------|--------------------------------------------------------------------|
| **`koi_model_snr`**    | —     | Signal-to-noise ratio of the transit fit                           |
| **`koi_fpflag_nt`**    | 0/1   | Non-transit variability flag                                       |
| **`koi_fpflag_ss`**    | 0/1   | Stellar variability flag                                           |
| **`koi_fpflag_co`**    | 0/1   | Centroid offset flag                                               |
| **`koi_fpflag_ec`**    | 0/1   | Eclipsing-companion flag                                           |

### 4. Host-Star Parameters
| Feature            | Unit        | Description                                                   |
|--------------------|-------------|---------------------------------------------------------------|
| **`koi_steff`**    | K           | Stellar effective temperature                                 |
| **`koi_slogg`**    | cgs         | Stellar surface gravity                                       |
| **`koi_srad`**     | Solar radii | Stellar radius                                                |
| **`koi_kepmag`**   | mag         | Kepler-band magnitude                                         |

---

## 🔍 What Is a Transit?

A **transit** occurs when a KOI passes between the observer (Earth/Telescope) and its host star, causing a temporary dip in brightness. This dip:

- Reveals the **size** of the planet (via depth).  
- Yields the **orbital period** (via repeated dips).  
- Helps infer if a KOI lies in the **Goldilocks zone** (via equilibrium temperature).

---

## 🌍 Planetary Insights

- **`koi_prad`** helps distinguish **Rocky** vs. **Gas-Giant** worlds.  
- **Equilibrium temperature** (`koi_teq`) indicates potential **habitability**.

---

## ⚠️ False Positives

Flags (`koi_fpflag_*`) highlight:

- **Instrumental artifacts**  
- **Stellar variability**  
- **Eclipsing binaries** mimicking planetary signals  

---

## ⭐ Host-Star Context

Host-star parameters (`koi_steff`, `koi_slogg`, `koi_srad`, `koi_kepmag`) provide:

- The **stellar environment** shaping transit characteristics.  
- **Validation** of inferred planetary properties.

---

_OrbitalFish_ transforms the art of exoplanet discovery into a data-driven engine, separating true worlds from imposters across the cosmos.
