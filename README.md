![Made with MATLAB](https://img.shields.io/badge/Made%20with-MATLAB-orange)
![Research Project](https://img.shields.io/badge/Project-Research-blue)
![License MIT](https://img.shields.io/badge/License-MIT-green)

# Effect of reverse total shoulder arthroplasty on muscle synergies and shoulder kinematics

This repository contains the data processing and analysis scripts developed for a study on the **effect of reverse total shoulder arthroplasty** on **muscle synergies** and **joint kinematics**.  
The project aims to:  
- Process electromyographic (EMG) and kinematic data from patients before and after surgery, as well as from asymptomatic subjects;  
- Extract and compare **muscle synergies** (inter-muscular coordination);  
- Analyze humero-thoracic, scapulo-thoracic, and glenohumeral joint kinematics;  
- Perform inter-group statistical comparisons using ANOVA, t-tests, clustering analyses, SPM1D, and cosine similarity.  

The repository is organized into six main folders: **SYNERGIES**, **ELECTROMYOGRAPHY**, **KINEMATIC**, **CLUSTERING**, **MEAN PROFILE**, and **INDIVIDUAL ANALYSIS**. A user guide (in French) detailing each folder (6), file (19), and function (104) is also provided.  

---

## Table of Contents
- [1) SYNERGIES](#1-synergies)
- [2) ELECTROMYOGRAPHY](#2-electromyography)
- [3) KINEMATIC](#3-kinematic)
- [4) CLUSTERING](#4-clustering)
- [5) MEAN PROFILE](#5-mean-profile)
- [6) INDIVIDUAL ANALYSIS](#6-individual-analysis)

---

## 1) SYNERGIES
Preparation of EMG data for muscle synergy analysis based on functional movements.  
Divided into two subfolders:

### 1.1) solo_functional
- Processing of **a single functional movement** for **one subject**.  
- EMG extraction, processing, and normalization.  
- Automatic segmentation into **3 cycles** using the RHLE marker (elbow).  
- Signal cleaning, visualization, and export of the processed EMG matrix.  

### 1.2) main_functional
- Processing of **4 combined functional movements** (12 cycles).  
- Optional manual segmentation, artifact cleaning (standard deviation).  
- Concatenation of all EMG signals into a global matrix.  

---

## 2) ELECTROMYOGRAPHY
Analysis of muscle activations from analytical and functional movements.  
Organized into several subfolders:

### 2.1) Analytic
- Display of normalized raw signals from reference movements.  

### 2.2) Functional
- **Band-pass filtering** (15–475 Hz),  
- **Signal rectification** (full-wave),  
- **Smoothing** (Root Mean Square),  
- **Activation normalization** (task-specific maximal normalization),  
- Calculation of **mean activation profiles**, **signal-to-noise ratio**, and **muscle activation ratios**,  
- Artifact cleaning and detection of serratus anterior activity (cardiac artifacts).  
- Calculation of **muscle ratios**, **signal-to-noise ratio**, and **mean profiles**.  
- Preparation for **SPM1D** analysis on combined mean signals.  

---

## 3) KINEMATIC
Shoulder kinematic analysis using Euler angles.  

### 3.1) Main
- Extraction of glenohumeral, scapulo-thoracic, and humero-thoracic angles according to the International Society of Biomechanics (Wu et al., 2005) from Qualisys markers.  
- Cycle detection and validation, centering, correction, and angle filtering.  
- Calculation of **global means**, **peaks**, **amplitudes**, and **velocities**.  
- Inter-limb comparability (left vs. right shoulder).  

### 3.2) Plot_kin
- Plotting of **mean humero-thoracic elevation curves**.  
- Inter-group comparisons using **SPM1D**.  

---

## 4) CLUSTERING
Methods for clustering EMG and kinematic data.  

### 4.1) Kinematic clustering
- Clustering of **humero-thoracic elevation curves** using k-means.  
- Automatic cluster number selection via the **elbow method**.  

### 4.2) Synergies clustering
- Clustering of **W** (muscle weights) and **H** (temporal activations) vectors.  
- Combined application of **PCA** and **k-means**.  

---

## 5) MEAN PROFILE
Comparison of mean profiles extracted from muscle synergy analysis.  

### 5.1) Comparaison_VAF
- Comparison of **variance accounted for (VAF)** values between groups.  

### 5.2) Comparaison_SYN
- Comparison of **muscle weights (W)** and **activations (H)** using **ANOVA with post-hoc tests**.  
- Pearson correlations, barplots, and curves.  

---

## 6) INDIVIDUAL ANALYSIS
Individual analysis of EMG, kinematics, and synergy profiles.  

### 6.1) Electromyography
- Comparison of **EMG peaks** between groups, by muscle and subject.  

### 6.2) Kinematic
- Comparison of **humero-thoracic peaks and amplitudes** between groups and subjects.  

### 6.3) Synergy
- Calculation of **cosine similarity** between each individual synergy and the asymptomatic reference profile.
