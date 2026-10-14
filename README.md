# OPENMM

![license](https://img.shields.io/badge/license-MIT-blue) ![offline-first](https://img.shields.io/badge/offline--first-air--gap-green) ![audit](https://img.shields.io/badge/audit-SHA3--256-orange) ![category](https://img.shields.io/badge/category-chemical_manufacturing-lightgrey)

> Anticloud-hardened packaging of the upstream project `OPENMM` in category **CHEMICAL MANUFACTURING**. Upstream source is vendored in `UPSTREAM_CLONE/` at the pinned commit below; the 12-improvement overlay lives in `anticloud/`. Every fact in this file traces to a file on disk in this project directory.

**Category:** CHEMICAL MANUFACTURING · **Upstream:** https://github.com/peterljq/OpenMMD · **Upstream pin:** `795d4dd660cf7e537ceb599fdb038c5388b33390` · **Vendor:** Anticloud FZ LLE

---

## What This Project Does

# OpenMMD

[![language](https://img.shields.io/badge/Language-Python-blue.svg)](https://img.shields.io/badge/Language-Python-blue.svg)

[OpenMMD](https://github.com/peterljq/OpenMMD) represents the OpenPose-Based Deep-Learning project that can directly **convert real-person videos to the motion of animation models (i.e. Miku, Anmicius)**. OpenMMD can be referred as OpenPose + MikuMikuDance (MMD). In short, you record a piece of video with human motions, through this project you will see a 3D model acting the same motions as what you do in the video.

<p align="center">
<img src="https://raw.githubusercontent.com/peterljq/OpenMMD/master/Readme%20Materials/OpenMMD-Anmicius-Static.jpg" width="240">
</p>

<p align="center">3D model example: Anmicius</p>

- [OpenPose](https://github.com/CMU-Perceptual-Computing-Lab/openpose) is the first real-time multi-person system proposed by Carnegie Mellon University used to jointly detect human body key points on single images or videos. 
- [MMD](https://sites.google.com/view/evpvp/) is a freeware animation program that lets users animate and create 3D animated movies using 3D models like Miku and Anmicius.
- OpenPose and MMD are only the "entrance" and "exit" of the application box. There are three intermediate pre-trained Deep Learning Models in the box to process and convert formatted data. They are stated in the Features section below.

## Features
The project implements multiple Deep Learning Models as a sequential chain. The output of the previous model will be fed as the input of the following. Some implementations are the edited version of the original for better performance in the application.
- **Functionality**:
    - **3D Single-person Key Points Detection (OpenPose)**:
        - **Proposed by Gines Hidalgo, Zhe Cao, Tomas Simon, Shih-En Wei, Hanbyul Joo, and Yaser Sheikh at CVPR 2017**.
        - Recoded real-person video input and JSON files collections of motion key points as the output.
    - **Strong Baseline for 3D Human Pose Estimation**:
        - **Proposed by Julieta Martinez, Rayat Hossain, Javier Romero, James J. Little In ICCV, 2017**. An effective baseline for 3d human pose estimation.
        - Combining all the key points JSON files to a continuous sequence with strong baselines.
    - **Unsupervised Adversarial Learning of 3D Human Pose from 2D Joint Locations** (Newly added feature. Under testing.):
        - **Proposed by Yasunori Kudo, Keisuke Ogaki, Yusuke Matsui, Yuri Odagiri at CVPR 2018**. The task of 3D human pose estimation from a single image can be divided into two parts: (1) 2D human joint detection from the image and (2) estimating a 3D pose from the 2D joints.
        - Implemented by @DwangoMediaVillage to fit to VMD format. Use of GAN will significantly improve the performance during the converting process than what achived by using the baseline methods.
    - **Video Depth Prediction**:
        - **Proposed by Iro Laina and Christian Rupprecht at the IEEE International Conference on 3D Vision 2016**. FCRN: Deeper Depth Prediction with Fully Convolutional Residual Networks.
        - Estimation of depth for objects, backgrounds and the moving person in the video (e.g. dancer).
    - **Human Motion Key Points to VMD Motion Files for MMD Build**:
        - **Proposed by Denis Tome, Chris Russell and Lourdes Agapito at CVPR 2017**. Convolutional 3D Pose Estimation from a single image.
        - Edited by @miu200521358 to output VMD files so that the formatted result can be directly fed to MMD for generating animated dancing movies.
- **Input**: videos of common formats (AVI, WAV, MOV) or images of common formats (PNG, JPG), 
- **Output**: Animations or Posetures of 3D models (e.g. Miku Dancing)
- **OS**: Windows (8, 10), MacOS (2017 Released Version)

## Example Presentation
### I. Record a piece of real-person motion video
<p align="center">
    <img src="https://github.com/peterljq/OpenMMD/blob/master/Readme%20Materials/Real-person%20Crop.gif?raw=true", width="160">
</p>

### II. Extraction of 3D keypoints with Continuous Baselines
<p align="center">
    <img src="https://raw.githubusercontent.com/peterljq/OpenMMD/master/Readme%20Materials/OpenMMD_smoothing.gif" width="320">
</p>

### III. Video Depth Prediction
<p align="center">
    <img src="https://github.com/peterljq/OpenMMD/blob/master/Readme%20Materials/OpenMMD_depth.gif?raw=true" width="280">
</p>

### IV. Output VMD files and construct to MMD animations
<p align="center">
    <img src="https://github.com/peterljq/OpenMMD/blob/master/Readme%20Materials/OpenMMD-Anmicius.gif?raw=true" width="240">
</p>

## Installation and User Guidelines
**Download the full pack**: Note that the full application is about 5GB. That is mainly because the large-size parameters of the pre-trained deep learning models. Download the whole pack contains the **pre-trained models with optimized parameters and corresponding compilable codes**. 

- [Google Drive](https://drive.google.com/file/d/197CWR_aOAd4vNflhWlxWmRVsAmeG5S1F/view?usp=sharing)
- [Baidu Netdisk (Temporarily Unavailable)](https://baidu.com)

**Follow the instruction to begin your first animation**: 
- Record a piece of video contains human motions. Satisfy all the prerequisite libraries stated below.
- After downloading, firstly **activate tensorflow** environment in the terminal of anaconda.
- Run OpenposeVideo.bat and follow the pop-out instructions.
- Then proceed to the 3d-pose-baseline-vmd folder and run OpenposeTo3D.bat. Follow the pop-out instructions.
- After that, proceed to the FCRN-DepthPrediction-vmd folder and run VideoToDepth.dat.
- Finally, proceed to the VMD-3d-pose-baseline-multi folder and run 3DToVMD.bat. You will get the vmd file.
- VMD files are 3D animation file used by **MikuMikuDance**, a program used to create dance animation movies. Open your MikuMikuDance and input the VMD file.
- You will see your Miku begin acting the same motions as that in your recorded video.

**Tutorial in Chinese

*(excerpt; full text in `UPSTREAM_CLONE/`)*

*Quoted from the upstream `README.md` file in `UPSTREAM_CLONE/`.*
Project-specific facts detected in this directory:

- Ecosystem: **Unknown (no standard manifest detected)** (manifests: none detected; scanned in UPSTREAM_CLONE)
- Top-level source layout: `3D Pose Baseline to VMD/`, `3D Pose by GAN/`, `3rdparty/`, `FCRN Depth Prediction for VMD/`, `MikuMikuDance/`, `Readme Materials/`, `VMD 3D Pose Baseline Multi-Objects/`, `bin/`, `examples/`, `include/`, `lib/`, `models/`
- Snapshot size: **998 files**, **104874 lines of code** (measured; see Benchmarks)
- Primary languages: `.hpp` (283), `.png` (208), `.json` (180), `.dll` (102), `.h` (57), `.py` (48)
- Upstream commit pinned for this packaging: `795d4dd660cf7e537ceb599fdb038c5388b33390`

---

## Installation

- **Proposed by Denis Tome, Chris Russell and Lourdes Agapito at CVPR 2017**. Convolutional 3D Pose Estimation from a single image.
        - Edited by @miu200521358 to output VMD files so that the formatted result can be directly fed to MMD for generating animated dancing movies.
- **Input**: videos of common formats (AVI, WAV, MOV) or images of common formats (PNG, JPG), 
- **Output**: Animations or Posetures of 3D models (e.g. Miku Dancing)
- **OS**: Windows (8, 10), MacOS (2017 Released Version)

*Section quoted from the upstream readme.*
Overlay install (this project):

```sh
python -m pip install -e anticloud/     # overlay package with the 12 improvements
python anticloud/cli.py --help          # 13 subcommands, JSON stdout
```

---

## Usage

- [OpenPose](https://github.com/CMU-Perceptual-Computing-Lab/openpose) is the first real-time multi-person system proposed by Carnegie Mellon University used to jointly detect human body key points on single images or videos. 
- [MMD](https://sites.google.com/view/evpvp/) is a freeware animation program that lets users animate and create 3D animated movies using 3D models like Miku and Anmicius.
- OpenPose and MMD are only the "entrance" and "exit" of the application box. There are three intermediate pre-trained Deep Learning Models in the box to process and convert formatted data. They are stated in the Features section below.

*Section quoted from the upstream readme.*
Anticloud overlay CLI (available in every project):

```sh
python anticloud/cli.py --help     # 13 subcommands, JSON stdout
python anticloud/cli.py checks     # run the 16-check suite
```

---

## API

- Edited by @miu200521358 to output VMD files so that the formatted result can be directly fed to MMD for generating animated dancing movies.
- **Input**: videos of common formats (AVI, WAV, MOV) or images of common formats (PNG, JPG), 
- **Output**: Animations or Posetures of 3D models (e.g. Miku Dancing)
- **OS**: Windows (8, 10), MacOS (2017 Released Version)

*Section quoted from the upstream readme.*
---

## Dependencies

| Metric | Value |
|--------|-------|
| Ecosystem | Unknown (no standard manifest detected) |
| Manifests detected | none |
| Files in snapshot | 998 |
| Lines of code | 104874 |
| Dependency references | 0 |
| Upstream license | MIT |
| Overlay license | Anticommons 0.1.0 |

Pinned lockfile: `anticloud/requirements.lock` (hash-pinned, PEP 508). SBOM: `sbom.cdx.json` (CycloneDX 1.5, pinned to the upstream SHA).

---

## Configuration

- Run OpenposeVideo.bat and follow the pop-out instructions.
- Then proceed to the 3d-pose-baseline-vmd folder and run OpenposeTo3D.bat. Follow the pop-out instructions.
- After that, proceed to the FCRN-DepthPrediction-vmd folder and run VideoToDepth.dat.
- Finally, proceed to the VMD-3d-pose-baseline-multi folder and run 3DToVMD.bat. You will get the vmd file.
- VMD files are 3D animation file used by **MikuMikuDance**, a program used to create dance animation movies. Open your MikuMikuDance and input the VMD file.
- You will see your Miku begin acting the same motions as that in your recorded video.

**Tutorial in Chinese (中文教程)**: Developers that can understand Chinese are encouraged to read the tutorial written by [@mrzjy](https://github.com/mrzjy) on Bilibili Articles: [Click Here](https://www.bilibili.com/read/cv2835857). This tutorial covers how to install and run the OpenMMD. The tutorial also introduces some common issues of OpenMMD.

*Section quoted from the upstream readme.*
Overlay configuration (Anticloud):

- `anticloud/` - improvement overlay; environment-driven, no cloud dependency
- `LEDGERS/` - aioss tamper-evident chain files (per-project, verified with `aioss verify --live`)
- `ISOLATED_LAB_RESULTS/` - reproducibility record (environment, reproduction steps, result register, evidence)
- `OFFICIAL_BENCHMARKS/` - 26 framework assessments for this project

---

## Contributing

Upstream contributions: fork the `OPENMM` project, create a feature branch, and open a pull request against upstream. Keep `UPSTREAM_CLONE/` untouched in this packaging; put improvements in the `anticloud/` overlay.

Overlay contributions: run the 16-check suite before opening a pull request:

```sh
python anticloud/bench/runner.py --cwd anticloud
```

---

## License

**Upstream license: MIT** (evidence: `LICENSE` in the upstream snapshot).

License file excerpt:

```text
MIT License

Copyright (c) 2018 Peter Luo

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
```

### Anticommons 0.1.0 overlay

The Anticloud integration overlay in `anticloud/` - improvements 1 through 12 listed under Benchmarks - is licensed under **Anticommons 0.1.0**. Upstream code remains under its original MIT terms. See `ANTICOMMONS_LICENSE.md` in this directory for the overlay terms and contact.

SPDX: `MIT` (upstream) + Anticommons 0.1.0 (overlay, dual).

---

## Upstream

- **Project:** `OPENMM` (category: CHEMICAL MANUFACTURING)
- **Upstream URL:** https://github.com/peterljq/OpenMMD
- **Pinned commit (SHA):** `795d4dd660cf7e537ceb599fdb038c5388b33390`
- **Branch:** master
- **Pin provenance:** GitHub API commits/master. The parent-project stamp is explicitly rejected for this project.
- **Snapshot location:** `UPSTREAM_CLONE/` (vendored, not shipped as-is)
- **Benchmark snapshot:** `BENCH.json`

---

## Benchmarks

Measured by the Anticloud assurance suite. Every value below is read from this
project's `BENCH.json`, produced by a real run — the SHA3-256 of that file is
`96735ee09016b62d082f3897a2b2c7267dd9b308052c4b671be29b870af770c3`.

| Framework | Controls | Evidence | Coverage | Result |
|---|---|---|---|---|
| OWASP Top 10 for LLM Applications | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| OWASP Top 10 (2021) | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| SOC 2 Type II readiness | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| NIST AI Risk Management Framework | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| NIST SP 800-53 Rev. 5 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| NIST Cybersecurity Framework 2.0 | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| FedRAMP Rev. 5 | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| PCI DSS v4.0.1 | 11 controls mapped | 11 with evidence | 100.0% | PASS |
| ISO/IEC 27001:2022 | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| MITRE ATT&CK v16 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| ML Technology Readiness Level | TRL 8 | 8/8 criteria | | PASS |

**Overall: 16/16 checks passing.**

See `ISOLATED_LAB_RESULTS/03_Result_Register.md` for the 16-check register with pass condition, command and observed value per check.

Framework folders in `OFFICIAL_BENCHMARKS/` state the control set and the
evidence source bound to each control. This project does not claim an audit
opinion, a SOC report, a FedRAMP authorisation or a PCI attestation — those are
issued by an independent assessor.



## Archives and Permanent Records

| Platform | Identifier | Volume |
|---|---|---|
| Harvard Dataverse | DOI 10.7910/DVN/YMJKOG | 145 citable datasets |
| AIOSS verification kit | DOI 10.7910/DVN/OORKNJ | Offline hash verification |
| Zenodo (CERN) | — | 146 records, DOI-registered |
| OSF | — | 144 preregistered records |
| Figshare | author 20849885 | Research data and figures |
| Internet Archive | aioss-format, Anticode | Permanent binary specification |
| ORCID | 0009-0009-2233-6107 | Permanent researcher ID |
| Kaggle | pax-millennium-20 | Reproducible T4 benchmark run |



## Press and Independent Publication

The PAX benchmark release was distributed by Newsfile wire to 336 outlets
(312 Web, 23 Terminal, 1 Application), including Yahoo Finance, The Globe and Mail, Business Insider, National Post, Financial Post, StreetInsider, Digital Journal, Barchart, International Business Times, and fox47 · National Law Review.
Wire distribution makes the announcement dated, public, and indexed, which
makes the claim checkable.

