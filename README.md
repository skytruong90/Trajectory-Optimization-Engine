# Trajectory-Optimization-Engine

[![Language](https://img.shields.io/badge/C++17-%2300599C?style=flat-square&logo=c%2B%2B&logoColor=white)](https://github.com/skytruong90/Trajectory-Optimization-Engine)
[![Domain](https://img.shields.io/badge/Domain-Defense_M%26S-red?style=flat-square)](https://github.com/skytruong90/Trajectory-Optimization-Engine)
[![Status](https://img.shields.io/badge/Status-Active-00FF88?style=flat-square)](https://github.com/skytruong90/Trajectory-Optimization-Engine)

## Project Overview

A C++ trajectory optimization engine for defense ballistic systems — computing optimal flight paths that minimize time-of-flight, maximize range, or minimize fuel consumption under aerodynamic and mission constraints. Implements direct collocation and gradient-based optimization methods used in professional defense M&S environments.

---

## Features

- **Multi-Objective Optimization** — Minimize time-of-flight, fuel consumption, or miss distance simultaneously.
- **Constraint Handling** — Enforces aerodynamic limits, no-fly zones, and terminal guidance constraints.
- **Direct Collocation** — Discretizes trajectory into nodes and solves as a nonlinear programming problem.
- **Gradient-Based Solver** — Implements SLSQP and interior-point methods for fast convergence.
- **6DOF Integration** — Full rigid-body dynamics integration along optimized trajectory.

---

## Technical Background

| Concept | Implementation |
|--------|----------------|
| Optimization Method | Direct collocation / SLSQP |
| Dynamics | 6DOF rigid-body equations of motion |
| Constraints | Aerodynamic limits, terminal conditions |
| Output | Optimal state/control history + trajectory CSV |

---

## Getting Started

```bash
git clone https://github.com/skytruong90/Trajectory-Optimization-Engine.git
cd Trajectory-Optimization-Engine
mkdir build && cd build
cmake ..
make -j4
./traj_opt --config config/mission_params.yaml
```

---

## Future Enhancements

- Pseudospectral methods (Gauss-Lobatto collocation)
- Real-time trajectory reshaping for mid-course guidance
- Multi-vehicle cooperative trajectory planning

---

<div align="center">

[![View Repository](https://img.shields.io/badge/View_Repository-%E2%86%97-00C8FF?style=for-the-badge&labelColor=050A0F)](https://github.com/skytruong90/Trajectory-Optimization-Engine)

</div>

---
---

# Atmospheric-Reentry-Simulator

[![Language](https://img.shields.io/badge/C++17-%2300599C?style=flat-square&logo=c%2B%2B&logoColor=white)](https://github.com/skytruong90/Atmospheric-Reentry-Simulator)
[![Domain](https://img.shields.io/badge/Domain-Hypersonic_M%26S-red?style=flat-square)](https://github.com/skytruong90/Atmospheric-Reentry-Simulator)
[![Status](https://img.shields.io/badge/Status-Active-00FF88?style=flat-square)](https://github.com/skytruong90/Atmospheric-Reentry-Simulator)

## Project Overview

High-fidelity C++ atmospheric reentry simulation for hypersonic vehicle modeling. Implements variable-density atmospheric models, aerodynamic heating, and drag-modulated reentry dynamics — applicable to ICBM reentry vehicle simulation and hypersonic glide vehicle (HGV) analysis.

---

## Features

- **US Standard Atmosphere 1976** — Altitude-varying density, pressure, temperature, and speed of sound.
- **Aerodynamic Heating** — Stagnation point heat flux computation using Fay-Riddell model.
- **Hypersonic Drag** — Mach-dependent drag coefficients from 0 to Mach 25.
- **RK4 Integration** — 4th-order Runge-Kutta numerical integration of reentry equations of motion.
- **Ballistic Coefficient** — Configurable BC for reentry vehicle sizing analysis.

---

## Technical Background

| Concept | Implementation |
|--------|----------------|
| Atmosphere Model | US Standard Atmosphere 1976 |
| Heat Transfer | Fay-Riddell stagnation heating |
| Drag Model | Mach-dependent CD table lookup |
| Integration | RK4 variable time-step |
| Output | Altitude, velocity, heat rate vs. time |

---

<div align="center">

[![View Repository](https://img.shields.io/badge/View_Repository-%E2%86%97-00C8FF?style=for-the-badge&labelColor=050A0F)](https://github.com/skytruong90/Atmospheric-Reentry-Simulator)

</div>

---
---

# IMU-Sensor-Model

[![Language](https://img.shields.io/badge/C++17-%2300599C?style=flat-square&logo=c%2B%2B&logoColor=white)](https://github.com/skytruong90/IMU-Sensor-Model)
[![Domain](https://img.shields.io/badge/Domain-GNC_Navigation-red?style=flat-square)](https://github.com/skytruong90/IMU-Sensor-Model)
[![Status](https://img.shields.io/badge/Status-Active-00FF88?style=flat-square)](https://github.com/skytruong90/IMU-Sensor-Model)

## Project Overview

A C++ Inertial Measurement Unit (IMU) sensor model for 6DOF navigation simulation. Models accelerometer and gyroscope measurement errors including bias, scale factor, noise, and misalignment — enabling realistic navigation performance assessment in defense M&S environments.

---

## Features

- **Accelerometer Model** — Bias, scale factor error, white noise, and vibration rectification error.
- **Gyroscope Model** — Bias instability, angle random walk, and g-sensitivity modeling.
- **Allan Variance** — Characterizes IMU noise performance per IEEE 952 standard.
- **Error Budgeting** — Computes navigation error growth from IMU specification inputs.
- **Monte Carlo Ready** — Randomized error generation for statistical navigation performance analysis.

---

## IMU Error Model

```cpp
// IMU measurement = truth + bias + scale_factor_error + noise
Vector3D IMUSensorModel::getAccelMeasurement(const Vector3D& trueAccel) {
    Vector3D bias       = accelBias;
    Vector3D sfError    = trueAccel * accelScaleFactor;
    Vector3D noise      = sampleGaussianNoise(accelNoiseDensity, dt);
    return trueAccel + bias + sfError + noise;
}
```

---

<div align="center">

[![View Repository](https://img.shields.io/badge/View_Repository-%E2%86%97-00C8FF?style=for-the-badge&labelColor=050A0F)](https://github.com/skytruong90/IMU-Sensor-Model)

</div>

---
---

# Zero-Trust-Network-Architecture

[![Terraform](https://img.shields.io/badge/Terraform-%235835CC?style=flat-square&logo=terraform&logoColor=white)](https://github.com/skytruong90/Zero-Trust-Network-Architecture)
[![AWS](https://img.shields.io/badge/AWS-%23FF9900?style=flat-square&logo=amazon-aws&logoColor=white)](https://github.com/skytruong90/Zero-Trust-Network-Architecture)
[![Domain](https://img.shields.io/badge/Domain-Defense_Security-red?style=flat-square)](https://github.com/skytruong90/Zero-Trust-Network-Architecture)
[![Status](https://img.shields.io/badge/Status-Active-00FF88?style=flat-square)](https://github.com/skytruong90/Zero-Trust-Network-Architecture)

## Project Overview

Terraform implementation of a Zero Trust Network Architecture (ZTNA) for defense cloud environments. Enforces "never trust, always verify" principles across all network layers — identity, device, application, and data — aligned to NIST SP 800-207 and DoD Zero Trust Reference Architecture.

---

## Zero Trust Pillars

| Pillar | Implementation |
|--------|---------------|
| Identity | AWS IAM Identity Center + MFA enforcement |
| Device | AWS Systems Manager compliance checks |
| Network | VPC micro-segmentation + PrivateLink |
| Application | API Gateway + WAF + mTLS |
| Data | KMS encryption + S3 bucket policies |
| Visibility | CloudTrail + Security Hub + GuardDuty |

---

## Getting Started

```bash
git clone https://github.com/skytruong90/Zero-Trust-Network-Architecture.git
cd Zero-Trust-Network-Architecture/terraform
terraform init
terraform plan -var="environment=dev"
terraform apply -var="environment=dev"
```

---

<div align="center">

[![View Repository](https://img.shields.io/badge/View_Repository-%E2%86%97-00C8FF?style=for-the-badge&labelColor=050A0F)](https://github.com/skytruong90/Zero-Trust-Network-Architecture)

</div>

---
---

# Threat-Hunt-Playbooks

[![KQL](https://img.shields.io/badge/KQL-Azure_Sentinel-0072C6?style=flat-square&logo=microsoftazure&logoColor=white)](https://github.com/skytruong90/Threat-Hunt-Playbooks)
[![Domain](https://img.shields.io/badge/Domain-Defense_SOC-red?style=flat-square)](https://github.com/skytruong90/Threat-Hunt-Playbooks)
[![Status](https://img.shields.io/badge/Status-Active-00FF88?style=flat-square)](https://github.com/skytruong90/Threat-Hunt-Playbooks)

## Project Overview

A library of KQL-based threat hunting playbooks for Azure Sentinel, aligned to the MITRE ATT&CK framework. Designed for defense SOC operations — covering initial access, lateral movement, privilege escalation, and data exfiltration detection in classified cloud environments.

---

## Playbook Library

| Playbook | MITRE Tactic | Severity |
|----------|-------------|----------|
| Brute Force Detection | TA0006 Credential Access | High |
| Lateral Movement via PsExec | TA0008 Lateral Movement | Critical |
| Privilege Escalation Off-Hours | TA0004 Privilege Escalation | Critical |
| Data Exfiltration via DNS | TA0010 Exfiltration | High |
| Impossible Travel Detection | TA0001 Initial Access | High |
| Ransomware Precursor Activity | TA0040 Impact | Critical |

---

<div align="center">

[![View Repository](https://img.shields.io/badge/View_Repository-%E2%86%97-00C8FF?style=for-the-badge&labelColor=050A0F)](https://github.com/skytruong90/Threat-Hunt-Playbooks)

</div>

---
---

# STIG-Compliance-Automation

[![Python](https://img.shields.io/badge/Python-3670A0?style=flat-square&logo=python&logoColor=ffdd54)](https://github.com/skytruong90/STIG-Compliance-Automation)
[![Domain](https://img.shields.io/badge/Domain-DoD_Compliance-red?style=flat-square)](https://github.com/skytruong90/STIG-Compliance-Automation)
[![Status](https://img.shields.io/badge/Status-Active-00FF88?style=flat-square)](https://github.com/skytruong90/STIG-Compliance-Automation)

## Project Overview

Automated DISA STIG compliance checking and remediation for DoD systems. Scans Linux and container environments against STIG benchmarks, generates compliance reports, and applies automated remediations — reducing manual compliance effort by 80% for defense program security assessments.

---

## Features

- **RHEL STIG Scanner** — Automated checks against DISA RHEL 8/9 STIG benchmarks.
- **Container STIG** — Docker and Kubernetes container hardening checks.
- **Auto-Remediation** — Applies approved fixes for non-compliant findings automatically.
- **Compliance Report** — Generates CAT I/II/III finding reports in XCCDF format.
- **CI/CD Integration** — Runs as a pipeline stage to catch compliance drift before deployment.

---

<div align="center">

[![View Repository](https://img.shields.io/badge/View_Repository-%E2%86%97-00C8FF?style=for-the-badge&labelColor=050A0F)](https://github.com/skytruong90/STIG-Compliance-Automation)

</div>

---
---

# Red-Team-Toolkit

[![Python](https://img.shields.io/badge/Python-3670A0?style=flat-square&logo=python&logoColor=ffdd54)](https://github.com/skytruong90/Red-Team-Toolkit)
[![Domain](https://img.shields.io/badge/Domain-Offensive_Security-red?style=flat-square)](https://github.com/skytruong90/Red-Team-Toolkit)
[![Status](https://img.shields.io/badge/Status-Active-00FF88?style=flat-square)](https://github.com/skytruong90/Red-Team-Toolkit)

## Project Overview

A defensive red team toolkit for security validation in classified defense environments. Provides controlled adversary simulation capabilities to test detection coverage, incident response procedures, and security control effectiveness — supporting RMF authorization activities and purple team exercises.

> ⚠️ **Authorized Use Only** — This toolkit is designed for use in authorized penetration testing and security validation activities only.

---

## Capabilities

| Module | Description |
|--------|-------------|
| Recon | Network enumeration and asset discovery |
| Credential Testing | Password policy validation |
| Lateral Movement Sim | Controlled movement simulation for detection testing |
| Persistence Testing | Validates detection of common persistence mechanisms |
| Exfil Simulation | Tests DLP controls and egress monitoring |
| Report Generator | Automated findings report in RMF format |

---

<div align="center">

[![View Repository](https://img.shields.io/badge/View_Repository-%E2%86%97-00C8FF?style=for-the-badge&labelColor=050A0F)](https://github.com/skytruong90/Red-Team-Toolkit)

</div>

---
---

# Incident-Response-Automation

[![Python](https://img.shields.io/badge/Python-3670A0?style=flat-square&logo=python&logoColor=ffdd54)](https://github.com/skytruong90/Incident-Response-Automation)
[![Azure](https://img.shields.io/badge/Azure-Sentinel-0072C6?style=flat-square&logo=microsoftazure&logoColor=white)](https://github.com/skytruong90/Incident-Response-Automation)
[![Domain](https://img.shields.io/badge/Domain-Defense_SOC-red?style=flat-square)](https://github.com/skytruong90/Incident-Response-Automation)
[![Status](https://img.shields.io/badge/Status-Active-00FF88?style=flat-square)](https://github.com/skytruong90/Incident-Response-Automation)

## Project Overview

Automated incident response playbooks for defense SOC operations — integrating Azure Sentinel, Logic Apps, and Python to orchestrate detection-to-remediation workflows. Reduces mean time to respond (MTTR) by automating triage, containment, and notification steps for common defense threat scenarios.

---

## Playbook Coverage

| Incident Type | Auto-Response Actions |
|--------------|----------------------|
| Brute Force Attack | Block IP, notify SOC, lock account |
| Malware Detection | Isolate endpoint, capture memory dump |
| Privilege Escalation | Revoke session, alert admin, audit log |
| Data Exfiltration | Block egress, preserve evidence, escalate |
| Ransomware Activity | Network isolation, snapshot volumes |

---

<div align="center">

[![View Repository](https://img.shields.io/badge/View_Repository-%E2%86%97-00C8FF?style=for-the-badge&labelColor=050A0F)](https://github.com/skytruong90/Incident-Response-Automation)

</div>

---
---

# Defense-GitOps-Pipeline

[![Kubernetes](https://img.shields.io/badge/Kubernetes-%23326ce5?style=flat-square&logo=kubernetes&logoColor=white)](https://github.com/skytruong90/Defense-GitOps-Pipeline)
[![ArgoCD](https://img.shields.io/badge/ArgoCD-EF7B4D?style=flat-square&logo=argo&logoColor=white)](https://github.com/skytruong90/Defense-GitOps-Pipeline)
[![Domain](https://img.shields.io/badge/Domain-Defense_DevOps-red?style=flat-square)](https://github.com/skytruong90/Defense-GitOps-Pipeline)
[![Status](https://img.shields.io/badge/Status-Active-00FF88?style=flat-square)](https://github.com/skytruong90/Defense-GitOps-Pipeline)

## Project Overview

A GitOps-based CI/CD pipeline for secure defense software delivery using ArgoCD and Kubernetes. Implements declarative infrastructure management, automated rollbacks, and audit-complete deployment history — aligned to DoD DevSecOps reference architecture.

---

## Pipeline Stages

```
Code Push → SAST Scan → Container Build → Image Scan → ArgoCD Sync → EKS Deploy → DAST Scan
```

---

## Features

- **ArgoCD GitOps** — Declarative, Git-driven deployment with automatic drift detection and remediation.
- **SAST/DAST Integration** — Static and dynamic security testing at every pipeline stage.
- **Image Signing** — Cosign-based container image signing for supply chain security.
- **Audit Trail** — Complete deployment history with who/what/when for RMF compliance.
- **Automated Rollback** — Instant rollback to last known good state on deployment failure.

---

<div align="center">

[![View Repository](https://img.shields.io/badge/View_Repository-%E2%86%97-00C8FF?style=for-the-badge&labelColor=050A0F)](https://github.com/skytruong90/Defense-GitOps-Pipeline)

</div>

---
---

# Hardened-EKS-Cluster

[![Terraform](https://img.shields.io/badge/Terraform-%235835CC?style=flat-square&logo=terraform&logoColor=white)](https://github.com/skytruong90/Hardened-EKS-Cluster)
[![AWS](https://img.shields.io/badge/AWS-EKS-%23FF9900?style=flat-square&logo=amazon-aws&logoColor=white)](https://github.com/skytruong90/Hardened-EKS-Cluster)
[![Status](https://img.shields.io/badge/Status-Active-00FF88?style=flat-square)](https://github.com/skytruong90/Hardened-EKS-Cluster)

## Project Overview

STIG-hardened AWS EKS cluster configuration for DoD workloads — provisioned via Terraform with CIS Kubernetes Benchmark and DISA STIG controls applied. Designed for defense simulation and mission-critical application hosting in IL4/IL5 environments.

---

## Hardening Controls

| Control | Implementation |
|--------|---------------|
| Private Endpoint | No public API server access |
| Node Hardening | DISA STIG RHEL AMI for worker nodes |
| Pod Security | OPA Gatekeeper admission control |
| Network Policy | Calico micro-segmentation |
| Secrets Management | AWS Secrets Manager + KMS |
| Audit Logging | EKS control plane logs → CloudWatch |
| Image Policy | Only signed images from approved ECR |

---

<div align="center">

[![View Repository](https://img.shields.io/badge/View_Repository-%E2%86%97-00C8FF?style=for-the-badge&labelColor=050A0F)](https://github.com/skytruong90/Hardened-EKS-Cluster)

</div>

---
---

# FedRAMP-Terraform-Modules

[![Terraform](https://img.shields.io/badge/Terraform-%235835CC?style=flat-square&logo=terraform&logoColor=white)](https://github.com/skytruong90/FedRAMP-Terraform-Modules)
[![AWS](https://img.shields.io/badge/AWS-GovCloud-%23FF9900?style=flat-square&logo=amazon-aws&logoColor=white)](https://github.com/skytruong90/FedRAMP-Terraform-Modules)
[![Status](https://img.shields.io/badge/Status-Active-00FF88?style=flat-square)](https://github.com/skytruong90/FedRAMP-Terraform-Modules)

## Project Overview

Reusable Terraform modules pre-configured to meet FedRAMP Moderate and High baseline controls. Accelerates ATO (Authority to Operate) for defense cloud deployments by providing compliant-by-default infrastructure components aligned to NIST SP 800-53.

---

## Module Library

| Module | Controls Covered |
|--------|----------------|
| `vpc-fedramp` | SC-7, SC-8, AC-17 |
| `eks-fedramp` | CM-6, CM-7, SI-3 |
| `s3-fedramp` | SC-28, AC-3, AU-9 |
| `iam-fedramp` | AC-2, AC-6, IA-5 |
| `kms-fedramp` | SC-12, SC-13, SC-28 |
| `logging-fedramp` | AU-2, AU-3, AU-12 |

---

<div align="center">

[![View Repository](https://img.shields.io/badge/View_Repository-%E2%86%97-00C8FF?style=for-the-badge&labelColor=050A0F)](https://github.com/skytruong90/FedRAMP-Terraform-Modules)

</div>

---
---

# Container-Security-Scanner

[![Python](https://img.shields.io/badge/Python-3670A0?style=flat-square&logo=python&logoColor=ffdd54)](https://github.com/skytruong90/Container-Security-Scanner)
[![Docker](https://img.shields.io/badge/Docker-%230db7ed?style=flat-square&logo=docker&logoColor=white)](https://github.com/skytruong90/Container-Security-Scanner)
[![Status](https://img.shields.io/badge/Status-Active-00FF88?style=flat-square)](https://github.com/skytruong90/Container-Security-Scanner)

## Project Overview

Automated container vulnerability scanning pipeline for defense CI/CD environments. Integrates Trivy and Grype scanners into Jenkins/GitLab pipelines — blocking deployments on critical CVEs and generating STIG-aligned vulnerability reports for ATO package submissions.

---

## Features

- **Multi-Scanner** — Trivy + Grype for comprehensive CVE coverage.
- **Pipeline Gate** — Blocks deployment on CRITICAL/HIGH CVEs automatically.
- **SBOM Generation** — Software Bill of Materials for supply chain transparency.
- **ATO Reporting** — Generates vulnerability findings in XCCDF/OVAL format.
- **Registry Integration** — Scans ECR, Docker Hub, and private registries.

---

<div align="center">

[![View Repository](https://img.shields.io/badge/View_Repository-%E2%86%97-00C8FF?style=for-the-badge&labelColor=050A0F)](https://github.com/skytruong90/Container-Security-Scanner)

</div>

---
---

# Multi-Region-Failover-AWS

[![Terraform](https://img.shields.io/badge/Terraform-%235835CC?style=flat-square&logo=terraform&logoColor=white)](https://github.com/skytruong90/Multi-Region-Failover-AWS)
[![AWS](https://img.shields.io/badge/AWS-Route53_%7C_RDS-%23FF9900?style=flat-square&logo=amazon-aws&logoColor=white)](https://github.com/skytruong90/Multi-Region-Failover-AWS)
[![Status](https://img.shields.io/badge/Status-Active-00FF88?style=flat-square)](https://github.com/skytruong90/Multi-Region-Failover-AWS)

## Project Overview

Active-passive multi-region failover architecture on AWS for mission-critical defense systems. Provides sub-60-second RTO (Recovery Time Objective) and near-zero RPO (Recovery Point Objective) using Route53 health checks, RDS cross-region replication, and S3 replication — ensuring mission continuity under regional outage scenarios.

---

## Architecture

| Component | Primary Region | DR Region |
|-----------|---------------|-----------|
| Compute | EKS Active | EKS Warm Standby |
| Database | RDS Primary | RDS Read Replica |
| Storage | S3 Primary | S3 Cross-Region Replication |
| DNS | Route53 Primary | Route53 Failover |
| RTO | — | < 60 seconds |
| RPO | — | < 5 minutes |

---

<div align="center">

[![View Repository](https://img.shields.io/badge/View_Repository-%E2%86%97-00C8FF?style=for-the-badge&labelColor=050A0F)](https://github.com/skytruong90/Multi-Region-Failover-AWS)

</div>

---
---

# Real-Time-Telemetry-Engine

[![Language](https://img.shields.io/badge/C++17-%2300599C?style=flat-square&logo=c%2B%2B&logoColor=white)](https://github.com/skytruong90/Real-Time-Telemetry-Engine)
[![Domain](https://img.shields.io/badge/Domain-Defense_M%26S-red?style=flat-square)](https://github.com/skytruong90/Real-Time-Telemetry-Engine)
[![Status](https://img.shields.io/badge/Status-Active-00FF88?style=flat-square)](https://github.com/skytruong90/Real-Time-Telemetry-Engine)

## Project Overview

A high-performance C++ real-time telemetry ingestion engine for defense simulation systems. Processes 6DOF state vectors, sensor data, and event streams at 1kHz+ throughput — providing real-time data distribution to analysis tools, visualization systems, and hardware-in-the-loop interfaces.

---

## Features

- **1kHz+ Throughput** — Lock-free ring buffer architecture for real-time data ingestion.
- **Multi-Channel** — Simultaneous ingestion from multiple simulation entities.
- **DDS Integration** — Data Distribution Service (DDS) publish/subscribe middleware.
- **Timestamping** — Microsecond-precision hardware timestamp synchronization.
- **Binary Protocol** — Compact binary telemetry format for bandwidth efficiency.

---

<div align="center">

[![View Repository](https://img.shields.io/badge/View_Repository-%E2%86%97-00C8FF?style=for-the-badge&labelColor=050A0F)](https://github.com/skytruong90/Real-Time-Telemetry-Engine)

</div>

---
---

# Flight-Data-Recorder

[![Language](https://img.shields.io/badge/C++17-%2300599C?style=flat-square&logo=c%2B%2B&logoColor=white)](https://github.com/skytruong90/Flight-Data-Recorder)
[![Domain](https://img.shields.io/badge/Domain-Defense_M%26S-red?style=flat-square)](https://github.com/skytruong90/Flight-Data-Recorder)
[![Status](https://img.shields.io/badge/Status-Active-00FF88?style=flat-square)](https://github.com/skytruong90/Flight-Data-Recorder)

## Project Overview

A C++ flight data recorder for capturing and replaying 6DOF simulation state in defense M&S environments. Records full state vectors at configurable sampling rates, supports binary and CSV output formats, and enables deterministic simulation replay for V&V activities and post-flight analysis.

---

## Features

- **State Vector Recording** — Captures position, velocity, attitude, rates, forces, and moments at up to 1kHz.
- **Binary Format** — Compact binary recording for long-duration simulations.
- **Deterministic Replay** — Bit-exact replay of recorded simulations for V&V.
- **CSV Export** — Human-readable export for Python/MATLAB post-processing.
- **Configurable Channels** — Select specific state variables for targeted recording.

---

<div align="center">

[![View Repository](https://img.shields.io/badge/View_Repository-%E2%86%97-00C8FF?style=for-the-badge&labelColor=050A0F)](https://github.com/skytruong90/Flight-Data-Recorder)

</div>

---
---

# High-Performance-Data-Pipeline

[![Language](https://img.shields.io/badge/C++17-%2300599C?style=flat-square&logo=c%2B%2B&logoColor=white)](https://github.com/skytruong90/High-Performance-Data-Pipeline)
[![Domain](https://img.shields.io/badge/Domain-Defense_M%26S-red?style=flat-square)](https://github.com/skytruong90/High-Performance-Data-Pipeline)
[![Status](https://img.shields.io/badge/Status-Active-00FF88?style=flat-square)](https://github.com/skytruong90/High-Performance-Data-Pipeline)

## Project Overview

A C++ high-performance data pipeline for real-time defense simulation telemetry processing. Implements lock-free queues, SIMD-optimized data transforms, and parallel processing stages to achieve sub-millisecond latency for mission-critical simulation data flows.

---

## Features

- **Lock-Free Architecture** — SPSC/MPMC ring buffers for zero-contention data flow.
- **SIMD Optimization** — AVX2 vectorized data transforms for throughput maximization.
- **Pipeline Stages** — Configurable processing stages: ingest → filter → transform → output.
- **Backpressure Handling** — Graceful degradation under load with configurable drop policies.
- **Metrics Dashboard** — Real-time throughput, latency, and queue depth monitoring.

---

<div align="center">

[![View Repository](https://img.shields.io/badge/View_Repository-%E2%86%97-00C8FF?style=for-the-badge&labelColor=050A0F)](https://github.com/skytruong90/High-Performance-Data-Pipeline)

</div>
