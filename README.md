# GNSS-Raw-Measurements-Dataset-u-blox-ZED-F9P
High-precision dual-frequency GNSS data with carrier phase measurements, interference detection, and complete navigation solutions.

# 📡 GNSS Dataset: u-blox ZED-F9P Dual-Frequency Measurements

![DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.XXXXXX-blue)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)
![Format](https://img.shields.io/badge/Format-UBX%2BCSV-orange)
![GNSS](https://img.shields.io/badge/GNSS-Dual--frequency-green)

## 📋 Dataset Overview

| Metric | Specification |
|--------|--------------|
| **Receiver** | u-blox ZED-F9P High Precision GNSS Module |
| **Antenna** | Survey-grade active patch antenna |
| **Platform** | Raspberry Pi 4B with automated logging |
| **Duration** | >1 hours continuous measurement |
| **Environment** | Urban/Rural transitional zone |
| **Data Rate** | 1 Hz (configurable to 10 Hz) |
| **Signals** | GPS L1/L2C, GLONASS L1/L2, Galileo E1/E5b BEIDOU|
| **Raw Output** | UBX binary format (R01.13 protocol) |
| **Processed** | CSV with navigation solutions |

## 📁 Files Included

### Primary Data Files:
- **`gps_20260203_015628.ubx`** (85.3 MB)
  - Raw UBX binary stream containing all measurements
  - Includes: Pseudorange, carrier phase, Doppler, SNR, navigation data
  - Format: u-blox proprietary binary (fully documented)

- **`gps_20260203_015628_clean.csv`** (2.1 MB)
  - Processed navigation solutions with quality metrics
  - 15 essential columns for analysis and visualization
  - Compatible with Python/R/Excel/Tableau

### Supporting Files:
- `dataset_metadata.json` - Complete dataset description (JSON-LD)
- `coordinate_system.pdf` - Coordinate reference system documentation
- `receiver_configuration.ubx` - Receiver configuration used

## 🎯 Target Applications

### Research & Academia
- **PPP/RTK Algorithm Development** - Dual-frequency carrier phase data
- **Ionospheric Studies** - L1/L2 differences for TEC calculation
- **Multipath Characterization** - Urban environment analysis
- **Receiver Performance** - Low-cost vs. geodetic-grade comparison

### Industry & Development
- **Autonomous Systems** - Sensor fusion and dead reckoning
- **Precision Agriculture** - Guidance system validation
- **Survey & Mapping** - Equipment testing and calibration
- **Timing Applications** - Network synchronization studies

### Education & Training
- **GNSS Signal Processing** - Real-world raw measurements
- **Geomatics Engineering** - Practical data analysis exercises
- **Python/R Programming** - Time-series and geospatial analysis

## 📊 CSV Data Dictionary

### Time References
| Column | Format | Description | Precision |
|--------|--------|-------------|-----------|
| `UTC_Time` | `YYYY-MM-DD HH:MM:SS.sss` | Coordinated Universal Time | 1 ms |
| `GPS_Time_ms` | Integer | GPS Time of Week (milliseconds) | 1 ms |
| `Fix_Time_ms` | Integer | Time since first fix | 1 ms |

### Position & Attitude
| Column | Units | Range | Accuracy |
|--------|-------|-------|----------|
| `Latitude` | Decimal degrees | -90 to 90 | 0.000001° |
| `Longitude` | Decimal degrees | -180 to 180 | 0.000001° |
| `Altitude_HAE_m` | Meters | -1000 to 20000 | 0.1 m |
| `Altitude_MSL_m` | Meters | -1000 to 20000 | 0.1 m |
| `Heading_deg` | Degrees | 0 to 360 | 0.01° |
| `Speed_kmh` | km/h | 0 to 2000 | 0.1 km/h |

### Quality Metrics
| Column | Units | Ideal | Poor |
|--------|-------|-------|------|
| `Satellites_Used` | Count | >8 | <4 |
| `HDOP` | Unitless | <1.0 | >5.0 |
| `PDOP` | Unitless | <2.0 | >8.0 |
| `VDOP` | Unitless | <1.5 | >6.0 |
| `Fix_Status` | Category | 3D | NO_FIX |

### Integrity Monitoring
| Column | Values | Description |
|--------|--------|-------------|
| `Jamming_Status` | OK/WARNING/CRITICAL | RF interference detection |
| `Fix_Status` | NO_FIX/2D/3D/GNSS+DR | Solution type |

## 🔬 Data Quality Assessment

### Statistical Summary
Dataset Statistics
Total observations: 5,412

Time span: >1 hour

Average HDOP: 1.2 ± 0.3

Average satellites: 9.4 ± 1.8

3D fix percentage: 98.7%

Jamming warnings: 0.3%

Position stability (σ): 0.8 m horizontal, 1.2 m vertical

### Quality Classification
| Class | HDOP | Satellites | Fix Type | Percentage |
|-------|------|------------|----------|------------|
| **Excellent** | <1.0 | >10 | 3D | 42.3% |
| **Good** | 1.0-2.0 | 7-10 | 3D | 48.1% |
| **Moderate** | 2.0-5.0 | 5-7 | 2D/3D | 8.9% |
| **Poor** | >5.0 | <5 | Any | 0.7% |


## Contact Points
Technical Questions: GitHub Discussions

Research Collaboration: research@example.com

Commercial Licensing: licensing@example.com

For questions, issues, or collaboration opportunities, please open an issue in the repository.
*Dataset collected and processed with u-blox ZED-F9P GNSS receiver and Raspberry Pi 4B platform*

## 🔗 Related Resources

Software Tools
u-center: u-blox official configuration software

RTKLIB: Open-source GNSS processing toolkit

PyGPSClient: Python GUI for GNSS data visualization

GNSS-SDR: Software-defined GNSS receiver


## Documentation
ZED-F9P Integration Manual

UBX Protocol Specification

RINEX Format Specification
