# Hybrid SEIRS-W Model for Dysentery Transmission

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXX)

A hybrid deterministic-stochastic compartmental model for dysentery transmission incorporating both waterborne and person-to-person pathways, with applications in epidemiology, public health intervention, and forecasting.

## 📋 Table of Contents
- [Overview](#overview)
- [Model Description](#model-description)
- [Installation](#installation)
- [Usage](#usage)
- [Repository Structure](#repository-structure)
- [Figures](#figures)
- [Data Availability](#data-availability)
- [Citation](#citation)
- [License](#license)
- [Contact](#contact)

## 🔬 Overview

This repository contains the complete implementation of the Hybrid SEIRS-W (Susceptible-Exposed-Infected-Recovered-Susceptible with Water compartment) model for dysentery transmission dynamics. The model integrates:

- **Dual transmission pathways**: Waterborne and person-to-person transmission
- **Environmental reservoir**: Water compartment tracking pathogen concentration
- **Seasonal variations**: Time-varying parameters for water contamination
- **Intervention strategies**: Sanitation, hygiene promotion, vaccination scenarios
- **Hybrid approach**: Deterministic ODEs with stochastic parameter uncertainty

## 📊 Model Description

### Compartments
- **S(t)**: Susceptible individuals
- **E(t)**: Exposed/Latent individuals
- **I(t)**: Infected individuals
- **R(t)**: Recovered individuals
- **W(t)**: Water pathogen concentration

### Key Parameters
| Parameter | Symbol | Description | Range/Value |
|-----------|--------|-------------|-------------|
| β | Transmission rate | Person-to-person | 0.5-4.0 |
| α | Contamination rate | Water contamination | 0-3.0 |
| ξ | Water transmission coefficient | - | 0-1.0 |
| γ | Recovery rate | 1/(duration) | 2.5-4.0 |
| ν | Pathogen decay rate | Water clearance | 3.0-6.0 |
| K | Half-saturation constant | Water transmission | 50-150 |
| σ | Incubation rate | 1/(latent period) | 4.0-8.0 |
| μ | Natural birth/death rate | - | 0.001-0.01 |
| δ | Disease-induced mortality | - | 0.001-0.01 |
| ω | Waning immunity rate | 1/(immunity duration) | 0.05-0.2 |

### Basic Reproduction Number
$$
\mathcal{R}_0 = \frac{\beta\sigma}{(\sigma+\mu)(\gamma+\mu+\delta)} + \frac{\xi\alpha\sigma}{K\nu(\sigma+\mu)(\gamma+\mu+\delta)}
$$

## 🚀 Installation

### Prerequisites
- Python 3.8 or higher
- pip package manager

### Method 1: Using pip
```bash
# Clone the repository
git clone https://github.com/abadiabraha20/hybrid_dysentery_model.git
cd hybrid_dysentery_model

# Install dependencies
pip install -r requirements.txt
