---
sidebar_label: 'Security'
title: "Security in Astro"
id: security
description: Learn how Astro responds to and implements a variety of security concepts
---

## Overview

Astronomer Cloud is a fully managed data orchestration service that allows you to run your data pipelines in your public cloud account on Amazon Web Services (AWS), respecting the need to keep your data private, secure, and within corporate boundaries.

The Astronomer Cloud architecture is secure by default, using encryption in transit, encryption at rest, strong cryptographic protocols, authentication, and role-based access control for authorization to your data pipelines, with a host of flexible and secure connectivity options to your critical data sources.

Astronomer Cloud uses a shared responsibility model, where security and compliance is a shared responsibility between Astronomer, Astronomer Cloud customers, and public cloud providers.

## [Shared Responsibility Model](shared-responsibility-model.md)

Astronomer Cloud operates on a model of shared responsibility, which means that both the Astronomer team and Astronomer customers are responsible for the security of the platform

## [Architecture](https://docs.astronomer.io/cloud/#architecture)

Astronomer Cloud boasts a hybrid deployment model founded on a Control Plane hosted by Astronomer and a Data Plane that is hosted in your cloud environment. It optimizes for security whilst relieving your team of operational overhead.

## Data Protection

Astronomer Cloud uses both encryption in transit and encryption at rest to protect data across and within the Data and Control Planes. See [Encryption in Transit](https://docs.astronomer.io/cloud/data-protection#encryption-in-transit) and [Encryption at Rest](https://docs.astronomer.io/cloud/data-protection#encryption-at-rest) for more details.

## [Resilience](resilience.md)

The Astronomer Cloud Control and Data Planes are architected and deployed on major public clouds to take advantage of their resilient, secure and highly available regions. Additionally, both planes are designed and archtected to take advantage of best in class security products offered by the public clouds.

## Data Privacy and Compliance

Astronomer Cloud is AICPA SOC 2 Type I certified with respect to the security, availability, and confidentiality Trust Service Categories. If you are interested in obtaining (NDA required) our SOC 2 Report and Penetration Test report, contact [sales@astronomer.io](https://www.notion.so/Sales-Operations-36c4d78df58747a2815449b7acbe97bd)

Astronomer is committed to pursuing SOC 2 Type II, GDPR, and HIPAA compliance in 2022.

## [Disaster Recovery](disaster-recovery.md)

While Astronomer Cloud Data Plane is designed to withstand and survive in-region Availability Zone (AZ) degradations and outages, rest assured Astronomer can also help you recover from major region failures by restoring configuration and secrets from a secure and highly available data store.

## [Physical and Environment Security](shared-responsibility-model.md#cloud-provider-security-responsibilities)

Astronomer Cloud leverages all three major public cloud providers (Azure, Google Cloud Platform, Amazon Web Services), thus physical and environmental security is handled entirely by those providers. Each cloud service provider provides an extensive list of compliance and regulatory assurances that they are rigorously tested against, including SOC 1/2-3, PCI-DSS, and ISO27001.

Astronomer is a global remote company first. We have some small offices in the US, but they are treated as trustless. Employees need to authenticate to all applications and systems using our IdP (Okta) with MFA even if using office WiFi.
