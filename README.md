
# Systementor AB — Cloud Storage Requirements Specification

**Project:** Cloud Native Computing — Assignment 1
**Document Type:** Requirements Specification
**Version:** 1.0
**Status:** Initial Requirements
**Client:** Systementor AB

---

## 1. Introduction

### 1.1 Purpose

This document defines the requirements for evaluating and selecting a cloud-based data storage solution for Systementor AB.

The objective is to identify a cost-effective, secure, and manageable storage solution capable of supporting the company's data volumes, access patterns, and retention requirements.

### 1.2 Project Scope

The project involves evaluating three cloud storage alternatives based on:

- Storage capacity and data lifecycle management
- Operational and storage costs
- Data security and access control
- Storage administration, monitoring, and API capabilities

The extended evaluation also covers containerization and Kubernetes services offered by the selected cloud providers.

## 2. Business Context

Systementor AB collects large volumes of data from various Internet of Things (IoT) sensors.

The collected data is used in multiple data processing pipelines. Its access frequency decreases over time, creating an opportunity to optimize storage costs through different storage classes and lifecycle policies.

The company requires a solution that provides long-term data retention while maintaining appropriate security and accessibility.

## 3. Data Characteristics

| Attribute                   | Requirement             |
| --------------------------- | ----------------------- |
| Data source                 | IoT sensors             |
| Daily data generation       | Approximately 10 GB     |
| Daily file count            | Approximately 100 files |
| Average file size           | Approximately 100 MB    |
| Frequently accessed data    | First 14 days           |
| Infrequently accessed data  | After 14 days           |
| Long-term traceability data | After 6 months          |
| Total retention period      | 24 months               |
| Data classification         | Non-public              |

## 4. Functional Requirements

### FR-01 — Cloud Storage

The proposed solution shall provide cloud-based storage capable of accommodating the specified daily data generation volume.

### FR-02 — Data Lifecycle Management

The solution shall support the management of data throughout its 24-month retention period.

The evaluation shall consider storage alternatives appropriate for three distinct lifecycle phases:

1. **Hot data:** Data generated within the previous 14 days.
2. **Infrequently accessed data:** Data older than 14 days.
3. **Long-term retention data:** Data older than six months, retained primarily for traceability.

### FR-03 — Data Retention

The solution shall support retaining files for a total of 24 months.

### FR-04 — Storage Administration

The evaluation shall identify available management consoles and APIs for:

- Inspecting stored data
- Managing storage resources
- Monitoring storage usage
- Controlling storage configurations

## 5. Non-Functional Requirements

### NFR-01 — Security

Stored data shall not be publicly accessible.

The evaluation shall address security mechanisms available from each provider.

### NFR-02 — Access Control

The evaluation shall investigate available authorization and access-management mechanisms.

### NFR-03 — Cost Efficiency

The evaluation shall estimate the costs associated with the proposed storage alternatives.

Cost comparisons shall account for the specified data volumes, access patterns, and retention requirements.

### NFR-04 — Long-Term Data Accessibility

The proposed solution shall support access to retained data throughout the required retention period.

## 6. Cloud Provider Evaluation

Three cloud storage alternatives shall be investigated and compared.

Potential providers include, but are not limited to:

- Amazon Web Services (AWS)
- Microsoft Azure
- Google Cloud
- Oracle Cloud Infrastructure
- IBM Cloud

The final selection of providers and recommended solution shall be justified through technical and economic analysis.

### 6.1 Evaluation Criteria

| Criterion            | Description                                         |
| -------------------- | --------------------------------------------------- |
| Storage capabilities | Suitability for the specified IoT data volumes      |
| Lifecycle management | Support for changing storage requirements over time |
| Pricing              | Estimated storage and operational costs             |
| Security             | Protection of non-public data                       |
| Access control       | Available authorization mechanisms                  |
| Administration       | Management consoles and APIs                        |
| Long-term retention  | Support for the required 24-month retention period  |

## 7. Extended Requirements — Containerization and Kubernetes

For the advanced evaluation (VG), the project shall investigate container and Kubernetes solutions offered by the selected cloud providers.

The evaluation shall address:

- Available container services
- Available Kubernetes services
- Associated pricing models and costs
- Relevant considerations for running additional workloads on the selected cloud platform

The purpose is to assess the providers' suitability beyond data storage alone.

## 8. Assumptions and Open Questions

The following information has not been specified in the original assignment and may require assumptions during the evaluation.

| ID    | Open Question                                                    |
| ----- | ---------------------------------------------------------------- |
| OQ-01 | Which geographic region should host the data?                    |
| OQ-02 | How frequently is historical data retrieved?                     |
| OQ-03 | What retrieval latency is acceptable for archived data?          |
| OQ-04 | What availability and redundancy levels are required?            |
| OQ-05 | Are there regulatory or geographic restrictions on data storage? |
| OQ-06 | What is the expected monthly volume of outgoing data transfers?  |
| OQ-07 | Is automated deletion required after 24 months?                  |
| OQ-08 | What workloads might eventually run in containers or Kubernetes? |

These questions shall be addressed through documented assumptions where necessary.

## 9. Project Deliverables

### 9.1 Standard Requirements (G)

A technical report of **3–4 pages** comparing three cloud storage alternatives.

The report shall cover:

- Cloud provider comparison
- Storage costs
- Security and permissions
- Management consoles and APIs
- Other relevant storage considerations

### 9.2 Advanced Requirements (VG)

In addition to the standard requirements, the report shall include an evaluation of container and Kubernetes services and their associated costs.

## 10. Expected Outcome

The project shall produce a documented comparison of three cloud storage alternatives and a justified recommendation for Systementor AB.

The recommendation shall consider the company's data generation rate, access patterns, retention requirements, security needs, and estimated costs.

For the advanced evaluation, the recommendation shall also consider the availability and cost of container and Kubernetes services.

---

**Document Status:** Initial specification derived from the assignment brief. Technical assumptions, provider selections, and architecture decisions are to be established during the investigation.
